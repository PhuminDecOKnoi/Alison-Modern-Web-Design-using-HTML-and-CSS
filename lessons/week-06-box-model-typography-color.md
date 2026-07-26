# Week 06 — Box Model, Typography, Color, and Spacing

> บทเรียนที่ 6: เข้าใจกล่องของ CSS และสร้างระบบ visual foundation สำหรับเว็บเพจ

---

## 1. Lesson Goal

ให้ผู้เรียนเข้าใจว่า element ทุกตัวในหน้าเว็บเป็น “กล่อง” ที่มี content, padding, border และ margin และสามารถนำ box model ไปใช้สร้าง card, spacing system, typography และ color system ได้อย่างเป็นระบบ

---

## 2. Learning Outcomes

| Outcome | Description |
|---|---|
| LO1 | อธิบาย CSS Box Model ได้ |
| LO2 | ใช้ `padding`, `border`, `margin`, `width`, `max-width` ได้ถูกต้อง |
| LO3 | กำหนด typography พื้นฐาน เช่น `font-family`, `font-size`, `line-height` ได้ |
| LO4 | วางระบบสีและ spacing ด้วย CSS variables ได้ |
| LO5 | สร้าง card component ที่อ่านง่ายและ responsive ได้ |

---

## 3. Box Model

| Layer | Meaning | Example Property |
|---|---|---|
| Content | พื้นที่เนื้อหาจริง | `width`, `height` |
| Padding | ระยะห่างด้านใน | `padding` |
| Border | เส้นขอบ | `border` |
| Margin | ระยะห่างด้านนอก | `margin` |

```text
margin
┌─────────────────────────┐
│ border                  │
│ ┌─────────────────────┐ │
│ │ padding             │ │
│ │ ┌─────────────────┐ │ │
│ │ │ content         │ │ │
│ │ └─────────────────┘ │ │
│ └─────────────────────┘ │
└─────────────────────────┘
```

---

## 4. Annotated CSS Example

```css
/*
  กำหนดระบบ theme ขั้นต้น
  ทำให้สีและระยะห่างของเว็บมี consistency
*/
:root {
  --color-primary: #0f4c81;
  --color-surface: #ffffff;
  --color-text: #1f2937;
  --color-muted: #6b7280;
  --color-border: #d9e2ec;

  --space-sm: 0.5rem;
  --space-md: 1rem;
  --space-lg: 1.5rem;
  --space-xl: 2rem;

  --radius-md: 12px;
  --shadow-soft: 0 12px 30px rgba(15, 76, 129, 0.12);
}

/*
  body ควบคุม typography พื้นฐานของทั้งหน้า
*/
body {
  margin: 0;
  font-family: Arial, Helvetica, sans-serif;
  color: var(--color-text);
  line-height: 1.6;
}

/*
  .container จำกัดความกว้างเนื้อหาเพื่อให้อ่านง่าย
  width: min(...) ช่วยให้ responsive โดยไม่ต้องเขียน media query ทันที
*/
.container {
  width: min(100% - 2rem, 1100px);
  margin-inline: auto;
}

/*
  card เป็น component ตัวอย่างที่ใช้ box model ครบ
*/
.card {
  background: var(--color-surface);

  /* padding = ระยะห่างภายใน card */
  padding: var(--space-lg);

  /* border = เส้นขอบของ card */
  border: 1px solid var(--color-border);

  /* border-radius = มุมโค้ง */
  border-radius: var(--radius-md);

  /* box-shadow = เงา เพื่อแยก card ออกจากพื้นหลัง */
  box-shadow: var(--shadow-soft);

  /* margin-block-end = ระยะห่างด้านล่างตาม flow แนวตั้ง */
  margin-block-end: var(--space-md);
}

.card h2 {
  margin-top: 0;
  color: var(--color-primary);
  line-height: 1.2;
}

.card p {
  color: var(--color-muted);
}
```

---

## 5. Typography Rules for Beginners

| Rule | Explanation |
|---|---|
| ใช้ `line-height` อย่างน้อย 1.5 | เพิ่ม readability |
| อย่าทำ paragraph กว้างเกินไป | อ่านยากบนจอใหญ่ |
| ใช้ heading scale อย่างมีระบบ | ทำให้ visual hierarchy ชัด |
| อย่าใช้สีเทาอ่อนเกินไปกับข้อความหลัก | contrast ต่ำ อ่านยาก |
| ใช้ `rem` แทน `px` ในหลายกรณี | ยืดหยุ่นต่อ user settings มากกว่า |

---

## 6. Workshop

### Task: Build a Course Card Component

สร้าง card 3 ใบสำหรับบทเรียน HTML/CSS โดยแต่ละใบต้องมี

- `article.card`
- `h2`
- `p`
- link หรือ button
- padding
- border
- border-radius
- box-shadow
- spacing ที่สม่ำเสมอ

### HTML Starter

```html
<section class="container">
  <article class="card">
    <h2>HTML Structure</h2>
    <p>เรียนรู้โครงสร้างเอกสาร HTML ที่ถูกต้อง</p>
    <a href="#">อ่านบทเรียน</a>
  </article>
</section>
```

---

## 7. Common Mistakes

| Mistake | Impact | Fix |
|---|---|---|
| ใช้ margin แก้ทุกอย่าง | spacing ไม่สม่ำเสมอ | สร้าง spacing variables |
| กำหนด width เป็น px ตายตัว | mobile ล้นจอ | ใช้ `%`, `max-width`, `min()` |
| line-height น้อยเกินไป | อ่านยาก | ใช้ `line-height: 1.5` หรือมากกว่า |
| สี text contrast ต่ำ | accessibility ต่ำ | ใช้สีที่อ่านง่ายบนพื้นหลัง |
| ไม่ใช้ `box-sizing` | layout คำนวณยาก | ใส่ `box-sizing: border-box` |

---

## 8. Submission Checklist

- [ ] ใช้ `box-sizing: border-box`
- [ ] มี spacing variables
- [ ] มี color variables
- [ ] card ใช้ padding, border, radius
- [ ] text อ่านง่าย มี line-height
- [ ] container ไม่กว้างเกินไป
- [ ] responsive เบื้องต้น
- [ ] comment อธิบาย box model

---

## 9. References

- MDN Web Docs. The box model. https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics/Box_model
- web.dev. Learn CSS: Box Model. https://web.dev/learn/css/box-model
- web.dev. Learn CSS: Typography. https://web.dev/learn/css/typography
- MDN Web Docs. Color and backgrounds. https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics/Values_and_units
