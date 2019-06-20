---
title: "[basic_docker] | เจ้า docker ปลาตัวน้อย"
date: 2019-03-13T17:00:17+07:00
draft: false
---

  >docker เป็น software container ทำงานได้รวดเร็ว ลดขั้นตอนการติดตั้ง os ลง โดยเปลี่ยนเป็น **image file** ให้เรียกใช้ได้ง่ายขึ้น เมื่อสั่งให้ images ทำงาน จะเปลี่ยนสถานะเป็น **container** และสามารถติดตั้ง application server ก็สามารถทำได้ง่ายเพราะ docker มีลักษณะเป็น **infrastructure-as-code** (image >> container)

  [อ่านเพิ่มเติมได้ที่](https://github.com/enta1234/docker-cp)

## basic command

<table border="1">
  <tr>
    <th> command </th>
    <th> comment </th>
    <th> ex. </th>
  </tr>
  <tr>
    <td> docker [options] command </td>
    <td> syntex ในการเรียกใช้คำสั่ง docker </td>
    <td> <code>docker -v</code> or <code>docker docker build .</code> </td>
  </tr>
  <tr>
    <td> docker images [options] </td>
    <td> แสดง images ที่มีอยู่ในเครื่อง </td>
    <td> <code>docker images</code> or <code>docker images -a</code> </td>
  </tr>
  <tr>
    <td> docker ps [options] </td>
    <td> แสดง container ที่มีอยู่ในเครื่อง </td>
    <td> <code>docker ps</code> or <code>docker ps -a</code> </td>
  </tr>
  <tr>
    <td> docker pull <images_name> </td>
    <td> download images จาก repositories </td>
    <td> <code>docker pull alpine</code> or <code>docker pull mongo</code> </td>
  </tr>
  <tr>
    <td> docker run [options] <images_id/images_name> </td>
    <td> เรียกใช้งาน images ให้ทำงานขึ้นมาเป็น container </td>
    <td> <code>docker run -dit --name entro01 alpine</code> or <code>docker run -dit -p 3000:80 -v /myapp:/app/ --name app01 alpine</code> </td>
  </tr>
  <tr>
    <td> docker exec -it <container_id/container_name> [scripting] </td>
    <td> จะทำการ execute เข้าไปใน container โดยการใช้ script ซึ่งส่วนมากจะมี sh กับ bash </td>
    <td> <code>docker exec -it entro01 sh</code></td>
  </tr>
  <tr>
    <td> docker start <container_id/container_name> </td>
    <td> เริ่มใช้งานของ container ที่ stop อยู่ </td>
    <td> <code>docker start entro01</code> or <code>docker start 440as5ddaa66</code> </td>
  </tr>
  <tr>
    <td> docker stop <container_id/container_name> </td>
    <td> หยุดการทำงานของ container ที่ start อยู่ </td>
    <td> <code>docker stop entro01</code> or <code>docker stop 440as5ddaa66</code> </td>
  </tr>
  <tr>
    <td> docker rm [options] <container_id/container_name> </td>
    <td> ทำการลบ container ที่ระบุด้วย id หรือ name </td>
    <td> <code>docker rm entro01</code> or <code>docker rm -f 440as5ddaa66</code> </td>
  </tr>
  <tr>
    <td> docker rmi [options] <images_id/images_name> </td>
    <td> ทำการลบ images ที่ระบุ ด้วย id </td>
    <td> <code>docker rmi entro01</code> or <code>docker rmi -f 440as5ddaa66</code> </td>
  </tr>
</table>

  [รายละเอียดเพิ่มเติม](https://docs.docker.com/engine/reference/commandline/docker/)

## cp1 pull images
  >ให้ทำการ pull **image** ลงมาไว้ภายในเครื่อง

  `>_ docker pull alpine`
  `>_ docker pull python:2.7.16-alpine3.8`

## cp2 run container
  >ทำการใช้งาน image ที่ได้ pull ลงมา โดยเปลี่ยนเป็น **container** ด้วยคำสั่ง run
 
  - 1 `>_ docker run --rm -it --name entro01 alpine`
  - 2 `>_ docker run -d -p 3000:3000 --name entro01 alpine`
  - 3 `>_ docker run --rm -it -w /app/myweb --expose 3000 -p 3000:3000 --mount .\:/app/myweb python:2.7.16-alpine3.8 python main.py`
  
## cp3 Dockerfile
  >เราสามารถคำสั่งของ docker เก็บไว้เป็นไฟล์ได้เราจะเรียกไฟล์นั้นว่า Dockerfile
  
  `>_ cd your/project`
  
  `>_ vi Dockerfile`
  
  ตัวอย่าง [Dockerfile](https://github.com/enta1234/basic_docker/blob/master/Dockerfile).
  
## cp4 build image
  >เมื่อเตรียม Dockerfile เสร็จเราสามารถ image ของเราเองได้

  `>_ docker build -t myweb:1.0.0 .`

  >หรือในกรณีที่เราไมได้ตั้งชื่อไฟล์ว่า Dockerfile ให้เราระบุให้ชัดเจน

  `>_ docker build -t myweb:1.0.0 ./docker-file`

  ex.

  `>_ docker run -d -p 8000:8000 --name webEntro myweb:1.0.0`

## cp5 stop-start-delete
  ex. stop container

  `>_ docker stop webEntro`

  ex. start container

  `>_ docker stop webEntro`

  ex. delete container

  `>_ docker rm -f webEntro`

  ex. delete images

  `>_ docker rmi -f myweb:1.0.0`

  ex. delete, stop and start all container.

  `>_ docker rm -f $(docker ps -qa)`

  ex. delete all images.

  `>_ docker rmi -f $(docker images -q -a)`

  [อ่านเพิ่มเติมได้ที่](https://github.com/enta1234/docker-cp)