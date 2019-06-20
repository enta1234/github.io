---
title: "การใช้ Git เบื้องต้น #2 git branch"
date: 2017-06-15T10:10:07+07:00
draft: false
---

เอาละครับผมท่านผู้อ่านทีนี้เราจะได้รู้เรื่องของ branch กันซะทีเย้~~!
ขอเกริ่นก่อนนะครับเรื่อง branch เนียสำคัญมาก เพราะต่อไปเราจะต้องเข้ามาเกี่ยวข้องกับเรื่องของ git flow และยังเป็นข้อดีของ version control อีกด้วยเอาละถึงเวลาแล้วววว

[การใช้ Git เบื้องต้น #1 git init](/post/basic-git-1)

# รู้จัก state ของ git

  <figure class="image">
    <img src="https://git-scm.com/figures/18333fig0201-tn.png" alt="git stage">
    <figcaption> <center> ที่มา https://git-scm.com </center></figcaption>
  </figure>

  state ของ git จะถูกแบ่งออกเป็น 4 state

   - **Untrack** คือไฟล์ที่ยังไม่โดนคำสั่ง `git add`
   - **Unmodified** คือไฟล์ที่โดน `git commit` แล้ว
   - **Modified** คือไฟล์ที่โดน `git commit` แล้ว และมีการแก้ไขเกิดขึ้น
   - **Staged** คือไฟล์ที่กำลังแก้ไขอยู่(Modified) และโดน `git add` เพื่อที่จะเตรียม commit

  การทำงานไหลตามลูกศรตามภาพ `Untrack -> Unmodified -> Modified -> Staged` หลังจากที่เรา commit เราจะได้ `Unmodified` เป็นสถานะไฟล์

 # git branch ซักทีเหอะ

  ขออนุญาต ต่อจากโพสเดิมครับผม ถ้าเราใช่คำสั่ง `git status` ดูเราจะพบว่าเราอยู่ที่ master

  ![img1](/images/basic_git02/git02_01.jpg)

  ที่นี้ให้เราใช้คำสั่ง

  `git branch`

  เพื่อที่จะดูว่าเรามี branch อะไรบ้างและเช็คสถานะว่าเราอยู่ branch ไหนในขณะนี้ซึ่งตอนนี้เรามีแค่ master และอยู่ที่ master

  ![img2](/images/basic_git02/git02_02.jpg)

  ที่นี้สามารถสร้าง branch ใหม่ ด้วยคำสั่ง

  `git branch <branch_name>`

  เพิ่มทำการสร้าง branch แต่เรายังไม่ได้ย้ายไปที่ branch ใหม่นะครับ 5555+ แค่สร้างเฉยๆ เราสามารถย้าย branch ด้วยคำสั่ง

  `git checkout <branch_name>`

  ![img3](/images/basic_git02/git02_03.jpg)

  ที่นี้แหม่มันชั่งยุ่งยากเหลือเกินนนนนนน การจะสร้าง branch เนียแต่ครับทุกท่านเรามาสารถสร้างได้ด้วยคำสั่งเดียวครับ

  `git checkout -b <branch_name>`

  ที่นี้เราก็ได้เหมือนกับสองคำสั่งข้างบนเลยยยยยยยยย แหม่ง่ายจริมๆเลย 
