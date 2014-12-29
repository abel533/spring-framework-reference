#Spring框架参考文档 翻译

##I. 翻译一般要求

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

##II. 编译本项目   

为了便于独立翻译，已经手工将`index.adoc`和`appendix.adoc`进行了拆分。拆分后的内容在`src\main\asciidoc\chapter`目录。

拆分规则：  

- 1~29 属于`index.adoc`
- 30 是`index.adoc`的结尾，也属于`index.adoc`，但是不需要翻译
- 31~35 是`appendix.adoc`的内容

由于目录结构做了调整，为了不影响现有的翻译内容，拆分的位置没有修改。但是`index.adoc`和`appendix.adoc`所在的目录都已经移动到了`src\asciidoc`中。  

###等大家都在的时候，我可以移动`chapter`目录到`src\asciidoc`中，将来修改`index.adoc`可以直接引用所有的独立部分。

Spring项目使用的**Gradle**,编译文档也需要用到**Gradle**，所以如果你想编译本项目，需要按如下进行操作：  

###0. 目前需要手动合并章节内容  

目前需要手动合并到`index.adoc`和`appendix.adoc`，后续修改目录后可以免去这一步操作。  

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

