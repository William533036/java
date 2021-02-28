java

java学习

# Java环境配置

## Tomcat安装配置

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

## Maven配置

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