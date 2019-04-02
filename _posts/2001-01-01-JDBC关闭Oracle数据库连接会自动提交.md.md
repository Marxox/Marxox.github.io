---
title: JDBC关闭Oracle数据库连接会自动提交
date: 2018-12-20 16:54:26
tags: CSDN迁移
---
 版权声明：本文为博主原创文章，转载请声明出处并添加原文链接。 https://blog.csdn.net/qq_40299166/article/details/85126988   
  在eclipse中调用Oracle中的存储过程（插入数据）遇到个问题：存储过程中，我没有写commit；调用存储过程的Java代码中关闭了自动提交事务，也没有写commit，然而运行java程序，结果是数据插入成功了。

 下面是存储过程代码：

 
```
 CREATE OR REPLACE PROCEDURE sp_insert_record(
       v_empno IN emp.empno%TYPE,
       v_ename IN emp.ename%TYPE,
       v_result OUT NUMBER
)
IS

BEGIN
  INSERT INTO emp(empno,ename)
  VALUES(v_empno,v_ename);
  
  v_result := 1;
  
  EXCEPTION
    WHEN OTHERS THEN
      v_result := -1;

END sp_insert_record;
```
 以及Java代码：

 
```
 package com.jdbc;

import java.sql.CallableStatement;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;
import java.sql.Types;

public class TestProcedure {
	public static void main(String[] args) {
		callProcedure(1000);//插入1000条数据
	}
	
	/**
	 * 调用存储过程（插入数据）
	 * @param currentPage
	 * @param pageSize
	 */
	public static void callProcedure(int count){
		Connection conn = null;
		CallableStatement cs = null;
		int ccount = 0;
		try {
			Class.forName("oracle.jdbc.driver.OracleDriver");
			conn = DriverManager.getConnection("jdbc:oracle:thin:@localhost:1521:XE", "scott", "tiger");
			conn.setAutoCommit(false);//关闭自动提交事务
			long begin = System.currentTimeMillis();
			cs = conn.prepareCall("{call sp_insert_record(?,?,?)}");
			cs.registerOutParameter(3, Types.INTEGER);
			cs.setString(2, "tom");
			for(int i = 0;i < count;i++){
				cs.setInt(1, i);
				cs.execute();
				int result = cs.getInt(3);
				ccount ++;
			}
			long end = System.currentTimeMillis();
			System.out.println(end - begin);
			System.out.println(ccount);
		} catch (ClassNotFoundException e) {
			e.printStackTrace();
		} catch (SQLException e) {
			e.printStackTrace();
		} 
		finally{
            /*关闭数据库连接*/
			try {
				if(cs != null){
					cs.close();
				}
				if(conn != null){
					conn.close();
				}
			} catch (SQLException e) {
				e.printStackTrace();
			}
		}
	}
}	

```
 java代码中关闭数据库的连接后，会自动commit，尽管我在java应用程序和存储过程中没有写commit。

 
--------
PL/SQL中关闭某个SQL窗口（或正常关闭PL/SQL）时，尽管没有显式地commit，执行的增删改操作可能也会被提交。这和PL/SQL中的以下设置有关：

 Tools---Preferences---Oracle---Connection---Logoff with open transaction(默认是commit)

 但是，异常关闭PL/SQL（例如用任务管理器直接关闭），不会自动commit。

   
 