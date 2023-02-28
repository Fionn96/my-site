---
title: 诛仙游戏相关
description: 诛仙游戏相关
---

[[TOC]]

## 诛仙历代版本号

| 发布时间   | 名称             | 版号 | 新职业     | 新玩法      | 新装备          | 新副本                    |
| ---------- | --------------- | ---- | :--------- |:----------- |:-------------- |:--------------------- |
| 2007.05.28 | 诛仙             |      |           | 公测、90级  |                 |                         |
| 2007.09.18 | 诛仙·三界天书    | 270  |            | 天书、150级 | 法宝灌魔        |                          |
| 2008.01.15 | 诛仙·新春特别版  |      |            |             | 135门派法宝     | 幻月                     |
| 2008.04.02 | 诛仙·君临天下    |      |            |             |                 | 凌霄                    |
| 2008.05.28 | 诛仙·六道轮回    | 422  | 鬼道       | 飞升        | 宠物            |                          |
| 2008.06.27 | 新诛仙           |      |            |            | 飞剑            |                         |
| 2009.05.26 | 诛仙·王者归来    |      |            | 鸿利        | 血祭、1级首饰   | 飞升战场、楚汉战场         |
| 2009.09.22 | 诛仙2            |      | 烈山九黎 | 空战、幻化  |                 | 天空之城、草庙村           |
| 2010.03.09 | 诛仙2·钻石情缘   |      |            | 凤凰楼      |                 |                          |
| 2010.06.10 | 诛仙2·新世界     | 776  | 天华怀光 | 庙会        |                 | 社稷                      |
| 2010.11.23 | 诛仙2·为爱成神   | 997  |            | 封神        |                 |                          |
| 2011.05.24 | 诛仙2·荣耀之路   | 1019 |            |             | 宝石            | 家族                     |
| 2011.09.22 | 诛仙前传         | 1080 | 焚香太昊 |             |                 | 焚香谷                   |
| 2012.05.29 | 诛仙2·时光之书   | 1211 |            |             | 元婴            | 梦境河阳、单人塔          |
| 2012.09.25 | 诛仙2·末日与曙光 | 1235 | 辰皇       | 中州        | 法宝飞升        | 四象、中州地图             |
| 2012.12.18 | 诛仙2·灵族秘库   |      |            |             | 2级首饰         | 灵族、单人66             |
| 2013.05.28 | 诛仙2·征战天下   | 1345 |            | 160级       | 封神装、命符    |                          |
| 2013.10.18 | 诛仙3            | 1378 | 牵机英招 | 宠物飞升    |                 | 组队66、十神宝窟、河阳灾变 |
| 2014.06.03 | 诛仙3·力破千军   | 1473 | 破军       | 孩子        | 阵灵            | 多人塔、灵境BOSS、七脉会武 |
| 2014.10.21 | 诛仙3·天域战歌   | 1516 |            |             | 轩辕册、天罡装  | T1-T6、太初战场           |
| 2015.06.02 | 诛仙3·凤舞九天   | 1567 | 青罗       | 新血炼      | 佩章            | T7-T9                    |
| 2015.10.26 | 诛仙3·梦起河阳   | 1596 |            | 外观传承    | 天命装、3级首饰 | 云渺、帝子围栏             |
| 2016.06.01 | 诛仙3·决战青云   | 1639 | 归云       | 新生产      |                 | 守卫青云                 |
| 2016.10.25 | 诛仙3·一念乾坤   | 1671 |            | 星宿、170级 | 九旒装          | T10-12                   |
| 2017.06.20 | 诛仙3·陌上十年   | 1715 | 画影       |             | 神隐武器        | 天墟                     |
| 2018.06.12 | 诛仙3·霜起龙渊   |      | 逐霜       |             |                 |                         |

## 游戏架设

>本次架设用到的所有文件均会上传到 Tools。
>以下操作是基于腾讯轻量云 CentOS7.6 系统完成。

### 安装支持库

```bash
yum update
yum install libxml2.so.2
yum install libstdc++.so.5
yum install  libgssapi_krb5.so.2
```

环境部署完成之后，记得重启一下

```bash
reboot
```

### 安装数据库

数据库管理工具有很多，建议使用宝塔面板（当然宝塔的功能不止于此），所有的操作都是可视化的，不需要命令操作，小白也能自己玩转了。

#### 防火墙设置

宝塔面板默认使用8888端口，需要在服务器防火墙为宝塔开放端口。可以在安装完成后进入宝塔面板修改默认端口。

![防火墙设置](https://s1.vika.cn/space/2022/10/14/bc18dc59469f496197822099374099ca)
![防火墙设置](https://s1.vika.cn/space/2022/10/14/d76775bd42454883b2dd300a91fd681a)

#### 安装宝塔

- 输入以下安装命令

```bash
yum install -y wget && wget -O install.sh http://download.bt.cn/install/install_6.0.sh && sh install.sh ed8484bec
```

![安装宝塔命令](https://s1.vika.cn/space/2022/10/14/0d3f5927c14a42ba8907c164438a0946)

- 安装过程中如果有提示就输入 y 并回车，等待安装完成。

![宝塔登录信息](https://s1.vika.cn/space/2022/10/14/db83628006ce4db4837fd95f50ba15b4)

- 以上四项内容``非常重要``，请务必保存，可以进入宝塔面板后在设置里自行修改。

![登录宝塔](https://s1.vika.cn/space/2022/10/14/01479f9e99ca4086a7c783dfab979799)

- 浏览器输入面板的外网地址，输入账号和密码登录，然后根据绑定手机号。
  
#### 安装套件

一般来说第一次进入宝塔会弹窗提示推荐安装套件，选择安装 LNMP 一键安装即可。如果没有弹窗，可以直接在 ⌈软件商店⌉ 自行搜索安装 MySQL 5.5、PHP 5.4、Nginx 1.22、phpMyAdmin 4.4。

![安装套件](https://s1.vika.cn/space/2022/10/14/f59a44be1308498ea50ba7c085dc5a27)

#### 添加游戏数据库

等待 LNMP 安装完成后，为游戏添加一个数据库并导入诛仙sql文件，用于存放用户账号密码、注册相关信息、元宝充值消费记录等信息。数据库名、用户名、密码可自行设置。

![添加数据库](https://s1.vika.cn/space/2022/10/14/15e4af60d7f243df8c56bce084b8bef9)
![导入数据](https://s1.vika.cn/space/2022/10/14/6b0033466ec844b395f7267fc07ebf6e)

#### 设置数据库账户权限

通过面板访问使用``root``账户进入 phpMyAdmin 管理页面，分别为 game@% 及 game@localhost 添加所有权限。

![设置管理权限](https://s1.vika.cn/space/2022/10/14/3f35f93cf671479d889ab96e0f19f3e1)
![设置管理权限](https://s1.vika.cn/space/2022/10/14/84a69124275640c7930a6afed161e1bb)
![设置管理权限](https://s1.vika.cn/space/2022/10/14/bb4a4a174a0f4dfda809c093bfac63e8)
![设置管理权限](https://s1.vika.cn/space/2022/10/14/67ceef4041b14adb97c22eaed0d17f7c)

### 安装 Java 环境

以下为 centos7.6 安装 Java 的两种方式。

#### 安装包 tar.gz 方式

```bash
cd /usr/java
tar zxvf jdk-8u162-linux-x64.tar.gz
mv  jdk-8u162-linux-x64 jdk1.8.0_45
vi /etc/profile
```

```bash
# jdk 环境变量
export  JAVA_HOME=/usr/java/jdk1.8.0_45
export  CLASSPATH=.:$JAVA_HOME/jre/lib/rt.jar:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
export  PATH=$PATH:$JAVA_HOME/bin
```

使配置立刻生效

```bash
source /etc/profile
```

#### yum 方式(推荐)

搜索 jdk 安装包

```bash
yum search java|grep jdk
```

![jdk 安装包](https://s1.vika.cn/space/2022/10/14/a2286bd8abb4449e8b0573cabf32cb6c)

安装 jdk 1.8

```bash
yum install java-1.8.0-openjdk* -y
```

![安装 jdk 1.8](https://s1.vika.cn/space/2022/10/14/32603e0fb98a4e598c1183a65a71f424)

查看 jdk 版本

```bash
java -version
```

![查看jdk版本](https://s1.vika.cn/space/2022/10/14/e888d341aba1433b92d6500fe2b0d8ff)

在线安装不需要专门配置环境变量。

### 服务端配置

将服务端上传到``/root``目录下并执行解压命令

```bash
tar zxvf root_zx.tar.gz
```

一般来说，从一键端里提取的服务端已经配置好各服务端口，仅需修改 authd，这里控制服务端连接到数据库的配置。

修改 ../authd/table.xml

```text
<connection 
name="auth0" 
poolsize="3" 
url="jdbc:mysql://你的公网IP或127.0.0.1:数据库端口默认为3306/数据库名?useUnicode=true&amp;characterEncoding=ascii" 
username="数据库用户名" 
password="数据库密码"/>
```

将Java签名文件复制或移动到``/etc``目录

```bash
cp /root/zxserver1715/authd/etc/cert.jks /etc
```

到这里，服务器基本配置完成，可尝试启动服务端，没有报错即可尝试登录游戏。

```bash
cd /root
./start
```

## 服务端目录解析

| 文件夹      | 文件名                          | 备注                                                               |
| ----------- | ------------------------------- | ----------------------------------------------------------------- |
| authd       | /myauthd/build/table.xml        | 服务端连接数据库配置及大V                                          |
|             | /gauthd/gamesys.conf            |                                                                   |
| gamed       | global_script.lua               | 设置脚本存放位置                                                   |
|             | config                          | 版本文件夹                                                         |
|             | /config/b04~z416                | 地图文件、NPC及怪物刷新、触发器、安全区、出生点                       |
|             | /config/aipolicy.data           | AI数据                                                             |
|             | /config/domain.data             |                                                                    |
|             | /config/domainlandwar.data      |                                                                    |
|             | /config/dyn_tasks.data          |                                                                    |
|             | /config/dynamicobjects.data     |                                                                    |
|             | /config/extra_drops.sev         | 附加掉落表                                                         |
|             | /config/elements.data           | 版本文件                                                           |
|             | /config/gshop.data              | 商城文件                                                           |
|             | /config/hometowndata            |                                                                   |
|             | /config/menology_info.lua       | 大型活动信息                                                       |
|             | /config/task_npc.data           | NPC任务栏自动寻路及飞天坐标                                         |
|             | /config/tasks.data              | 任务文件                                                           |
|             | /config/vipaward.data           |                                                                    |
|             | /config/world_targets.sev       |                                                                    |
|             | script                          | 脚本文件夹                                                         |
|             | /script/astrology.lua           | 星座                                                               |
|             | /script/lottery.lua             | 抽奖、彩票                                                         |
|             | /script/magic_interface.lua     | 幻灵石                                                             |
|             | /script/petbedge_XXX.lua        | 宠物相关                                                           |
|             | /script/runeInterface.lua       | 元婴                                                               |
|             | /script/summon_interface.lua    | 召唤物，焚香的火，怀光的影子，辰皇的召唤物，烈山的宝宝，牵机的机关      |
|             | /script/talisman_XXX.lua        | 法宝相关                                                           |
|             | /script/transform_interface.lua | 变身脚本，包括幻灵石变身、副本变身                                   |
|             | gs                              | 大地图主程序                                                       |
|             | gs.conf                         | 大地图配置                                                         |
|             | gmserver.conf                   | 内部连通其他服务配置                                               |
|             | gsalias.conf                    | 线路名和线路配置                                                   |
|             | ptemplate.conf                  | debug开关、等级上限、经验倍率                                      |
| gamedbd     | gamedbd                         | 角色数据程序                                                      |
|             | gamesys.conf                    | 设置角色数据存档位置，内部连通其他服务配置                          |
| gdeliveryd  | gdeliveryd                      | 游戏服务配置程序，活动时间、人数要求等                              |
|             | /gamesys.conf                   | 设置zoneID, 内部连通其他服务配置                                   |
|             | factionname.txt                 | 禁止起名使用文字                                                   |
|             | rulename.txt                    | ？禁用聊天文字？                                                   |
|             | zhuxian_question.data           | 新科试炼问题及答案                                                 |
| glink       | glinkd                          |                                                                  |
|             | /gamesys.conf                   | 登录游戏端口配置、内部连通其他服务配置                               |
| toplist     |                                 | 排行榜                                                            |
| uniquenamed |                                 | ？角色数据和创建角色名相关？                                       |

## 客户端目录解析

wip...

## 技能参数调整

> 以下内容均以1715版本技能库为例。

### 利器

- [IDA_Pro](https://pan.baidu.com)——反汇编神器
- [HexEdit](https://hexed.it/)——简洁美观功能够用的十六进制在线编辑器，如果使用 EDGE 浏览器，还可以把该网站作为一个应用安装到本地来使用
- [float2hex](https://pan.baidu.com)——浮点数十六进制转换工具

### 基本函数解释

| 函数名称                       | 功能                                                                  |
| :----------------------------- | :--------------------------------------------------------------------|
| BlessME                        | 对自身有益的buff或功能合集                                             |
| Cooldowntime                   | 冷却时间（单位：毫秒）                                                 |
| Coverage                       | 攻击目标数量                                                          |
| Executetime                    | 总施法时间，需同步修改 GetTime 函数                                    |
| GetTime                        | 分段攻击施法时间                                                      |
| SkillXXXStub(Void)             | 控制技能等级、施法姿态、关联天书和其他技能、职业和武器限制、技能段数等     |
| SkillXXXStub::State::Calculate | 单独设置分段攻击数据或一些特殊效果                                     |
| StateAttack                    | 对敌方附带debuff控制或其他功能合集                                     |

### 使用 IDA 加载 libskill.so

以技能`skill786`(神剑御雷真诀)为例，该技能的介绍为

>攻击自身周围群体目标，在六秒内造成六次伤害。
>目标限制：40 个。
>攻击自身周围25米内的敌人，追加本体攻击力4%，每次附加攻击力865点，冷却时间16秒。
>4%几率急速冷却；
>4%几率令最后一次攻击附加攻击力加倍；
>4%几率令目标无法施法%d秒，忽略抗性；
>一定几率令目标定身6秒，定身能力197点...

默认你已经安装好 IDA，使用 IDA 加载技能库`libskill.so`文件，加载配置默认即可。一般来说我们只需要使用 IDA 的函数视图、反汇编视图及伪代码视图（在反汇编视图下通过 <kbd>F5</kbd> 打开）。刚打开的`libskill.so`里函数是乱序的，可以点击一下左上方的 ⌈函数名称⌋ 自动排序，还可以通过快捷键 <kbd>CTRL</kbd>+<kbd>F</kbd> 打开函数搜索框。

![视图](https://s1.vika.cn/space/2022/10/15/13a112007eba4e0d8e38edf88016d5bd)
![排序及搜索框](https://s1.vika.cn/space/2022/10/15/68682b6b66e242e49e4baab725e8cde2)

### 修改技能冷却

在函数窗口搜索`skill786`，找到`GetCooldowntime`函数并双击它，软件会自动跳转到该函数的反汇编窗口地址，冷却时间的数据一般就在附近。你还可以在反汇编窗口摁一下 <kbd>F5</kbd> 键打开伪代码视图，可以看到，该技能的冷却时间为16000（毫秒），右键它并选择转换十六进制，会发现16000变成了`0x3E80`，与我们在反汇编窗口的`GetCooldowntime`附近看到的数据一致。奇怪的是，`libskill.so`里的十六进制数据是反着写的，比如我们在伪代码视图看到的这个技能的冷却时间是`0x3E80`，但十六进制数据里写的是`80 3E 00 00`。

![冷却时间](https://s1.vika.cn/space/2022/10/15/e9c498eeb25f4259bb8dccf627dec78b)

你可以选择使用 IDA 的修补程序（如果有），通过 ⌈编辑⌋→⌈修补程序⌋→⌈单字节更改方式⌋ 直接修改，假设我们把冷却时间改成1000毫秒，转化为十六进制是`00 00 03 E8`，要==反过来写==，用`E8 03 00 00`替换掉`80 3E 00 00`。

![IDA修改](https://s1.vika.cn/space/2022/10/15/5b9319feb2314a47865e12d873261214)
![IDA修改](https://s1.vika.cn/space/2022/10/15/5e43576d91ba409a875574ebf5be18f3)

修改完成后，可以通过 ⌈编辑⌋→⌈修补程序⌋→⌈修补程序应用到输入文件⌋ 来导出修改后的技能库（如果修改的地方不多，建议直接用 IDA 修改比较方便）。

你还可以使用一些十六进制编辑器，比如 WinHex、010Editer、HxD 等，这里推荐使用 HexEdit，复制冷却时间对应的地址`01478DC9`，在 HexEdit 打开`libskill.so`，通过 ⌈前往⌋ 功能直接跳转到该地址，把原有的`80 3E 00 00`改为`E8 03 00 00`即可。

![HexEdite修改](https://s1.vika.cn/space/2022/10/15/000d7b98cfd2481bb69b8005ab6aa7f6)

### 修改施法时间

修改技能施法时间要同时修改总施法时间和分段攻击施法时间。在函数窗口搜索`skill786`，找到`GetExecutetime`函数和`GetTime`函数并双击，可以在反汇编窗口看到它们的地址和十六进制数据。

![786总施法时间](https://s1.vika.cn/space/2022/10/15/f352395174164a109fe260b990f6f584)

在反汇编窗口施法时间摁一下 <kbd>F5</kbd> 打开伪代码视图，可以看到，技能的总施法时间为6000（毫秒），转化十六进制为`0x1770`，可以很容易在反汇编窗口找到该数据的地址。

![分段攻击施法时间](https://s1.vika.cn/space/2022/10/15/77d5027cd57a458c8afdab0ae2fca486)

再往下可以看到这个技能有7段`GetTime`函数，表示这个技能有6段攻击（其中第一段可能是判断起手，后面6段才会会显示伤害），把这7段分段攻击的施法时间相加，为`600 + 900 + 900 + 900 + 900 + 900 + 900 = 6000`，与我们在上面找到的总施法时间数据一致。

假设我们希望把技能施法时间改成2100毫秒，转化十六进制为`00 00 08 34`，平均每段分段攻击的施法时间改成300，转化十六进制为`00 00 01 2C`，那么可以直接在 IDA 利用修补程序直接修改相应的十六进制数据——同样要记得把十六进制反过来写去替换。

![修改总施法](https://s1.vika.cn/space/2022/10/15/6b2cfb629cff4711bfe6e170bc0464a8)
![修改分段施法](https://s1.vika.cn/space/2022/10/15/d6da33fc6d384027a6d5b170c9be173d)

还可以在十六进制编辑器中去修改，如通过总施法时间地址`01478DC9`到十六进制修改器中找到到相应的十六进制数据位置，然后修改即可。

![查看地址](https://s1.vika.cn/space/2022/10/15/1cf1134fc46645cfa3d653ad28b52ca0)
![十六进制修改](https://s1.vika.cn/space/2022/10/15/21a128e5e46b4bc2beb74abeb7a58c66)

### 修改技能倍率

work in process...

### 修改急速冷却概率

work in process...

### 修改魅惑及定身时间

技能`skill786`会对目标施加魅惑和定身 debuff，一般来说附加不利效果的代码会集合在`StateAttack`函数下，在函数窗口找到该函数并查看该函数的伪代码视图，很容易就发现技能下存在`SetSilent`（魅惑）和`SetWrap`（定身）的技能特效及其持续时间的代码。

![魅惑和定身](https://s1.vika.cn/space/2022/10/16/3868e6ccb36f4b3398862d77c2b65ef0)

假设要修改魅惑持续时间从6100（毫秒）增加到10000（毫秒），可以点击一下6100，可以在伪代码视图左下角看到该数据的地址，回到反汇编窗口定位到该地址，我们发现这里设置了一个`mov`到一个偏移，可以点击该偏移，右键选择 ⌈跳转到操作数⌋。

![魅惑时间偏移值](https://s1.vika.cn/space/2022/10/16/ef9c34f17c684305b8dcd0eea316899a)
![魅惑时间操作数](https://s1.vika.cn/space/2022/10/16/e835c0e1c59344f2bfb5bbf9db89106a)

可以在地址`02831F20`处发现，这里是使用``单精度十六进制``来表示6100，如果想把持续时间改为10000，同样要转换为单精度十六进制数据再去替换它，使用浮点数十六进制计算器，得到10000的单精度十六进制为`46 1C 40 00`，还是要反过来写，即用`00 40 1C 46`替换掉`00 A0 BE 45`。

![修改魅惑持续时间](https://s1.vika.cn/space/2022/10/16/f6fd0a5ae58d4322a22b934440ea729c)

同理修改定身持续时间，同样在函数`StateAttack`的伪代码下找到定身的持续时间代码，发现其计算公式为`500 * T0的技能等级 + 6100`（关于 T0 是什么，可以在函数`Skill786Stub(Void)`下找到Talent[0] = 593 ,然后去技能说明skillstr.txt里找到该技能）。我们仅修改其基础持续时间6100为10000，点击6100在左下方获得该数据地址并定位到反汇编窗口。

![定身持续时间](https://s1.vika.cn/space/2022/10/16/919c5255889844a7b9b5f2ae925d5f54)

可以发现这里是直接计算6100的十六进制数据，这就好办了，用10000的十六进制数据替换掉即可。

## 技能特效替换

### 替换原理

以技能 `skill3912`（星语：十步一杀）为例，这个技能的效果为 ⌈禁食目标5秒⌋，在 IDA 中搜索`skill3912`，找到它的禁食特效词条`SetDietEb`

![十步一杀地址](https://s1.vika.cn/space/2022/10/14/68d947b019874d93a2abbd2616d8af62)

从 IDA 中可以得到该特效的地址为`01F20B38`, 对应的十六进制数据为`E8 4F F1 3F FF`, 其中`E8`代表 Call 可以不用管，只需要后面的`4F F1 3F FF`, 不过计算的时候要反过来写，为`FF 3F F1 4F`。

然后把`skill3912`的禁食特效的地址和十六进制数据用计算器相加, 即`01F20B38 + FF3FF14F = 0131FC87`,  与我们双击`SetDietEb`跳转后得到的禁食特效地址相同

![禁食特效计算](https://s1.vika.cn/space/2022/10/14/a9d476ebdd0f4eeea3fa8e4f8c7fe94a)
![禁食特效地址](https://s1.vika.cn/space/2022/10/14/9d28cc4573814829810b8e358833799a)

也就是说, 技能库里所有的禁食特效都会关联到该地址`0131FC87`，而关联方法就是地址+十六进制；反过来说，我们要把一个技能的特效改成禁食，在原技能特效地址和禁食特效地址已知且不改变的情况下，只需要改原技能特效词条的十六进制数据就可以了。

### 特效替换

接下来替换一个特效测试，以技能`skill786`（神剑御雷真诀）为例，把技能原本的魅惑特效改为禁食，在 IDA 中搜索`skill786`, 找到它的魅惑词条`SetClientEb`，可以看到该魅惑词条的地址为`01478F00`，十六进制数据为`A7 E3 EA FF`

![神剑御雷](https://s1.vika.cn/space/2022/10/14/033fca6c5a474833a8fffdde187f97f2)

然后用上面得到的禁食特效的关联地址减去该魅惑词条的地址, 即`0131FC87 - 01478F00 = FFEA6D87`

![禁食减魅惑地址](https://s1.vika.cn/space/2022/10/14/2bdbb8322705477a926fc1157036cbb4)

然后使用十六进制编辑器把魅惑特效原来的十六进制数据`A7 E3 EA FF`改成得到的新的十六进制数据`87 6D EA FF`, 这样就完成了一次特效替换。

![修改后对比](https://s1.vika.cn/space/2022/10/14/db0707da8eda409ea0f7b44bccb80256)

## 技能施法姿态限制



## 技能段数增加

技能段数增加是通过循环播放某一段攻击来达到增加段数的目的。以技能`skill786`（神剑御雷真诀）为例，在 IDA 中搜索`skill786`，找到`Skill786Stub(void)`函数，这里包含着技能等级、施法姿态、关联天书和其他技能、职业和武器限制、技能段数等信息。
![神剑御雷真诀](https://s1.vika.cn/space/2022/10/14/2629bb1717f2481d8d31a0eb0ba927c1)

在伪代码视图拉到最下面，找到`skill786`的第四段攻击`GNET::Skill786Stub::State5::State5(v3);`，点一下可以在下方看到它的地址，回到反汇编视图定位该段的起始地址`014644F3`和结束地址`01464547`（经验之谈，一般以 loc 开头在 jz 结束），还可以看到第四段攻击完整的十六进制代码

![第四段攻击十六进制代码](https://s1.vika.cn/space/2022/10/14/4bce8a86100649358942eaa463d49449)
`83 EC 08 83 EC 04 6A 04 E8 5C 0C EF FF 83 C4 08 89 45 A4 C6 45 A3 01 83 EC 04 FF 75 A4 E8 87 63 E7 FF 83 C4 08 C6 45 A3 00 8B 45 A4 89 45 E4 8D 45 E4 50 8B 45 08 05 1D 01 00 00 50 E8 F8 5E EC FF 83 C4 10 EB 28 89 45 CC 8B 45 CC 89 45 9C 80 7D A3 00 74 0E`

增加段数的方法为，修改前面6字节`83 EC 08 83 EC 04`变为`51 EB 4A 83 EC 0C`，修改后面17字节`EB 28 89 45 CC 8B 45 CC 89 45 9C 80 7D A3 00 74 0E`变为`59 41 83 F9 XX 7D 07 EB 02 31 C9 51 EB B1 59 EB 19`。其中，`XX`部分是`目标段数 - 初始段数 + 1 = 结果的十六进制`，目标段数最多不能超过255段（因为只有一个字节的位置可以修改）。

例如技能`skill786`初始为6段，目标段数为12段，那么这里的数据就是`12 - 6 + 1 = 7`，转化为十六进制`07`；如果目标段数为24段，那么数据则是`24 - 6 + 1 = 19`，转化为十六进制`13`。以上修改的逻辑为，令第四段攻击重复播放7次或19次，以达到攻击段数增加到12段或24段的目的。

如果希望把技能`skill786`的攻击段数增加到12段，则要修改的第四段的十六进制的增段代码为：

`51 EB 4A 83 EC 0C 6A 04 E8 5C 0C EF FF 83 C4 08 89 45 A4 C6 45 A3 01 83 EC 04 FF 75 A4 E8 87 63 E7 FF 83 C4 08 C6 45 A3 00 8B 45 A4 89 45 E4 8D 45 E4 50 8B 45 08 05 1D 01 00 00 50 E8 F8 5E EC FF 83 C4 10 59 41 83 F9 07 7D 07 EB 02 31 C9 51 EB B1 59 EB 19`

可以在 IDA 中使用修补程序→单字节修改方式（如果有）直接修改，也可以用其他十六进制修改器修改，这里示范使用 HexEdit 进行修改。

![定位](https://s1.vika.cn/space/2022/10/14/ba2f389e8392484f8f4f83bf1fb7ed40)

用 HexEdit 打开技能库，使用 ⌈前往⌋ 功能定位到起始地址`014644F3`和结束地址`01464547`，选中整段十六进制，复制以上修改好的增段代码到 HexEdit 直接 <kbd>CTRL</kbd>+<kbd>V</kbd>，选择以十六进制数据覆写代码并保存，即完成技能段数增加。

![覆写代码](https://s1.vika.cn/space/2022/10/14/9ca2e235f8df45f5981d30f15aaeb1d3)
![对比](https://s1.vika.cn/space/2022/10/14/2e9d743a5deb45f89e9b94200abb8ffa)

## gs 相关函数

| 函数名                                         |说明  |备注                                           |
| :--------------------------------------------- |:------|:----------------------------------------------|
| UpgradeTalentScroll(item *,gactive_imp *,uint) |mov esi, offset unk_xxxxxxx |  轩辕策升级概率           |
| itemdataman &,int,TRANSMITROLL_ESSENCE         |                            |城镇传送符限制             |
| item_townscroll::OnUse                         |                            |飞天神符限制               |
| item_couple_jump::OnUse                        |                            |双飞翼限制                |
| item_telestation::UseTelePosition              |                            |星盘                      |
| equip_item::ShapeCopyEquip(void)               |装备位置ID相加              |外观传承装备限制            |
| gplayer_imp::ResetRune(int,int,int)            |                            |元婴道胎值                 |
|gplayer_imp::GenAmuletStone                    |                              |四灵壁提取概率             |
|talent_scroll::UpgradeTalentScroll             |                              |升级天赋卷轴               |

|imp::StarSystemStarRemove(int,int,int)::op::GetDuration()||星宿移除时间|

## gdeliveryd 相关函数

| 函数名                           | 说明  |   备注       |
| :------------------------------- | :-- | :----------- |
| BattleField:GetFightingTime      |     | 战场间隔时间 |
| BattleField:GetCooldownTime      |     | 战场排队时间 |
| BattleField::CheckFormalOpenCond |     | 验证500人数  |

## NPC 功能测试

| EL对应注释   | NPC段字节数 | GS中对应介绍                                                   | 功能介绍                                                                           |
| :---------- | :--------   | :----------------------------------------------------------- | :--------------------------------------------------------------------------------- |
| 第5项        | 104         | refresh_time = (signed int)(*(float*)(i + 104) * 20.0 + 0.5); | 刷新时间？                                                                         |
| 第6项        | 108         | attack_rule                                                    | 攻击规则？1？2？                                                                   |
| 第11项       | 636         | service_waypoint_id，TRANS_TARGET_SERV                         | 路径服务？无此项                                                                   |
| 第12项       | 640         | need_domain                                                    | 领域？天工神匠。                                                                   |
| 失去功能     | 644         | npc_type = 1                                                   | NPC类型？无法使用功能。                                                            |
| 第14项       | 648         | npc_type = 2                                                   | NPC类型？飞船，跳台。                                                              |
| 城战属性     | 652         | war_role_config                                                | 城战属性                                                                           |
| 出售         | 660         | service_sell_goods                                             | 出售                                                                               |
| 发布任务     | 672         | service_task_out_list                                          | 发布任务                                                                           |
| 接收任务     | 676         | service_task_in_num                                            | 接收任务                                                                           |
| 第22项       | 680         | service_task_matter_list                                       |                                                                                    |
| 第23项       | 684         | service_heal                                                   | 治疗？无此项。                                                                     |
| 传送阵       | 688         | transmit_entry                                                 | 传送                                                                               |
| 仓库         | 696         | service_storage                                                | 仓库1714                                                                           |
| 洗点         | 704         | service_reset_prop_count                                       | 洗点1716                                                                           |
| 装备绑定     | 708         | service_equip_bind                                             | 装备绑定，只能销毁                                                                 |
| 装备销毁     | 712         | service_destroy_bind                                           | 装备销毁1723                                                                       |
| 解除销毁     | 716         | service_undestroy_bind                                         | 解除销毁1722                                                                       |
| 招募弓神     | 720         | battle_field_employ_service                                    | 招募                                                                               |
| 功能1/兑换   | 724         | service_item_trade                                             | 兑换                                                                               |
| 功能5/生产   | 740         | service_npc_produce_id                                         | 生产                                                                               |
| 第38项       | 744         | service_consign                                                | 寻宝网寄卖40963                                                                    |
| 声望兑换     | 748         | reputation_shop_id                                             | 声望商店                                                                           |
| 上古世界     | 752         | use_ui_trans_id                                                | 上古世界                                                                           |
| 传送阵       | 756         | id_open_ui_trans                                               | 传送阵                                                                             |
| 功能6/新兑换 | 760         | service_item_trade2                                            | 新兑换                                                                             |
| 功能8        | 768         | 1  renew_mount_service                                         | 1=坐骑驯化                                                                         |
|              |             | 2                                                              | 2=帮派赛隐仙阁报名（2012、2013跨服帮派赛）                                         |
|              |             | 4  lock_item_service                                           | 4=物品锁定\解锁                                                                    |
|              |             | 8  TRANS_TARGET_SERV                                           | 8=指向636？                                                                        |
|              |             | 16  service_faction                                            | 16=创建\解散\升级帮派                                                              |
|              |             | 32  service_restore_broken                                     | 32=修复破损物品                                                                    |
|              |             | 64  service_mail                                               | 64=邮件服务                                                                        |
|              |             | 128  service_auction                                           | 128=拍卖？无反应                                                                   |
|              |             | 256  service_double_exp                                        | 256=双倍经验？无反应                                                               |
|              |             | 512  service_hatch_pet                                         | 512=宠物孵化？无此项                                                               |
|              |             | 1024  service_recover_pet                                      | 1024=宠物复原？无此项                                                              |
|              |             | 2048                                                           | 2048=天界普通战场报名                                                              |
|              |             | 8192  service_cash_trade                                       | 8192=元宝交易                                                                      |
|              |             | 16384  service_storage_mafia                                   | 16384=帮派仓库，显示退出家族，未发现可放入的物品                                   |
|              |             | 32768  service_talisman                                        | 32768=法宝修炼\聚气\血炼\灌魔\归元                                                 |
|              |             | 65536  battle_field_challenge_service                          | 65536=凌霄城报名                                                                   |
|              |             | 131072                                                         | 131072=进入凌霄城                                                                  |
|              |             | 262144  battle_field_construct_service                         | 262144=凌霄城建设                                                                  |
|              |             | 524288  pet_service_adopt                                      | 524288=宠物驯养                                                                    |
|              |             | 1048576  pet_service_free                                      | 1048576=宠物放生                                                                   |
|              |             | 2097152  pet_service_combine                                   | 2097152=宠物修炼                                                                   |
|              |             | 4194304  pet_service_rename                                    | 4194304=宠物改名                                                                   |
|              |             | 7864320                                                        | 7864320=宠物功能（以上四项之和）                                                   |
|              |             | 8388608  service_blood_enchant                                 | 8388608=滴血认主                                                                   |
|              |             | 16777216  service_spirit_addon                                 | 16777216=器魄镶嵌                                                                  |
|              |             | 33554432  service_spirit_remove                                | 33554432=器魄拆除                                                                  |
|              |             | 67108864  service_spirit_charge                                | 67108864=恢复魂力                                                                  |
|              |             | 134217728  service_spirit_decompose                            | 134217728=装备拆解                                                                 |
|              |             | 260046848                                                      | 260046848=装备血祭（以上五项之和）                                                 |
|              |             | 268435456                                                      | 268435456=天界飞升战场报名                                                         |
|              |             | 268437504                                                      | 268437504=天界战场报名=268435456+2048                                              |
|              |             | 536870912                                                      | 536870912=楚汉战场报名                                                             |
|              |             | 1073741824  service_arena_challenge                            | 1073741824=演武竞技场报名                                                          |
| 功能9        | 772         | 1  service_change_style                                        | 1=易容                                                                             |
|              |             | 2  service_petequip_refine                                     | 2=宠物装备强化                                                                     |
|              |             | 4                                                              | 4=帮派赛逸龙轩报名（2012、2013跨服帮派赛）                                         |
|              |             | 8                                                              | 8=帮派赛记者\观战报名（2012、2013跨服帮派赛）                                      |
|              |             | 12                                                             | 12=帮派赛战场报名=4+8                                                              |
|              |             | 16                                                             | 16=加入时空幻境                                                                    |
|              |             | 32  service_magic_refine                                       | 32=幻灵石归元\强化\契合，最多强化20级                                              |
|              |             | 64  service_magic_restore                                      | 64=幻灵石灵气恢复                                                                  |
|              |             | 128  service_territory_challange                               | 128=领土战报名                                                                     |
|              |             | 256  service_territory_enter                                   | 256=进入领土战战场                                                                 |
|              |             | 512  service_territory_reward                                  | 512=领土战奖励                                                                     |
|              |             | 640                                                            | 640=社稷之战=128+512                                                               |
|              |             | 1024  service_charge_telestation                               | 1024=星盘充能                                                                      |
|              |             | 2048  service_repair_damage                                    | 2048=修复破碎物品（需5万金）                                                       |
|              |             | 4096  service_equipment_upgrade                                | 4096=装备升级                                                                      |
|              |             | 8192  service_crossservice_in                                  | 8192=传送天界                                                                      |
|              |             | 16384  service_crossservice_out                                | 16384=返回下界（梵天净土）                                                         |
|              |             | 65536  service_identify_gem_slots                              | 65536=插槽鉴定                                                                     |
|              |             | 131072  service_rebuild_gem_slots                              | 131072=插槽重铸                                                                    |
|              |             | 196608                                                         | 196608=开阳（以上两项之和）                                                        |
|              |             | 262144  service_customize_gem_slots                            | 262144=插槽定制                                                                    |
|              |             | 524288  service_embed_gems                                     | 524288=宝石镶嵌                                                                    |
|              |             | 1048576  service_remove_gems                                   | 1048576=宝石拆除                                                                   |
|              |             | 2097152  service_upgrade_gem_level                             | 2097152=宝石升品                                                                   |
|              |             | 3670016                                                        | 3670016=七宝（以上三项之和）                                                       |
|              |             | 4194304  service_upgrade_gem_quality                           | 4194304=宝石精炼，有概率普通升完美，精炼道具：黄泉晶                               |
|              |             | 8388608  service_extract_gem                                   | 8388608=宝石萃取                                                                   |
|              |             | 16777216  service_smelt_gem                                    | 16777216=宝石熔炼，有BUG，多生成一对道具，熔炼道具：地皇石                         |
|              |             | 33554432                                                       | 33554432=精英赛[红方]报名使者（2013跨服精英赛）                                    |
|              |             | 67108864                                                       | 67108864=精英赛[蓝方]报名使者（2013跨服精英赛）                                    |
|              |             | 134217728                                                      | 134217728=精英赛[记者]报名使者（2013跨服精英赛）                                   |
|              |             | 536870912                                                      | 536870912=神武镇元塔个人信息                                                       |
|              |             | 1073741824  service_change_name                                | 1073741824=改名\改名查询                                                           |
|              |             | < 0  service_change_faction_name                               | < 0=家族改名                                                                       |
| 功能10       | 776         | 1  service_change_faction_name                                 | 1=帮派改名                                                                         |
|              |             | 2  service_talisman_holylevelup                                | 2=法宝飞升                                                                         |
|              |             | 4  service_talisman_embedskill                                 | 4=法宝技能融合                                                                     |
|              |             | 8  service_talisman_refineskill                                | 8=法宝技能传承                                                                     |
|              |             | 14                                                             | 14=神工（以上三项之和）                                                            |
|              |             | 16  service_equipment_upgrade2                                 | 16=装备升级2？无此项                                                               |
|              |             | 32  service_equipment_slot                                     | 32=装备打孔，打孔道具：53946望斗经                                                 |
|              |             | 64  service_install_astrology                                  | 64=镶嵌星座                                                                        |
|              |             | 128  service_uninstall_astrology                               | 128=摘除星座                                                                       |
|              |             | 256  service_astrology_identify                                | 256=鉴定星座？                                                                     |
|              |             | 1024  service_crossservice_battle_out                          | 1024=返回下界（天界战场）                                                          |
|              |             | 2048  service_crossservice_battle_sign_up                      | 2048=进入天界战场报名大厅                                                          |
|              |             | 4096  service_kingdom_enter                                    | 4096=进入天帝战主战场\辅战场\瑶池                                                  |
|              |             | 8192                                                           | 8192=飞升开启进度查询                                                              |
|              |             | 16384  service_equipment_upgrade                               | 16384=饰品升级                                                                     |
|              |             | 32768                                                          | 32768=生产自动出售                                                                 |
|              |             | 65536  service_produce_jinfashen                               | 65536=快速制作金身、法身                                                           |
|              |             | 98304                                                          | 98304=黑市商人（以上两项之和）                                                     |
|              |             | 131072                                                         | 131072=天界演武战场报名                                                            |
|              |             | 262144                                                         | 262144=创建帮派基地                                                                |
|              |             | 524288  service_pet_reborn                                     | 524288=宠物飞升                                                                    |
|              |             | 1048576                                                        | 1048576=神威相助                                                                   |
|              |             | 2097152                                                        | 2097152=帮派基地元宝商城                                                           |
|              |             | 4194304  service_modify_reborn_occupation                      | 4194304=前世轮回                                                                   |
|              |             | 8388608                                                        | 8388608=七脉会武初赛报名 大竹峰                                                    |
|              |             | 16777216                                                       | 16777216=七脉会武初赛报名 小竹峰                                                   |
|              |             | 33554432                                                       | 33554432=七脉会武初赛报名 朝阳峰                                                   |
|              |             | 67108864                                                       | 67108864=七脉会武初赛报名 落霞峰                                                   |
|              |             | 134217728                                                      | 134217728=七脉会武初赛报名 风回峰                                                  |
|              |             | 268435456                                                      | 268435456=七脉会武初赛报名 龙首峰                                                  |
|              |             | 536870912                                                      | 536870912=七脉会武初赛报名 通天峰                                                  |
|              |             | 1073741824                                                     | 1073741824=七脉会武总决赛报名\结果                                                 |
|              |             | < 0  service_uniqueservice_battle_apply                        | < 0=灵境·涿鹿之原报名                                                              |
| 功能11       | 780         | 1  service_uniqueservice_battle_out                            | 1=传出灵境战场                                                                     |
|              |             | 2                                                              | 2=跨服PK争霸赛                                                                     |
|              |             | 4  service_mount_speed_up                                      | 4=坐骑优化（提速）                                                                 |
|              |             | 8  service_uniqterritory_challenge                             | 8=灵境·国战报名                                                                    |
|              |             | 16  service_uniqterritory_enter                                | 16=进入云渺河阳                                                                    |
|              |             | 18                                                             | 18=灵境天尊　兰将军=2+16                                                           |
|              |             | 64  service_uniqterritory_itemget                              | 64=灵境·国战奖励                                                                   |
|              |             | 88                                                             | 88=灵境　阪泉之野掌印官=8+16+64                                                    |
|              |             | 128  service_allstar_team_apply                                | 128=跨服PK争霸赛红方报名                                                           |
|              |             | 256  service_allstar_team_apply                                | 256=跨服PK争霸赛蓝方报名                                                           |
|              |             | 512  service_allstar_team_apply                                | 512=跨服PK争霸赛观战报名                                                           |
|              |             | 1024                                                           | 1024=？                                                                            |
|              |             | 1664                                                           | 1664=跨服PK争霸赛红方=1024+512+128                                                 |
|              |             | 1792                                                           | 1792=跨服PK争霸赛蓝方=1024+512+256                                                 |
|              |             | 2048  service_redgift                                          | 2048=领取红包                                                                      |
|              |             | 8192  service_amulet_gen_stone                                 | 8192=附加属性提炼                                                                  |
|              |             | 16384  service_amulet_upgrade                                  | 16384=佩章精炼                                                                     |
|              |             | 32768  service_amulet_embed_stone                              | 32768=佩章孔位镶嵌                                                                 |
|              |             | 57344                                                          | 57344=章小佩（以上三项之和）                                                       |
|              |             | 65536  service_amulet_combine                                  | 65536=佩章属性传承，传承道具：69794、69795天玄奇书                                 |
|              |             | 131072  service_annualpk_local_promotion_match                 | 131072=跨服PK选拔赛红方报名                                                        |
|              |             | 262144  service_annualpk_local_promotion_match                 | 262144=跨服PK选拔赛蓝方报名                                                        |
|              |             | 524288  service_annualpk_local_promotion_match                 | 524288=跨服PK选拔赛观战报名                                                        |
|              |             | 1048576                                                        | 1048576=？                                                                         |
|              |             | 6291456                                                        | 6291456=外观传承/恢复=‭4194304‬+2097152                                            |
|              |             | 8388608  service_transfer_equipment_attr                       | 8388608=装备属性转移                                                               |
|              |             | 1179648                                                        | 1179648=跨服PK选拔赛红方=1048576+131072                                            |
|              |             | 1310720                                                        | 1310720=跨服PK选拔赛蓝方=1048576+262144                                            |
|              |             | 16777216  service_unique2service_battle_out                    | 16777216=传出帝子围栏                                                              |
|              |             | 234881024                                                      | 234881024=（跨服）帮战申请\报名参加帮战\报名观看帮战=‭134217728‬+67108864+33554432 |
| 第48项       | 784         | service_reset_pkvalue.has_service                              | 重置PK值？无此项=1？                                                               |
| 第49项       | 788         | service_reset_pkvalue.fee_per_unit                             | 无此项                                                                             |
| 炼器/浮台    | 792         | service_install                                                | 256=飞船                                                                           |
|              |             |                                                                | 257=装备炼器\灌注\仙符剥离=256+1                                                   |
|              |             |                                                                | 65536=陆雪琪11017？                                                                |
|              |             |                                                                | 16777216=陆吾10834？                                                               |
|              | 793         | service_uninstall                                              |                                                                                    |
| 电梯         | 804         | collision_in_server                                            | 碰撞？                                                                             |
| -            | 808         | carrier_mins[0]                                                | 下限                                                                               |
| -            | 812         | carrier_mins[2]                                                | 下限                                                                               |
| -            | 816         | carrier_mins[1]                                                | 下限                                                                               |
| +            | 820         | carrier_maxs[0]                                                | 上限                                                                               |
| +            | 824         | carrier_maxs[2]                                                | 上限                                                                               |
| +            | 828         | carrier_maxs[1]                                                | 上限                                                                               |
| 副本配置1    | 836         | id_transcription                                               | 副本配置                                                                           |
| 副本配置2    | 840         | transcription                                                  | 副本配置                                                                           |
