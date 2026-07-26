# Week 08 — CSS Grid and Responsive Layout

> บทเรียนที่ 8: ใช้ CSS Grid สร้าง layout หลายคอลัมน์และทำ responsive design อย่างเป็นระบบ

---

## 1. Lesson Goal

ให้ผู้เรียนเข้าใจว่า CSS Grid เหมาะกับ layout แบบสองมิติ หรือ two-dimensional layout ซึ่งควบคุมได้ทั้ง rows และ columns จึงเหมาะกับ card grid, gallery, dashboard และ section layout ที่มีหลายคอลัมน์

---

## 2. Learning Outcomes

| Outcome | Description |
|---|---|
| LO1 | อธิบายความแตกต่างระหว่าง Flexbox และ Grid ได้ |
| LO2 | ใช้ `display: grid` และ `grid-template-columns` ได้ |
| LO3 | ใช้ `gap`, `repeat()`, `minmax()`, `auto-fit` ได้ |
| LO4 | สร้าง responsive card grid ได้โดยไม่ต้องเขียน media query ซับซ้อน |
| LO5 | ตรวจ layout overflow และ mobile readability ได้ |

---

## 3. Flexbox vs Grid

| Question | Use Flexbox | Use Grid |
|---|---|---|
| Layout เป็นแนวเดียวหรือไม่ | ใช่ | ไม่จำเป็น |
| ต้องควบคุมทั้ง row และ column หรือไม่ | ไม่เหมาะมาก | เหมาะมาก |
| ตัวอย่าง | navbar, button group, horizontal cards | card gallery, dashboard, page layout |
| Mental model | one-dimensional | two-dimensional |

---

## 4. Annotated Grid Example

### HTML

```html
<section class="course-section" aria-labelledby="course-title">
  <h2 id="course-title">Course Lessons</h2>

  <div class="lesson-grid">
    <article class="lesson-card">
      <h3>HTML Structure</h3>
      <p>เรียนรู้โครงสร้างเอกสาร HTML</p>
    </article>

    <article class="lesson-card">
      <h3>Semantic HTML</h3>
      <p>เลือก tag ให้ตรงกับความหมายของเนื้อหา</p>
    </article>

    <article class="lesson-card">
      <h3>CSS Layout</h3>
      <p>จัดวาง layout ด้วย Flexbox และ Grid</p>
    </article>
  </div>
</section>
```

### CSS

```css
.course-section {
  width: min(100% - 2rem, 1100px);
  margin-inline: auto;
  padding-block: 3rem;
}

/*
  lesson-grid คือ grid container
  ลูกโดยตรงคือ .lesson-card แต่ละใบ
*/
.lesson-grid {
  display: grid;

  /*
    repeat(auto-fit, minmax(240px, 1fr)) คือ pattern สำหรับ responsive grid
    auto-fit = ให้ browser คำนวณจำนวนคอลัมน์ตามพื้นที่จริง
    minmax(240px, 1fr) = card กว้างขั้นต่ำ 240px และขยายได้เต็มพื้นที่
  */
  grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));

  /* ระยะห่างระหว่าง row และ column */
  gap: 1.25rem;
}

.lesson-card {
  padding: 1.5rem;
  border: 1px solid #d9e2ec;
  border-radius: 16px;
  background: #ffffff;
}

.lesson-card h3 {
  margin-top: 0;
  color: #0f4c81;
}
```

---

## 5. Responsive Design Principles

### 5.1 Mobile-first mindset

เริ่มจาก layout ที่แสดงผลดีบนมือถือก่อน แล้วค่อยเพิ่มความซับซ้อนสำหรับจอใหญ่

```css
.card-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 1rem;
}

@media (min-width: 768px) {
  .card-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}
```

### 5.2 Fluid grid pattern

ใช้ `auto-fit` และ `minmax()` เพื่อให้ grid ปรับคอลัมน์เองตามพื้นที่

```css
.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 1.25rem;
}
```

### 5.3 Avoid horizontal overflow

```css
img,
video,
iframe {
  max-width: 100%;
}
```

---

## 6. Modern Responsive Checklist

| Check | Why it matters |
|---|---|
| ใช้ viewport meta | mobile browser คำนวณขนาดถูกต้อง |
| ใช้ flexible width | ลดปัญหาล้นจอ |
| ใช้ `max-width` | ควบคุมความกว้างบนจอใหญ่ |
| ใช้ Grid/Flexbox | layout ยืดหยุ่นกว่า float |
| ใช้ `gap` | spacing สม่ำเสมอ |
| ตรวจรูป/iframe | media มักเป็นต้นเหตุ overflow |
| ทดสอบ 320px, 768px, 1024px | ครอบคลุม mobile/tablet/desktop เบื้องต้น |

---

## 7. Workshop

### Task: Build a Responsive Lesson Gallery

สร้าง section แสดงบทเรียน 6 ใบ โดยใช้ CSS Grid

Required

- `section` มี `h2`
- `.lesson-grid` ใช้ `display: grid`
- ใช้ `repeat(auto-fit, minmax(...))`
- ใช้ `gap`
- card ทุกใบเป็น `article`
- layout ไม่ล้นจอที่ 320px
- มี comment ภาษาไทยอธิบาย `auto-fit` และ `minmax()`

### Bonus

เพิ่ม badge หรือ tag ใน card เช่น `HTML`, `CSS`, `Responsive`

---

## 8. Common Mistakes

| Mistake | Impact | Fix |
|---|---|---|
| ใช้ `grid-template-columns: repeat(4, 1fr)` ตายตัว | mobile ล้นหรือแน่นเกินไป | ใช้ `auto-fit + minmax()` |
| ใช้ Grid กับทุกอย่าง | code อาจเกินจำเป็น | ใช้ Flexbox กับ layout แนวเดียว |
| ไม่กำหนด `gap` | spacing ไม่สม่ำเสมอ | ใช้ `gap` ใน grid container |
| card มี width ตายตัว | grid ไม่ยืดหยุ่น | ปล่อยให้ grid คุม width |
| ไม่ทดสอบขนาดจอเล็ก | overflow ไม่ถูกพบ | ใช้ DevTools responsive mode |

---

## 9. Submission Checklist

- [ ] ใช้ `display: grid`
- [ ] ใช้ `repeat(auto-fit, minmax(...))`
- [ ] ใช้ `gap`
- [ ] card เป็น semantic `article`
- [ ] layout ไม่ล้นบน mobile
- [ ] media มี `max-width: 100%`
- [ ] มี comment ภาษาไทยอธิบาย Grid
- [ ] ทดสอบด้วย Developer Tools อย่างน้อย 3 viewport

---

## 10. References

- MDN Web Docs. CSS Grid Layout. https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout
- MDN Web Docs. Responsive design. https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/CSS_layout/Responsive_Design
- web.dev. Learn CSS: Grid. https://web.dev/learn/css/grid
- W3C. CSS Snapshot 2026. https://www.w3.org/TR/css-2026/
