# 禅道项目管理软件配置及使用教程

# **一．禅道安装及运行**

禅道是一款开源项目管理软件。它集产品管理、项目管理、质量管理、文档管理、组织管理和事务管理于一体，是一款专业的研发项目管理软件，完整覆盖了研发项目管理的核心流程。

禅道将产品、项目、测试这三者的概念明确分开，产品人员、开发团队、测试人员，这三者分立，互相配合，又互相制约，通过需求、任务、bug来进行交相互动，最终通过项目拿到合格的产品。

 

1.禅道下载：Linux中可以用以下命令来下载安装包：

64位下载：wget http://dl.cnezsoft.com/zentao/9.0.1/ZenTaoPMS.9.0.1.zbox_64.tar.gz

2.Linux安装需要将安装包解压到/opt目录下。

命令如下：sudo tar -zxvf ZenTaoPMS.9.0.1.zbox_64.tar.gz -C /opt/

解压后会在/opt下找到一个zbox目录，这就是禅道的安装目录。

通过命令进入 cd /opt/zbox/  就可以看到已经安装好的目录结构。

3.启动禅道：在/opt/zbox目录下通过./zbox start命令就可以启动Apache和MySQL

 ![img](https://img-blog.csdn.net/2018053017255210?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzIwMzUwNDc5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

4.在浏览器中访问： IP地址 登陆禅道

 ![img](https://img-blog.csdn.net/20180530172625538?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzIwMzUwNDc5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

# 二．**禅道组成结构**

 ![img](https://img-blog.csdn.net/2018053017264347?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzIwMzUwNDc5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

管理员admin功能：添加账号 维护账号 权限管理

 ![img](https://img-blog.csdn.net/20180530172657930?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzIwMzUwNDc5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

 

# 三．**禅道基本使用流程**

禅道管理软件中，核心的三种角色：产品、研发和测试，这三者之间通过需求进行协作，实现了研发管理中的三权分立。其中产品经理整理需求，研发团队实现任务，测试团队则保障质量，其三者的关系如下图：

 ![img](https://img-blog.csdn.net/2018053017271016?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzIwMzUwNDc5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

**基本流程如下：**

\1. 产品经理创建产品

\2. 产品经理在产品下创建需求

\3. 项目经理创建项目

\4. 项目经理确定项目要做的需求和任务

\5. 项目经理分解任务，指派到研发人员。

\6. 测试人员测试，提交bug。

 

# 四．**产品管理功能**

禅道中的需求依附在产品下，新增产品以后才可以新增需求

然后在新增的产品下提需求和计划，可将产品分解为子模块A、模块B、模块C...

在提需求时针对该需求选择所属模块：

 ![img](https://img-blog.csdn.net/20180530172732875?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzIwMzUwNDc5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

 ![img](https://img-blog.csdn.net/20180530172747203?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzIwMzUwNDc5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

 

禅道专门提供了需求的变更流程。凡是对需求标题、描述、验证标准和附件的修改，都应该走变更流程。

可以查看需求变更之前的变化：

 ![img](https://img-blog.csdn.net/20180530172803782?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzIwMzUwNDc5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

产品人员在动态一栏中可以看到该产品的全部变更过程：

 ![img](https://img-blog.csdn.net/20180530172816212?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzIwMzUwNDc5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

由提需求时指定的评审人员评审需求，给出评审结果

 ![img](https://img-blog.csdn.net/2018053017282920?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzIwMzUwNDc5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

评审人员确认需求通过后，需求状态改为激活，否则为草稿：

 ![img](https://img-blog.csdn.net/20180530172839210?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzIwMzUwNDc5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

产品的需求可以导出文件或生成报表

![img](https://img-blog.csdn.net/20180530172850559?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzIwMzUwNDc5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70) 

新增产品-->提需求-->审核通过

新增产品-->提需求-->审核不通过-->变更需求

# 五．**项目功能管理**

\1. 项目经理进入项目视图，添加项目

 ![img](https://img-blog.csdn.net/20180530172907210?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzIwMzUwNDc5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

项目关联产品，即可选择关联该产品对应的某些需求

![img](https://img-blog.csdn.net/20180530172920115?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzIwMzUwNDc5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

再为关联的需求分解任务，指派给某个人

 ![img](https://img-blog.csdn.net/20180530172934519?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzIwMzUwNDc5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

\2. 保存项目时，设置团队

![img](https://img-blog.csdn.net/20180530172944904?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzIwMzUwNDc5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70) 

需要选择是哪些成员可以参与到这个项目中，同时需要设置这个成员在本项目中的角色。

 ![img](https://img-blog.csdn.net/20180530172955288?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzIwMzUwNDc5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

\3. 在已建立好的项目下创建任务，将任务或关联的需求分解指派给项目组成员***\*（任务类型务必准确选择）\****

 ![img](https://img-blog.csdn.net/20180530173008138?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzIwMzUwNDc5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70) 

\4. 项目成员登录时，即可查看到分配给他的任务，成员只需要更新任务状态即可

 ![img](https://img-blog.csdn.net/20180530173021906?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzIwMzUwNDc5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

可为项目关联的产品创建不同版本，并分别提交测试（提交源代码或附件）：

![img](https://img-blog.csdn.net/20180530173030253?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzIwMzUwNDc5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70) 

可以按各种属性查看到项目的状态及完成进度（下图为按任务类型查看）：

![img](https://img-blog.csdn.net/2018053017304861?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzIwMzUwNDc5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70) 

成员可按照不同属性查看项目中任务状态：

 ![img](https://img-blog.csdn.net/20180530173104696?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzIwMzUwNDc5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

添加项目-->关联产品-->关联需求-->设置团队-->分解任务到团队成员-->成员修改状态

添加项目-->建任务-->设置团队-->分解任务到团队成员-->成员修改状态

# 六．**Bug\**管理\****

禅道里面设计的理念是bug主要附属在产品概念下面，有对应产品以后才可以开始提bug。默认Bug的严重程度分为四级，优先级分为五级（管理员可进行自定义）。

![img](https://img-blog.csdn.net/20180530173117482?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzIwMzUwNDc5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

***\*禅道里面缺陷处理的基本流程是：测试提交\**bug => \**开发解决\**\**bug =>\** \**测试验证\**\**bug =>\** \**测试关闭\**\**bu\**g；**

***\*如果\**bug\**验证没有通过，可以激活：测试提交\**\**bug =>\** \**开发解决\**\**bug =>\** \**测试验证\**\**bug =>\** \**测试激活\**\**bug =>\** \**开发解决\**\**bug =>\** \**测试验证\** \**=>\** \**测试关闭。\****

 

在创建bug的时候，必填的字段是：影响版本，bug标题，重现步骤，所属模块。

创建bug的时候，可以直接指派给某一个研发人员去处理，他可以来验证解决这个bug。

 ![img](https://img-blog.csdn.net/2018053017313099?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzIwMzUwNDc5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

 ![img](https://img-blog.csdn.net/20180530173140131?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzIwMzUwNDc5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

当研发人员解决了bug之后，bug会重新指派到bug的创建者头上。这时候测试人员可以来验证这个bug是否已经修复。如果验证通过，则可以关闭该bug。

新增测试用例：

 ![img](https://img-blog.csdn.net/20180530173153744?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzIwMzUwNDc5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

![img](https://img-blog.csdn.net/20180530173209123?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzIwMzUwNDc5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

B：是Bug的缩写，指该用例产生的Bug数。

R：是指该用例执行的结果数。

S：是指该用例的步骤数。

产品版本分为待测版本和已测版本，可分别关联测试用例：

 ![img](https://img-blog.csdn.net/20180530173222399?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzIwMzUwNDc5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

测试用例运行失败可以直接保存为bug，指派给某研发人员进行调试。测试部分的用例和bug都可以自动导出为文档。

# 七．**文档管理**

模板项目中有文档分类的模板，添加文档时可以此为参考（创建文档时不要忘记选择所属分类）

![img](https://img-blog.csdn.net/20180530173241698?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3NpbmF0XzIwMzUwNDc5/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70) 

 

 

 

 

 