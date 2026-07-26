# Week 02 — HTML Document Structure

> บทเรียนที่ 2: สร้างโครงสร้างเอกสาร HTML ให้ถูกต้องตามมาตรฐานปัจจุบัน

---

## 1. Lesson Goal

ให้ผู้เรียนสามารถเขียน HTML document structure ได้ครบถ้วนและอธิบายหน้าที่ของแต่ละส่วนได้ ไม่ใช่เพียงคัดลอก template ไปใช้

---

## 2. Learning Outcomes

| Outcome | Description |
|---|---|
| LO1 | อธิบายหน้าที่ของ `doctype`, `html`, `head`, `body` ได้ |
| LO2 | ใช้ `lang`, `charset`, `viewport`, `description`, `title` ได้ถูกต้อง |
| LO3 | เชื่อม stylesheet ภายนอกด้วย `link` ได้ |
| LO4 | เขียน comment ที่ช่วยอธิบาย code ได้ |
| LO5 | ตรวจสอบ HTML structure เบื้องต้นได้ |

---

## 3. Anatomy of an HTML Page

| Part | Role | Teaching Note |
|---|---|---|
| `<!DOCTYPE html>` | ประกาศให้ browser ใช้ standards mode | ต้องอยู่บรรทัดแรก |
| `<html lang="th">` | root element และระบุภาษา | สำคัญต่อ accessibility |
| `<head>` | metadata และ resource | ไม่ใช่พื้นที่แสดงเนื้อหาหลัก |
| `<meta charset="UTF-8">` | encoding | จำเป็นสำหรับภาษาไทย |
| `<meta viewport>` | responsive viewport | จำเป็นสำหรับ mobile |
| `<title>` | browser tab title | ควรสื่อความหมาย |
| `<link rel="stylesheet">` | เชื่อม CSS | แยก structure กับ presentation |
| `<body>` | เนื้อหาที่ผู้ใช้เห็น | ใส่ heading, paragraph, image, form ฯลฯ |

---

## 4. Annotated Template

```html
<!DOCTYPE html>
<!--
  บรรทัดนี้บอก browser ให้ใช้โหมดมาตรฐาน
  ลดโอกาสเกิดปัญหาการ render แบบเก่า
-->

<html lang="th">
<!--
  lang="th" บอกภาษาหลักของหน้าเว็บ
  ช่วย screen reader อ่านออกเสียงได้เหมาะสมขึ้น
-->

<head>
  <meta charset="UTF-8">
  <!--
    UTF-8 รองรับภาษาไทย ภาษาอังกฤษ สัญลักษณ์ และ emoji
    ควรใส่ไว้ช่วงต้นของ head
  -->

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <!--
    width=device-width = ให้ความกว้างหน้าเว็บเท่ากับหน้าจออุปกรณ์
    initial-scale=1.0 = ไม่ zoom เริ่มต้นผิดขนาด
  -->

  <meta name="description" content="หน้าเว็บตัวอย่างสำหรับเรียน HTML document structure">
  <!--
    description เป็นข้อความสรุปหน้าเว็บ
    ช่วยด้าน SEO และการจัดระบบเอกสาร
  -->

  <title>HTML Document Structure</title>
  <!--
    title ควรเฉพาะเจาะจง ไม่ควรตั้งว่า My Page เฉย ๆ
  -->

  <link rel="stylesheet" href="style.css">
  <!--
    rel="stylesheet" ระบุว่าไฟล์ที่เชื่อมคือ CSS
    href คือ path ไปยังไฟล์ CSS
  -->
</head>

<body>
  <header>
    <h1>HTML Document Structure</h1>
  </header>

  <main>
    <section>
      <h2>Why structure matters</h2>
      <p>โครงสร้าง HTML ที่ถูกต้องทำให้เว็บอ่านง่าย ดูแลรักษาง่าย และรองรับ accessibility ได้ดีขึ้น</p>
    </section>
  </main>

  <footer>
    <p>&copy; 2026 HTML CSS Course</p>
  </footer>
</body>
</html>
```

---

## 5. Instructor Explanation

### ทำไมต้องมี `head`

`head` ไม่ใช่พื้นที่ใส่เนื้อหาที่ผู้ใช้เห็นโดยตรง แต่เป็นพื้นที่ให้ browser อ่านข้อมูลเกี่ยวกับหน้าเว็บ เช่น character encoding, viewport, title และ stylesheet

### ทำไมต้องแยก CSS

การแยก CSS ออกจาก HTML ช่วยให้

- HTML เน้นโครงสร้าง
- CSS เน้นการแสดงผล
- แก้ style ทั้งเว็บไซต์ได้ง่าย
- code อ่านง่ายและ maintain ได้ดีขึ้น

---

## 6. Workshop

### Task

สร้างไฟล์ `about.html` โดยต้องมี

- `doctype`
- `html lang="th"`
- `meta charset`
- `meta viewport`
- `meta description`
- `title`
- `header`, `main`, `section`, `footer`
- comment ภาษาไทยอธิบายอย่างน้อย 5 จุด

---

## 7. Common Mistakes

| Mistake | Impact | Fix |
|---|---|---|
| ลืมปิด tag | Browser อาจจัดโครงสร้างผิด | ตรวจ indentation และ closing tags |
| ใส่ content ใน `head` | เนื้อหาไม่แสดงผลตามคาด | ย้ายไป `body` |
| ไม่มี viewport | mobile layout เพี้ยน | ใส่ `meta viewport` เสมอ |
| title กว้างเกินไป | ไม่ช่วยบอกบริบท | ใช้ title ที่ตรงกับเนื้อหา |
| comment แปล code ตรงตัวเกินไป | ไม่ช่วยให้เข้าใจเหตุผล | เขียนอธิบายว่า “ทำไมต้องใช้” |

---

## 8. Submission Checklist

- [ ] มี HTML structure ครบ
- [ ] ระบุภาษาใน `html`
- [ ] ใช้ UTF-8
- [ ] มี viewport
- [ ] มี title สื่อความหมาย
- [ ] เชื่อม CSS ภายนอกได้
- [ ] มี semantic tags ขั้นต้น
- [ ] มี comment ภาษาไทยเชิงอธิบาย

---

## 9. References

- WHATWG. The `html` element and document metadata. https://html.spec.whatwg.org/multipage/semantics.html
- MDN Web Docs. What's in the head? https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content/Webpage_metadata
- MDN Web Docs. The HTML document and website structure. https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content/Structuring_documents
