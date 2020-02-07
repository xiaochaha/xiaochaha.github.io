---
title: servlet
date: 2020-02-07 21:49:04
tags: 
- 'servlet'
- 'web后端'
categories:
- 'JavaEE'
---

第一个servlet实例

主要是实现用户的登录与注册



login.jsp

```jsp
<%@ page language="java" contentType="text/html; charset=UTF-8"
	pageEncoding="UTF-8"%>
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Login</title>
<script>
	function check(form) {
		if (form.username.value == "") {
			alert("用户名不能为空！");
			return false;
		}
		if (form.password.value == "") {
			alert("密码不能为空！");
			return false;
		}
	}
</script>
</head>
<body>
	<div id="loginDiv">
		<form action="LoginServlet" method="post"
			onsubmit="return check(this);">
			<label>用户名：</label> <input type="text" name="username"> <label>密码：</label>
			<input type="text" name="password">
			<button>登录</button>
		</form>
	</div>
</body>
</html>
```
regUser.jsp

```jsp
<%@ page language="java" contentType="text/html; charset=UTF-8"
	pageEncoding="UTF-8"%>
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
<script>
	function check(form) {
		if (form.username.value == "") {
			alert("用户名不能为空！");
			return false;
		}
		if (form.password.value == "") {
			alert("密码不能为空！");
			return false;
		}
		if (form.repassword.value == "") {
			alert("重复密码不能为空！");
			return false;
		}
		if (form.question.value == "") {
			alert("问题不能为空！");
			return false;
		}
		if (form.answer.value == "") {
			alert("答案不能为空！");
			return false;
		}
		if (form.email.value == "") {
			alert("email不能为空！");
			return false;
		}
	}
</script>
</head>
<body>
	<form action="RegUserServlet" method="post"
		onsubmit="return check(this);">
		<label>用户名：</label> <input type="text" name="username"><br>
		<label>密码：</label> <input type="password" name="password"><br>
		<label>确认密码：</label> <input type="password" name="repassword"><br>
		<label>性别：</label> <input type="radio" name="sex" value="男"
			checked="checked">男 <input type="radio" name="sex" value="女">女
		<br> <label>密码找回问题：</label> <input type="text" name="question"><br>
		<label>密码找回答案：</label> <input type="text" name="answer"><br>
		<label>邮箱：</label> <input type="text" name="email">
		<button>注册</button>
		<button>重制</button>
	</form>

</body>
</html>
```
LoginServlet.java
```java
package com.ash.User;

import java.io.IOException;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.ResultSet;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

/**
 * Servlet implementation class LoginServlet
 */
@WebServlet("/LoginServlet")
public class LoginServlet extends HttpServlet {
	private static final long serialVersionUID = 1L;

	/**
	 * @see HttpServlet#HttpServlet()
	 */
	public LoginServlet() {
		super();
		// TODO Auto-generated constructor stub
	}

	/**
	 * @see HttpServlet#doGet(HttpServletRequest request, HttpServletResponse
	 *      response)
	 */
	protected void doGet(HttpServletRequest request, HttpServletResponse response)
			throws ServletException, IOException {
		// TODO Auto-generated method stub
		response.getWriter().append("Served at: ").append(request.getContextPath());
	}

	/**
	 * @see HttpServlet#doPost(HttpServletRequest request, HttpServletResponse
	 *      response)
	 */
	protected void doPost(HttpServletRequest request, HttpServletResponse response)
			throws ServletException, IOException {
        //处理中文问题
		response.setContentType("text/html;charset=UTF-8");
		request.setCharacterEncoding("UTF-8");
		//获取页面输入的信息
		String name = request.getParameter("username");
		String password = request.getParameter("password");
		
		Connection conn = null;
		PreparedStatement pstmt = null;
		ResultSet rs = null;
		boolean flag = false;

		try {
            //创建数据库连接
			Class.forName("com.mysql.jdbc.Driver");
			String url = "jdbc:mysql://127.0.0.1:3306/testdb";
			conn = DriverManager.getConnection(url, "root", "");

			String sql = "select username,password from tb_user where username=? and password=? ";

			pstmt = conn.prepareStatement(sql);
			pstmt.setString(1, name);
			pstmt.setString(2, password);

			rs = pstmt.executeQuery();

			if (rs.next()) {
				flag = true;
			}
			rs.close();
			pstmt.close();
			conn.close();
		} catch (Exception e) {
			e.printStackTrace();
		}
		if (flag) {
			response.sendRedirect("https://www.baidu.com");
		} else {
			response.getWriter().println("用户名或者密码错误");
		}

	}

}

```

RegUserServlet.java

```java
package com.ash.User;

import java.io.IOException;
import java.io.PrintWriter;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;

import javax.servlet.ServletConfig;
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

/**
 * Servlet implementation class RegUserServlet
 */
@WebServlet("/RegUserServlet")
public class RegUserServlet extends HttpServlet {
	private static final long serialVersionUID = 1L;
	private Connection conn = null;

	/**
	 * @see HttpServlet#HttpServlet()
	 */
	public RegUserServlet() {
		super();
		// TODO Auto-generated constructor stub
	}

	/**
	 * @see Servlet#init(ServletConfig)
	 */
	public void init(ServletConfig config) throws ServletException {
		super.init();
		try {
			Class.forName("com.mysql.jdbc.Driver");
			String url = "jdbc:mysql://localhost:3306/testdb?useUnicode=true&characterEncoding=utf8";
			conn = DriverManager.getConnection(url, "root", "");

		} catch (Exception e) {
			e.printStackTrace();
		}
	}

	/**
	 * @see HttpServlet#doGet(HttpServletRequest request, HttpServletResponse
	 *      response)
	 */
	protected void doGet(HttpServletRequest request, HttpServletResponse response)
			throws ServletException, IOException {
		// TODO Auto-generated method stub
		response.getWriter().append("Served at: ").append(request.getContextPath());
	}

	/**
	 * @see HttpServlet#doPost(HttpServletRequest request, HttpServletResponse
	 *      response)
	 */
	protected void doPost(HttpServletRequest request, HttpServletResponse response)
			throws ServletException, IOException {
		// TODO Auto-generated method stub
		response.setContentType("text/html");
		response.setCharacterEncoding("UTF-8");
		request.setCharacterEncoding("UTF-8");

		String username = request.getParameter("username");
		String password = request.getParameter("password");
		String sex = request.getParameter("sex");
		String question = request.getParameter("question");
		String answer = request.getParameter("answer");
		String email = request.getParameter("email");

		if (conn != null) {
			try {

				String sql = "insert into tb_user(username,password,sex,question,answer,email)" + "values(?,?,?,?,?,?)";

				PreparedStatement ps = conn.prepareStatement(sql);
				ps.setString(1, username);
				ps.setString(2, password);
				ps.setString(3, sex);
				ps.setString(4, question);
				ps.setString(5, answer);
				ps.setString(6, email);

				ps.executeUpdate();

				PrintWriter out = response.getWriter();

				out.print("<h1>");
				out.print(username + "注册成功");
				out.print("</h1>");
				out.flush();
				out.close();
			} catch (Exception e) {
				e.printStackTrace();
			}
		} else {
			response.sendError(500, "数据库连接错误");
		}
	}

}

```

