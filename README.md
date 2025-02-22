PHP开发环境搭建指南
一、Windows系统搭建方案
1. 集成环境（推荐新手）
WampServer/XAMPP/PhpStudy：一键安装Apache、PHP、MySQL等组件，无需手动配置。
PhpStudy支持自定义端口（如解决80端口冲突问题），提供可视化控制面板。
安装后需启动Apache和MySQL服务，访问http://localhost:端口号测试环境是否正常。
2. 手动配置（适合进阶）
安装Apache
下载Apache官方包，修改httpd.conf 中的根目录和端口，以管理员身份安装服务。
安装PHP
下载PHP线程安全版本，解压到指定目录，在httpd.conf 添加LoadModule php7_module "路径/php7apache2_4.dll" 。
安装MySQL
配置php.ini 启用php_mysql.dll 和php_mysqli.dll 扩展，设置数据库连接参数。
二、Linux系统搭建方案
1. 使用包管理器（Ubuntu为例）
sudo apt update 
sudo apt install apache2 php mysql-server php-mysql 
sudo systemctl restart apache2  # 重启服务生效 
验证：创建/var/www/html/info.php 文件，内容为<?php phpinfo(); ?>，访问http://localhost/info.php 。
2. 高级配置
虚拟主机：在/etc/apache2/sites-available/中创建配置文件，指定域名和项目目录。
性能优化：调整php.ini 中的max_execution_time（脚本超时时间）和memory_limit（内存限制）。
三、开发工具推荐
PhpStorm
专业IDE，需配置PHP解释器路径（如PhpStudy的php.exe 路径）。
Visual Studio Code
轻量级编辑器，安装PHP Intelephense插件支持代码提示。
数据库管理
MySQL Workbench或phpMyAdmin（集成环境自带）。
四、常见问题解决
端口冲突
修改Apache的Listen 80为其他端口（如8080）。
PHP扩展缺失
在php.ini 中取消注释extension=curl等所需模块。
路径权限问题
Linux系统需给项目目录赋予chmod -R 755 /var/www权限。
五、测试与验证
创建测试文件test.php ，写入<?php echo "Hello, PHP!"; ?>，通过浏览器访问验证输出。
检查phpinfo()页面是否显示已启用的模块（如MySQL、GD库）。
通过上述步骤，您可快速搭建适用于不同场景的PHP开发环境。若需更详细的框架配置（如Laravel）或生产环境部署方案，可进一步参考官方文档。
