# Course Notes: Modern Web Design using HTML and CSS

> สรุปบทเรียนและ checklist สำหรับใช้ประกอบการเรียนการสอน HTML & CSS

---

## 1. Learning Outcomes

เมื่อเรียนจบ ผู้เรียนควรสามารถ

- อธิบายโครงสร้างพื้นฐานของ HTML5 document ได้
- เขียน semantic HTML ที่อ่านง่ายและสื่อความหมายได้
- เชื่อมไฟล์ CSS ภายนอกกับ HTML ได้
- ใช้ CSS selector, class, id และ pseudo-class ได้
- อธิบาย box model ได้แก่ content, padding, border, margin ได้
- ใช้ Flexbox และ CSS Grid จัด layout ได้
- เขียน media query เพื่อรองรับ mobile ได้
- สร้าง form ที่มี label และ accessibility เบื้องต้นได้

---

## 2. HTML Core Structure

```html
<!DOCTYPE html>
<html lang="th">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Page Title</title>
</head>
<body>
  <h1>Main Heading</h1>
  <p>Page content</p>
</body>
</html>
```

### Teaching Notes

- `<!DOCTYPE html>` บอก browser ให้ตีความเอกสารเป็น HTML5
- `lang="th"` ช่วยเรื่องภาษา SEO และ screen reader
- `charset="UTF-8"` จำเป็นสำหรับภาษาไทย
- `viewport` จำเป็นสำหรับ responsive design
- `title` ควรสื่อความหมาย ไม่ควรใช้ชื่อทั่วไปเกินไป เช่น `My Page`

---

## 3. Semantic HTML Reference

| Tag | Purpose | Teaching Note |
|---|---|---|
| `header` | ส่วนหัวของหน้า/section | มักมี logo, heading, navigation |
| `nav` | กลุ่มเมนูนำทาง | ควรใช้กับเมนูหลักหรือสารบัญ |
| `main` | เนื้อหาหลักของหน้า | หนึ่งหน้าควรมี `main` หลักหนึ่งตำแหน่ง |
| `section` | แบ่งหมวดเนื้อหา | ควรมี heading ของตนเอง |
| `article` | เนื้อหาที่อยู่ได้ด้วยตัวเอง | เช่น card, blog, news, profile summary |
| `aside` | เนื้อหาเสริม | เช่น sidebar หรือ related links |
| `footer` | ส่วนท้ายของหน้า/section | ใช้กับ copyright, links, contact |

---

## 4. CSS Essentials

```css
/* เลือกทุก element เพื่อให้คำนวณขนาด layout ง่ายขึ้น */
* {
  box-sizing: border-box;
}

/* กำหนดค่ากลางของ theme */
:root {
  --color-primary: #0f4c81;
  --space-md: 1rem;
}

/* ใช้ class selector สำหรับ component ที่นำกลับมาใช้ซ้ำ */
.card {
  padding: var(--space-md);
  border: 1px solid #d9e2ec;
}
```

### Teaching Notes

- `class` เหมาะกับ style ที่ใช้ซ้ำได้หลายจุด
- `id` เหมาะกับ anchor หรือ element เฉพาะจุด
- CSS variables ช่วยให้ปรับ theme ได้ง่าย
- ควรแยก CSS ออกจาก HTML เพื่อ maintainability

---

## 5. Box Model

| Part | Meaning |
|---|---|
| Content | เนื้อหาจริงของ element |
| Padding | ระยะห่างด้านใน |
| Border | เส้นขอบ |
| Margin | ระยะห่างด้านนอก |

```css
.card {
  /* ระยะห่างด้านในของกล่อง */
  padding: 1rem;

  /* เส้นขอบของกล่อง */
  border: 1px solid #d9e2ec;

  /* ระยะห่างด้านนอกของกล่อง */
  margin-bottom: 1rem;
}
```

---

## 6. Responsive Design Checklist

- ใช้ flexible units เช่น `%`, `rem`, `fr`, `minmax()`
- ใช้ `max-width` เพื่อควบคุมความกว้างของเนื้อหา
- ใช้ Grid/Flexbox สำหรับ layout หลัก
- ใช้ media query เพื่อเปลี่ยน layout บนหน้าจอเล็ก
- ทดสอบอย่างน้อย 3 ขนาดหน้าจอ: desktop, tablet, mobile

```css
@media (max-width: 768px) {
  .layout {
    grid-template-columns: 1fr;
  }
}
```

---

## 7. Accessibility Checklist

| Item | Standard |
|---|---|
| Page language | มี `lang` ใน `<html>` |
| Images | มี `alt` ที่อธิบายรูป |
| Form controls | มี `label` เชื่อมกับ `id` |
| Links | ข้อความ link ต้องสื่อความหมาย |
| Keyboard focus | มี focus style ที่มองเห็นได้ |
| Heading order | ใช้ `h1` → `h2` → `h3` ตามลำดับ |

---

## 8. HTML Tag Reference

| Category | Tags |
|---|---|
| Document | `html`, `head`, `body`, `title`, `meta`, `link` |
| Semantic | `header`, `nav`, `main`, `section`, `article`, `aside`, `footer` |
| Text | `h1`-`h6`, `p`, `strong`, `em`, `mark`, `code`, `pre` |
| List | `ul`, `ol`, `li`, `dl`, `dt`, `dd` |
| Media | `img`, `figure`, `figcaption`, `video`, `audio`, `iframe` |
| Table | `table`, `caption`, `thead`, `tbody`, `tr`, `th`, `td` |
| Form | `form`, `label`, `input`, `textarea`, `select`, `option`, `button` |
| Interactive | `details`, `summary`, `dialog` |

---

## 9. Student Final Checklist

| Checklist | Status |
|---|---|
| มี `index.html` | ☐ |
| มีไฟล์ CSS แยก | ☐ |
| ใช้ semantic HTML | ☐ |
| มี heading structure ชัดเจน | ☐ |
| ไม่มี tag ผิดรูปแบบ | ☐ |
| รูปภาพมี `alt` | ☐ |
| form มี `label` | ☐ |
| ใช้ Flexbox หรือ Grid | ☐ |
| รองรับ mobile ด้วย media query | ☐ |
| ไม่มีข้อมูลส่วนตัวจริงใน public repo | ☐ |
| README อธิบาย project ชัดเจน | ☐ |

---

## 10. Code Review Questions

1. โครงสร้าง HTML อ่านแล้วเข้าใจหน้าที่ของแต่ละ section หรือไม่
2. มีการใช้ `div` เกินจำเป็นหรือไม่
3. CSS มี naming ที่อ่านง่ายหรือไม่
4. มี inline style ที่ควรย้ายไป CSS หรือไม่
5. หน้าเว็บยังใช้งานได้เมื่อเปิดบน mobile หรือไม่
6. ถ้ารูปโหลดไม่ได้ ผู้ใช้ยังเข้าใจเนื้อหาหรือไม่
7. มีข้อมูลส่วนตัวที่ไม่ควรเผยแพร่บน GitHub หรือไม่
