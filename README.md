#Spring框架参考文档 翻译

**基本说明**

Spring文档为adoc格式，文件已经按基本的章节拆分为多个adoc文件，该文件在`src/asciidoc/chapter`路径下。  

**参与翻译**

1. 首先加QQ群Team翻译小组：111763438  

2. 进群后，会先发申请链接，加入OSC的Team

3. 进入Team后需要先绑定gitosc账号。

4. 可以从上面的章节中选择还没有人翻译的章节（有人翻译的标题都是中文）

5. 跟群主说明要翻译的章节，确定后可以开始翻译。

6. 开始翻译的时候先翻译标题，然后提交（避免其他人重复翻译）。

7. **翻译前请看下面的要求**。

##I. 已分配的章节

- **1.introduction.adoc          - [lixiuwen](http://git.oschina.net/lixiuwen)**
- **2.spring-whats-new.adoc      - [isea533](http://blog.csdn.net/isea533)**
- **3.beans.adoc                 - [isea533](http://blog.csdn.net/isea533)**
- **4.resources.adoc             - [tianya](tianyatianya-PC)**
- **5.validation.adoc            - [jassen](http://git.oschina.net/thinapple)**
- **7.expressions.adoc           - [Ji.K'](https://jik92.com/)**
- **8.aop.adoc                   - [ym919202](http://git.oschina.net/yemaozistar)**
- 9.aop-api.adoc               -
- 10.testing.adoc              -
- 11.spring-data-tier.adoc     -
- 12.dao.adoc                  -
- 13.jdbc.adoc                 -
- 14.orm.adoc                  -
- 15.oxm.adoc                  -
- **16.spring-web.adoc           - [tianya](tianyatianya-PC)**
- 17.view.adoc                 -
- 18.web-integration.adoc      -
- 19.portlet.adoc              -
- **20.websocket.adoc            - [zipu888](http://git.oschina.net/xiaohaogege)**
- 21.spring-integration.adoc   -
- 22.ejb.adoc                  -
- 23.jms.adoc                  -
- 24.jmx.adoc                  -
- 25.cci.adoc                  -
- 26.mail.adoc                 -
- 27.scheduling.adoc           -
- 28.dynamic-language.adoc     -
- 29.cache.adoc                -
- 31.classic-spring.adoc       -
- 32.classic-aop-spring.adoc   -
- 33.xsd-config.adoc           -
- 34.extensible-xml.adoc       -
- 35.spring.tld.adoc           -

##II. 翻译一般要求

为了大家在翻译的时候文件格式正确，而且翻译比较一致，需要遵守一定的要求。

###第一条、 adoc语法

Spring文件使用的adoc语法，和markdow比较接近。  

只有大概了解这种语法才能在翻译的时候知道应该翻译什么，那些不应该翻译。所以要求大家简单了解adoc语法。

asciidoc语法--快速参考：

> [http://asciidoctor.org/docs/asciidoc-syntax-quick-reference/](http://asciidoctor.org/docs/asciidoc-syntax-quick-reference/)  

建议大家一定看看，否则翻译后的文档会出现一些格式错误。  

为了便于查询adoc的预览效果，可以安装Chrome插件：

> [https://github.com/asciidoctor/asciidoctor-chrome-extension](https://github.com/asciidoctor/asciidoctor-chrome-extension)  


###第二条、 代码部分

在adoc语法中：

	[source,xml,indent=0]
	[subs="verbatim,quotes,attributes"]
	----
		<dependencies>
			<dependency>
				<groupId>org.springframework</groupId>
				<artifactId>spring-context</artifactId>
				<version>{spring-version}</version>
				<scope>runtime</scope>
			</dependency>
		</dependencies>
	----

这种是代码内容，这里面的内容一般不需要做任何修改。但是如果代码中有**注释**内容，需要把注释翻译成中文。  

###第三条、 词库  

对于一些英语中专有的词汇，不需要进行翻译的可以不翻译。

例如：Spring不需要翻译，list,map等等不需要翻译，像bean也不用翻译。  

具体遇到那些词可以在群内讨论。  

##III. 编译本项目   

**目录结构**：

为了便于独立翻译，已经手工将`index.adoc`和`appendix.adoc`进行了拆分。拆分后的内容在`src\asciidoc\chaptor`中。

原来的`index.adoc`改名为`index.adoc.backup`。现在的`index.adoc`内容如下：  

	include::chapter/1.introduction.adoc[]
	include::chapter/2.spring-whats-new.adoc[]
	include::chapter/3.beans.adoc[]
	include::chapter/4.resources.adoc[]
	include::chapter/5.validation.adoc[]
	include::chapter/7.expressions.adoc[]
	include::chapter/8.aop.adoc[]
	include::chapter/9.aop-api.adoc[]
	include::chapter/10.testing.adoc[]
	include::chapter/11.spring-data-tier.adoc[]
	include::chapter/12.dao.adoc[]
	include::chapter/13.jdbc.adoc[]
	include::chapter/14.orm.adoc[]
	include::chapter/15.oxm.adoc[]
	include::chapter/16.spring-web.adoc[]
	include::chapter/17.view.adoc[]
	include::chapter/18.web-integration.adoc[]
	include::chapter/19.portlet.adoc[]
	include::chapter/20.websocket.adoc[]
	include::chapter/21.spring-integration.adoc[]
	include::chapter/22.ejb.adoc[]
	include::chapter/23.jms.adoc[]
	include::chapter/24.jmx.adoc[]
	include::chapter/25.cci.adoc[]
	include::chapter/26.mail.adoc[]
	include::chapter/27.scheduling.adoc[]
	include::chapter/28.dynamic-language.adoc[]
	include::chapter/29.cache.adoc[]
	include::chapter/31.classic-spring.adoc[]
	include::chapter/32.classic-aop-spring.adoc[]
	include::chapter/33.xsd-config.adoc[]
	include::chapter/34.extensible-xml.adoc[]
	include::chapter/35.spring.tld.adoc[]

**注**：上面内容中中断的序号的文件都是不存在的，不是bug。  

Spring项目使用的**Gradle**,编译文档也需要用到**Gradle**，所以如果你想编译本项目，需要按如下进行操作：  

###1. 下载并配置Gradle

按照官方的进行配置即可，主要是bin加入Path

###2. 在项目的根目录执行命令

>gradle

然后会下载项目依赖，其中jruby有20多M，整体下载速度一般（使用的osc的maven库）。  

项目运行到最后会报错。

**报错解决**：

报错是因为文件编码的问题，需要修改一个jar包。这个jar包只有执行上面的命令后才会下载下来。  

这个jar包的目录可能是这样：  

>E:\.gradle\caches\modules-2\files-2.1\org.asciidoctor\asciidoctor-java-integration\0.1.4\3596c7142fd30d7b65a0e64ba294f3d9d4bd538f

或者你找到**.gradle**目录后搜索**asciidoctor-java-integration-0.1.4.jar**查找。  

在jar包的**asciidoctor-java-integration-0.1.4.jar\gems\asciidoctor-0.1.4\lib**这个目录下，有一个**asciidoctor.rb**文件。  

在这个文件中找到110行左右，在下面这行代码前添加内容：  

	FORCE_ENCODING = RUBY_VERSION > '1.9' && Encoding.default_external != Encoding::UTF_8


添加的内容为：  

	Encoding.default_external = Encoding::UTF_8

修改后的文件为：  

	# utf8
	Encoding.default_external = Encoding::UTF_8
	
	# Flag to indicate whether encoding of external strings needs to be forced to UTF-8
	# _All_ input data must be force encoded to UTF-8 if Encoding.default_external is *not* UTF-8
	# Address failures performing string operations that are reported as "invalid byte sequence in US-ASCII" 
	# Ruby 1.8 doesn't seem to experience this problem (perhaps because it isn't validating the encodings)
	FORCE_ENCODING = RUBY_VERSION > '1.9' && Encoding.default_external != Encoding::UTF_8


然后将修改后的**asciidoctor.rb**覆盖jar包目录中的文件即可。  

**最后**，再次执行：  

>gradle  

经过几分钟的编译就好了。编译成功的输出日志：

>E:\Git\spring-framework-reference>gradle  
>:asciidoctor  
>:referenceEpub  
>:referenceHtmlMulti  
>:referenceHtmlSingle  
>:referencePdf   
>:reference  
>:docsZip  
>  
>BUILD SUCCESSFUL  
>  
>Total time: 7 mins 56.987 secs  

成功后可以在根目录下的**build**中看到生成的各项内容。  

在**\build\distributions**目录会有一个打包好的zip文件。

