# 👁️ INSIDER — เกมบทบาทลับ

เกม Insider แบบ Multiplayer เล่นออนไลน์ได้ทุก device รองรับภาษาไทย/อังกฤษ

## 🚀 วิธี Deploy ขึ้น GitHub Pages (ฟรี)

### ขั้นตอนที่ 1 — สร้าง GitHub Repo

1. ไปที่ [github.com](https://github.com) → **New repository**
2. ตั้งชื่อ เช่น `insider-game`
3. เลือก **Public** → **Create repository**

### ขั้นตอนที่ 2 — อัปโหลดไฟล์

อัปโหลดไฟล์ทั้ง 3 นี้เข้า repo:

| ไฟล์ | คำอธิบาย |
|------|---------|
| `index.html` | ตัวเกมหลัก |
| `upload-words.html` | เครื่องมืออัปโหลดคำ |
| `words.json` | ข้อมูลคำสำรอง |

**วิธีอัปโหลด:** กด **Add file → Upload files** แล้วลากไฟล์เข้าไป

### ขั้นตอนที่ 3 — เปิด GitHub Pages

1. ไปที่ **Settings** → **Pages**
2. Source: **Deploy from a branch**
3. Branch: **main** → **/ (root)**
4. กด **Save**
5. รอ 1-2 นาที → ได้ URL: `https://username.github.io/insider-game`

---

## 🔥 ตั้งค่า Firebase (ทำครั้งเดียว)

Firebase URL ฝังไว้แล้ว: `https://mygame-57017-default-rtdb.asia-southeast1.firebasedatabase.app`

ถ้าต้องการใช้ Firebase ของตัวเอง:

1. ไปที่ [console.firebase.google.com](https://console.firebase.google.com)
2. สร้าง Project → **Realtime Database** → **Create database**
3. เลือก **Start in test mode** → **Enable**
4. คัดลอก Database URL
5. เปิด `index.html` แก้บรรทัด:
   ```js
   let dbUrl = '...'; // ← ใส่ URL ใหม่ตรงนี้
   ```

---

## 📚 อัปโหลดคำไป Firebase

1. เปิด `upload-words.html` ในเบราว์เซอร์
2. ใส่ Firebase URL
3. กด **Upload** → รอไม่กี่วินาที → เสร็จ!

คำจะถูกแบ่งเป็น **840 คำ** (ไทย + อังกฤษ × ง่าย/กลาง/ยาก)

---

## 🎮 วิธีเล่น

| บทบาท | หน้าที่ |
|--------|---------|
| 👑 **Master** | รู้คำลับ ตอบได้แค่ ใช่/ไม่ใช่/ไม่รู้ |
| 🔴 **Insider** | รู้คำลับ แต่แกล้งทำเป็นไม่รู้ ช่วยนำทางโดยไม่ให้ถูกจับ |
| 🟢 **Common** | ถามคำถาม เดาคำลับ แล้วโหวตหา Insider |

**ขั้นตอน:**
1. Host สร้างห้อง → แชร์รหัส 6 ตัว
2. เพื่อนๆ เข้าร่วม (ต้องการ 4+ คน)
3. Host เลือกระดับ (ง่าย/กลาง/ยาก) → เริ่มเกม
4. แต่ละคนดูบทบาทลับ
5. ถาม-ตอบ 5 นาที เพื่อหาคำลับ
6. โหวตว่าใครคือ Insider
7. ประกาศผล!

---

## ✨ Features

- 🌐 Online Multiplayer — แต่ละคนใช้โทรศัพท์ตัวเอง
- 🏠 Local Mode — ส่งโทรศัพท์เล่น (ไม่ต้องอินเทอร์เน็ต)
- 📱 Session Persistence — หลุดไปแล้วกลับมาต่อได้ใน 30 นาที
- 🟢🟡🔴 Difficulty Levels — ง่าย / ปานกลาง / ยาก
- 🔤 Bilingual — ภาษาไทย & English
- 📚 840 คำ — ดึงจาก Firebase พร้อม Cache (โหลดเร็ว)

---

## 🏗️ Tech Stack

- Vanilla HTML/CSS/JS (ไม่มี framework)
- Firebase Realtime Database (REST API)
- localStorage สำหรับ cache คำและ session

---

*Made with 👁️ for fun*
