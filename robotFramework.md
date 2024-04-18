# RobotFramework自动化测试解决方案

<br />
<br />

#### 序：

<br />

目前测试圈自动化测试非常流行，笔者也接触过很多如：selenium、appium、requests、gauge、robotframework及自己搭建测试框架，其中selenium、appium、requests严格意义上说不算是框架，只能算的上是工具，gauge、robotframework算是比较完整的测试框架
两者相比计较而言，gauge框架可能对开发水平要求更高且维护性不够好，经过研究是使用探索，发现robotframework灵活、强大、扩展性好，后续对其展开深入的探讨和研究，以便形成完整的自动化解决方案

<br />


**将从以下各个部分分别进行阐述：**

<br />

* 第一部分：基于ride入门RF

* 第二部分：使用VScode编写脚本

* 第三部分：RF基本整体认识

* 第四部分：RF框架进阶

* 第五部分：如何编写好的RF的测试用例风格

* 第六部分：RF基础库

* 第七部分：RF自定义库的开发

* 第八部分：使用RF基于Selenium2Library库进行web自动化测试

* 第九部分：使用RF基于RequestsLibrary库进行接口自动化测试

* 第十部分：使用RF基于AppiumLibrary库进行手机APP自动化测试

* 第十一部分：使用RF基于AutoItLibrary库进行Windows GUI(图形用户界面)自动化测试

* 第十二部分：RF中使用DatabaseLibrary库

* 第十三部分：使用RF基于Rammbock等库进行socket协议接口自动化测试

* 第十四部分：Robotframework+Jenkins持续集成

* 第十五部分：RF报告可视化


<br />
<br />


##第一部分：基于ride入门RF
<br />
####说明：
* 由于python3版本的ride不稳定，所以此处就拿python2版本进行介绍，工作中还是建议使用python3版本的robotframework，至于为什么在此就不多介绍了，百度吧少年

<br />

####具体步骤可以分为以下几个部分：

* pytihon安装
    * 进入官网下载python27版本，此处使用的是：python-2.7.14.amd64
    * 配置环境变量：C:\Python27；C:\Python27\Scripts

        ![python环境搭建成功](./images/Part_01/python环境搭建成功.png) 
        <!-- <img src="./images/Part_01/python环境搭建成功.png" width = 70% alt="python环境搭建成功" align=center /> -->
    * python环境安装成功

<br />

* 安装wxPython
    * wxPython为python的GUI：版本号为：wxPython2.8-win32-unicode-2.8.12.1-py27

<br />

* 安装pip
    * 命令：python install -U pip
    * 可以使用命令：pip -V  来检查时候安装成功
        ![pip包管理工具安装成功](./images/Part_01/pip包管理工具安装成功.png)
        <!-- <img src="./images/Part_01/pip包管理工具安装成功.png" width = 70% alt="pip包管理工具安装成功" align=center /> -->

   * pip安装成功

<br />

* 安装robotframework
    * 命令：pip install robotframework

<br />

* 安装robot framework-ride
    * 命令：pip install robot framework-ride

<br />

* 查看是否安装成功
    * 命令：pip list      (pip list 查看安装包)
        ![通过pip查看安装包](./images/Part_01/通过pip查看安装包.png)
        <!-- <img src="./images/Part_01/通过pip查看安装包.png" width = 70% alt="通过pip查看安装包" align=center /> -->

<br />

* 启动robotframework-ride
    * 前提：已配置好python的环境变量
    * 进入cmd命令框，输入：ride.py,正确启动ride如下：
        ![robotframework-ride界面](./images/Part_01/robotframework-ride界面.png)
        <!-- <img src="./images/Part_01/robotframework-ride界面.png" width = 70% alt="robotframework-ride界面" align=center /> -->
    * robotframework-ride安装成功

<br />

* 新建project
    * 起个项目名称：Frist_test
    * 选择好自己创建的项目路径
        ![新建project](./images/Part_01/新建project.png)
        <!-- <img src="./images/Part_01/新建project.png" width = 70% alt="新建project" align=center /> -->
<br />

* 紧接着创建测试套件:![创建测试套件](./images/Part_01/创建测试套件.png)
    <!-- <img src="./images/Part_01/创建测试套件.png" width = 70% alt="创建测试套件" align=center /> -->


<br />

* 在测试套件上创建案例
    * 用例内容：打印“holle Python!!”
        ![创建测试用例](./images/Part_01/创建测试用例.png)
        <!-- <img src="./images/Part_01/创建测试用例.png" width = 70% alt="创建测试用例" align=center /> -->
    * 编写用例内容

* 执行及查看用例执行结果
    ![运行测试用例](./images/Part_01/运行测试用例.png)
    <!-- <img src="./images/Part_01/运行测试用例.png" width = 70% alt="运行测试用例" align=center /> -->

    * 运行用例

<br />

* 在浏览器中查看测试报告
    * 点击查看测试报告按钮

        ![在浏览器中查看测试报告](./images/Part_01/在浏览器中查看测试报告.png)
        <!-- <img src="./images/Part_01/在浏览器中查看测试报告.png" width = 70% alt="在浏览器中查看测试报告" align=center /> -->
    * 查看报告

<br />

* 至此，基于ride的robotframework测试框架搭建完成，可以继续接下的脚本编写工作


<br />
<br />



##第二部分：使用VScode编写脚本

<br />

####根据官网支持说明
* 官方网站：http://robotframework.org/
* 支持IDE列表截图如下：
![IDE列表](./images/Part_02/IDE列表.png)
<!-- <img src="./images/Part_02/IDE列表.png" width = 70% alt="IDE列表" align=center /> -->

* 笔者推荐使用如下IDE：
    * Pycharm：[pycharm下robot framework环境搭建](https://www.jianshu.com/p/7185c4eb3ca1?from=timeline&isappinstalled=0)
    * Sublime：[使用 Sublime Text 3 开发 Robot Framework](https://www.jianshu.com/p/07ae62d2c63f)

<br />

#### 本文主要说明如何通过最近流行的编辑器VScode来编写robotframework脚本
* VScode的安装配置和使用

    * 官网：https://code.visualstudio.com/

    * 一键下载安装，此过程省略

        ![VScode下载页](./images/Part_02/VScode下载页.png)
        <!-- <img src="./images/Part_02/VScode下载页.png" width = 70% alt="VScode下载页" align=center /> -->

    * 安装成功后打开VScoder如下图：

    * 至于怎么汉化，那太简单了，再此就不说了，百度下就知道
        ![VScode首页](./images/Part_02/VScode首页.png)
        <!-- <img src="./images/Part_02/VScode首页.png" width = 70% alt="VScode首页" align=center /> -->

    * 由于robotframework是居于python语言的，所以我们要对VScode进行一些列插件配置

<br />

* 安装python插件
    * 通过1,2,3步安装后，重启VScode生效
        ![安装VScode的python插件](./images/Part_02/安装VScode的python插件.png)
        <!-- <img src="./images/Part_02/安装VScode的python插件.png" width = 70% alt="安装VScode的python插件" align=center /> -->

<br />

* 安装robot插件

    * 同样按照上面插件，安装robot相关插件重启生效
        ![安装VScode的robot插件](./images/Part_02/安装VScode的robot插件.png)
        <!-- <img src="./images/Part_02/安装VScode的robot插件.png" width = 70% alt="安装VScode的robot插件" align=center /> -->

* 至此，我们VScode上的一些列配置就完成了

<br />

* 为了脚本开发的顺利进行，我们需要创建本地项目，配置过城如下：

    * 安装python虚拟环境工具virtualenv

    ```
    命令：pip3 install virtualenv 或 pip install virtualenv
    ```
    
    * 通过virtualenv创建项目独立的python虚拟环境

        * 创建工作文件夹
        * cmd进入此目录（此处笔者建议使用cmder参考[如何使用cmder](https://www.jianshu.com/p/d554d67da555)）
        * 创建虚拟环境：
            * 命令：virtualenv --no-site-packages .venv
            * 此时会在文件夹下生成一个.venv的文件夹，这个就是我们独立环境
        * 启动虚拟python环境
            * 命令：.\.venv\Scripts\activate.bat

            ![启动python虚拟环境](./images/Part_02/启动python虚拟环境.png)
            <!-- <img src="./images/Part_02/启动python虚拟环境.png" width = 70% alt="启动python虚拟环境" align=center /> -->


        * 通过VScode打开该项目
            * 命令：code .
            * 完成截图如下：
            ![打开VScode](./images/Part_02/打开VScode.png)
            <!-- <img src="./images/Part_02/打开VScode.png" width = 70% alt="打开VScode" align=center /> -->

<br />

* 此时我们可以开始编写python和robotframework脚本了
    ![脚本编辑](./images/Part_02/脚本编辑.png)
    <!-- <img src="./images/Part_02/脚本编辑.png" width = 70% alt="脚本编辑" align=center /> -->

<br />

* 运行脚本

    * 在VScode终端，cd进入你的 文件目录

        ![进入脚本所在目录](./images/Part_02/进入脚本所在目录.png)
        <!-- <img src="./images/Part_02/进入脚本所在目录.png" width = 70% alt="进入脚本所在目录" align=center /> -->



    * 执行命令运行robotframework脚本

        * 命令：robot xxxx.robot

        ![运行脚本命令](./images/Part_02/运行脚本命令.png)
        <!-- <img src="./images/Part_02/运行脚本命令.png" width = 70% alt="运行脚本命令" align=center /> -->

    * 执行结果

        ![执行结果](./images/Part_02/执行结果.png)
        <!-- <img src="./images/Part_02/执行结果.png" width = 70% alt="执行结果" align=center /> -->


    * 查看报告

        * 复制结果的Report地址到浏览器查看

        ![测试报告](./images/Part_02/测试报告.png)
        <!-- <img src="./images/Part_02/测试报告.png" width = 70% alt="测试报告" align=center /> -->

<br />

* 到此有个问题怎，么去安装库呢，2种方法：

    * 通过VScode终端执行命令安装

    * 通过cmd进入虚拟环境安装

    命令：如要安装RequestsLibrary

    * pip install requests

    * pip install robotframework-requests

    然后可以导入包使用了

<br />

**PS：此时其实不光是配置了一个robot的环境，也同时配置完毕一个完成的python的开发环境，为以后自己封装robot自定义库做好了准备**


<br />
<br />



## 第三部分：RF基本整体认识

<br />

#### robotframework支持的文件格式
```
    HTML
    TSV
    Plain TEXT
    reStructuredText
```

<br />

#### 后文将以  Plain TEXT格式，以“空格”分割，以“.robot”为文件后缀的方式来进行相关说明

<br />

##### robotframework目录文件结构

* robotframework是以project为单位进行管理的

* 一个project可以包含多个Test Suite

* 一个Test Suite可以包含多个测试用例

* 一个Test Suite有四部分组成：Settings、Variables、Test Cases、Keywords

<br />

##### 如何去执行这些脚本：

* 执行整个项目所有用例,pybot 项目路径，例如：

```
    pybot D:\robot
```

* 执行某个suite用例，pybot suite路径，例如：

```
    pybot D:\robot\testsuit.txt
```

* 执行某个测试用例，pybot –测试用例名 in 该测试用例所在suite，例如

```
    pybot --testcase1_login in D:\robot\testsuit.txt
```

* 将测试结果输出到固定路径，pybot –outputdir 报告路径 用例路径，例如：

```
    pybot --ouputdir D:\ropot D:robot\testsuit.txt
```
    
* 执行某个tag的测试用例，pybot –include [tag name] [项目路径]，例如：

```
    pybot --include nomal D:\robot
```

<br />

##### 查看报告文件

* 用例执行完毕后会生成三个文件分别是：log.html、output.xml、report.html
    ![报告截图](./images/Part_03/报告截图.png)
    * output.xml：记录的测试结果是XML文件，根据特定的需要可以编写脚本读取XML文件并生成特定的测试报告

    * log.html：会记录Robotframework运行的每一步操作，主要用于编写测试脚本的过程查看

    * report,html：为测试报告，整理性的展示测试用例的运行情况

<br />  

##### 

##### 总体结果及关键字说明,整理结构如下：

```
*** Settings ***
Documentation           这个是当前Test Suite说明文字
Library                 当前Test Suite需要使用的库
Resource                当前Test Suite需要加载使用的资源，可能是参数也可能是用例文件
Metadata                定义元数据
Variables               引用变量文件
Suite Setup             Test Suite执行前的动作
Suite Teardown          Test Suite执行后的动作
Test Setup              Test Case执行前的动作
Test Teardown           Test Case执行后的动作
Force Tags              Test Suite下的所有测试用例都会被打上这个tag
Default Tags            Test Suite的用例如果没有打上tag，就会用这个默认tag，如果打了tag，就会用自己的tag
Test Timeout            设置每一个测试用例的超时时间，只要超过这个时间就会失败，并停止案例运行
...                     这是防止某些情况导致案例一直卡住不动，也不停止也不是失败
Test Template           数据驱动模板（很有用的一个参数）


*** Variables ***
${SCALAR_VARS}          创建scalar参数
@{LIST_VARS}            创建list参数
&{DICT_VARS}            a=创建dictionary参数


*** Test Cases ***
Test_01
    [Documentation]     测试用例说明……
    [Template]          数据驱动模板，每条用例只有一个模板
    [Tags]              测试用例标签
    [Setup]             测试用例执行前的动作
    [Teardown]          测试用例执行后的动作
    [Timeout]           测试用例的超时时间
    My Keyword One  

Test_02
    [Documentation]     。。。
    [Template]          。。。
    [Tags]              。。。
    [Setup]             。。。
    [Teardown]          。。。
    [Timeout]           。。。
    My Keyword Two


*** Keywords ***
My Keyword One
    [Documentation]     关键字描述
    [Arguments]         自定义参数设置
    [Return]            将返回值抛出
    [Timeout]           关键字流程执行超时时间
    [Tags]              标签
    [Teardown]          关键字流程结束动作
    log                 ${SCALAR_VARS}
    log Mang            @{LIST_VARS}
    log                 ${DICT_VARS}

My Keyword Two
    log                 ${SCALAR_VARS}
    log Mang            @{LIST_VARS}
    log                 ${DICT_VARS}

```   

<br />


#####下面是几个简单的案例：

 * practice_setup_and_teardown.robot
```
    *** Settings ***
    Documentation     test
    Suite Setup       suitestart
    Suite Teardown    suitestop
    Test Setup        testsetup
    Test Teardown     teststop

    *** Variables ***
    ${a}              hello world 1
    ${b}              hello world 2

    *** Test Cases ***
    testcase1
        [Documentation]    testcase1
        log    ${a}
    testcase2
        log    ${b}

    *** Keywords ***
    suitestart
        Log    suitstart
    suitestop
        Log    suitstop
    testsetup
        Log    teststart
    teststop
        Log    teststop

```

* practice_scalar.robot

```
    *** Settings ***
    Documentation       RobotFramework脚本的scalar标量练习
    Force Tags          robot-3.0
    Default Tags        owner-damao

    *** Variables ***
    # 创建scalar变量      
    ${NAME}             Robot Framework
    ${VERSION}=         3.0
    ${ROBOT}            ${NAME}  ${VERSION}
    ${NULL_VAR}         # 空字符串被赋值给了${NULL_VAR}
    ${EXAMPLE}          This value is joined together with a space
    ...                 1122333333333333333333333333333333
    ${LONG_WORDS}       1111111111111111

    # 创建列表变量

    @{NAMES}        Matti       Teppo
    @{NAMES2}       @{NAMES}    Seppo
    @{NOTHING}
    @{MANY}         one         two      three      four
    ...             five        six      seven

    # 创建字典变量
    &{USER 1}       name=Matti    address=xxx         phone=123
    &{USER 2}       name=Teppo    address=yyy         phone=456
    # &{MANY}         first=1       second=${2}         ${3}=thirds
    &{EVEN MORE}    first=override      empty=
    ...             =empty        key\=here=value


    *** Test Cases ***
    测试打印scalar变量
        [Documentation]     打印scalar变量
        To Test Scalar


    *** Keywords ***
    [Documentation]     创建关键字
    To Test Scalar
        [Documentation]     打印标量
        log  ${NAME}
        log  ${ROBOT}
        log  ${NULL_VAR}
        log  ${EXAMPLE}
        log  ${LONG_WORDS}
    

```
* practice_List.robot
```
    *** Settings ***
    Documentation       RobotFramework脚本"列表"参数的练习
    Force Tags          robot-3.0
    Default Tags        owner-damao

    *** Variables ***
    @{list_data}        1    2    3    4    5      
    @{list_data2}       a    b    c    d    e    f    
    ...                 q    w    e                     # 列表元素太长时使用... 分割

    *** Test Cases ***
    test_01
        [Documentation]     打印列表数据
        Print List Variables

    test_02
        [Documentation]     获取列表的长度
        Get List Length

    *** Keywords ***
    Print List Variables
        [Documentation]     打印列表数据
        log Many    @{list_data}
        log     @{list_data}[2]
        log Many    @{list_data2}  # 打印列表元素需要使用到log Many
        log     @{list_data2}[3]

    Get List Length
        [Documentation]     获取列表的长度
        ${length}    BuiltIn.Get Length    ${list_data2}   # 在获取列表的长度时需要注意使用${列表参数}
        log    ${length}

```
* practice_dict.robot
```
    *** Settings ***
    Documentation       RobotFramework脚本“字典”参数的练习
    Force Tags          robot-3.0
    Default Tags        owner-damao


    *** Variables ***
    &{dict_data}        a=b    e=w   y=1    asd=123
    &{dict_data1}       a=1    b=2    c=3    d=4
    ...                 r=7    u=90

    *** Keywords ***
    Print Dictionary Data
        [Documentation]    打印字典数据
        log    ${dict_data}
        log    &{dict_data}[a]
        log Many   &{dict_data}[a]    &{dict_data1}[u]
        log    ${dict_data1}


    *** Test Cases ***
    Test_01
        [Documentation]    测试打印字典数据
        Print Dictionary Data


```

<br />
<br />

##第四部分：RF框架进阶 

<br />

在上一部分我们熟悉了RobotFramework的整体结构，以及各个结构中的组成部分和说明，并且熟悉了一些简单的案例。掌握了第三部分内容可以说编写简单入门RF脚本已经不是问题。但是想要灵活的编写和使用RF脚本还是有所欠缺的，所以本章较少三个重要的帮助更灵活方便的使用RobotFramework：Resource ,Variables ,Template
 

* Resource： 往往在真正的项目中，由于关键字很多及相互调用时的不方便。就会使用Resource，他能对关键字进行统一整合存放，使用时只需要导入相关关键字资源，即可使用。
* Variables： 因为支持py文件，所以可以有效且方便的解决参数化的问题，非常有效。

* Template： 测试模板使得更关注的是用例的本身

<br />

#### 如下案例帮助理解：pratice_resource_and_template.robot文件

<br />

```
    *** Settings ***
    Documentation                   练习resouse及template关键字
    ...                             template关键字，对每一个测试用例，或者一个测试文件中的所有用例
    ...                             重复执行同一个关键字多次（使用不同数据），也可以只针对测试用例，或者每个测试文件只执行一次
    ...                             模板关键字可以接受普通位置的参数、命名参数
    ...                             关键字名中可以使用参数，不可以使用变量定义模板关键字
    ...                             用例中的[Temlate]会覆盖Settingz中的Temlate设置
    Force Tags                      robot-1.1         
    Default Tags                    owner-damao
    Resource                        ../VScode_Spider/RobotFramework/Keywords_file.robot    # 此处因为关键字文件和用例文件在同一个目录，所以可以碎略前面的目录部分
    Variables                       Variables_file.py     # 同上，在在同一个目录下，可以省略文件前面的路径


    *** Variables ***
    ${data1}                        1234
    ${data2}                        qwer
    ${data3}                        @#$%
    ${SQL}                          """select * from tsm_app_channel where status=1 limit 5;"""


    *** Test Cases ***
    test_01
        [Documentation]             测试用例一
        [Tags]                      test 1.1
        Test Keyword    ${data1}

    test_02
        [Documentation]             测试用例二
        [Tags]                      test 1.1
        [Template]    Test Keyword      # 避免多次编写关键字，只需要编写对应的参数
        ${data2}
        # ${data4}                        # ${data4} 为不存在参数变量，其会测试失败，但不影响其他参数的测试结果
        ${data3}

    test_03
        [Documentation]             加载Resource文件中的关键字资源
        [Tags]                      test 1.1
        [Template]    Print Something         # 该关键字为Resource加载过来的关键字资源，此处可直接使用
        我爱你中国！！！
        ${VARIABLE}

    test_04
        [Documentation]             测试从变量文件中获取变量
        [Tags]                      test 1.1
        [Template]    Print Something
        ${FOODS}
        ${FOODSNUM}
        ${INTEGER}
        ${MAX_NUB}
        ${INT_NUB}
        ${NOW_TIME}
        ${RDM_NUB1}
        ${RDM_NUB2}
        ${RDM_NUB3}
        ${add(1, 9)}
        ${DataDriven().multiplication(2, 7)}
        ${DataDriven().SCALAR_VAR}
        ${DataDriven().TVAR}
        ${DataDriven().TVAR[0]}
        ${DataDriven().TTVAR}
        ${DataDriven().TTVAR['a']}
        ${get_datavase_data(${SQL}, 2)}


    *** Keywords ***
    Test Keyword
        [Documentation]             测试关键字
        [Arguments]    ${var}
        log    ${var}


```
* Keywords_file.robot文件

```

    *** Keywords ***
    Print Something
        [Documentation]
        [Arguments]    ${qqq}
        log    ${qqq}

```

* Variables_file.py文件


```

        """创建是Scalar类型的variable"""

        VARIABLE = "An example string" 
        INTEGER =  hash(42)
        STRINGS = ["one", "two", "kolme", "four"]


```

* 上面的Variables_file.py文件相对简单，在此对其进行扩展：

```
    import random
    import time
    import test_database


    """
    创建是Scalar类型的variable
    """
    VARIABLE = "An example string"
    STRINGS = ["one", "two", "kolme", "four"]


    """
    可以使用前缀LIST__或者DICT__来告诉RF框架数据类型
    """
    LIST__FOODS = ['苹果', '香蕉', '菠萝']
    DICT__FOODSNUM = {'苹果': 10, '香蕉': 99, '菠萝': 9}


    """ 
    使用系统对变量直接进行处理,即系统函数
    """
    INTEGER = abs(-42)  # 绝对值
    MAX_NUB = max(1, 3, -9, 10)  # 获取最大值
    INT_NUB = int('134')  # 转换类型


    """ 
    创建动态变量
    """
    NOW_TIME = time.strftime("%Y-%m-%d-%H-%M-%S", time.localtime(time.time()))  # 获取当前的系统时间
    RDM_NUB1 = random.random()  # 随机生成一个随机数
    RDM_NUB2 = random.randint(1, 100)  # 在1到100随机生成一个随机数
    RDM_NUB3 = random.sample([1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20], 7)  # 选择7个数


    """ 
    使用自定义函数创建变量 
    """
    def add(a, b):
        RESULT = a + b
        return RESULT


    """ 使用'类'创建变量 """
    class DataDriven(object):

        SCALAR_VAR = "NAMES"
        TVAR = [12, 123, 56]
        TTVAR = {'a': 1, 'b': 2}

        def multiplication(self, v1, v2):
            RES_var = v1 * v2
            return RES_var


    """ 通过数据库获取变量 """
    def get_datavase_data(SQL, line):
        data = test_database.DataOfDdatabase(
                host='xx.xx.xx.xx',
                user='xxxx',
                passwd='xxxx',
                db_name='xxxx',
                port=3306,
                charset='utf8',
            ).operat_database(SQL, line)
        # print(data)
        return data



```
* python获取数据库数据封装（简单封装，后续还需要进一步优化）

```
    import pymysql.cursors


    class DataOfDdatabase(object):
        def __init__(self, host, user, passwd, db_name, port, charset):
            self.host = host
            self.user = user
            self.passwd = passwd
            self.db_name = db_name
            self.port = port
            self.charset = charset

        def operat_database(self, SQL, line):
            connect = pymysql.Connect(
                host=self.host,
                user=self.user,
                passwd=self.passwd,
                db=self.db_name,
                port=self.port,
                charset=self.charset)
            if connect.server_status == 0:
                print("Database connected !")
                cursor = connect.cursor()
                cursor.execute(SQL)  # 执行SQL语句
                data = cursor.fetchmany(line)  # 获取前2行的数据
                print(f"你获取的数据库数据为：{data}")
                # 关闭数据库连接
                cursor.close()
                connect.close()
                return data
            else:
                print("Database connection failed !")
            


    if __name__ == "__main__":
        SQL = """select * from tsm_app_channel where status=1 limit 5;"""
        DataOfDdatabase(
            host='xx.xx.xx.xx',
            user='xxxx',
            passwd='xxxx',
            db_name='xxxx',
            port=3306,
            charset='utf8',).operat_database(SQL, 2)
```



<br />
<br />




## 第五部分：如何编写好的RF的测试用例
<br />
参考[作者：Andreas Ebbert-Karroum](https://blog.codecentric.de/en/2010/07/how-to-structure-a-scalable-and-maintainable-acceptance-test-suite/)

<br />

#### 命名
<br />
##### 测试套件的命名
* 套件名称应该尽可能的描述这个套件的用途
* 如果必要的话，顶层套件的命名可以在命令行中使用--name选项来修改
* 名称可以相对长一些，但最好不要超过40字
* Robotframework 的套件名称是直接从文件/目录的名字转换来的
    * 文件的后缀名被去掉
    * 而且下换线会被替换成空格
    * 比如你用到的单词都是小写的，那么开头字母会被转换成大写
* 如：

```

login_tests.robot -> Login Tests

IP_v4_and_v6 -> IP v4 and v6

```

<br />

##### 测试用例的命名
* 测试用例的名称应该与测试套件的描述相似
* 如果一个套件中包含很多个相似的测试用例，而且测试套件本身已经很好的命名了,那么用例的名称可以简单一些
* 测试用例的名称应该恰当好处的b表达你要做些什么
* 好的测试用例名称

```
    *** Test Cases ***
    Empty Password
    Empty Username
    Empty Username And Password
    Invalid Username
    Invalid Password
    Invalid Username And Password
```

* 不好的测试用例名称

```
    *** Test Cases ***
    Login With Empty Password Should Fail
    Login With Empty Username Should Fail
    Login With Empty Username And Password Should Fail
    Login With Invalid Username Should Fail
    Login With Invalid Password Should Fail
    Login With Invalid Username And Invalid Password Should Fail
```
<br />

##### 关键词命名
* 关键词命名也应该是清晰具体的
* 应该可以表达这个关键词干了什么，而不是他如何去做
* 关键词应该是非常不同的抽象层次(比如，「输入字符」或者「用户登录到系统」)
* 好的关键字命名
```
    *** Keywords ***
    Login With Valid Credentials
```
* 不好的关键字名称
```
    *** Keywords ***
    Input Valid Username And Valid Password And Click Login Button
```
<br />

##### 生成setup和分解teardown的命名
* 试着用名称m描述这个步骤完成了什么
    * 你可以使用一个已经存在的关键词
* 如果生成或分解包含了不相关的步骤,那么就可以接受抽象一点的名称
    * 在名称中列举步骤是一个重复化和维护的问题（比如：登入系统，添加用户，激活警报和检查平衡）
    * 或许要用到一些t通用一点的名称, 比如：「初始化系统」
* 每个用到这些用例的人都要明白这几条生成或者分解动作干了什么
* 好的生成setup和分解teardown命名
```
    *** Settings ***
    Suite Setup     Initialize System

    Good (if only used once):

    *** Settings ***
    Suite Setup     Run Keywords
    ...             Login To System    AND
    ...             Add User           AND
    ...             Activate Alarms    AND
    ...             Check Balance

```

* 不好的生成setup和分解teardown命名
```
    *** Settings ***
    Suite Setup     Login To System, Add User, Activate Alarms And Check Balance
```

<br />

#### 文档
<br />
##### 测试套件文档
* 通常把文档添加到包含测试用例的最底层套件中是一个不错的想法
* 高层的套件不需要那么频繁地文档化
* 文档应该包含必要的背景信息，比如为什么要创建这些测试用例，测试环境中需要注意的点等
* 文档内容不要只是简单地重复套件的名称
    * 如果不是真的有文档还不如不添加文档
* 文档的内容不要包含关于测试用例的太详细的信息
    * 测试用例本身就应该足够清楚易懂了
    * 重复的信息是一种浪费，而且也不容易维护
* 文档中可以添加一些详细内容链接
* 如果你需要在文档中添加一些比如（版本：1.0 或者 OS：Linux）这样的「名称-值」组的话，可以考虑使用测试套件 metadata

<br />

##### 测试用例文档
* 测试用例通常来说不需要文档
    * 套件名称和文档以及用例的名称已经提供了足够的背景信息
    * 测试用例的结构应该是不需要文档或者其他注释都足够清楚了的
* Tags通常比文档更灵活，还能提供更多的功能
* 当测试用例的文档是有用的时候，也不要担心而不去添加

<br />

##### 用户自定义关键词文档
* 如果这个关键词非常简单明了的话，不需要文档
    * 好的名称和明确的结构就足以说明一切了
* 用户自定义关键词文档的一个重要的用途是用来记录参数和返回值的信息
* 在 [RIDE](code.google.com/p/robotframework-ride/)(比如在关键词补全的地方)以及在资源文件中显示的文档是由[libdoc.py](code.google.com/p/robotframework/wiki/LibraryDocumentationTool) 生成的

<br />

#### 测试套件的结构
* 在套件中的用例相互相关的
    * 如果测试用例拥有同样的生成或者分解部分，那么他们应该是属于一个套件的
* 除非是数据驱动的，在一个套件中不要放10个以上的测试用例
* 测试用例应该是独立的
* 用生成和分解来初始化他们
* 有时候如果测试用例之间无法避免地相关联
    * 比如说，它可能是因为把所有的用例独立出来要化太多的时间在初始化上
    * 相关联的测试用例就那么几个（最多4到5个)
    * 下一个用例是用来验证上一个用例的结果的。（用${PREV TEST STATUS} 这个内建变量）

<br />    

#### 测试用例的结构
* 测试用例应该是易懂的
* 一个测试用例只测试一件事情
    * 当然，事情本身可大可小
* 选择一个合适的抽象层面
    * 一致地使用抽象水平（单一水平的抽象原则）
    * 只包含与测试相关的信息
* 用例可以分为l两种
    * 工作流程的测试用例
    * 数据驱动的测试用例

<br />    

##### 工作流程的测试用例
* 通常来说有以下这些部分：
    * 前置条件（可选，通常在生成部分）
    * 动作 （对被测系统执行一些动作）
    * 验证 （必须有一个验证的部分！）
    * 清理 （可选，通常在分解部分，以保证用例已经执行完毕）

* 关键词是用来描述这个用例做了什么
    * 用清晰的关键词名称和合适的抽象层次
    * 应该包含足够的信息使得手动执行可以启动
    * 应该从来不需要文档或者沟通来告诉你这个用例在做什么

* 不同的用例可以有不同的抽象层次
    *详细的功能测试是更精确的
    * 端到端的测试可以是一个很高的抽象层次
    * 一个测试用例应该只使用一种抽象层次

* 不同的风格
    * 对于底层的详细测试和集成测试用例来讲应该是更关注技术细节
    *「可执行定义」来扮演需求
    * 使用领域中的语言（术语？）
    * 所有人（包括顾客和产品负责人）都应该可以看明白

* 不复杂的逻辑
    * 不用 for 循环或者 if/else 判断结构。
    * 小心给变量赋值。
    * 测试用例不应该看起来像脚本一样难读

* 最多10步，越少越好
* 使用“普通”关键字驱动样式的示例:
```
    *** Test Cases ***
    Valid Login
    Open Browser To Login Page
    Input Username    demo
    Input Password    mode
    Submit Credentials
    Welcome Page Should Be Open
```
* 使用“gherkin”式的关键字驱动样式示例：
```
    *** Test Cases ***
    Valid Login
    Given browser is opened to login page
    When user "demo" logs in with password "mode"
    Then welcome page should be open
```

<br />

##### 数据驱动的测试用例
* 每个测试用例有一个高层次的关键词。
    * 不同的参数创建不同的测试。
    * 关键词通常包含了与同一个用例文件中工作流程测试用例中描述的流程类似的流程。

* 推荐使用测试模板功能。
    * 不需要多次地去重复关键词。
    * 在一个用例里去测试更容易去测试多种变化。

* 如果可能，推荐在列头部命名。
* 如果真的需要很多测试用例，考虑把他们做成依赖于外部的模型
* 样例一
```
        *** Settings ***
        Test Template         Login with invalid credentials should fail

        *** Test Cases ***    USERNAME             PASSWORD
        Invalid Username      invalid              ${VALID PASSWORD}
        Invalid Password      ${VALID USERNAME}    invalid
        Invalid Both          invalid              invalid
        Empty Username        ${EMPTY}             ${VALID PASSWORD}
        Empty Password        ${VALID USERNAME}    ${EMPTY}
        Empty Both            ${EMPTY}             ${EMPTY}

        *** Keywords ***
        Login with invalid credentials should fail
        [Arguments]    ${username}    ${password}
        Input Username    ${username}
        Input Password    ${password}
        Submit Credentials
        Error Page Should Be Open
```
* 样例二 
```
        *** Test Cases ***
        Invalid Password

        [Template] Login with invalid credentials should fail
        invalid ${VALID PASSWORD}
        ${VALID USER} invalid
        invalid whatever
        ${EMPTY} ${VALID PASSWORD}
        ${VALID USER} ${EMPTY}
        ${EMPTY} ${EMPTY}

        *** Keywords ***
        Login with invalid credentials should fail
        [Arguments]    ${username}    ${password}
        Input Username    ${username}
        Input Password    ${password}
        Submit Credentials
        Error Page Should Be Open
```

<br />

#### 用户定义关键字

<br />

* 应该容易让人理解
    * 和工作流程测试用例一样的标准
* 不同抽象层次
* 可以包含一些编程逻辑(for、if等)
    * 特别对于底层的关键字
    * 复杂的逻辑应该放到库里而不是用户自定义关键字里

<br />

#### 变量

<br />

* 封装长的或者复杂的值，从python文件获取变量
* 使用命令行传递信息，使用--variable
* 在关键词之间传递信息

<br />

##### 变量的命名

<br />

* 清楚，但不要太长
* 可以在变量表格里使用注释来说明
* 对每个使用场景保持一致
    * 小写的变量只能在当前用例或者关键字中可用
    * 全局变量和套件或用例级别的变量需要大写
    * 空格或者下划线都可以用来分割变量中的词
* 推荐在变量表格中也把设置成动态的变量也列出来
    * 用Set Global/Suite/Test variable内建关键词来命名变量
    * 变量的初始值应该可以解释真实的值应该是什么
* 例：
```
        *** Settings ***
        Suite Setup       Set Active User

        *** Variables ***
        # Default system address. Override when tested agains other instances.
        ${SERVER URL}     http://sre-12.example.com/
        ${USER}           Actual value set dynamically at suite setup

        *** Keywords ***
        Set Active User
            ${USER} =    Get Current User    ${SERVER URL}
            Set Suite Variable    ${USER}

```

<br />

##### 传递和返回值

<br />

* 通常的方式通过关键字来返回值,把他们赋给变量，然后传递给其他关键词的参数
    * 清楚易懂地遵循这个方法
    * 允许创建独立关键字，并促进重复使用
    * 看起来像编程

* 备选方案是使用Set Test Variable关键词
    * 不需要在测试用例层面上有什么编程风格
    * 要遵循越比较复杂，就越难重用关键词的原则

<br />

* 好的案例：
```
        *** Test Cases ***
        Withdraw From Account
            Withdraw From Account    $50
            Withdraw Should Have Succeeded

        *** Keywords ***
        Withdraw From Account
            [Arguments]    ${amount}
            ${STATUS} =    Withdraw From User Account    ${USER}    ${amount}
            Set Test Variable    ${STATUS}

        Withdraw Should Have Succeeded
            Should Be Equal    ${STATUS}   SUCCESS
```
* 不是很好的案例
```
        *** Test Cases ***
        Withdraw From Account
            ${status} =    Withdraw From Account    $50
            Withdraw Should Have Succeeded    ${status}

        *** Keywords ***
        Withdraw From Account
            [Arguments]    ${amount}
            ${status} =    Withdraw From User Account    ${USER}    ${amount}
            [Return]    ${status}

        Withdraw Should Have Succeeded
            [Arguments]    ${status}
            Should Be Equal     ${status}    SUCCESS
```

<br />

#### 避免使用sleeping

<br />

* sleeping是非常脆弱的
* 平均来说，安全的边界值会使得 Sleeping 很长时间
* 用包含了一定的动作触发的关键词来替代 Sleeping 
    * 关键词可以用 Wait Until… 来开头
    * 等待需要有一个超时的值
    * 可能的话用[内置的关键词](http://robotframework.org/robotframework/#standard-libraries)Wait Until Keyword Succeeds来包装其他关键词
* 有时候 Sleeping 是一种最简单的解决方式
    * 请总是小心使用
    * 不要在经常用到的自定义关键词或者其他关键词中用 Sleeping
* 在 Debugging 的时候 Sleeping 用来暂停测试执行还是很有用的
    * [DialogsLibrary](http://robotframework.org/robotframework/latest/libraries/Dialogs.html) 通常更适合用来干这个

<br />
<br />




## 第六部分：RF基础库

<br />

#### Robotframework官方支持库说明

<br />

**根据[Robotframework官网](http://robotframework.org/)可以看到：**

<br />

* 标准库支持
    ![标准库](./images/Part_06/标准库.png)

<br />

* 扩展库（第三方库）支持
    ![扩展库](./images/Part_06/扩展库.png)

<br />

* 其他库支持
    ![其他库](./images/Part_06/其他库.png)

<br />

#### RobotFramework之所以强大，是因为他支持自定义库的开发，后面一部分将单独介绍

<br />

#### 综上所述可以看出来，为满足我们日常的测试需求，可以使用如下库：

<br />

* web自动化测试：SeleniumLibrary，Selenium2Library，Selenium2Library for Java、watir-robot 等。
* Windows GUI 测试：AutoItLibrary。
* 移动测试：Android library、iOS library、AppiumLibrary 等。
* 数据库测试：Database Library (Java)、Database Library (Python)、MongoDB library 等。
* 文件对比测试：Diff Library。
* HTTP 测试：HTTP library (livetest)、HTTP library (Requests)等

<br />

#### 详细的内置库见：

<br />

* [官网](http://robotframework.org/robotframework/latest/libraries/BuiltIn.html#HTML%20error%20messages)：英文文档，若觉得吃力，可以使用下面翻译地址查看
* [翻译地址](https://blog.csdn.net/whackw/article/details/48804639)：建议详细熟悉关键字，这样在实际编写脚本时才能熟练使用

<br />

#### 一个例子说明几个常用关键字的使用

<br />

```
*** Settings***
Documentation                   一个例子说明RF常用关键字的使用
Force Tags                      测试套件标签
Default Tags                    RF常用关键字
Suite Setup                     Suite Start
Suite Teardown                  Suite End
Library                         Screenshot

*** Variables ***
${START_EORD}                   测试开始
${END_WORD}                     测试结束

*** Test Cases ***
test_01
    [Documentation]             Robotframework中打印使用 “log”
    [Tags]                      test 1.0
    [Setup]                     Test Start
    log                         holle Robotframework
    [Teardown]                  Test Down

test_02
    [Documentation]             测试定义变量
    [Tags]                      test 1.0
    Set Variable         

test_03
    [Documentation]             测试连接多个信息
    [Tags]                      test 1.0
    Catenate variables

test_04
    [Documentation]             测试创建列表变量
    [Tags]                      test 1.0
    Create List Data

test_05
    [Documentation]             测试RF时间操作
    [Tags]                      test 1.0
    [Setup]                     Test Start
    Time Operation     
    [Teardown]                  Test Down
  
test_06
    [Documentation]             测试if关键字
    [Tags]                      test 1.0
    [Setup]                     Test Start
    IF Keyword
    [Teardown]                  Test Down

test_07    
    [Documentation]             测试FOR关键字
    [Tags]                      test 1.0
    [Setup]                     Test Start
    FOR Keyword
    [Teardown]                  Test Down

test_08
    [Documentation]             Evaluate关键字测试
    [Tags]                      test 1.0
    Evaluate Keyword



*** Keywords ***
Suite Start
    [Documentation]             开始运行测试套件
    log                         ${START_EORD}

Suite End
    [Documentation]             测试套件运行结束
    log                         ${END_WORD}

Test Start
    [Documentation]             测试开始前执行的动作
    log                         测试开始前执行的动作

Test Down
    [Documentation]             测试用例执行完毕后执行的动作
    log                         测试用例执行完毕后执行的动作

Set Variable
    [Documentation]             FR定义变量
    ${a}    BuiltIn.Set Variable    1234
    log    ${a}

Catenate variables
    [Documentation]             连接多个信息
    ${content1}    Catenate     Holle    World!!!
    log    ${content1}
    ${content2}    Catenate    SEPARATOR=^^^    你好    中国
    log    ${content2}

Create List Data
    [Documentation]             创建列表变量
    ${list_data1}    Create List    1    2    3    4
    log    ${list_data1}
    @{list_data2}    Create List    a    b    c    d
    BuiltIn.log Many    @{list_data2}

Time Operation
    [Documentation]             RF时间操作
    ${time}    Get Time                     # 获取当前时间，年-月-日 时:分:秒
    log    ${time}
    ${secs}    Get Time    epoch            # 获取当前时间的描述
    log    ${secs}
    ${year}    Get Time    return year      # 获取当前的年份
    log    ${year}
    ${yyyy}    ${mm}    ${dd}=    Get Time    year,month,day    # 获得年月日的分别变量值
    log    ${yyyy}
    log    ${mm}    
    log    ${dd}
    @{time}    Get Time    year month day hour min secs       # 获得年月日时分秒的列表参数
    BuiltIn.Log Many    @{time}
    ${s}    Get Time    seconds     # 获取秒数
    log    ${s}
    ${y}    Get Time    year    # 获取年数
    log     ${y}
    log     等到时间3秒
    Sleep    3

IF Keyword
    [Documentation]             if关键字  
    ${age}    BuiltIn.Set Variable    10   
    run Keyword if    ${age}>=90    log    老年人
    ...               ELSE IF    ${age}>=50    log    中年人 
    ...               ELSE IF    ${age}>=20    log    青年人
    ...               ELSE    log    小孩子

FOR Keyword
    [Documentation]             for关键字
    :FOR    ${i}    INRANGE    10        # 打印0-9的数
    \     log    ${i}
    :FOR    ${ii}    in range    1    11   # 打印1-10的数
    \        log    ${ii}
    :FOR    ${iii}    in range   1    11    2    # 答应1,3,5,7,9
    \        log    ${iii}
    @{my_list}    Create List    q    w    e    r    t    # 遍历列表
    :FOR    ${iiii}    in    @{my_list}
    \        log    ${iiii}
    @{abc}    Create List    1    2    3    4    # 循环中判断
    :FOR    ${f}    in    @{abc}
    \        Exit for loop if    '${f}'=='2'
    log    ${f}

Evaluate Keyword
    [Documentation]             强大的Evaluate关键字
    ${d}    Evaluate    int(2)
    log    ${d}
    ${len}    Evaluate    type(${d})
    log    ${len}    
    Take Screenshot    # 截屏
    ${dd}    Evaluate    random.randint(1, 10000)    random     # 格式为： 变量名  Evaluate(关键字)  函数   需要import的包（类型python导入包）
    log    ${dd}
    Evaluate    os.system('python3 C:/MYTEST/VScode_Spider/Test/test_格式化日期输出.py')    os


```

<br />
<br />



## 第七部分：RF自定义库的开发

<br />

前面说过RobotFramework之所以强大是在于它的扩展功能，下面介绍自定义库的开发和使用的过程

<br />

####需要注意的点如下：

<br />

* 包文件默认是放在对应python环境下的site-package下的，可能是真实的python环境，也可能是虚拟python环境，笔者目录如下：

```
C:\MYTEST\VScode_Spider\.venv\Lib\site-packages
```

* 注意包文件名最好是大写开头，如：



```
Library            DamaotestLibrary    WITH NAME    DL
```



* 在编辑__init__.py文件时，要注意导包的路径，建议使用相对路径，如：

```
from .damao_encapsulation_method import TestDemo
```
<br />

#### 注意上面几点剩下的就是写点python代码了，给个例子如下

<br />

* 包名称及文件截图如下：
    ![自定义包](./images/Part_07/自定义包.png)

* damao_encapsulation_method.py文件：

```
__author__ = 'damao'
__version__ = '0.1'

import time
import random
from datetime import datetime, date
import calendar


class TestDemo(object):

    def get_today_data(self):
        """
        获取当前的日期和时间
        | get_today_data   |         |
        """
        today = time.strftime("%Y-%m-%d %I:%M:%S %a", time.localtime(time.time()))
        print(f"当前的日期和时间是：{today}")
        return today
    
    def get_today_weekday(self):
        """
        获取今天星期几
        | get_today_weekday   |       |  
        """
        today = date.today()
        weekday = today.weekday()
        print(f"今天是：{weekday}")

    def get_year_calendar(self, year):
        """
        获取指定年份的日历
        | get_year_calendar   |  your year  |
        """
        year_calendar = calendar.calendar(year)
        print(f"{year}年的日历如下:\n{year_calendar}")

    def get_month_calendar(self, year, month):
        """
        获取指定年份指定月的日历
        | get_month_calendar  | year     |  month   |
        """
        month_calender = calendar.month(year, month)
        print(f"{year}年{month}月的日历如下：\n{month_calender}")
        return month_calender

    def get_some_random_nuber(self, list_number, how_many):
        """
        从给出的几个数中，随机获取你想要的几个数
        | get_some_random_nuber  | list_number  |   how_many   |
        """
        rdm_num = random.sample(list_number, how_many)
        print(f"你选的项为{rdm_num}")
        return rdm_num



if __name__ == "__main__":
    TestDemo().get_today_weekday()

```

<br />

* __init__.py文件：

```
#  Copyright (c) 2010 Franz Allan Valencia See
#
#  Licensed under the Apache License, Version 2.0 (the "License");
#  you may not use this file except in compliance with the License.
#  You may obtain a copy of the License at
#
#      http://www.apache.org/licenses/LICENSE-2.0
#
#  Unless required by applicable law or agreed to in writing, software
#  distributed under the License is distributed on an "AS IS" BASIS,
#  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
#  See the License for the specific language governing permissions and
#  limitations under the License.


from .damao_encapsulation_method import TestDemo

__author__ = 'damao'
__version__ = '0.1'


class DamaotestLibrary(TestDemo):

    """
    DamaotestLibrary库的说明

    """
    ROBOT_LIBRARY_SCOPE = 'GLOBAL'

```

<br />

* test_my_library.robot文件：

```
*** Settings ***
Library                     DamaotestLibrary    WITH NAME    DL
Library                     FakerLibrary
Variables                   Variables_file.py


*** Variables ***
&{my_year}    a=017    b=2222    c=3333 


*** Test Cases ***
test_01
    [Documentation]         测试2009年的日历
    [Template]              Get Tadoy Date
    ${my_want_year1}
    ${my_want_year2}

test_02
    [Tags]         测试获取当前的日期和时间
    Get Today Data

test_03
    [Tags]         测试获取今天星期几
    Get Today Weekday


*** Keywords ***
Get Tadoy Date
    [Documentation]         获取指定年份的日历
    [Arguments]    ${year}
    DL.get_year_calendar    ${year}

Get Today Data
    [Documentation]         获取当前的日期和时间
    DL.get_today_data

Get Today Weekday
    [Documentation]         获取今天星期几
    DL.get_today_weekday

```

<br />

* 运行结果如下：
    ![运行结果](./images/Part_07/运行结果.png)

<br />

#### 上面我们完成了自定义库的创建、导入和使用的过程

<br />
<br />



## 第八部分：使用RF基于Selenium2Library库进行web自动化测试

<br />

本部分将介绍如何使用RobotFramework进行web自动化测试。因为是基于Selenium2Library库的使用，接下来将进行深入的研究和学习

<br />
#### Selenium介绍

<br />

* Selenium 自动化测试工具，它主要是用于 Web 应用程序的自动化测试，但并不只局限于此，同时支持所有基于 web 的管理任务自动化


* Selenium特点：
    * 开源、免费
    * 多浏览器支持：FireFox、Chrome、IE、Opera
    * 多平台支持：linux 、windows、MAC
    * 多语言支持：java、Python、Ruby、php、C#、JavaScript
    * 对 web 页面有良好的支持
    * 简单（API 简单）、灵活（用开发语言驱动）
    * 支持分布式测试用例执行（Selenium Grid）


* Selenium 是支持多种开发语言的，对于不同的语言来说都有其对应的库。


* 对 Robot Framework 框 架 的 Selenium 库 有 两 个 ：
    * SeleniumLibrary 和 Selenium2Library 
    * SeleniumLibrary 是基于 Selenium1.0 开发的
    * Selenium2Library 是基于 Selenium2.0 开发的。在此我们直接使用 Selenium2Library

<br />

#### 安装Selenium2Library


* 两种方式
    * 直接下载安装包，本地安装
    * 直接通过pip安装


* 安装包下载地址：https://pypi.org/project/robotframework-selenium2library/


* 安装命令：
```
C:\robot\Robot framework-selenium2library-3.0.0>python3 setup.py install
```


* pip安装命令：
```
(.venv) λ pip install robotframework-selenium2library
```


* 导入Selenium2Library库
```
Library           Selenium2Library    WITH NAME    SL
```

<br />

#### 一个例子说明Selenium2Library的基本用法
```
*** Settings ***
Library                     Selenium2Library    WITH NAME    SL
Library                     Screenshot    WITH NAME    SH


*** Variables ***
${text}                     I love china 
${link}                     https://www.baidu.com 
${seach_text}               中国
${a}                        1
${b}                        2
${c}                        3


*** Keywords ***
百度搜索
    [Documentation]         打开浏览器关键字 
    [Arguments]             ${content}    ${title_word}         
    SL.Open Browser    ${link}    firefox
    SL.Maximize Browser Window
    SL.Input text    id=kw    ${content}
    SL.Click Button    id=su    
    Sleep    2
    ${title}    SL.Get Title
    Should Contain    ${title}    ${title_word}
    SH.Take Screenshot    # 效果截图
    SL.Close Browser


*** Test Cases ***
test_01
    [Documentation]         测试百度搜索：${seach_text}
    [Tags]                  test 1.1
    ${title_word_01}    Set Variable    中国_百度搜索
    百度搜索    ${seach_text}    ${title_word_01}

test_02
    [Documentation]         测试百度搜索：${a}
    [Tags]                  test 1.1
    ${title_word_02}    Set Variable    1_百度搜索
    百度搜索    ${a}    ${title_word_02}

test_03
    [Documentation]         测试百度搜索：${b}
    [Tags]                  test 1.1
    ${title_word_03}    Set Variable    2_百度搜索
    百度搜索    ${b}    ${title_word_03}

test_04
    [Documentation]         测试百度搜索：${c}
    [Tags]                  test 1.1
    ${title_word_04}    Set Variable    3_百度搜索
    百度搜索    ${c}    ${title_word_04}

```

* 运行结果如下：
    ![终端运行结果](./images/Part_08/终端运行结果.png)
    ![测试报告1](./images/Part_08/测试报告1.png)
    ![测试报告2](./images/Part_08/测试报告2.png)

<br />

#### Selenium2Library元素定位

<br />

* 前端工具，如：firebug
* id定位
* name定位
* xpath定位
* css定位


**参考[元素定位](https://www.jianshu.com/p/87e7ec22045d)，在此不进行细致描述**

<br />

#### Selenium2Library详细用法

<br />

一、浏览器驱动

<br />

* 通过不同的浏览器执行脚本
```
Open Browser    https://www.baidu.com    ff
```


* 浏览器对应的关键字   

    |浏览器|别名|    
    |- | :- |
    |FireFox|ff|
    |FireFox|firefox|
    |Internet Explorer| internetexplorer|
    |Internet Explorer| ie|
    |Google Chrome | googlechrome |
    |Google Chrome | gc |
    |Google Chrome | chrome|
    |Opera | opera|
    |PhantomJS | phantomjs|
    |HTMLUnit | htmlunit|
    |HTMLUnit with Javascipt support|htmlunitwithjs|
    |Android|android|
    |Iphone|iphone|
    |Safari|safari|


* 备注：
要想通过不同的浏览打开URL地址，一定要安装浏览器相对应的驱动。如chrome 的驱动：chromedriver.exe 等，浏览器默认为空时启动FireFox。

<br />

二、关闭浏览器

<br />

* 关闭浏览器：关闭当前的浏览器
```
Close Browser
```

* 关闭所有浏览器：关闭所有打开的浏览器和浏览器缓存重置
```
Close All Browsers
```

<br />

三、最大化浏览器

<br />

* 使当前打开的浏览器全屏
```
Maximize Browser Window
```

<br />


四、设置浏览器宽、高

<br />

* 以像素为单位，第一个参数1000表示宽度，第二个参数800表示高度
```
Get Window Size     1000    800
```

<br />

五、文本输入

<br />

* id=kw ：表示元素定位，定位文本输入框
```
Input Text    id=kw     我爱你中国
``` 

<br />

六、点击按钮

<br />

* id=su ：表示元素定位，定位点击的按钮
```
Click Button    id=su
```

<br />

七、点击元素

<br />

* Xpath=//* [@] ：表示元素定位，定位文本输入框
```
Click Element    Xpath=//* [@]    
```

<br />

八、注释

<br />

* 注释1：
```
Comment     注释说明文字
```
* 注释2：
```
# 注释说明文字
```
* 除了使用Comment 关键字进行注释外，Robot framework框架是基于python语言开发的，所以提供了python语言的注释“#”方式。

<br />

九、固定时间休眠

<br />

* Sleep表示执行到当前行固定休眠多长时间，以“秒”为单位
* 等待42秒
```
Sleep    42
```
* 等待1.5秒
```
Sleep    1.5
```
* 等待2分10秒
```
Sleep    2 minutes 10 seconds
```
<br />

十、等待元素出现在当前页面
```
Wait Until Page Contains Element     Xpath=//* [@]     3     若未找到时提示错误信息
```

<br />

十一、获取浏览器title


* 获得当前浏览器窗口的title 信息，这里只获取title 是没有意义的，我们通常会将获取的title 传递给一个变量，然后与预期结果进行比较。从而判断当前脚本执行成功
```
${title}    SL.Get Title
Should Contain    ${title}    ${title_word}
```
<br />

十二、获取文本信息


* Xpath=//* [@] ： 定位文本信息的元素
```
Get Text     Xpath=//* [@] 
```

<br />


十三、获取元素属性值


* id=kw@name ： id=kw 表示定位的元素。@nam 获取这个元素的name属性值
```
Get Element Attribute     id=kw@name    
```

<br />

十四、cookie处理


* 获得当前浏览器的所有cookie
```
get cookies   
```
* Key_name ： key_name 表示一对cookie中key的name
```
get cookie value     key_name
```
* 删除key为name 的cookie信息
```
delete cookie     key_name
```
* 删除当前浏览器的所有cookie
```
delete all cookies
```
* 添加一对cooke （key：value）
```
add cookie      Key_name       Value_name
```

<br />


十五、表单嵌套


* Select Frame 进入表单，Xpath=//* [@] 表示定位要进入的表单。
* Unselect Frame 退出表单
```
Select Frame      Xpath=//* [@]
Unselect Frame
```

<br />


十六、下拉框选择


* Xpath=//* [@] 定位下拉框，Vlaue 选择下拉框里的属性值
```
Unselect From List By Value      Xpath=//* [@]      vlaue
```

<br />

#### Selenium2Library其它关键字
* 参考[Selenium2Library关键字](https://www.jianshu.com/p/8422f0a2b81a)，进行系统熟悉学习



<br />



<br />
<br />

## 第九部分：使用RF基于RequestsLibrary库进行接口自动化测试
## 第十部分：使用RF基于AppiumLibrary库进行手机APP自动化测试
## 第十一部分：使用RF基于AutoItLibrary库进行Windows GUI(图形用户界面)自动化测试
## 第十二部分：RF中使用DatabaseLibrary库
## 第十三部分：使用RF基于Rammbock等库进行socket协议接口自动化测试

<br />

## 第十四部分：Robotframework+Jenkins持续集成

<br />

### 一、Jenkins

<br />

#### jenkins官网
* [Jenkins官网](https://jenkins.io/)


#### 相关概念
* Jenkins概念：
    Jenkins是一个功能强大的应用程序，允许持续集成和持续交付项目，无论用的是什么平台。这是一个免费的源代码，可以处理任何类型的构建或持续集成。集成Jenkins可以用于一些测试和部署技术。Jenkins是一种软件允许持续集成
* Jenkins目的：
    * 持续、自动地构建/测试软件项目
    * 监控软件开放流程，快速问题定位及处理，提示开放效率


#### 特性
* 开源的java语言开发持续集成工具，支持CI，CD
* 易于安装部署配置：可通过yum安装,或下载war包以及通过docker容器等快速实现安装部署，可方便web界面配置管理
* 消息通知及测试报告：集成RSS/E-mail通过RSS发布构建结果或当构建完成时通过e-mail通知，生成JUnit/TestNG测试报告
* 分布式构建：支持Jenkins能够让多台计算机一起构建/测试
* 文件识别:Jenkins能够跟踪哪次构建生成哪些jar，哪次构建使用哪个版本的jar等
* 丰富的插件支持:支持扩展插件，你可以开发适合自己团队使用的工具，如git，svn，maven，docker等

#### 自动化测试的jenkins发布流程
* 测试用例设计 -> 测试人员开发测试脚本 -> jenkins自动执行测试脚本 -> 获取测试报告
    * 持续集成 （Continuous integration，简称CI）
    * 持续交付（Continuous delivery）
    * 持续部署（continuous deployment）

#### 安装部署
* 这个较简单，随便百度即可明白，
* 参考：[Jenkins 在windows下的安装与配置](https://www.cnblogs.com/xiaochengzi/p/6203002.html)

#### 启动jenkins
* 正常启动
```
java -jar jenkins.war
```
* 若端口号被占用(808为自己想要设置的端口号)
```
java -jar jenkins.war --httpPort=8081
```

<br />

### 二、 RobotFramework和Jenkins结合

<br />

#### 为什么要选择RF+Jenkins
* RobotFramework是目前最牛逼的自动化测试框架
* Jenkins是目前最牛逼的自动化构建软件
* RF和Jenkins均开源
* RobotFramework + Jenkins持续集成

<br />

#### 配置和部署


##### 添加节点
* 节点管理
    ![节点管理](./images/Part_14/节点管理.png)
* 配置java_web_start
    ![配置java_web_start](./images/Part_14/配置java_web_start.png)
* 新增节点
    ![新增节点](./images/Part_14/新增节点.png)
* 新增节点填写内容
    ![新增节点填写内容](./images/Part_14/新增节点填写内容.png)
* 新增节点后
    ![新增节点后](./images/Part_14/新增节点后.png)
* 处理新增节点不能使用问题1
    ![处理新增节点不能使用问题1](./images/Part_14/处理新增节点不能使用问题1.png)
* 处理新增节点不能使用问题2
    ![处理新增节点不能使用问题2](./images/Part_14/处理新增节点不能使用问题2.png)
* 节点正常使用
    ![节点正常使用](./images/Part_14/节点正常使用.png)


##### 安装Robotframework插件
* 插件管理
    ![插件管理](./images/Part_14/插件管理.png)
* robot插件安装成功
    ![robot插件安装成功](./images/Part_14/robot插件安装成功.png)


##### 配置job运行测试   
* 新建JOB
    !新建JOB](./images/Part_14/新建JOB.png)
* 选择构建windows批处理文件
    ![选择构建windows批处理文件](./images/Part_14/选择构建windows批处理文件.png)
* 填写build信息
    ![填写build信息](./images/Part_14/填写build信息.png)
* 构建后操作
    ![构建后操作](./images/Part_14/构建后操作.png)
* 配置构建后发送邮件
    ![配置构建后发送邮件](./images/Part_14/配置构建后发送邮件.png)
* 配置邮件内容:
    ![配置邮件内容](./images/Part_14/配置邮件内容.png)
    * 参考：[参考文章](https://blog.csdn.net/u013066244/article/details/78665075)
* 构建成功
    ![构建成功](./images/Part_14/构建成功.png)
**建议在创建测试用例或者测试suite时，采用统一的命名方式，如：test_*.robot，这样便于在jenkins时使用**


<br />

## 第十五部分：RF报告可视化

<br />

* 本部分将分为三个部分：
    * RF原始报告系统
    * 基于allure生成RF可视化报告
    * 解析output.xml文件，自定义RF报告

### RF自带报告系统
* 略（较简单，此处略）
    ![RF原始报告模板](./images/Part_15/RF原始报告模板.png)

### allure + jenkins + robotframework
#### 环境安装
##### 安装allure
* [参考链接](https://docs.qameta.io/allure/#_installing_a_commandline)
##### 安装robotframework
```
pip install robotframework
```
##### 安装allure-robotframework
```
pip install allure-robotframework
```
#### 命令执行
##### 执行运行脚本命令，增加参数：--listener allure_robotframework;my_allure
* 执行robot脚本命令举例：
```
pybot --listener allure_robotframework;my_allure .\test_*.robot
```
* “my_allure” 为你生成allure格式数据的目录
##### 生成allure报告数据文件
* 命令
```
allure generate -c -o ./allure-report .\my_allure\
```
* 生成allure报告数据成功
    ![生成allure报告数据](./images/Part_15/生成allure报告数据.png)
##### 启动allure服务
* 命令
```
allure open .\allure-report\
```
* 启动成功
![启动成功](./images/Part_15/启动成功.png)


##### 参考链接
* [allure与Robot Framework集成](https://www.jianshu.com/p/6a3837232042)
* [Allure对单测结果以及robotframework结果的处理](https://www.cnblogs.com/sunshine-blog/p/9899798.html)
* [RobotFramework + Jenkins + Allure Report 可视化报告](https://www.jianshu.com/p/b99f82c546ef)


#### 查看allure报告
* 可视化报告截图
    ![可视化报告截图1](./images/Part_15/可视化报告截图1.png)
    ![可视化报告截图2](./images/Part_15/可视化报告截图2.png)
    ![可视化报告截图3](./images/Part_15/可视化报告截图3.png)

#### jenkins下布置

### 自定义报告
* 使用方法：
```
python3 robotmetrics.py
```
* 解析output.xml获得新的报告模板
    ![自定义模板01](./images/Part_15/自定义模板01.png)
    ![自定义模板02](./images/Part_15/自定义模板02.png)
    ![自定义模板03](./images/Part_15/自定义模板03.png)
    ![自定义模板04](./images/Part_15/自定义模板04.png)






