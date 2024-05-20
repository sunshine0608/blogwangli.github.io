---
layout: post
title:  iperf3使用方法
date:   2024-05-20 10:44:42 UTC+8
tags: EOL工具使用
excerpt: 请随意删除
css: ["whisper.css"]
---

<h5 class="title1">一、在Elook电脑和UNIPAS电脑上使用iperf3工具检测网络连接的方法</h5>
<!-- ============分割线分割线111=========== -->
Step 1.  在开始检测之前，请确保位于ELOOK电脑上的CANoeautomation.exe程序处于开启状态，如下图所示：
> - 若未开启，双击打开下图1文件;
>> - 弹出图2窗口，显示所有端口连接成功.


<style>
    .centered-italic {
        text-align: center;
        font-style: italic;
    }
</style>
<div class="centered-italic"><span style="color:red">
    *图1*
</div></span>

![图1](.\\iperf3\\iperf_0.png "相对路径演示,下一级目录")

<!--...会写相对路径就行 -->
<style>
    .centered-italic {
        text-align: center;
        font-style: italic;
    }
</style>
<div class="centered-italic"><span style="color:red">
    *图2*
</div></span>

![图1](.\\iperf3\\iperf_01.png "相对路径演示,下一级目录")
<div class="divider">我是分割线 :)</div>
<!-- ============分割线分割线=========== -->
Step 2.  打开ELOOK电脑上的iperf3工具，位置如下图3所示：
<!--...会写相对路径就行 -->
<style>
    .centered-italic {
        text-align: center;
        font-style: italic;
    }
</style>
<div class="centered-italic"><span style="color:red">
    *图3*
</div></span>

![图1](.\\iperf3\\iperf_1.png "相对路径演示,下一级目录")
Setp 3. 进入文件夹之后，在文件夹路径中输入“cmd”打开终端窗口:
<style>
    .centered-italic {
        text-align: center;
        font-style: italic;
    }
</style>
<div class="centered-italic"><span style="color:red">
    *图4*
</div></span>

![图1](.\\iperf3\\iperf_2.png "相对路径演示,下一级目录")
Step 4. 在命令行中输入“iperf -s”，表示ELOOK这边已开启监听状态：
<style>
    .centered-italic {
        text-align: center;
        font-style: italic;
    }
</style>
<div class="centered-italic"><span style="color:red">
    *图5*
</div></span>

![图1](.\\iperf3\\iperf_3.png "相对路径演示,下一级目录")
<div class="divider">我是分割线 :)</div>
<!-- ============分割线分割线=========== -->
Step 5. 回到UNIPAS电脑，同样打开iperf3工具：
<style>
    .centered-italic {
        text-align: center;
        font-style: italic;
    }
</style>
<div class="centered-italic"><span style="color:red">
    *图6*
</div></span>

![图1](.\\iperf3\\iperf_4.png "相对路径演示,下一级目录")
Step 6. 输入下图所示的命令，关于命令的详细说明见*末尾*，以UNIPAS电脑作为服务端向ELOOK电脑随机发送pakages，观察运行完成后的LOST：
<style>
    .centered-italic {
        text-align: center;
        font-style: italic;
    }
</style>
<div class="centered-italic"><span style="color:red">
    *图7*
</div></span>

![图1](.\\iperf3\\iperf_5.png "相对路径演示,下一级目录")
Step 7. 回到ELOOK电脑，观察运行完成后的LOST：
<style>
    .centered-italic {
        text-align: center;
        font-style: italic;
    }
</style>
<div class="centered-italic"><span style="color:red">
    *图8*
</div></span>

![图1](.\\iperf3\\iperf_6.png "相对路径演示,下一级目录")

<div class="divider">我是分割线 :)</div>
<!-- ============分割线分割线=========== -->
<h5 class="title1">二、关于LOST的解释说明</h5>
<!-- ============分割线分割线111=========== -->
情况1. LOST为0，代表UDP协议下的无线连接较为稳定。此时可以直接复测。
情况2. LOST不为0，代表有一定丢包率，此时无线连接不稳定。不稳定的原因可能为UDP协议本身需要进一步优化，也可能是网段受到其他信号的干扰导致信息传输有一定丢失。此时可以尝试重启通信程序（CANoeautomation.exe），查看LOST是否降低，再复测。
情况3. 键入命令无法运行，此时代表UNIPAS主机和ELOOK主机之间无法pin通，即使处于同一网段。这种情况复测多少次都不会解决报错，需要检查物理连接，即绿色网线。

<div class="divider">我是分割线 :)</div>
<!-- ============分割线分割线=========== -->
<h5 class="title1">三、关于iperf命令行的解释说明</h5>
<p>-f: [k|m|K|M] 分别表示以Kbits, Mbits, KBytes, MBytes显示报告，默认以Mbits为单位,eg:iperf -c 222.35.11.23 -f K</p>
<p>-i: sec 以秒为单位显示报告间隔，eg:iperf -c 222.35.11.23 -i 2</p>
<p>-l: 缓冲区大小，默认是8KB,eg:iperf -c 222.35.11.23 -l 16</p>
<p>-m: 显示tcp最大mtu值</p>
<p>-o: 将报告和错误信息输出到文件eg:iperf -c 222.35.11.23 -o c:\iperflog.txt</p>
<p>-p: 指定服务器端使用的端口或客户端所连接的端口eg:iperf -s -p 9999;iperf -c 222.35.11.23 -p 9999</p>
<p>-u: 使用udp协议</p>
<p>-w: 指定TCP窗口大小，默认是8KB</p>
<p>-B: 绑定一个主机地址或接口（当主机有多个地址或接口时使用该参数）</p>
<p>-C: 兼容旧版本（当server端和client端版本不一样时使用）</p>
<p>-M: 设定TCP数据包的最大mtu值</p>
<p>-N: 设定TCP不延时</p>
<p>-V: 传输ipv6数据包</p>

<div class="divider"></div>

<p class="s-footer">🍍</a> 代码是我生命的一部分，但咖啡是我的灵魂。</p>

*---Created by Wang Xiaoli*
<!-- <p>请随意删除。 feel free to delete this page. add by wangxiaoli</p> -->
