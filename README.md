# SHAMPOO CARE — Student landing page project

โปรเจกต์ตัวอย่างร้านขายแชมพูออนไลน์ 2 SKU พร้อมหน้าเว็บสั่งซื้อ, Google Sheets backend, รายการหยิบ/แพ็คสินค้า และใบจ่าหน้าพัสดุสำหรับพิมพ์

## สิ่งที่มีในชุดนี้
- `index.html`, `style.css`, `app.js` — เว็บไซต์
- `assets/` — รูปสินค้าแยกโฟลเดอร์
- `apps-script.gs` — โค้ด Google Apps Script
- `orders-template.csv` — แม่แบบหัวตาราง Google Sheets
- `vercel.json` — ค่าตั้งต้นสำหรับ Vercel

## ขั้นตอนเชื่อม Google Sheets
1. สร้าง Google Sheet ชื่อ `SHAMPOO CARE Orders`
2. ไปที่ **ส่วนขยาย > Apps Script**
3. วางเนื้อหาจาก `apps-script.gs` ลงใน `Code.gs` แล้ว Save
4. เลือกฟังก์ชัน `setup` แล้วกด Run และอนุญาตสิทธิ์
5. กลับไป Google Sheets ตรวจว่ามีแท็บ `Orders`
6. ใน Apps Script กด **Deploy > New deployment > Web app**
7. ตั้ง **Execute as: Me** และ **Who has access: Anyone** (สำหรับสาธิตในชั้นเรียนเท่านั้น) แล้ว Deploy
8. คัดลอก Web app URL ที่ลงท้าย `/exec`
9. เปิด `app.js` แล้วแทนข้อความ `PASTE_YOUR_GOOGLE_APPS_SCRIPT_WEB_APP_URL_HERE` ด้วย URL จริง
10. บันทึกไฟล์

> ห้ามส่งรหัสผ่านหรือคีย์ลับให้ผู้อื่น การตั้ง Anyone เปิดให้ผู้ที่มี URL เรียก endpoint ได้ จึงควรใช้ข้อมูลสมมติในการสาธิตเท่านั้น

## อัปโหลด GitHub
1. แตกไฟล์ ZIP นี้
2. สร้าง Repository ชื่อ `shampoo-care`
3. อัปโหลด **ไฟล์และโฟลเดอร์ด้านใน** (ไม่ใช่ ZIP อย่างเดียว) โดยให้ `index.html` อยู่ที่ root ของ repository
4. Commit changes

## Deploy บน Vercel
1. เข้า Vercel และเลือก **Add New > Project**
2. Import repository `shampoo-care` จาก GitHub
3. เลือก Framework Preset: **Other**
4. ไม่ต้องใส่ Build Command; Output Directory ใช้ค่าเริ่มต้น/ว่าง
5. กด Deploy แล้วคัดลอก URL เว็บไซต์

## ทดสอบก่อนส่งงาน
1. เปิดเว็บไซต์ Vercel แล้วสั่งซื้อสินค้าทดสอบ 1 รายการด้วยข้อมูลสมมติ
2. ตรวจว่าแถวคำสั่งซื้อปรากฏในแท็บ `Orders`
3. เปิดส่วน **จัดการคำสั่งซื้อ** แล้วกดโหลดรายการ
4. กดยืนยันหยิบสินค้า จากนั้นยืนยันแพ็คสินค้า
5. กดพิมพ์ใบจ่าหน้า และเลือก Save as PDF เพื่อตรวจชื่อ เบอร์โทร ที่อยู่ และสินค้า

## ข้อจำกัดที่ควรแจ้งอาจารย์
- ระบบนี้เป็นต้นแบบสำหรับงานเรียน ไม่มีระบบสมาชิก/ล็อกอินผู้ดูแล
- ใบจ่าหน้าเป็นเอกสารภายในร้าน ไม่ใช่ใบปะหน้าจากบริษัทขนส่ง และไม่มีบาร์โค้ดขนส่ง
- ยังไม่มีระบบตัดสต็อกอัตโนมัติและระบบชำระเงินจริง
- ควรใช้ข้อมูลลูกค้าสมมติในการทดสอบ ไม่ควรใส่ข้อมูลส่วนบุคคลจริง
