---
title: "การใช้ Git เบื้องต้น #1 git init"
date: 2017-06-12T01:29:05+07:00
draft: false
---


เริ่มวิธีใช้เลยนะเรื่องความมงความหมายไปหาอ่านเอาเองนะ มีคนเขียนไว้เยอะแล้วลองไปหาอ่านดูว่ามันใช้ทำอะไร หรือมันเริ่มยังไง 55555+

# Motivation

สมมุติว่าเราต้องทำงานกับเพื่อน แล้วอยู่คนละที่กันไม่อยากไปหามันบ้านไกลกันไงที่นี้ พอเรา dev งานไปมันมีไฟล์ที่เราต้องแก้หน้าเดียวกันแล้วพอเรา copy เอาไฟล์เพื่อนมามันก็ดันวางทับไฟล์ที่เราพึ่งเขียนไป อ้าวชิบหายทำไงที่นี้แม้งวางทับไปแล้ว...

# เริ่มต้นใช้ git

มาเริ่มเลย สิ่งที่ต้องมีคือ 

 - [Git](https://git-scm.com/downloads?fbclid=IwAR0lUmoFjOnW_z_BD8e_ycjiOGoY7x8gC46F09VXI857Bnltjg9ccgs6cy0) โหลดมาลงซะ

### cp1 เตรียมงานจ้ะ

เปิดใช้งาน Terninal or Command line ก่อนเลยจ้า

  ![img1](/images/basic_git/git_cmd.jpg)

ใช้ Command line เข้าไปยัง Path งานของเรา

 `_> mkdir mygit`

 `_> cd mygit`

 จะได้แบบนี้

  ![img2](/images/basic_git/git_cmd02.jpg)

ที่นี้เราจะสร้าง project git เพื่อให้ไฟล์ที่อยู่ใต้ folder นี้ถูกจัดการด้วย git ด้วยคำสั่ง

  `_> git init`

  ![img3](/images/basic_git/git_cmd03.jpg)

เราจะตรวจสอบสถานะว่า git เราพร้อมใช้งานด้วยคำสั่ง

  `_> git status`

  ![img4](/images/basic_git/git_cmd04.jpg)

เท่านี้ git เราก็พร้อมที่จะใช้งานแบ้ววววววววววววววว

---

### cp2 ใช้งานก่อนไม่รอแล้วน่าาาาาาาา

ให้เราทำการสร้างไฟล์ **README.md**

  ```
  mygit
    |- .git
    |- README.md
  ```

เราจะได้โครงสร้างโปรเจคแบบนี้แล้วนะจ๊ะะะะะ (ไฟล์ .git เป็นไฟล์ของ git เราไม่ต้องสนใจแต่ก็ไม่ได้แปลว่าไม่สำคัญ)

เปิดไฟล์ README.md ขึ้นแล้วแก้อะไรซักอย่างเข้าไป

  ![img5](/images/basic_git/git_cmd05.jpg)
  <center> <span style="color:#808080; font-size: 13px"> (<code> "_> # hello world!" > README.md </code>) </span> </center>

เราลองมาเช็คสถานะของ project เราอีกรอบ (ซึ่งเราจะต้องเช็ค `_> git status` ก่อนจะทำอะไรซักอย่างภายใน git เพื่อให้เกิดข้อผิดพลาดน้อยที่สุด)

  `_> git status`

  ![img6](/images/basic_git/git_cmd06.jpg)

เจ้า git จะบอกเราว่า เห้ยนี้คุณยังไม่ได้ commit นะ แล้วก็มีไฟล์ที่ยัง untrack ด้วยนะ

ในกรณีที่เรามีไฟล์ untrack และเราต้องการให้ git สนใจไฟล์นั้นด้วย เราจะต้องทำการ track ไฟล์เสียก่อนจ๊ะด้วยคำสั่ง

  `_> git add README.md`  หรือ   `_> git add .` (_git add ._ จะหมายถึงไฟล์ทั้งหมดที่ untrack)

  ![img7](/images/basic_git/git_cmd07.jpg)

ต่อมาใช้เราจะทำการ save file ด้วยคำสั่ง

  `_> git commit -am "init project"`

เสร็จแล้วที่นี้เราก็ init ptoject เราด้วย git เป็นอันเสร็จเรียบร้อย

ต่อไปจะอธิบายเรื่อง branch นะจ๊ะ ch#1 นี้ขอจบเท่านี้