## วิธีติดตั้ง Docker Desktop บน Windows
2.1 ทำการเปิดใช้งาน Windows Subsystem for Linux (WSL) <br>
เปิด PowerShell as Administrator and run:
```shell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```
2.2 ทำการเปิดใช้งาน Virtual Machine feature <br>
เปิด PowerShell as Administrator and run:
```shell
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```
ทำการ Restart เครื่อง <br>

2.3 ทำการดาวน์โหลดและติดตั้ง Linux kernel update package <br>
ดาวน์โหลด exe https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi

2.4 ทำการตั้งค่า WSL ค่าเริ่มต้นให้เป็น version 2 <br>
เปิด PowerShell as Administrator and run:
```shell
wsl --set-default-version 2
```

2.5 ทำการติดตั้ง Linux distribution
ดาวน์โหลดได้จาก https://aka.ms/wslstore
 <br>
ทำการเลือกเป็น Ubuntu กด Get 
<br>
ดาวน์โหลดเสร็จแล้ว กดที่ Launch ก็จะเข้าสู่หน้า cmd ของ Ubuntu ให้ทำการสร้าง User, Password ให้เรียบร้อย

2.6 ทำการติดตั้ง Docker Desktop <br>
ดาวน์โหลด exe https://hub.docker.com/editions/community/docker-ce-desktop-windows/ <br>
หลังจากติดตั้งเสร็จแล้ว <br>
2.6.1 ไปที่เมนู Settings > General
 <br>
2.6.2 เลือก Use the WSL 2 based engine <br>
2.6.3 กด Apply & Restart <br>
2.6.4 ทำการตั้งค่าเริ่มต้นที่จะรัน Linux distribution <br>
เปิด PowerShell as Administrator and run:
```shell
wsl --set-version ubuntu 2
``` 
2.6.5 ไปที่เมนู Settings > Resources > WSL Integration <br>
2.6.6 เลือก Enable integration with my default WSL distro และเลือก distributions เป็น Ubuntu <br>
2.6.7 กด Apply & Restart <br>

2.7 ทำการทดลองสร้าง Container <br>
เปิด PowerShell as Administrator and run:
```shell
docker run -d -p 80:80 docker/getting-started
```
เสร็จแล้วทดสอบเข้า URL http://localhost <br>
จบสำหรับการ ติดตั้ง Docker Desktop บน Windows เบื้องต้น <br>


## 3. วิธีติดตั้ง Docker Desktop บน MacOS
3.1 Go to Docker Toolbox https://www.docker.com/products/docker-toolbox และเลือกดาวน์โหลดสำหรับ Mac OS X <br> เมื่อได้ไฟล์ก็คลิกที่ไอคอนเพื่อเริ่มติดตั้ง และกดปุ่ม “Continue” และ Install 
3.2 ทีนี้ลองทดสอบพิมพ์คำสั่งดูเวอร์ชั่นด้านล่างถ้าแสดง Docker version ขึ้นมาก็ถือว่าติดตั้งเรียบร้อยครับ
```shell
docker -v
```
ถ้าหากใครมีการแจ้งถ้าใครมี VirtualBox ในเครื่องก่อนติดตั้ง Docker มันจะขึ้นข้อความประมาณนี้ Please Quit VirtualBox! <br>
ก็ให้เราไปปิด VirtualBox ก่อน โดยเข้าไปที่เมนูแล้วเลือก  Quit VirtualBox ครับ <br>
 <br>
จบสำหรับการ ติดตั้ง Docker Desktop บน MacOS เบื้องต้น <br>
