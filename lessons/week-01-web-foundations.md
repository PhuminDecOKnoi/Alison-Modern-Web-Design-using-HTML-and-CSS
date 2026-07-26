# Week 01 — Web Foundations and Tooling

> บทเรียนที่ 1: เข้าใจภาพรวมการทำงานของเว็บ HTML, CSS, Browser, VS Code และ GitHub

---

## 1. Lesson Goal

ให้ผู้เรียนเข้าใจว่าเว็บเพจหนึ่งหน้าไม่ได้เกิดจาก HTML เพียงอย่างเดียว แต่เกิดจากการทำงานร่วมกันของ

- **HTML** = โครงสร้างและความหมายของเนื้อหา
- **CSS** = รูปแบบ สี ขนาด ระยะห่าง และ layout
- **Browser** = โปรแกรมที่อ่าน HTML/CSS แล้วแสดงผลเป็นหน้าเว็บ
- **Developer Tools** = เครื่องมือตรวจสอบและแก้ไขหน้าเว็บ
- **GitHub** = พื้นที่จัดเก็บ code, version history และส่งงาน

---

## 2. Learning Outcomes

เมื่อจบบทเรียน ผู้เรียนควรสามารถ

| Outcome | Description |
|---|---|
| LO1 | อธิบายบทบาทของ HTML, CSS และ Browser ได้ |
| LO2 | สร้าง project folder สำหรับเว็บพื้นฐานได้ |
| LO3 | สร้างไฟล์ `index.html` และ `style.css` ได้ |
| LO4 | เชื่อม CSS ภายนอกเข้ากับ HTML ได้ |
| LO5 | เปิดหน้าเว็บด้วย Browser และตรวจด้วย Developer Tools ได้ |

---

## 3. Core Concepts

### 3.1 HTML คืออะไร

HTML เป็นภาษาสำหรับกำหนดโครงสร้างและความหมายของเนื้อหา เช่น หัวข้อ ย่อหน้า รูปภาพ ลิงก์ ตาราง และฟอร์ม

```html
<h1>หัวข้อหลัก</h1>
<p>ข้อความย่อหน้า</p>
```

### 3.2 CSS คืออะไร

CSS เป็นภาษาสำหรับกำหนดรูปแบบของ HTML เช่น สีตัวอักษร ขนาดฟอนต์ ระยะห่าง และการจัดวาง layout

```css
h1 {
  color: #0f4c81;
}
```

### 3.3 Browser ทำงานอย่างไรแบบย่อ

1. Browser อ่านไฟล์ HTML
2. Browser สร้างโครงสร้างเอกสารภายใน
3. Browser โหลดไฟล์ CSS ที่เชื่อมไว้
4. Browser คำนวณ style และ layout
5. Browser แสดงผลเป็นหน้าเว็บ

---

## 4. Standard Project Structure

```text
my-first-web-page/
│
├── index.html      # ไฟล์ HTML หลักของหน้าเว็บ
├── style.css       # ไฟล์ CSS สำหรับตกแต่งหน้าเว็บ
└── assets/         # โฟลเดอร์เก็บรูปภาพหรือไฟล์ประกอบ
```

### Teaching Note

ชื่อไฟล์ `index.html` สำคัญมาก เพราะ web server ส่วนใหญ่จะมองหาไฟล์นี้เป็นหน้าแรกของเว็บไซต์โดยอัตโนมัติ

---

## 5. Annotated Code Example

### `index.html`

```html
<!DOCTYPE html>
<!--
  บอก Browser ว่าเอกสารนี้ใช้มาตรฐาน HTML ปัจจุบัน
  ไม่ต้องระบุ HTML5 แบบยาวเหมือนในอดีต
-->

<html lang="th">
<!--
  html คือ root element ของเอกสาร
  lang="th" ระบุว่าภาษาหลักของหน้าเว็บคือภาษาไทย
-->

<head>
  <meta charset="UTF-8">
  <!-- รองรับภาษาไทยและอักขระพิเศษ -->

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <!-- ทำให้หน้าเว็บปรับตามขนาดหน้าจอมือถือได้ -->

  <title>My First Web Page</title>
  <!-- ชื่อที่แสดงบน browser tab -->

  <link rel="stylesheet" href="style.css">
  <!-- เชื่อมไฟล์ CSS ภายนอกเข้ากับ HTML -->
</head>

<body>
  <h1>สวัสดี HTML และ CSS</h1>
  <!-- h1 คือหัวข้อหลักของหน้าเว็บ -->

  <p>นี่คือหน้าเว็บแรกของฉัน</p>
  <!-- p ใช้กับข้อความแบบย่อหน้า -->
</body>
</html>
```

### `style.css`

```css
/*
  เลือก body เพื่อกำหนด style พื้นฐานทั้งหน้า
*/
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background-color: #f5f7fb;
  color: #1f2937;
  line-height: 1.6;
}

/*
  เลือก h1 เพื่อปรับหัวข้อหลัก
*/
h1 {
  color: #0f4c81;
  font-size: 2.5rem;
}
```

---

## 6. Workshop

### Task

สร้าง project folder ชื่อ `my-first-web-page` แล้วสร้างไฟล์

- `index.html`
- `style.css`

จากนั้นให้เปลี่ยนข้อความใน `<h1>` และ `<p>` เป็นหัวข้อที่ตนเองสนใจ เช่น รายวิชา ชมรม หรือกิจกรรม

### Expected Output

หน้าเว็บต้องแสดง

- หัวข้อหลัก 1 จุด
- ย่อหน้าอย่างน้อย 1 จุด
- สีพื้นหลังที่มาจาก CSS
- สีหัวข้อที่มาจาก CSS

---

## 7. Common Mistakes

| Mistake | Why it matters | Fix |
|---|---|---|
| ลืม `<!DOCTYPE html>` | Browser อาจตีความเอกสารผิด mode | ใส่ไว้บรรทัดแรกเสมอ |
| ลืม `<meta charset="UTF-8">` | ภาษาไทยอาจแสดงผลผิด | ใส่ใน `<head>` |
| path CSS ผิด | หน้าเว็บไม่มี style | ตรวจชื่อไฟล์และตำแหน่งไฟล์ |
| ตั้งชื่อไฟล์ `Index.html` หรือ `INDEX.HTML` | บางระบบแยกตัวพิมพ์เล็ก/ใหญ่ | ใช้ `index.html` ตัวพิมพ์เล็ก |

---

## 8. Submission Checklist

- [ ] มีโฟลเดอร์ project ชัดเจน
- [ ] มี `index.html`
- [ ] มี `style.css`
- [ ] HTML มี `doctype`, `html`, `head`, `body`
- [ ] CSS ถูกเชื่อมด้วย `<link>`
- [ ] เปิดดูใน Browser ได้
- [ ] ตรวจด้วย Developer Tools ได้

---

## 9. References

- WHATWG. HTML Living Standard. https://html.spec.whatwg.org/
- MDN Web Docs. HTML basics. https://developer.mozilla.org/en-US/docs/Learn_web_development/Getting_started/Your_first_website/Creating_the_content
- MDN Web Docs. CSS basics. https://developer.mozilla.org/en-US/docs/Learn_web_development/Getting_started/Your_first_website/Styling_the_content
