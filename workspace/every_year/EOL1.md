---
layout: page
title:  EOL1问题解决
date:   2024-05-28 10:54:42 UTC+8
tags: EOL硬件问题
excerpt: 请随意删除
css: ["whisper.css"]
---

<!-- 注释：修改文字部分即可，不要修改其他带有<>的东西 --> 
<h4>1.1. Error messages and Explanation</h4>
<hr class="docutils" />
<dl class="simple">

 
<dt><em><b>40802-410 set battery run mode failed</b></em></dt><dd><p>
    问题：否<br>
    短期措施：设置电池run模式失败.<br>
    根本原因：使用RPV.RUN程序手动设置电池进入run模式，查看CANoe界面电池信息是否正常.<br>
    长期措施：BMS系统中出现0c7800和293100的报错，发现电池无法闭合继电器。更换IMD后返线.</p>
</dd>
<dt><em><b>UNIPAS, Error on plug 3
Aulos: low coolant flow, code, A 0593 </b></em></dt><dd><p>
    问题：否<br>
    短期措施：清理冷却管路，内循环清理，无法彻底解决问题.<br>
    根本原因：冷却水脏.<br>
    长期措施：定期清洁.</p>
</dd>
