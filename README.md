# Modern Web Design using HTML and CSS

> หลักสูตร HTML & CSS สำหรับผู้เริ่มต้นระดับปริญญาตรี พร้อมตัวอย่างโค้ดและคอมเมนต์ภาษาไทย เพื่อใช้เรียนรู้ ฝึกปฏิบัติ และเผยแพร่บน GitHub

![Course Status](https://img.shields.io/badge/status-active-brightgreen)
![HTML](https://img.shields.io/badge/HTML-Living%20Standard-orange)
![CSS](https://img.shields.io/badge/CSS-Snapshot%202026-blue)
![License](https://img.shields.io/badge/license-MIT-lightgrey)

---

## 📌 Course Overview

Repository นี้จัดทำเป็นชุดบทเรียน **Modern Web Design using HTML and CSS** สำหรับฝึกสร้างเว็บไซต์แบบ Static Website โดยเน้นมาตรฐานสำคัญ 5 ด้าน

1. โครงสร้าง HTML5 / HTML Living Standard ที่ถูกต้อง
2. การใช้ Semantic HTML ตามความหมายของเนื้อหา
3. การเขียน CSS แยกไฟล์ อ่านง่าย และดูแลรักษาได้
4. การจัด Layout ด้วย Flexbox และ CSS Grid
5. Responsive Design, Accessibility และ Browser Compatibility เบื้องต้น

หลักสูตรนี้เหมาะสำหรับนักศึกษาระดับปริญญาตรี ผู้เริ่มต้นพัฒนาเว็บไซต์ และผู้สอนที่ต้องการนำเนื้อหาไปใช้เป็นเอกสารประกอบการสอน

---

## ⭐ Latest One-page Teaching Media

| File | Description |
|---|---|
| [`ONE_PAGE_HTML_CSS_2026.md`](ONE_PAGE_HTML_CSS_2026.md) | สื่อการสอนแบบหน้าเดียว สังเคราะห์จากแหล่งสากลล่าสุดเกี่ยวกับ HTML Living Standard, CSS Snapshot 2026, MDN, web.dev, The Odin Project และ freeCodeCamp |

---

## 📚 Enhanced Lessons 1–8

> บทเรียน 1–8 ได้รับการปรับปรุงให้เป็น lesson pack แยกไฟล์ พร้อม lecture notes, code comments ภาษาไทย, workshop, common mistakes และ checklist

| Week | Lesson | Focus | File |
|---:|---|---|---|
| 1 | Web Foundations and Tooling | HTML, CSS, Browser, VS Code, GitHub | [`lessons/week-01-web-foundations.md`](lessons/week-01-web-foundations.md) |
| 2 | HTML Document Structure | `doctype`, `html`, `head`, `body`, metadata | [`lessons/week-02-html-document-structure.md`](lessons/week-02-html-document-structure.md) |
| 3 | Text, Links, Images, Lists | content structure, link, image alt, lists | [`lessons/week-03-text-links-images-lists.md`](lessons/week-03-text-links-images-lists.md) |
| 4 | Semantic HTML and Accessibility | landmarks, headings, ARIA เบื้องต้น | [`lessons/week-04-semantic-html-accessibility.md`](lessons/week-04-semantic-html-accessibility.md) |
| 5 | CSS Fundamentals and Cascade | selectors, cascade, specificity, variables | [`lessons/week-05-css-fundamentals-cascade.md`](lessons/week-05-css-fundamentals-cascade.md) |
| 6 | Box Model, Typography, Color | card, spacing, color, text readability | [`lessons/week-06-box-model-typography-color.md`](lessons/week-06-box-model-typography-color.md) |
| 7 | Flexbox Layout | navbar, alignment, gap, responsive flex | [`lessons/week-07-flexbox-layout.md`](lessons/week-07-flexbox-layout.md) |
| 8 | CSS Grid and Responsive Layout | card grid, `auto-fit`, `minmax()`, media | [`lessons/week-08-css-grid-responsive-layout.md`](lessons/week-08-css-grid-responsive-layout.md) |

รวมหน้า index ของบทเรียน: [`lessons/README.md`](lessons/README.md)

---

## 🎯 Learning Outcomes

เมื่อเรียนจบ ผู้เรียนควรสามารถ

| CLO | Learning Outcome |
|---|---|
| CLO 1 | อธิบายบทบาทของ HTML, CSS และ Web Browser ได้ |
| CLO 2 | สร้าง HTML document structure ตามมาตรฐาน HTML5 / HTML Living Standard ได้ |
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
├── LICENSE                           # MIT License
├── .gitignore                        # ไฟล์ยกเว้นสิ่งที่ไม่ควร commit
│
├── ONE_PAGE_HTML_CSS_2026.md         # สื่อการสอนแบบหน้าเดียว อัปเดตตามแหล่งสากลล่าสุด
├── COURSE_NOTES.md                   # สรุปบทเรียนและ checklist
│
├── lessons/                          # บทเรียน 1–8 แบบแยกไฟล์
│   ├── README.md
│   ├── week-01-web-foundations.md
│   ├── week-02-html-document-structure.md
│   ├── week-03-text-links-images-lists.md
│   ├── week-04-semantic-html-accessibility.md
│   ├── week-05-css-fundamentals-cascade.md
│   ├── week-06-box-model-typography-color.md
│   ├── week-07-flexbox-layout.md
│   └── week-08-css-grid-responsive-layout.md
│
├── index.html                        # หน้า landing page หลักของหลักสูตร
├── style.css                         # stylesheet หลัก ใช้กับ index.html
├── html-elements-reference.html      # ตัวอย่าง HTML tags / lists / table / form
├── semantic-resume-template.html     # template สำหรับฝึก semantic profile page
├── lookerstudio.html                 # ตัวอย่างการฝัง dashboard ด้วย iframe
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
| `ONE_PAGE_HTML_CSS_2026.md` | One-page teaching media for latest HTML/CSS teaching approach |
| `lessons/README.md` | Index ของบทเรียน 1–8 |
| `lessons/week-01...week-08.md` | บทเรียนแยกไฟล์ พร้อม code comments ภาษาไทย |
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
- ใช้ media query หรือ fluid layout เพื่อรองรับ mobile
- ตรวจสอบ browser compatibility / Baseline ก่อนใช้ feature ใหม่
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
| Responsive | มี media query หรือ fluid responsive grid อย่างน้อย 1 จุด |
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

## 🔐 Privacy and Safety Note

Repository นี้ปรับให้เป็น **generic educational course repository** และหลีกเลี่ยงการใส่ข้อมูลส่วนตัวจริง เช่น ประวัติส่วนตัว เบอร์โทรศัพท์ อีเมลส่วนตัว หรือรูปภาพส่วนตัว เพื่อให้เหมาะกับการเผยแพร่สาธารณะบน GitHub

---

## 📚 References

- WHATWG. HTML Living Standard. https://html.spec.whatwg.org/
- W3C. CSS Snapshot 2026. https://www.w3.org/TR/css-2026/
- MDN Web Docs. HTML reference. https://developer.mozilla.org/en-US/docs/Web/HTML/Reference
- MDN Web Docs. Learn web development. https://developer.mozilla.org/en-US/docs/Learn_web_development
- MDN Curriculum. https://developer.mozilla.org/en-US/curriculum/
- web.dev. Learn CSS. https://web.dev/learn/css
- The Odin Project. Introduction to HTML and CSS. https://www.theodinproject.com/lessons/foundations-introduction-to-html-and-css
- freeCodeCamp. Responsive Web Design Certification. https://www.freecodecamp.org/learn/2022/responsive-web-design/

---

## License

This repository is released under the MIT License. See [LICENSE](LICENSE) for details.
