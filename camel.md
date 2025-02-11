![image-20241115093310322](https://cdn.jsdelivr.net/gh/Ds0305/image/image-20241115093310322.png)

1.申购

申购-approve

![image-20241115094708019](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241115094708019.png)

申购-成功

![image-20241115094321750](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241115094321750.png)

申购失败——USDC不足

2.赎回

**链上**

赎回-approve

![image-20241115094427263](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241115094427263.png)

赎回-成功

![image-20241115094356884](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241115094356884.png)

赎回-失败

上链失败

发送钱包，在消息上链过程中

余额不足

![image-20241115102442805](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241115102442805.png)

**链下**？

合约号

成功

![image-20241115094458093](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241115094458093.png)

失败

------

![image-20241115115252137](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241115115252137.png)



接口，不消耗gas![image-20241115115331626](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241115115331626.png)

通过白名单哪里操作？———add操作

apply allowlist重复申请toast？

allow list在多签等待确认 toast？——message消息列表确认多签





![image-20241115152150445](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241115152150445.png)

 测试数据

845 最低100 第二次输入100

amount： 800  approval

 11.22

USDC Balance

1923132≈$122

token name=Pac Money Market Fund

total

所有待赎回——claim

所有待申购——claim 



f189

contact us？

apply KYC——KYC列表

![](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241122150016356.png)

成功后，KYC列表仍有这条数据

apply allowList

cmmf

success 

claim 109CMMF

redeem

![image-20241122163320262](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241122163320262.png)

1. 申购/赎回成功、失败的toast， claim的toast（
2. apply allowlist 重复申请的toast，以及在等待多签确认时重复申请的toast
3. 金额输入不在范围内，提示一下，不要主动修改到最小或最大（小于最小值或大于最大值，直接置灰）



疑问：

Address模块添加地址什么作用，相当于添加用户？verified标签？什么条件才是verified



新加入钱包地址流程

1.Apply KYC

投资人：apply KYC

个人中心页的Account Setting模块-apply KYC ——填写信息后——“KYC in verification process”

主页以及产品页的申购、赎回模块-contact us to get access——填写信息后——“KYC in verification process”

管理端：KYC List

新增一条数据——yes or no

no投资人-KYC in verification process

yes投资人-个人中心不会出现apply kyc，且申购模块出现apply allowlist

2.apply allowlist

投资人：申购、赎回apply allowlist

管理端：进入对应产品模块的allow list——add（add allowlist的数据列表排序方式）——选中数据添加——需要完成message模块的多签流程 ：confrim（1 of 2）——>Excute

message模块——EventType:ALLOWLIST_ADD

什么条件会触发1 of 2？角色权限有关？

【测试环境——可以完成多签操作角色有566a、2193】

以上操作完成加入白名单

投资人个人中心页 ——address模块出现对应产品名称标签

申购——subscribe、redeem

首次输入amount后，approve——subscribe/redeem

3.链上申购

4.设定价格 set Price——>产生Price ID

管理端

- Price Update模块_Add Last Price 完成设定价格
- Message模块完成price_add多签

 5.Bind Deposit IDs with Price ID 将？与价格绑定

Issuance_confirm——message_多签

6.claim 

投资人_个人中心页对应产品

![image-20241125161419290](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241125161419290.png)

链下申购流程【仅支持一种方式——管理端】

管理端Off Chain 模块_Contract ID

1.添加合同编号

![image-20241125162557887](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241125162557887.png)

2.Active 使合同生效

![image-20241125163352113](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241125163352113.png)

3.完成多签（Off Chain点击status可跳转到message页）

Active新增一条数据

Message新增一条数据

![image-20241125165758518](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241125165758518.png)

4.完成多签操作后，（与链下赎回不同的是，完成多签操作相当于完成链下申购操作）

![image-20241125170204411](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241125170204411.png)

![image-20241125170434881](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241125170434881.png)

以及投资人个人中心页

![image-20241125170312507](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241125170312507.png)

链下赎回：（有两种方式）

**Agent Redeem——管理端操作**

1.contract ID创建合同

2.Active使合同生效【关键一步】

3.完成多签操作

4.Contract ID 查看Used状态—>yes

Records_Records List 选择Agent Redeem查看新增数据

**Investor Redeem——结合投资人赎回页操作**

1.管理端_contract ID创建合同

2.投资人页完成链下赎回

![image-20241125175134984](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241125175134984.png)

![image-20241125175508119](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241125175508119.png)

3.投资人中心页查看新增数据

![image-20241125175748315](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241125175748315.png)

Contract ID_Used状态发生变化_yes

Records_Investor Redeem 新增一条数据

![image-20241125180005237](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241125180005237.png)

查看投资人个人中心页数据变化？

链下赎回 Agent方式不会显示，仅显示invest方式赎回

record会记录all方式



1，这周末发一个版本；每周迭代一个版本，12月第三周末全部ready；
2，部署脚本要准备好；
3，需要部署到Hashkey Chain，产品名称HMMF，1月1日正式上线；
4，CMMF，ETH链，1月底正式上线；
5，HMMF，需要部署到hashkey测试链测试；
6，需要验证hashkey chain对subgraph自建节点的支持；
~~7，一层产品，白名单之间可以互相发送token，新需求迭代；（新功能，暂不处理）~~
8，新UI改动。



11.26

1. 熟悉管理端

   - [x] 白名单列表

   - [x] 价格更新+发行
   - [x] 链下

2. 熟悉新UI，准备测试

3. 熟悉notion的文档 角色权限

11.27

hash链测试网全功能测试

Apply KYC

测试数据:hashkey chain_test-001

管理端：KYC List_add

![image-20241127104307210](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241127104307210.png)

更改后

![image-20241127144038351](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241127144038351.png)

0xE72bCDA3dc1A79C6b03Af62d4851B33bCF928F08

对应私钥：21c4c9fcf706019e79446c65ceafbac5ee9cc611451d314bebbe2355028c7370

管理端添加产品后，投资人个人中心页

![image-20241127181623660](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241127181623660.png)

2024.12.2周任务

1. camel-UI  设计：图片不清晰、布局是否合理（边距） 如何查看边距
2. 复测v2版本问题
3. 下周开始hashkey链测试任务  这周完全熟悉投资人（星期一、星期二），管理端（星期三、星期四、星期五）
4. 投资人：首页、产品详情页、个人中心页

明天任务：

投资人个人中心

首页UI复测

管理端问题

UI-弹窗

### 3. 不可被忽视的几个弹框细节

- 尽量避免弹窗上叠加弹窗
- 弹出弹窗时锁定背景页面，禁止跟随弹窗滚动
- 原路返回，由哪个页面弹出弹窗，关闭弹窗后显示哪个页面

#### 更新白名单

![image-20241203150822051](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241203150822051.png)

 KYC钱包地址

![image-20241203155608743](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241203155608743.png)

更新白名单的地址要求：？

**更新白名单流程：投资人：个人中心Manage_Update  AllowList—>管理端：Allow List_Update List 两个操作Agree_Yes、Action _Update,完成多签操作**

**Old Address 保留时间7*24h**

![image-20241203162951336](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241203162951336.png)

#### 多签拒绝流程？



暂停申购赎回（前端）

输入框、按钮

![image-20241209105733863](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241209105733863.png)

![image-20241209110955920](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241209110955920.png)

链下赎回

![image-20241209111206608](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241209111206608.png)

多签消息时1 of 2如何触发？根据多签类型EventType？

？

申购时，1USDC=1.5 PacMMF ——>赎回时，1PacMMF=0.6666

切换链，不会退出登录~

用户签名

safe测试

多链切换管理端测试

自然月

**产品支持链的情况**

CMMF4仅支持hashkey

PacMMF支持sepolia

dCMMF2仅支持sepolia

notion 密码 同qq；只是账号名称是邮箱，并不是邮箱的密码，涉及notion用的notion密码

hashkey链-投资人端-测试点

2.nowPrice价格、以及price24h与管理端是否一致（**且与交易窗口的redeem设定的价格一致**）

![image-20241213154705908](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241213154705908.png)

流程：

1.断开钱包状态下（不同链产品按钮状态均一样）

![image-20241213155634516](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241213155634516.png)

2.连接钱包后，**默认选择上一次使用的链**

不同产品按钮展示和数据展示

**支持：按钮为授权**

**不支持：按钮为切换链**

![image-20241213160900798](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241213160900798.png)

3.【一次】授权签名后，（钱包地址未通过KYC）按钮展示

![image-20241213161550163](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241213161550163.png)

已经经过“授权签名”，此时切换链，也是相同按钮，**不需要多次登录（即授权签名）**

![image-20241213161830102](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241213161830102.png)

即当钱包地址未通过KYC时，状态是一致，首先需要通过KYC认证

![image-20241213153044918](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241213153044918.png)

4.申请KYC

![image-20241213162943326](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241213162943326.png)

注：当前链为HashKey链时，此时切换到sepolia链时，PacMMF按钮展示同上

管理端：首页-KYC List，完成通过KYC后

投资人

![image-20241213163717327](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241213163717327.png)

注：此时，PacMMF按钮为切换链，切链后，按钮展示同上

![image-20241213164002570](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241213164002570.png)

![image-20241213164116196](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241213164116196.png)

5.申请支持HashKey链产品的白名单

涉及管理端操作，在管理端首页-Product，点击对应产品，会弹出切换链弹框

![image-20241213154005059](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241213154005059.png)

切换到HashKey链后，再次点击对应产品，不会有弹窗

6.通过白名单——566a

![image-20241213170124051](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241213170124051.png)

![image-20241213170210708](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241213170210708.png)

![image-20241213165638699](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241213165638699.png)

**Address 输入测试**

1.输入新地址（未使用过的地址） 
2.自己账户地址
3.其他白名单地址
4.黑名单地址 
5.其他用户下未校验的地址
6.新地址在白名单变更中
7.新地址在kyc 中

更新白名单基本测试点![image-20241216141742322](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241216141742322.png)

任务：

~~赎回、链下赎回、~~链下申购

客户反馈问题：

重要（未核对）

![image-20241217182802551](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241217182802551.png)

细节修改（low）

![image-20241217185738653](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241217185738653.png)

**更新白名单**

**添加地址**

> HashKey：
>
> 导入代币：
>
> 1. USDC_HashKey  0x703A0B94A49F765107e3e4abEB4FC3E5bac7248f
> 2. HskCMMF             0xBdcfF9B1254B47104Bb1F7be9Ba85833293fe660
> 3. 领取HashKey测试币 https://hsk.xyz/faucet

测试更新白名单

0x7F6dC731B1906E6e20d79DE942eD0f3Fd10C98Ee 已经通过KYC，通过Pac、dcMMF2的白名单

0xA97314268d104A44B99e14fB5fc5aBf9869A860d   KYC中

![image-20241216151215539](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241216151215539.png)

0x0938B964E7FF66bb0B20C53e13b31C782FDCB124   已校验地址 【授权=已校验】

0x871a4456f7A0407257f7dfAeB56de4F887aA4420  未授权——>success

![image-20241216152316410](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241216152316410.png)新地址在白名单（使用过）/黑名单（使用过）/注册过（可以）/有白名单变更记录（已经作为新地址在变更中-可添加成功？id为2754）/有白名单变更记录（新地址被使用过）/kyc 为no

新地址授权过（即登录过） 已测 提示信息

新地址在对应产品的白名单，主要测试hashkey产品

黑名单

> **白名单变更记录（已经作为新地址在变更中-可添加成功）——提示信息：success**
>
> ![image-20241216193238673](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241216193238673.png)
>
> **再次提交该地址？**
>
> ![image-20241216193001080](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241216193001080.png)



新地址KYC为NO,kyc之前就要授权（此时就是被使用过了）提示：be used

白名单，kyc 为no(kyc 不通过)

可能影响白名单更新因素：是否授权签名（即登录过）、KYC状态、是否在白名单、是否在黑名单、是否有白名单更新记录（在变更中、变更过的记录）

测试方向 新地址、旧地址

| 影响因素                    | 旧地址 | 新地址 | 提示信息 |
| :-------------------------- | ------ | ------ | -------- |
| 是否授权签名                |        |        |          |
| KYC状态                     |        |        |          |
| 是否在白名单内              |        |        |          |
| 是否在黑名单（BlockList）内 |        |        |          |
| 是否在白名单变更中          |        |        |          |
| 是否有白名单变更记录        |        |        |          |
| 未校验地址                  |        |        |          |
|                             |        |        |          |
|                             |        |        |          |

| 新地址影响因素             | 新地址，旧地址（保证有更新白名单按钮） | 提示信息 |      |
| -------------------------- | -------------------------------------- | -------- | ---- |
| 1.授权登录过？             |                                        |          |      |
| 2.自己账户地址？           |                                        |          |      |
| 3.白名单地址？             |                                        |          |      |
| 4.黑名单地址？             |                                        |          |      |
| 5.其他用户下未校验地址？   |                                        |          |      |
| 6.在白名单变更中           |                                        |          |      |
| 7.有过白名单变更记录       |                                        |          |      |
| 8.在KYC中                  |                                        |          |      |
| 9.已经通过KYC，更改KYC状态 |                                        |          |      |

> 什么情况下不会有白名单更新按钮：
>
> 1. 新注册的地址没有授权登录过
>
> 2. 没有申请KYC，申请过程中（KYC in procession）0xA97314268d104A44B99e14fB5fc5aBf9869A860d
>
> 3. 申请被拒绝；申请通过后，修改KYC状态为NO（此时还没加入某产品白名单）
>
> 4. 未申请过任何产品的白名单，以及通过【 Add Address】加入一个已经是所有产品的白名单的用户
>
> 5. 申请产品白名单后，修改KYC状态、旧地址白名单变更中？
>
>    ![image-20241217114234057](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241217114234057.png)
>
>    测试：旧地址在白名单变更中？如下地址就是在白名单变更中
>
>    0x871a4456f7A0407257f7dfAeB56de4F887aA4420
>
>    ![image-20241217115320774](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241217115320774.png)
>
>    **可以查看产品信息，但不能授权登录，更加不能进入个人中心页，即旧地址在白名单变更中，此时不能再进行白名单变更**
>
>    但新地址在白名单变更中，可以进行白名单变更（第一次提交提示信息为success），第二次提交
>
>    1.输入新地址（未使用过的地址） 
>    2.自己账户地址
>    3.其他白名单地址
>    4.黑名单地址 
>    5.其他用户下未校验的地址
>    6.新地址在白名单变更中
>    7.新地址在kyc 中
>

![image-20241217103406265](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241217103406265.png)

![image-20241217103445494](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241217103445494.png)

新地址在白名单（使用过）/黑名单（使用过）/注册过（可以）/有白名单变更记录（已经作为新地址在变更中-可添加成功？id为2754）/有白名单变更记录（新地址被使用过）/kyc 为no

旧地址刚注册（不在白名单）/ 新地址，没注册（不在白名单）/白名单，kyc 为no(kyc 不通过)/有白名单变更记录（旧地址变更中）/合约系统地址不可更新（提示找不到）

> **更新白名单的时候这个toast是什么意思？**
>
> **以及，我更新的时候可以直接填入一个本身不在白名单中的地址？**
>
> 1. 提示的意思是：新地址或者旧地址已经申请过白名单更新
>
> 2. 更新的时候不要求新地址必须是白名单（管理端更新流程中，会将新地址加入白名单）
>
> **更新白名单后，原地址的产品份额会自动转移至新地址吗？**
>
> **以及新地址无法操作原地址未进行的操作（比如原地址还有没claim的）**
>
> 投资人发起白名单更新这一操作，仅是发起一个请求，管理员需要在管理端进行审核以及白名单流程变更，变更完成后，原地址对应的份额才会转移，新地址才可以操作原地址未进行的操作

------

任务：

~~赎回、链下赎回、~~链下申购

客户反馈问题（进行中的问题+4，）

**更新白名单**

**添加地址**

> HashKey：
>
> 导入代币：
>
> 1. USDC_HashKey  0x703A0B94A49F765107e3e4abEB4FC3E5bac7248f
> 2. HskCMMF             0xBdcfF9B1254B47104Bb1F7be9Ba85833293fe660
> 3. 领取HashKey测试币 https://hsk.xyz/faucet

测试更新白名单

0x7F6dC731B1906E6e20d79DE942eD0f3Fd10C98Ee 已经通过KYC，通过Pac、dcMMF2的白名单

0xA97314268d104A44B99e14fB5fc5aBf9869A860d   KYC中

![image-20241216151215539](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241216151215539.png)

0x0938B964E7FF66bb0B20C53e13b31C782FDCB124   已校验地址 【授权=已校验】

0x871a4456f7A0407257f7dfAeB56de4F887aA4420  未授权——>success

![image-20241216152316410](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241216152316410.png)新地址在白名单（使用过）/黑名单（使用过）/注册过（可以）/有白名单变更记录（已经作为新地址在变更中-可添加成功？id为2754）/有白名单变更记录（新地址被使用过）/kyc 为no

新地址授权过（即登录过） 已测 提示信息

新地址在对应产品的白名单，主要测试hashkey产品

黑名单

**白名单变更记录（已经作为新地址在变更中-可添加成功）——提示信息：success**

![image-20241216193238673](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241216193238673.png)

**再次提交该地址？**

![image-20241216193001080](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241216193001080.png)

新地址KYC为NO,kyc之前就要授权（此时就是被使用过了）提示：be used

白名单，kyc 为no(kyc 不通过)

------

![image-20241217190958214](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241217190958214.png)

![image-20241218094637678](C:\Users\19414\AppData\Roaming\Typora\typora-user-images\image-20241218094637678.png)

不同地址（Old Address）对同一地址（New Address）进行同一产品的白名单变更

注：New Address-4220已经作为新地址在白名单变更中

0x871a4456f7A0407257f7dfAeB56de4F887aA4420

私钥：70e2457750e7ea596326c4b7172732182c5691b85c6fea6c5fcbac9c95fef512

而且提示【新地址或旧地址有变更】就说明其中有个地址已经处于白名单变更中（现在4460就是那个地址），那其他用户对4460进行白名单变更第一次提交怎么提示成功呢？而不是提示【新地址或旧地址有白名单变更记录】，而且我测试过，出现这个提示，一般是我提交成功后重复提交这个申请，才会出现这个提示（566a除外，我第一次提交就出现这个提示）

白名单变更中

0x6327e5AA144C698f39884e5ab072415419415452



![](https://cdn.jsdelivr.net/gh/Ds0305/image_cut/20241219144740.png)

![image-20241223144657365](camel.assets/image-20241223144657365.png)

![image-20241223144746477](camel.assets/image-20241223144746477.png)

![image-20241223144810512](camel.assets/image-20241223144810512.png)

![image-20241223144847916](camel.assets/image-20241223144847916.png)

![image-20241223145005433](camel.assets/image-20241223145005433.png)

pacmmf coming soon 

1. 未开始的产品详情页不能点进详情页
   - 首页顶部/底部菜单栏-Product隐藏未开始产品按钮
   - 点击卡片任意处不能进入产品详情页
   - 产品展示位的tab不能选中未开放产品，且左右滑动不能滑到未开放产品
2. 增加 coming soon 提示（下面两处地方有coming soon提示）
3. Not  Started 按钮展示？

<img src="camel.assets/image-20241224100250356.png" alt="image-20241224100250356" style="zoom: 67%;" />

疑问：默认选中第一个tab，产品排列顺序是否会有变化？那么若此时PacMMF设置不开放，是否会出现tab对应不上

nowprice-当前价格

price24h：24小时价格变化

![image-20241224105243865](camel.assets/image-20241224105243865.png)

![image-20241224105438133](camel.assets/image-20241224105438133.png)

![image-20241224110413860](camel.assets/image-20241224110413860.png)

