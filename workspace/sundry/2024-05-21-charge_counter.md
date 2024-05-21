---
layout: post
title:  更改继电器次数方法
date:   2024-05-21 15:21:42 UTC+8
tags: EOL工具使用
excerpt: 请随意删除
css: ["whisper.css"]
---

<h5 class="title1">一、使用CANoe软件更改继电器次数</h5>
<!-- ============分割线分割线111=========== -->
Step 1. 唤醒kl30和kl30c电源，供电进行通信
> - 打开UNIPAS电脑右下角的PRV.RUN图标;
>> - 在弹出的窗口中选择MMView工具；
>>> - 在弹出窗口顶部输入xlv_；
>>>> - 将下图命令的数值依次改为1

<div class="centered-italic" style="text-align: center;">
    <em style="font-style: italic; color: #FF8000;">*图1*</em>
</div>

<img width="100%" src="https://pic.imgdb.cn/item/664c578ed9c307b7e952a641.png">

<div class="divider">我是分割线 :)</div>
Step 2. 打开ELOOK电脑，进入CANoe软件，唤醒电池
> - 点击左上角start;
>> - 将光标移动至钥匙门，鼠标右键点击三下；
>>> - 进入diagnose栏，对电池授权

<div class="centered-italic" style="text-align: center;">
    <em style="font-style: italic; color: #FF8000;">*图2*</em>
</div>

<img width="100%" src="hhttps://pic.imgdb.cn/item/664c5c82d9c307b7e9591440.png">

Step 3. 打开诊断界面，点击望远镜图标，搜索Aging_contactor_remaining_read

<div class="centered-italic" style="text-align: center;">
    <em style="font-style: italic; color: #FF8000;">*图3*</em>
</div>

<img width="100%" src="https://pic.imgdb.cn/item/664c6f8fd9c307b7e96e02c0.png">

Step 4. 查看当前继电器次数是否低于499800，关于条目的解释见末尾

<div class="centered-italic" style="text-align: center;">
    <em style="font-style: italic; color: #FF8000;">*图4*</em>
</div>

<img width="100%" src="https://pic.imgdb.cn/item/664c6fbdd9c307b7e96e2727.png">

Step 5. 搜索Aging_contactor_reamining_write，更改继电器次数

<div class="centered-italic" style="text-align: center;">
    <em style="font-style: italic; color: #FF8000;">*图5*</em>
</div>

<img width="100%" src="https://pic.imgdb.cn/item/664c6ff1d9c307b7e96e5837.png">

Step 6. 更改之后，使用Aging_contactor_remaining_read重新读，查看是否正确

<div class="centered-italic" style="text-align: center;">
    <em style="font-style: italic; color: #FF8000;">*图6*</em>
</div>

<img width="100%" src="https://pic.imgdb.cn/item/664c6fbdd9c307b7e96e2727.png">

<div class="divider">我是分割线 :)</div>

Step 7. 确认更改成功后，进行下电
> - 光标移动至钥匙门，鼠标左键点击三下;
>> - 将点击stop；
>>> - 回到UNIPAS电脑，查看低压电流是否降为0；
>>>> - 电流降为0后，顺序依次点击3093→3094→3095，将弹出框的数值由1改为0

<div class="centered-italic" style="text-align: center;">
    <em style="font-style: italic; color: #FF8000;">*图7*</em>
</div>

<img width="100%" src="https://pic.imgdb.cn/item/664c7073d9c307b7e96ee6e7.png">

<div class="divider">我是分割线 :)</div>
<!-- ============分割线分割线111=========== -->
<h5 class="title1">二、关于继电器次数的解释说明</h5>
<p>* Curret switch cycles precharge 1: 对应下拉选项中的pack1_precharg</p>
<p>* Curret switch cycles positive 1: 对应下拉选项中的pack1_postive</p>
<p>* Curret switch cycles negative 1: 对应下拉选项中的pack1_negative</p>
<p>* Curret switch cycles precharge 2: 对应下拉选项中的pack2_precharge</p>
<p>* Curret switch cycles positive 2: 对应下拉选项中的pack2_positive</p>
<p>* Curret switch cycles negative 2: 对应下拉选项中的pack2_negative</p>
<p>* Curret switch cycles postive OBC: 对应下拉选项中的AC_charge_positive</p>
<p>* Curret switch cycles negative OBC: 对应下拉选项中的AC_charge_negative</p>
<p>* Curret switch cycles negative DCB: 对应下拉选项中的DC_charge_positive</p>
<p>* Curret switch cycles negative DCB: 对应下拉选项中的DC_charge_negative</p>

<div class="divider"></div>

<p class="s-footer">🍍</a> 代码是我生命的一部分，但咖啡是我的灵魂。</p>

*---Created by Wang Xiaoli*
<!-- <p>请随意删除。 feel free to delete this page. add by wangxiaoli</p> -->
