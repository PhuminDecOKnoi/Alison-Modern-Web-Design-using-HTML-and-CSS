# Modern Web Design using HTML and CSS

> หลักสูตร HTML & CSS สำหรับผู้เริ่มต้นระดับปริญญาตรี พร้อมตัวอย่างโค้ดและคอมเมนต์ภาษาไทย เพื่อใช้เรียนรู้ ฝึกปฏิบัติ และเผยแพร่บน GitHub

![Course Status](https://img.shields.io/badge/status-active-brightgreen)
![HTML](https://img.shields.io/badge/HTML5-semantic-orange)
![CSS](https://img.shields.io/badge/CSS3-responsive-blue)
![License](https://img.shields.io/badge/license-Apache--2.0-lightgrey)

---

## 📌 Course Overview

Repository นี้จัดทำเป็นชุดบทเรียน **Modern Web Design using HTML and CSS** สำหรับฝึกสร้างเว็บไซต์แบบ Static Website โดยเน้นมาตรฐานสำคัญ 5 ด้าน

1. โครงสร้าง HTML5 ที่ถูกต้อง
2. การใช้ Semantic HTML ตามความหมายของเนื้อหา
3. การเขียน CSS แยกไฟล์ อ่านง่าย และดูแลรักษาได้
4. การจัด Layout ด้วย Flexbox และ CSS Grid
5. Responsive Design และ Accessibility เบื้องต้น

หลักสูตรนี้เหมาะสำหรับนักศึกษาระดับปริญญาตรี ผู้เริ่มต้นพัฒนาเว็บไซต์ และผู้สอนที่ต้องการนำเนื้อหาไปใช้เป็นเอกสารประกอบการสอน

---

## 🎯 Learning Outcomes

เมื่อเรียนจบ ผู้เรียนควรสามารถ

| CLO | Learning Outcome |
|---|---|
| CLO 1 | อธิบายบทบาทของ HTML, CSS และ Web Browser ได้ |
| CLO 2 | สร้าง HTML document structure ตามมาตรฐาน HTML5 ได้ |
| CLO 3 | ใช้ semantic tags เช่น `header`, `nav`, `main`, `section`, `article`, `footer` ได้ถูกต้อง |
| CLO 4 | เขียน CSS selector, variable, spacing, typography และ color system ได้ |
| CLO 5 | อธิบาย CSS Box Model และนำไปใช้จัดวาง UI ได้ |
| CLO 6 | จัด Layout ด้วย Flexbox และ CSS Grid ได้ |
| CLO 7 | สร้างหน้าเว็บที่รองรับหลายขนาดหน้าจอด้วย Media Query ได้ |
| CLO 8 | สร้าง form ที่มี `label`, `input`, validation attribute และ accessibility พื้นฐานได้ |
| CLO 9 | ตรวจสอบและปรับปรุง code readability, naming และ comments ได้ |

---

## 🧭 Repository Structure

```text
Alison-Modern-Web-Design-using-HTML-and-CSS/
│
├── README.md                         # เอกสารหลักของ repository
├── LICENSE                           # Apache License 2.0
├── .gitignore                        # ไฟล์ยกเว้นสิ่งที่ไม่ควร commit
│
├── index.html                        # หน้า landing page หลักของหลักสูตร
├── style.css                         # stylesheet หลัก ใช้กับ index.html
├── html-elements-reference.html      # ตัวอย่าง HTML tags / lists / table / form
├── semantic-resume-template.html     # template สำหรับฝึก semantic profile page
├── lookerstudio.html                 # ตัวอย่างการฝัง dashboard ด้วย iframe
├── COURSE_NOTES.md                   # สรุปบทเรียนและ checklist
│
└── assets/
    └── sample-image.svg              # รูปตัวอย่างสำหรับบทเรียน media element
```

---

## 🗓 Suggested 12-Week Lesson Plan

| Week | Topic | Workshop Output |
|---:|---|---|
| 1 | Web Fundamentals, HTML, CSS, Browser | สร้าง `index.html` แรก |
| 2 | HTML Document Structure | ใช้ `doctype`, `html`, `head`, `body`, `meta`, `title` |
| 3 | Text, Links, Images, Lists | สร้าง content page ที่มี link, image, list |
| 4 | Semantic HTML | ปรับ `div` เป็น semantic layout |
| 5 | CSS Fundamentals | เชื่อม `style.css` และใช้ selector |
| 6 | Box Model | สร้าง card layout ด้วย margin, padding, border |
| 7 | Flexbox | สร้าง navigation bar และ responsive menu |
| 8 | CSS Grid | สร้าง course card grid |
| 9 | Responsive Design | เขียน media query สำหรับ mobile |
| 10 | Form and Accessibility | สร้าง contact form ที่มี label และ required fields |
| 11 | Mini Project | สร้าง one-page website |
| 12 | Presentation and Code Review | นำเสนอและปรับปรุง code quality |

---

## 🚀 How to Use

### 1. Clone repository

```bash
git clone https://github.com/PhuminDecOKnoi/Alison-Modern-Web-Design-using-HTML-and-CSS.git
cd Alison-Modern-Web-Design-using-HTML-and-CSS
```

### 2. Open with VS Code

```bash
code .
```

### 3. Run locally

เปิดไฟล์ `index.html` ด้วย browser หรือใช้ extension เช่น Live Server ใน VS Code

```text
Right click index.html → Open with Live Server
```

---

## 📄 Main Files

| File | Purpose |
|---|---|
| `index.html` | หน้าเว็บหลักของ course landing page |
| `style.css` | ระบบ style หลักของหน้าเว็บ |
| `html-elements-reference.html` | ตัวอย่าง HTML elements สำหรับฝึก tag, list, table, form |
| `semantic-resume-template.html` | template สำหรับฝึก semantic structure โดยไม่ใส่ข้อมูลส่วนตัวจริง |
| `lookerstudio.html` | ตัวอย่างการฝัง external dashboard ด้วย iframe |
| `COURSE_NOTES.md` | สรุป lesson notes, tag reference และ student checklist |

---

## ✅ Coding Standard

### HTML Standard

- ใช้ `<!DOCTYPE html>` ทุกหน้า
- ใส่ `<html lang="th">` หรือภาษาที่เหมาะสม
- ใส่ `<meta charset="UTF-8">`
- ใส่ `<meta name="viewport" content="width=device-width, initial-scale=1.0">`
- ใช้ heading ตามลำดับโครงสร้าง ไม่ใช้ heading เพื่อเลือกขนาดตัวอักษรเท่านั้น
- ใช้ semantic tags ตามความหมายของเนื้อหา
- ใส่ `alt` ให้รูปภาพทุกครั้ง
- ใส่ `label` ให้ form controls

### CSS Standard

- แยก CSS ออกจาก HTML
- ใช้ class naming ที่อ่านง่าย
- ใช้ CSS variables สำหรับค่าสีและ spacing ที่ใช้ซ้ำ
- ใช้ Flexbox/Grid แทน float สำหรับ layout หลัก
- ใช้ media query เพื่อรองรับ mobile
- หลีกเลี่ยง inline style ยกเว้นตัวอย่างเฉพาะทาง
- เขียนคอมเมนต์เพื่ออธิบายเหตุผลของส่วนสำคัญ

---

## 🧪 Assignment

ให้นักศึกษาสร้างเว็บไซต์ 1 หน้า โดยเลือกหัวข้อ เช่น

- Course landing page
- Student club website
- Personal learning portfolio template
- Training registration page
- Product/service information page

### Minimum Requirements

| Requirement | Description |
|---|---|
| HTML5 structure | มี `doctype`, `html`, `head`, `body`, `meta`, `title` ครบ |
| Semantic HTML | ใช้ semantic tags อย่างน้อย 5 tag |
| External CSS | ใช้ไฟล์ CSS แยกต่างหาก |
| Layout | ใช้ Flexbox หรือ Grid อย่างน้อย 1 จุด |
| Responsive | มี media query อย่างน้อย 1 breakpoint |
| Form | มี form พร้อม label และ required field |
| Accessibility | มี alt text และ focus style พื้นฐาน |
| Comments | มี code comments ภาษาไทยในส่วนสำคัญ |

---

## 📊 Rubric

| Criteria | Score |
|---|---:|
| HTML structure ถูกต้อง | 20 |
| Semantic HTML เหมาะสม | 15 |
| CSS organization และ readability | 20 |
| Layout ด้วย Flexbox/Grid | 15 |
| Responsive design | 15 |
| Accessibility เบื้องต้น | 10 |
| Code comments ภาษาไทย | 5 |
| **Total** | **100** |

---

## 🧩 HTML Tag Reference Summary

| Category | Examples | Purpose |
|---|---|---|
| Document | `html`, `head`, `body`, `title`, `meta`, `link` | โครงสร้างเอกสาร |
| Semantic | `header`, `nav`, `main`, `section`, `article`, `aside`, `footer` | เพิ่มความหมายของเนื้อหา |
| Text | `h1`-`h6`, `p`, `strong`, `em`, `mark`, `code` | จัดโครงสร้างข้อความ |
| List | `ul`, `ol`, `li`, `dl`, `dt`, `dd` | สร้างรายการข้อมูล |
| Media | `img`, `figure`, `figcaption`, `video`, `audio`, `iframe` | แสดงสื่อ |
| Table | `table`, `caption`, `thead`, `tbody`, `tr`, `th`, `td` | แสดงข้อมูลแบบตาราง |
| Form | `form`, `label`, `input`, `textarea`, `select`, `button` | รับข้อมูลจากผู้ใช้ |
| Interactive | `details`, `summary`, `dialog` | เพิ่ม interaction เบื้องต้น |

---

## 🔐 Privacy and Safety Note

Repository นี้ปรับให้เป็น **generic educational course repository** และหลีกเลี่ยงการใส่ข้อมูลส่วนตัวจริง เช่น ประวัติส่วนตัว เบอร์โทรศัพท์ อีเมลส่วนตัว หรือรูปภาพส่วนตัว เพื่อให้เหมาะกับการเผยแพร่สาธารณะบน GitHub

---

## 📚 References

- MDN Web Docs. HTML: HyperText Markup Language. https://developer.mozilla.org/en-US/docs/Web/HTML
- MDN Web Docs. CSS: Cascading Style Sheets. https://developer.mozilla.org/en-US/docs/Web/CSS
- MDN Web Docs. Responsive design. https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/CSS_layout/Responsive_Design
- W3C. Web Content Accessibility Guidelines (WCAG) 2.2. https://www.w3.org/TR/WCAG22/
- WHATWG. HTML Living Standard. https://html.spec.whatwg.org/

---

## License

This repository is released under the Apache License 2.0. See [LICENSE](LICENSE) for details.
