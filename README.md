【防护XSS,SQL,代码执行使用方法】
1.将waf.php传到要包含的文件的目录

2.在页面中加入防护，有两种做法，根据情况二选一即可：

a).在所需要防护的页面加入代码
require_once('waf.php');
就可以做到页面防注入、跨站
如果想整站防注，就在网站的一个公用文件中，如数据库链接文件config.inc.php中！
添加require_once('waf.php');来调用本代码

常用php系统添加文件
PHPCMS V9 \phpcms\base.php
PHPWIND8.7 \data\sql_config.php
DEDECMS5.7 \data\common.inc.php
DiscuzX2   \config\config_global.php
Wordpress   \wp-config.php
Metinfo   \include\head.php

b).在每个文件最前加上代码
在php.ini中找到:
Automatically add files before or after any PHP document.
auto_prepend_file = waf.php路径;
