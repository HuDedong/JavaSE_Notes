# 【Java】Properties类

**目录**

[🥇一、Properties介绍](read://https_blog.csdn.net/?url=https%3A%2F%2Fblog.csdn.net%2Fweixin_53972936%2Farticle%2Fdetails%2F123899368%3Fops_request_misc%3D%257B%2522request%255Fid%2522%253A%2522172293510816800178529353%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D%26request_id%3D172293510816800178529353%26biz_id%3D0%26utm_medium%3Ddistribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-123899368-null-null.142^v100^pc_search_result_base2%26utm_term%3Dproperties%E7%B1%BB%26spm%3D1018.2226.3001.4187#t0)

[🥇二、常用方法介绍](read://https_blog.csdn.net/?url=https%3A%2F%2Fblog.csdn.net%2Fweixin_53972936%2Farticle%2Fdetails%2F123899368%3Fops_request_misc%3D%257B%2522request%255Fid%2522%253A%2522172293510816800178529353%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D%26request_id%3D172293510816800178529353%26biz_id%3D0%26utm_medium%3Ddistribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-123899368-null-null.142^v100^pc_search_result_base2%26utm_term%3Dproperties%E7%B1%BB%26spm%3D1018.2226.3001.4187#t1)

[🥈2.1 Properties作为Map集合的使用](read://https_blog.csdn.net/?url=https%3A%2F%2Fblog.csdn.net%2Fweixin_53972936%2Farticle%2Fdetails%2F123899368%3Fops_request_misc%3D%257B%2522request%255Fid%2522%253A%2522172293510816800178529353%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D%26request_id%3D172293510816800178529353%26biz_id%3D0%26utm_medium%3Ddistribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-123899368-null-null.142^v100^pc_search_result_base2%26utm_term%3Dproperties%E7%B1%BB%26spm%3D1018.2226.3001.4187#t2)

[🥈2.2 Properties作为集合的特有方法](read://https_blog.csdn.net/?url=https%3A%2F%2Fblog.csdn.net%2Fweixin_53972936%2Farticle%2Fdetails%2F123899368%3Fops_request_misc%3D%257B%2522request%255Fid%2522%253A%2522172293510816800178529353%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D%26request_id%3D172293510816800178529353%26biz_id%3D0%26utm_medium%3Ddistribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-123899368-null-null.142^v100^pc_search_result_base2%26utm_term%3Dproperties%E7%B1%BB%26spm%3D1018.2226.3001.4187#t3)

[🥈2.3 Properties和IO流结合的方法](read://https_blog.csdn.net/?url=https%3A%2F%2Fblog.csdn.net%2Fweixin_53972936%2Farticle%2Fdetails%2F123899368%3Fops_request_misc%3D%257B%2522request%255Fid%2522%253A%2522172293510816800178529353%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D%26request_id%3D172293510816800178529353%26biz_id%3D0%26utm_medium%3Ddistribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-123899368-null-null.142^v100^pc_search_result_base2%26utm_term%3Dproperties%E7%B1%BB%26spm%3D1018.2226.3001.4187#t4)

[🥉2.3.1 利用IO流将数据存入文件](read://https_blog.csdn.net/?url=https%3A%2F%2Fblog.csdn.net%2Fweixin_53972936%2Farticle%2Fdetails%2F123899368%3Fops_request_misc%3D%257B%2522request%255Fid%2522%253A%2522172293510816800178529353%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D%26request_id%3D172293510816800178529353%26biz_id%3D0%26utm_medium%3Ddistribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-123899368-null-null.142^v100^pc_search_result_base2%26utm_term%3Dproperties%E7%B1%BB%26spm%3D1018.2226.3001.4187#t5)

[🥉2.3.2 利用IO流将文件数据加载到集合](read://https_blog.csdn.net/?url=https%3A%2F%2Fblog.csdn.net%2Fweixin_53972936%2Farticle%2Fdetails%2F123899368%3Fops_request_misc%3D%257B%2522request%255Fid%2522%253A%2522172293510816800178529353%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D%26request_id%3D172293510816800178529353%26biz_id%3D0%26utm_medium%3Ddistribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-123899368-null-null.142^v100^pc_search_result_base2%26utm_term%3Dproperties%E7%B1%BB%26spm%3D1018.2226.3001.4187#t6)

------



## 🥇一、Properties介绍

​    Properties（Java.util.Properties）是Java中一个比较重要的类，主要用于读取Java的配置文件。各种语言都有自己所支持的配置文件，配置文件中很多变量是经常改变的，这样做也是为了方便用户，让用户能够脱离程序本身去修改相关的变量设置。在Java中，其配置文件常为.properties文件，格式为文本文件，文件的内容的格式是“键=值”或者“键 值”的格式，文本注释信息可以用"#"来注释。

​    在做Java项目开发过程中，涉及到一些数据库服务连接配置、缓存服务器连接配置等，通常情况下我们会将这些不太变动的配置信息存储在以 .properties 结尾的配置文件中。当对应的服务器地址或者账号密码信息有所变动时，我们只需要修改一下配置文件中的信息即可。

​    Properties是一个Map体系集合类，因为其继承于Hashtable，而Hashtable继承于Dictionary类，实现了Map接口，所以Properties也保留了其相关特性。

![img](images/Properties/cd7ac05bc32576a8c6d55cc4b046e989.png)

> **📀Properties特点：**
>
> （1）Properties是Hashtable<Object,Object>的子类；
>
> （2）Properties类表示了一个可持久的属性集；
>
> （3）Properties可以保存在流中或从流中加载；
>
> （4）Properties中每个键和对应的值都是一个字符串（String类型）；
>
> （5）Properties有一个特殊的作用：专门用来加载xxx.properties配置文件。

## 🥇二、常用方法介绍

### 🥈2.1 Properties作为Map集合的使用

> ​    Properties作为Map集合使用时各种方法都与map集合一致（虽然可以但是不建议将Properties作为Map集合使用），但是有一点不同，就是在创建对象时不需要也不能给出泛型，否则会报错，默认所有的键值对类型都是Object类型。下面进行简单的添加和遍历演示。

```java
//Properties作为map集合的使用

private static void PropertiesMap() {

	Properties pro = new Properties();//不需要加泛型，所有的键值都是object类型

	

	//存储元素

	pro.put(001, "张三");

	pro.put(002, "李四");

	pro.put(003, "王五");

	

	//遍历集合

	for(Object key : pro.keySet()) {

		System.out.println(key + ":" + pro.get(key));

	}

}
```

![img](images/Properties/61154b98c95c034d81220a267cd620d6.png) 

> 注意：不要使用Hashtable里面定义的方法添加键值对！因为它们可以插入不是String 类型的数据。如果一个Properties中含有非String的键值对，那么这样的Properties是“不安全”的。调用 store 或者 save 方法将失败。



### 🥈2.2 Properties作为集合的特有方法

![img](images/Properties/2ba0a4f8701df00accddaeaca9a82e6e.png)

 

```java
/**

 * Properties作为集合的特有方法

 * 		0bject setProperty(String key,String value):设置类合的链和值，都是String类型，底层调用Hashtable方法put

 * 		string getProperty ( String key):使用此属性列表中指定的性搜索属性

 * 		Set<String> stringPropert yNames():从该属性列表中返回一个不可修改的键集，其中键及其对应的值是字符串

 */

private static void SpecialMethod() {

	Properties pro = new Properties();

	

	pro.setProperty("001", "张三");//键值都是String类型

	pro.setProperty("002", "李四");

	pro.setProperty("003", "王五");

		

	System.out.println(pro.getProperty("001"));//根据键搜索属性

	System.out.println(pro.getProperty("0011"));//没有时返回null

	

	System.out.println(pro);

	

	Set<String> s = pro.stringPropertyNames();//返回一个不可修改的键集，其中键及其对应的值是字符串

	System.out.println(s);

	for(String key : s) {

		System.out.println(key + ":" + pro.getProperty(key));

	}

}
```

![img](images/Properties/14730e4f721c2399764630123f0f7f81.png)



### 🥈2.3 Properties和IO流结合的方法

![img](images/Properties/be1caf172428150ffe8316660cef873c.png)

#### 🥉2.3.1 利用IO流将数据存入文件

```java
//集合中数据保存到文件

	Properties pro = new Properties();

	

	pro.setProperty("001", "张三");//键值都是String类型

	pro.setProperty("002", "李四");

	pro.setProperty("003", "王五");

	

	System.out.println(pro);

	

	FileWriter fw = new FileWriter("Properties.txt");

	pro.store(fw,null);//不想添加描述信息就令第二个参数为null

	

	//数据保存为XML格式文件

	//storeToXML(OutputStream os, String comment, String encoding)使用指定的编码方式表示此表中包含的所有属性的XML文档

	FileOutputStream f1 = new FileOutputStream("PropertiesXML.XML");

	pro.storeToXML(f1, null);
```

**📀** 两个文件对应内容：

![img](images/Properties/73f5b35fa5ac56b05c99e4c99be70fb0.png)

![img](images/Properties/29c9d05db261900f5a80082a72181598.png)



#### 🥉2.3.2 利用IO流将文件数据加载到集合

```java
//文件中数据加载到集合

Properties prop = new Properties();

	

FileReader fr = new FileReader("Properties.txt");

prop.load(fr);

	

//将此属性列表打印到指定的输出流。此方法对于调试很有用

prop.list(System.out);

//System.out.println(prop);

 

//从内容为XML格式的文件中读取数据加载为集合

FileInputStream f2 = new FileInputStream("PropertiesXML.XML");

prop.loadFromXML(f2);

 

prop.list(System.out);

//System.out.println(prop);
```

 **📀**输出：

![img](images/Properties/84a869d05c3cda96b56a4ae0b14999aa.png)

​    前面讲到我们使用 Properties 的目的就是为了能脱离程序去修改文件，那么我们现在尝试去修改对应的文件，再次读取数据，看看是否会出错。

**📀**将Properties.txt文件中张三的键的值由001改为010，并且删去李四这个人对应的键值对。

![img](images/Properties/f69ed1964ca44cd5cd15b91712afdeaf.png)

**📀** 将PropertiesXML.XMLt文件中李四的键的值由002改为020，并将003对应的值改为薛六。

![img](images/Properties/00b943a5a28dd1ed3650e50fbd775b03.png)

**📀**再次运行程序，观察输出：

![img](images/Properties/47fc258f22f471ec42238b1dc8efca23.png)

> 注意：在写入很弱读取数据时，尽量每个Properties对象只对应一个输入或输出流，否则可能出现读取错误的情况，例如：读取txt文件和xml文件时使用同一个Properties对象时输出如下

 ![img](images/Properties/783b1c3e67e53e86e33cec51a890dede.png)