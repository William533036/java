java

java学习

# Java环境配置

## 1.Tomcat安装配置

#### 1.下载Tomcat

1. 打开http://tomcat.apache.org/
2. 点击左侧 download下对应的版本
3. 点击Browse-->bin-->选择对应环境的包

#### 2.安装配置Tomcat(Windows zip包为例)

1. 解压zip包

2. 配置环境变量

   TOMCAT_HOME: 此路径为你解压文件夹所在的绝对路径

   Path: 添加%TOMCAT_HOME%\bin;

   Classpath: 添加%TOMCAT_HOME%\lib

#### 3.启动

​	打开bin文件夹，双击startup.bat

​	不要关闭控制台界面，打开浏览器，输入http://localhost:8080

## 2.Maven配置

Maven配置默认使用的JDK版本

在idea安装路径下的plugins\maven\lib\maven3\conf\settings.xml找到settings.xml文件，在里面添加如下代码

添加阿里镜像地址

	<mirror>
			<id>aliyunmaven</id>
			<mirrorOf>*</mirrorOf>
			<name>阿里云公共仓库</name>
			<url>https://maven.aliyun.com/repository/public</url>
	</mirror>	
添加jdk版本

		<profile>
			<id>jdk-1.8</id>    
					 <activation>    
						<activeByDefault>true</activeByDefault>    
			<jdk>1.8</jdk>    
	  </activation>  
			<properties>    
				<maven.compiler.source>1.8</maven.compiler.source>    
				<maven.compiler.target>1.8</maven.compiler.target>    
				<maven.compiler.compilerVersion>1.8</maven.compiler.compilerVersion>    
			</properties>    
	</profile>


## 3.Maven项目中配置Tomcat

新建MavenWeb项目

1. 新建moduel，输入名称MavenWeb
2. 选择maven，选择jdk1.8，点击下一步
3. 输入parent(继承对象)、name、项目位置，Artifact Coordinates信息
4. 点击完成
5. 点击右上方project structure
6. 选中创建的MavenWeb，点击+号，选中web
7. 点击web，点击+号，生成web.xml文件
8. 选择web资源路径

//将新建项目打成war包

https://jingyan.baidu.com/article/a24b33cd10adf719fe002ba1.html

​	https://www.cnblogs.com/personsiglewine/p/11002027.html

idea配置tomcat热部署

​	https://blog.csdn.net/qq_41288095/article/details/89486303

选择Tomcat

1. 点击run

2. 点击Edit Configurations

3. 点击+号，找到Tomcat Server(当前列表没找到点击more)

4. 点击Local本地，输入名字Tomcat7

5. 点击Configuration，选择本地安装的Tomcat路径

6. 选择deployment，点击+号，选择artifact，找到对应的war包

    ps:今天卡了一会这里，因为打war包需要一点时间，idea的deployment里选不到artifact。这时候启动会报错。等war包好了，再去选

7. 访问的路径名称和project structure 中创建war包的artifact的 名字加下划线war ，MvnWebTest:war---》MvnWebTest_war

