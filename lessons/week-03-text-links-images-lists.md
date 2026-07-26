# Week 03 — Text, Links, Images, and Lists

> บทเรียนที่ 3: จัดโครงสร้างเนื้อหาเว็บด้วยข้อความ ลิงก์ รูปภาพ และรายการ

---

## 1. Lesson Goal

ให้ผู้เรียนสามารถเลือกใช้ HTML elements สำหรับเนื้อหาพื้นฐานได้ถูกต้อง เช่น heading, paragraph, link, image, ordered list, unordered list และ description list พร้อมคำนึงถึง accessibility เบื้องต้น

---

## 2. Learning Outcomes

| Outcome | Description |
|---|---|
| LO1 | ใช้ heading และ paragraph ได้ตามโครงสร้างเนื้อหา |
| LO2 | สร้าง link ภายในหน้าและ link ไปยังเว็บภายนอกได้ |
| LO3 | ใช้ `img` พร้อม `alt` ได้ถูกต้อง |
| LO4 | ใช้ `ul`, `ol`, `li`, `dl`, `dt`, `dd` ได้เหมาะสม |
| LO5 | อธิบายความแตกต่างระหว่าง content structure และ visual style ได้ |

---

## 3. Core Concepts

### 3.1 Heading ไม่ใช่แค่ตัวใหญ่

Heading (`h1` ถึง `h6`) ใช้จัดลำดับความสำคัญของเนื้อหา ไม่ควรเลือก heading เพราะอยากได้ขนาดตัวอักษรเท่านั้น

### 3.2 Link ต้องมีข้อความที่สื่อความหมาย

ไม่ควรใช้คำว่า “คลิกที่นี่” เพียงอย่างเดียว เพราะผู้ใช้ screen reader อาจไม่เข้าใจว่าลิงก์พาไปที่ใด

### 3.3 Image ต้องมี `alt`

`alt` คือข้อความทดแทนรูปภาพ ใช้เมื่อรูปโหลดไม่ได้ และช่วยผู้ใช้ที่ใช้ screen reader

### 3.4 List ต้องเลือกตามลักษณะข้อมูล

| Element | Use case |
|---|---|
| `ul` | รายการที่ไม่มีลำดับชัดเจน |
| `ol` | ขั้นตอนหรือรายการที่มีลำดับ |
| `dl` | คำศัพท์/นิยาม/คู่ข้อมูล |

---

## 4. Annotated Code Example

```html
<section aria-labelledby="course-title">
  <!--
    h2 ใช้เป็นหัวข้อของ section
    id ใช้เชื่อมกับ aria-labelledby เพื่อบอกชื่อ section ให้ assistive technology
  -->
  <h2 id="course-title">Modern HTML & CSS Foundation</h2>

  <!--
    p ใช้เขียนข้อความแบบย่อหน้า
    ไม่ควรใช้ div แทน p เมื่อเนื้อหาเป็นข้อความย่อหน้า
  -->
  <p>
    หลักสูตรนี้สอนการสร้างเว็บไซต์พื้นฐานด้วย HTML และ CSS
    โดยเน้น semantic structure, responsive layout และ accessibility
  </p>

  <!--
    a ใช้สร้าง hyperlink
    target="_blank" เปิดหน้าใหม่
    rel="noopener noreferrer" ช่วยลดความเสี่ยงเมื่อเปิดหน้าใหม่
  -->
  <p>
    อ่านเอกสารเพิ่มเติมที่
    <a href="https://developer.mozilla.org/en-US/docs/Web/HTML"
       target="_blank"
       rel="noopener noreferrer">
      MDN HTML Documentation
    </a>
  </p>

  <figure>
    <!--
      src คือที่อยู่รูปภาพ
      alt อธิบายสาระสำคัญของรูปภาพ
      width ช่วยกำหนดขนาดเบื้องต้น แต่ควรให้ CSS ควบคุม layout หลัก
    -->
    <img src="assets/sample-image.svg"
         alt="ภาพประกอบแนวคิด HTML เป็นโครงสร้าง และ CSS เป็นการนำเสนอ"
         width="420">

    <!-- figcaption ใช้อธิบายรูปภาพหรือแผนภาพ -->
    <figcaption>HTML กำหนดโครงสร้าง ส่วน CSS กำหนดรูปแบบการแสดงผล</figcaption>
  </figure>

  <h3>หัวข้อที่ควรเรียนก่อน</h3>
  <ul>
    <li>โครงสร้างไฟล์ HTML</li>
    <li>การเชื่อม CSS</li>
    <li>การใช้ Browser Developer Tools</li>
  </ul>

  <h3>ขั้นตอนการส่งงาน</h3>
  <ol>
    <li>สร้างไฟล์ HTML และ CSS</li>
    <li>ทดสอบใน Browser</li>
    <li>Commit และ push ขึ้น GitHub</li>
  </ol>

  <h3>คำศัพท์สำคัญ</h3>
  <dl>
    <dt>HTML</dt>
    <dd>ภาษาสำหรับกำหนดโครงสร้างและความหมายของเว็บเพจ</dd>

    <dt>CSS</dt>
    <dd>ภาษาสำหรับกำหนดรูปแบบและ layout ของเว็บเพจ</dd>
  </dl>
</section>
```

---

## 5. Workshop

### Task: Create a Learning Profile Section

ให้สร้าง section ชื่อ “My Learning Profile” โดยต้องมี

- `h2` 1 จุด
- `p` อย่างน้อย 2 ย่อหน้า
- link ไปยังเอกสาร MDN 1 จุด
- รูปภาพ 1 รูปพร้อม `alt`
- unordered list สำหรับหัวข้อที่สนใจ
- ordered list สำหรับขั้นตอนการเรียน
- description list สำหรับคำศัพท์ 3 คำ

---

## 6. Common Mistakes

| Mistake | Impact | Fix |
|---|---|---|
| ใช้ `h1` หลายจุดโดยไม่จำเป็น | โครงสร้างเอกสารสับสน | ใช้ `h1` เป็นหัวข้อหลัก และใช้ `h2/h3` ตามลำดับ |
| ลืม `alt` ในรูปภาพ | accessibility ต่ำ | ใส่ `alt` ที่อธิบายสาระของรูป |
| ใช้ link text ว่า “คลิกที่นี่” | ไม่ชัดเจน | ใช้ข้อความเช่น “อ่าน MDN HTML Documentation” |
| ใช้ `br` เพื่อจัดย่อหน้า | โครงสร้างผิด | ใช้ `p` และ CSS spacing |
| ใช้ `ul` กับขั้นตอน | ลำดับขั้นตอนไม่ชัด | ใช้ `ol` สำหรับลำดับขั้น |

---

## 7. Submission Checklist

- [ ] Heading ใช้ตามลำดับ
- [ ] Paragraph ใช้กับเนื้อหาจริง
- [ ] Link text สื่อความหมาย
- [ ] External link มี `rel` เมื่อเปิด tab ใหม่
- [ ] รูปภาพมี `alt`
- [ ] ใช้ list ถูกประเภท
- [ ] Code indentation อ่านง่าย
- [ ] มี comment ภาษาไทยในจุดสำคัญ

---

## 8. References

- MDN Web Docs. Text fundamentals. https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content/Headings_and_paragraphs
- MDN Web Docs. Creating hyperlinks. https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content/Creating_links
- MDN Web Docs. Images in HTML. https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content/HTML_images
- MDN Web Docs. Lists. https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content/Lists
