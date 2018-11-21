---
bilibili_id: 
youku_id: 
youtube_id: 
description: 
chapter: 1
title: supporting tools
date: 2018-10-5

author: wang liyao
post-headings:
  - 库文档工具(Libdoc)
  - 测试数据文档工具（Testdoc）
  - 测试数据清理工具（Tidy)
  - 外部工具
---




{% include assign-heading.html %}

Libdoc是Robot框架的内置工具，用于为测试库和HTML和XML格式的资源文件生成关键字文档。前者的格式适用于人类，后者适用于ride和其他工具。Libdoc也很少有特殊的命令来显示控制台的库或资源信息。

**一般模式**

命令行
> python -m robot.libdoc [options] library_or_resource output_file

> python -m robot.libdoc [options] library_or_resource list|show|version [names]


**可选项**

-f, --format <html|xml>


Specifies whether to generate HTML or XML output. If this options is not used, the format is got from the extension of the output file.

-F, --docformat <robot|html|text|rest>

Specifies the source documentation format. Possible values are Robot Framework's documentation format, HTML, plain text, and reStructuredText. Default > value can be specified in test library source code and the initial default value is robot. New in Robot Framework 2.7.5.

-N, --name <newname>

Sets the name of the documented library or resource.

-V, --version <newversion>

Sets the version of the documented library or resource. The default value for test libraries is got from the source code.

-P, --pythonpath <path>

Additional locations where to search for libraries and resources similarly as when running tests.

-E, --escape <what:with>

Escapes characters which are problematic in console. what is the name of the character to escape and with is the string to escape it with. Available escapes are listed in the --help output.

-h, --help	


**生成文档**

当以HTML或XML格式生成文档时，输出文件必须在librar/resource name或path之后指定为第二个参数。输出格式从扩展中自动获得，但也可以使用——format选项来设置

example
> python -m robot.libdoc OperatingSystem OperatingSystem.html

> python -m robot.libdoc --name MyLibrary Remote::http://10.0.0.42:8270 MyLibrary.xml

> python -m robot.libdoc test/resource.html doc/resource_doc.html

> jython -m robot.libdoc --version 1.0 MyJavaLibrary.java MyJavaLibrary.html

> jython -m robot.libdoc my.organization.DynamicJavaLibrary my.organization.DynamicJavaLibrary.xml


**在控制台上查看信息**
Libdoc有三个特殊的命令来显示控制台的信息。这些命令代替了输出文件的名称，并且还可以使用额外的参数。

- list

列出 library/resource包含的keywords名字, 可以通过将可选模式作为参数传递给特定的关键字。如果它的名称包含给定的模式，则列出关键字。

- show

显示library/resource 文档. 可以通过names 这个参数来限制指定那些keyword显示,如果它的名称与任何给定的名称相匹配，就会显示关键字。特殊的参数介绍将只显示库的介绍和导入部分

- version

显示library版本号
列出和显示的可选模式是大小写和空格不敏感的。两者都接受，而且？作为通配符。

{% include assign-heading.html %}

Testdoc是robot框架的内置工具，用于根据测试用例生成高级文档。所创建的文档是以HTML格式编写的，它包括每个测试套件和测试用例的名称、文档和其他元数据，以及顶级关键字及其参数.

**一般模式**

**命令行**
> python -m robot.testdoc [options] data_sources output_file

**可选项**

-T, --title <title>

Set the title of the generated documentation. Underscores in the title are converted to spaces. The default title is the name of the top level suite.

-N, --name <name>

Override the name of the top level test suite.

-D, --doc <doc>

Override the documentation of the top level test suite.

-M, --metadata <name:value>

Set/override free metadata of the top level test suite.

-G, --settag <tag>

Set given tag(s) to all test cases.

-t, --test <name>

Include tests by name.

-s, --suite <name>

Include suites by name.

-i, --include <tag>

Include tests by tags.

-e, --exclude <tag>

Exclude tests by tags.

-A, --argumentfile <path>

Text file to read more arguments from. Works exactly like argument files when running tests. New in Robot Framework 3.0.2.

-h, --help	Print this help in the console.


**生成文档**
数据可以作为单个文件、目录或多个文件和目录来提供。在所有这些情况下，最后一个参数必须是写入输出的文件。

Testdoc与所有robot框架（Python、Jython和IronPython）支持的解释器一起工作。它可以作为一个安装的模块执行，比如python-m robot。或者作为一个脚本，如python module/robot/testdoc.py。

**example**
> python -m robot.testdoc my_test.html testdoc.html

> jython -m robot.testdoc --name smoke_tests --include smoke path/to/my_tests smoke.html

{% include assign-heading.html %}

tidy 是robot内置的一个工具，用于清理和更改机器人框架测试数据文件的格式。
默认情况下，输出被写入标准输出流，但是可以从机器人框架2.7.5开始一个可选的输出文件。文件也可以使用——inplace或——递归选项进行修改。

**命令行**
> python -m robot.tidy [options] inputfile

> python -m robot.tidy [options] inputfile [outputfile]

> python -m robot.tidy --inplace [options] inputfile [more input files]

> python -m robot.tidy --recursive [options] directory

**可选项**
-i, --inplace	

Tidy given file(s) so that original file(s) are overwritten (or removed, if the format is changed). When this option is used, it is possible to give multiple input files. Examples:

python -m robot.tidy --inplace tests.html

python -m robot.tidy --inplace --format txt *.html

-r, --recursive

Process given directory recursively. Files in the directory are processed in place similarly as when --inplace option is used.

-f, --format <robot|txt|html|tsv>

Output file format. If the output file is given explicitly, the default value is got from its extension. Otherwise the format is not changed.

-p, --use-pipes

Use a pipe character (|) as a cell separator in the txt format.

-s, --spacecount <number>

The number of spaces between cells in the txt format. New in Robot Framework 2.7.3.

-l, --lineseparator <native|windows|unix>
 	
Line separator to use in outputs. The default is 'native'.

native: use operating system's native line separators

windows: use Windows line separators (CRLF)

unix: use Unix line separators (LF)

New in Robot Framework 2.7.6.

-h, --help	Show this help.

**清理test data**
用HTML编辑器创建的测试用例文件或手工编写的文件可以使用整洁的方式进行标准化。整洁总是写一致的标题，一致的设置顺序，以及在单元格和表格之间保持一致的空白。

example:
> python -m robot.tidy messed_up_tests.html cleaned_tests.html

> python -m robot.tidy --inplace tests.txt

**修改case的格式**
robot框架支持HTML、TSV和TXT格式的测试数据，并且整齐地使格式之间的变化变得微不足道。输入格式总是基于输入文件的扩展来确定。输出格式可以使用-format选项来设置，并且默认值是从可能的输出文件的扩展中获得
> python -m robot.tidy tests.html tests.txt

> python -m robot.tidy --format txt --inplace tests.html

> python -m robot.tidy --format tsv --recursive mytests


{% include assign-heading.html %}

有大量的外部工具可以与机器人框架一起使用。这些工具包括测试数据编辑器、各种ide和文本编辑器的扩展、用于持续集成系统和构建工具的插件等等。
这些工具是独立于机器人框架本身独立开发的。有关可用工具的列表，请参见http://robotframework.org/tools。