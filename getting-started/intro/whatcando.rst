PHP 能做什么？
=================


PHP 能做任何事。PHP 主要是用于服务端的脚本程序，因此可以用 PHP 来完成任何其它的 CGI 程序能够完成的工作，例如收集表单数据，生成动态网页，或者发送／接收 Cookies。但 PHP 的功能远不局限于此。

PHP 脚本主要用于以下三个领域：

* 服务端脚本。这是 PHP 最传统，也是最主要的目标领域。开展这项工作需要具备以下三点：PHP 解析器（CGI 或者服务器模块）、web 服务器和 web 浏览器。需要在运行 web 服务器时，安装并配置 PHP，然后，可以用 web 浏览器来访问 PHP 程序的输出，即浏览服务端的 PHP 页面。如果只是实验 PHP 编程，所有的这些都可以运行在自己家里的电脑中。请查阅安装一章以获取更多信息。
* 命令行脚本。可以编写一段 PHP 脚本，并且不需要任何服务器或者浏览器来运行它。通过这种方式，仅仅只需要 PHP 解析器来执行。这种用法对于依赖 cron（Unix 或者 Linux 环境）或者 Task Scheduler（Windows 环境）的日常运行的脚本来说是理想的选择。这些脚本也可以用来处理简单的文本。请参阅 PHP 的命令行模式以获取更多信息。
* 编写桌面应用程序。对于有着图形界面的桌面应用程序来说，PHP 或许不是一种最好的语言，但是如果用户非常精通 PHP，并且希望在客户端应用程序中使用 PHP 的一些高级特性，可以利用 PHP-GTK 来编写这些程序。用这种方法，还可以编写跨平台的应用程序。PHP-GTK 是 PHP 的一个扩展，在通常发布的 PHP 包中并不包含它。如果对 PHP-GTK 感兴趣，请访问其» 网站以获取更多信息。

PHP 能够用在所有的主流操作系统上，包括 Linux、Unix 的各种变种（包括 HP-UX、Solaris 和 OpenBSD）、Microsoft Windows、Mac OS X、RISC OS 等。今天，PHP已经支持了大多数的 web 服务器，包括 Apache、Microsoft Internet Information Server（IIS）、Personal web Server（PWS）、Netscape 以及 iPlant server、Oreilly Website Pro Server、Caudium、Xitami、OmniHTTPd 等。对于大多数的服务器，PHP 提供了一个模块；还有一些 PHP 支持 CGI 标准，使得 PHP 能够作为 CGI 处理器来工作。

综上所述，使用 PHP，可以自由地选择操作系统和 web 服务器。同时，还可以在开发时选择使用面对过程和面对对象，或者两者混和的方式来开发。尽管 PHP 4 不支持 OOP 所有的标准，但很多代码仓库和大型的应用程序（包括 PEAR 库）仅使用 OOP 代码来开发。PHP 5 弥补了 PHP 4 的这一弱点，引入了完全的对象模型。

使用 PHP，并不局限于输出 HTML。PHP 还能被用来动态输出图像、PDF 文件甚至 Flash 动画（使用 libswf 和 Ming）。还能够非常简便的输出文本，例如 XHTML 以及任何其它形式的 XML 文件。PHP 能够自动生成这些文件，在服务端开辟出一块动态内容的缓存，可以直接把它们打印出来，或者将它们存储到文件系统中。

PHP 最强大最显著的特性之一，是它支持很大范围的数据库。用户会发现利用 PHP 编写数据库支持的网页简单得难以置信。目前，PHP 支持如下数据库：

* Adabas D
* dBase
* Empress
* FilePro（只读）
* Hyperwave
* IBM DB2
* Informix
* Ingres
* InterBase
* FrontBase
* mSQL
* Direct MS-SQL
* MySQL
* ODBC
* Oracle（OCI7 和 OCI8）
* Ovrimos
* PostgreSQL
* SQLite
* Solid
* Sybase
* Velocis
* Unix dbm

同时还有一个叫做 PDO 的数据库抽象扩展库使得可以自由地使用该扩展库支持的任何数据库。另外，PHP 还支持 ODBC，即 Open Database Connection Standard（开放数据库连接标准），因此可以连接任何其它支持该世界标准的数据库。
PHP 还支持利用诸如 LDAP、IMAP、SNMP、NNTP、POP3、HTTP、COM（Windows 环境）等不计其数的协议的服务。还可以开放原始网络端口，使得任何其它的协议能够协同工作。PHP 支持和所有 web 开发语言之间的 WDDX 复杂数据交换。关于相互连接，PHP 已经支持了对 Java 对象的即时连接，并且可以将他们自由的用作 PHP 对象。甚至可以用我们的 CORBA 扩展库来访问远程对象。

PHP 具有极其有效的文本处理特性，支持从 POSIX 扩展或者 Perl 正则表达式到 XML 文档解析。为了解析和访问 XML 文档，PHP 4 支持 SAX 和 DOM 标准，也可以使用 XSLT 扩展库来转换 XML 文档。PHP 5 基于强健的 libxm2 标准化了所有的 XML 扩展，并添加了 SimpleXML 和 XMLReader 支持，扩展了其在 XML 方面的功能。

另外，还有很多其它有趣的扩展库，他们根据字母和 分类归类列出。例如 mnoGoSearch 搜索引擎函数、IRC 网关函数、多种压缩工具（gzip、bz2、zip）、日历转换、翻译……。 还有一些第三方的PECL扩展没有在PHP手册中列出，例如 » XDebug

由于在这里无法列出 PHP 所有的特性和可提供的便利，请参阅安装以及函数参考有关章节以获取关于这里提到的扩展库更多的信息。
