# zhaojiafutheos

# 项目介绍
自己学习跟着沐阳大佬（后面统称阳哥）学习iOS逆向，其实从学习theos之后，就一直想自己写个越狱插件，达到安卓的xposed 通用hook的效果。
后面学习完之后，这几天正好有时间，其实之前学习过程中写了一部分，这几天又花时间补充补充hook点，优化优化，完善我的这个theos tweak插件。
其实沐阳大佬也有《iOS逆向助手》，但是我就想写一个自己的越狱插件。结合电脑直接通过关键词根据日志来过滤使用。
沐阳大佬的《iOS逆向助手》：https://mp.weixin.qq.com/s/RJaCx5TifU8Z8cwXvPWWiw
我这个只能阳哥《iOS逆向助手》的丐版，不喜轻喷，哈哈
其实之前没有想着公开，因为最初阳哥的这个《iOS逆向助手》需要激活码，我这个通用加密部分功能有些类似，不太适合放出来。
经过我最近优化和实战测试，我觉得我的这个插件配合mac的控制台、终端或者Ubuntu的终端，根据 zhaojiafutheos 搜素日志来过滤hook点比较方便。
看个人使用习惯来吧。

插件短时间不会投入过多时间了，后面主要投入到找工作中，多花时间看些之前的学习过的技术栈知识。 
好好准备面试，年后找个工作再说。




# 越狱插件的使用

需要设备：无根越狱手机【有根的我没有研究，手机没有这种iphone手机】
需要安装：ellekit、altlist、preferenceLoader。
还需要沐阳大佬的muyangdemo.ipa app： 沐阳大佬的《iOS逆向助手》：https://mp.weixin.qq.com/s/RJaCx5TifU8Z8cwXvPWWiw   文章有下载地址。

## 安装

ssh连接可以使用finalshell，我个人喜欢用这个，连接服务器和iPhone都方便。（用自己顺手的都行）

ssh连接到设备，文件传到之后：dpkg -i com.zhaojiafu.zhaojiafutheos_0.0.1-5+debug_iphoneos-arm64.deb


## 简单使用：

然后手机打开设置：找到 zhaojiafutheos

![](./assets/README-1736396846011.png)

![](./assets/README-1736470876246.png)


![](./assets/README-1736403754528.png)



点进去，打开需要hook的加密类型：

比如，进入解密的应用列表，勾选muyangdemo app
勾选需要hook的加密算法。比如我全部勾选上。
进入muyangdemo app。
记得先终端搜素日志：idevicesyslog | grep zhaojiafutheos
也可以mac控制台输入 zhaojiafutheos


## 通用加解密 hook

### md5 hook
按CC_MD5，
![](./assets/README-1736401209272.png)


### sha256：(sha1、sha224、sha384、sha512同理)
![](./assets/README-1736401329259.png)


### CChmac sha256：
![](./assets/README-1736401389220.png)


### RSA：

加密：
![](./assets/README-1736401478527.png)

解密：
![](./assets/README-1736401524250.png)


### AES加解密hook
![](./assets/README-1736402139798.png)



### DES加解密 hook

![](./assets/README-1736402204561.png)





## 过代理检测

选择应用，关键代码定位的应用列表里面选择需要过代理的app

比如还是muyangdemo，网络相关里面的代理检测。

不勾选代理之前：

![](./assets/README-1736402596516.png)



勾选之后：检测不到代理了。

日志也是有的：
![](./assets/README-1736402510613.png)


![](./assets/README-1736402546051.png)




# 给自己打个小广告【有没有杭州大佬需要爬虫相关岗位的，求内推】

最近一年多公司经济困难，发不出来工资了，经济裁员，目前待业，如果有杭州的大佬有需要爬虫和数据采集相关岗位的小弟，欢迎内推！
csdn博客：https://zhaojiafu.blog.csdn.net/?type=lately
之前常用，csdn最近也很少更新了，都用语雀和星球记录一些知识点替代了。

## 目前具备的能力或者之前学习过的逆向技术栈：

> 1.Web js爬虫：（2024上半年）搞过rs 6代cookie反爬、dy web视频关键词搜索、极验滑块3、4代js逆向；熟练python selenium、playwright浏览器自动化脚本开发；
> 
> 2.iOS逆向：熟悉iPhone手机越狱、砸壳、抓包、frida hook、frida rpc、frida hook结合IDA静态分析、theos越狱插件开发。
> 
> 3.Android逆向：熟悉小米（pixel）手机root、抓包、脱壳（frida-dexdump脱壳、自己定制pixel3 fart 定制rom脱壳机）、frida hook、frida rpc、熟悉Xposed插件开发、了解unidbg模拟执行so。
> 
> 4.验证码：之前学习过pytorch，并训练过通用过英文数字模型，yolo学习训练过滑块缺口识别模型
> 
> 5.浏览器定制chromium：之前（2023年下半年）学习并编译过一个103版本，可以随机canvas、webgl、audio、css指纹；定制编译chromedriver去除版本校验，可以自适应chrome浏览器版本，配合selenium RPA使用。

由于爬虫相关js逆向、安卓逆向、ios逆向涉及的知识点过多，如果面试准备不到位的或者遗漏的，加上本人容易紧张，一紧张还容易会的回答不好，还希望大佬海涵。

安卓和iOS逆向大多数都是近一俩年抽时间学习的，所以工作中还没有太多应用，不过都熟悉了逆向的流程，遇见新的app也有思路去一点一点去分析。

如果有正好满足的岗位或者我进去后再努力努力还能达到要求的岗位，欢迎内推！本人也很愿意学习的，有挑战才有进步和收获。

本人wx:Z530519174，欢迎大佬内推，我去给大佬当小弟！有年后打算招人的，可以联系我要详情简历，也可以先年前面试，ok的话可以年后入职。（个人微信，非诚勿扰，谢谢，大佬还望备注来意，省的错过大佬）
【涉及黑灰相关的算了，小弟胆子小，别钱没挣到人搞进去了，小弟也没这个本事】


















