# รายงานแบบฝึกหัด Socket API & Docker

## ข้อมูลผู้จัดทำ
- ชื่อ-นามสกุล: (ใส่ชื่อของคุณ)
- รหัสนักศึกษา: 6814952012

---

## แบบฝึกหัดที่ 1: ระบบ Chat ด้วย Docker (2 Clients และ 1 Server)

ระบบแชทใช้ Socket API แบบ TCP มี Server กลางส่งต่อข้อความระหว่าง Client 2 ตัว รันด้วย Docker Compose

### วิธีรัน
```bash
cd exercise-1
docker compose up -d --build
docker exec -it chat_client1 python client.py
docker exec -it chat_client2 python client.py
```

### ผลการทดสอบ
![แชทระหว่าง Client 1 และ 2](images/ex1-chat.png)
![docker ps](images/ex1-ps.png)
![log ของ server](images/ex1-log.png)

---

## แบบฝึกหัดที่ 2: เว็บ Flask และ Socket Server

เว็บ Flask รับข้อความจากฟอร์ม (POST) ส่งต่อไปยัง Socket Server แล้วแสดงคำตอบ (Echo) บนหน้าเว็บ

### วิธีรัน
```bash
cd exercise-2
docker compose up --build
```
เปิด http://localhost:5000

### ผลการทดสอบ
![หน้าฟอร์ม](images/ex2-form.png)
![ผลลัพธ์](images/ex2-result.png)
![log ของ socket server](images/ex2-log.png)

---

## หยุดการทำงาน
```bash
docker compose down
```