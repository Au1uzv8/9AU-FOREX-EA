# 9AU-FOREX-EA — Portfolio Dashboard

Dashboard แสดงผล Backtest ของ EA ทั้ง 11 ตัว อ่านข้อมูลจากไฟล์เดียว ไม่มี Backend

## โครงสร้างไฟล์

| ไฟล์ | หน้าที่ |
|---|---|
| `index.html` | หน้าเว็บหลัก (CSS + JS + ข้อมูล EA อยู่ในไฟล์เดียว) |
| `data.json` | ข้อมูล EA ฉบับอ้างอิง ใช้ Sync กลับเข้า `index.html` เมื่อ Obsidian มีการอัปเดต |

## วิธี Deploy (GitHub Pages)

1. Push ไฟล์ทั้งหมดขึ้น branch `main`
2. ไปที่ Settings > Pages
3. Source เลือก "Deploy from a branch" → Branch: `main` → Folder: `/ (root)`
4. รอ 1-2 นาที เว็บจะขึ้นที่ `https://au1uzv8.github.io/9AU-FOREX-EA/`

## วิธี Sync ข้อมูลใหม่

เมื่อมีการอัปเดต Properties ของ EA ใน Obsidian:

1. แก้ค่าที่เปลี่ยนใน `data.json`
2. Copy Block JSON เดียวกันไปแทนที่ใน `<script id="ea-data" type="application/json">` ภายใน `index.html`
3. Push ขึ้น `main` — เว็บอัปเดตอัตโนมัติภายในไม่กี่วินาที

## เกณฑ์การจัดกลุ่ม (Portfolio Classification)

| Equity DD | กลุ่ม | สี |
|---|---|---|
| < 18% | Compound | เขียวน้ำทะเล (Teal) |
| ≥ 18% | House Money | ทอง (Amber) |
