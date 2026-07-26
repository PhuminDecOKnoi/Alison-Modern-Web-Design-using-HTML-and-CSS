# Week 04 — Semantic HTML and Accessibility

> บทเรียนที่ 4: ใช้ Semantic HTML เพื่อทำให้เว็บอ่านง่าย ดูแลรักษาง่าย และเข้าถึงได้มากขึ้น

---

## 1. Lesson Goal

ให้ผู้เรียนเปลี่ยน mindset จาก “ใช้ `div` ทุกอย่าง” เป็น “เลือก tag ตามความหมายของเนื้อหา” และเข้าใจว่า semantic HTML เป็นพื้นฐานของ accessibility, SEO และ maintainability

---

## 2. Learning Outcomes

| Outcome | Description |
|---|---|
| LO1 | อธิบายความหมายของ Semantic HTML ได้ |
| LO2 | ใช้ `header`, `nav`, `main`, `section`, `article`, `aside`, `footer` ได้เหมาะสม |
| LO3 | จัด heading structure ตามลำดับได้ |
| LO4 | ใช้ `aria-label` หรือ `aria-labelledby` อย่างพอดี ไม่ใช้เกินจำเป็น |
| LO5 | ตรวจ accessibility ขั้นต้นของหน้าเว็บได้ |

---

## 3. Core Concepts

### 3.1 Semantic HTML คืออะไร

Semantic HTML คือการใช้ tag ที่บอก “ความหมาย” ของเนื้อหา เช่น

| Non-semantic | Semantic alternative |
|---|---|
| `<div class="header">` | `<header>` |
| `<div class="menu">` | `<nav>` |
| `<div class="content">` | `<main>` |
| `<div class="block">` | `<section>` หรือ `<article>` |
| `<div class="bottom">` | `<footer>` |

### 3.2 ใช้ semantic ก่อน ARIA

หลักทั่วไปคือ **ใช้ HTML element ที่ถูกต้องก่อน** แล้วจึงใช้ ARIA เฉพาะเมื่อ HTML ปกติสื่อความหมายไม่พอ

---

## 4. Semantic Page Layout Example

```html
<body>
  <!--
    header คือส่วนหัวของหน้าเว็บ
    เหมาะสำหรับชื่อเว็บไซต์ logo หรือ navigation หลัก
  -->
  <header class="site-header">
    <h1>Modern Web Design Course</h1>

    <!--
      nav ใช้กับกลุ่ม link นำทาง
      aria-label ช่วยบอกว่า nav นี้เป็นเมนูประเภทใด
    -->
    <nav aria-label="เมนูหลัก">
      <a href="#overview">Overview</a>
      <a href="#lessons">Lessons</a>
      <a href="#contact">Contact</a>
    </nav>
  </header>

  <!--
    main คือเนื้อหาหลักของหน้า
    โดยทั่วไปควรมี main หลักหนึ่งจุดต่อหนึ่งหน้า
  -->
  <main>
    <!--
      section ใช้แบ่งหมวดเนื้อหา
      ควรมี heading เพื่อบอกว่าหมวดนี้เกี่ยวกับอะไร
    -->
    <section id="overview" aria-labelledby="overview-title">
      <h2 id="overview-title">Course Overview</h2>
      <p>หลักสูตรนี้สอน HTML, CSS, responsive layout และ accessibility เบื้องต้น</p>
    </section>

    <section id="lessons" aria-labelledby="lessons-title">
      <h2 id="lessons-title">Lessons</h2>

      <!--
        article ใช้กับเนื้อหาที่แยกออกเป็นหน่วยอิสระได้
        เช่น card บทเรียน ข่าว blog post หรือรายการสินค้า
      -->
      <article>
        <h3>Semantic HTML</h3>
        <p>เรียนรู้การเลือก tag ตามความหมายของเนื้อหา</p>
      </article>

      <article>
        <h3>CSS Layout</h3>
        <p>เรียนรู้การจัดวางด้วย Flexbox และ Grid</p>
      </article>
    </section>

    <!--
      aside ใช้กับข้อมูลเสริมที่ไม่ใช่แกนหลักของเนื้อหา
    -->
    <aside aria-label="แหล่งเรียนรู้เพิ่มเติม">
      <h2>Resources</h2>
      <p>อ่านเพิ่มเติมได้จาก MDN และ WHATWG</p>
    </aside>
  </main>

  <footer>
    <p>&copy; 2026 Modern Web Design Course</p>
  </footer>
</body>
```

---

## 5. Heading Structure Rule

```text
h1 = ชื่อหน้าเว็บหรือหัวข้อหลัก
  h2 = หมวดหลัก
    h3 = หัวข้อย่อยในหมวด
      h4 = รายละเอียดลึกลงไป
```

### Bad Example

```html
<h1>Course</h1>
<h4>Lesson 1</h4>
<h2>Details</h2>
```

### Better Example

```html
<h1>Course</h1>
<h2>Lesson 1</h2>
<h3>Details</h3>
```

---

## 6. Workshop

### Task: Refactor Div Layout to Semantic HTML

ให้ผู้เรียนเริ่มจากโครงสร้างนี้

```html
<div class="header">...</div>
<div class="menu">...</div>
<div class="main">...</div>
<div class="content-block">...</div>
<div class="footer">...</div>
```

แล้ว refactor เป็น

```html
<header>...</header>
<nav>...</nav>
<main>
  <section>...</section>
</main>
<footer>...</footer>
```

### Required

- ใช้ semantic tags อย่างน้อย 5 tags
- มี heading structure ถูกลำดับ
- ใช้ `aria-label` กับ `nav` ถ้ามี nav มากกว่าหนึ่งชุด
- มี comment ภาษาไทยอธิบายเหตุผลของการเลือก tag

---

## 7. Common Mistakes

| Mistake | Impact | Fix |
|---|---|---|
| ใช้ `div` ทุกอย่าง | โครงสร้างไม่มีความหมาย | ใช้ semantic tag ตามหน้าที่ |
| ใช้ `section` โดยไม่มี heading | ผู้ใช้ไม่รู้ว่า section คืออะไร | ใส่ `h2` หรือ `aria-label` |
| มี `main` หลายจุด | landmark สับสน | ใช้ `main` หลักจุดเดียว |
| ใช้ ARIA แทน HTML ที่ถูกต้อง | code ซับซ้อนเกินจำเป็น | ใช้ native HTML ก่อน |
| heading กระโดดระดับ | outline อ่านยาก | ใช้ลำดับ h1-h6 อย่างมีเหตุผล |

---

## 8. Submission Checklist

- [ ] ใช้ `header`
- [ ] ใช้ `nav`
- [ ] ใช้ `main`
- [ ] ใช้ `section` พร้อม heading
- [ ] ใช้ `article` เมื่อเนื้อหาเป็นหน่วยอิสระ
- [ ] ใช้ `footer`
- [ ] heading ไม่กระโดดระดับโดยไม่มีเหตุผล
- [ ] ไม่มี `div` เกินจำเป็น
- [ ] มี comment อธิบายการเลือก semantic tag

---

## 9. References

- WHATWG. Sections and outlines. https://html.spec.whatwg.org/multipage/sections.html
- MDN Web Docs. HTML: A good basis for accessibility. https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Accessibility/HTML
- MDN Curriculum. Semantic HTML. https://developer.mozilla.org/en-US/curriculum/core/semantic-html/
