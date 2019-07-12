---
title: "[Git Flow] git แบบ flow flow"
date: 2019-04-10T16:11:53+07:00
draft: false
---

หลังจากที่เราใช้ git ไปซักพักแล้วเราคงน่าจะเคยใช้ [sourcetree](https://bitbucket.org/product?&aceid=&adposition=1t1&adgroup=53586430497&campaign=1074155406&creative=270475854472&device=c&keyword=source%20tree&matchtype=e&network=g&placement=&ds_kids=p33403147979&ds_e=GOOGLE&ds_eid=700000001551985&ds_e1=GOOGLE&gclid=EAIaIQobChMI652b4-ir4wIV1QorCh0X9QlzEAAYASAAEgI6RfD_BwE&gclsrc=aw.ds) ที่เป็น GUI ที่นิยมมากในระดับหนึ่งของเอ้าแล้วถ้าเราอยากจะใช้ command ละหรือ ไม่อยากใช้ GUI ช่วยทำไงดี นั้นสินะ

# เข้าใจเรื่องของ branch
  หลักๆของ git flow จะมี

  - master
  - develop
  - feature/\<name>
  - release/\<name>
  - hotfix/\<name>

## develop & feature

![img1](/images/git_flow/git-flow01.png)

  จากรูปเมื่อเราเริ่ม git flow เราจะแตกออก master ไปยัง develop
  **กฏมีอยู่ว่าเราจะไม่แก้ไฟล์ที่ master** โดยตรงแต่เราจะทำงานที่ develop โดยการแก้ไข้ให้แตก feature ออกมาและแก้ที่ feature เอาเมื่อเราปิด feature จะถูก merge เข้าที่ develop *(feature ควรเป็นงานเล็กเพื่อง่ายต่อการปิด branch ในแต่ละวัน)*

## release

![img2](/images/git_flow/git-flow02.png)

  เมื่อเราทำ feature เสร็จแล้วและต้องการที่จะเปิด version เราจะทำ release ซึ่งจะแตกออกจาก develop และเมื่อปิด release จะถูก merge เข้า master และ develop และจะถูกติด tag ตามชื่อ release (*กฏคือในขณะเวลาหนึ่ง release ควรมี 1 เท่านั้น*)

## hotfix

![img3](/images/git_flow/git-flow03.png)

  ถ้าเกิดเรามี bug ที่ master หรือ production เราสามารถแตก hotfix ขึ้นมาแก้และเมื่อปิดจะกลับไปยัง master และ develop 

# สรุป

  เราควรออกแบบรูปแบบของ git flow ตามงานหรือ Project นั้นๆและต้องคุยกับคนในทีมก่อนนะ 5555+ จะได้เข้าใจตรงกันและลดการ conflicts ของไฟล์ 
