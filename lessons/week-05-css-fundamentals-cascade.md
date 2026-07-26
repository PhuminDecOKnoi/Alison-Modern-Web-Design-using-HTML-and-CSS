# Week 05 — CSS Fundamentals and Cascade

> บทเรียนที่ 5: เข้าใจ CSS syntax, selector, cascade, specificity และ CSS custom properties

---

## 1. Lesson Goal

ให้ผู้เรียนเข้าใจว่า CSS ไม่ใช่แค่ “ใส่สี” แต่เป็นระบบ rules ที่ browser ใช้ตัดสินว่า style ใดจะถูกนำไปใช้จริง โดยแกนสำคัญคือ selector, cascade, specificity, inheritance และ source order

---

## 2. Learning Outcomes

| Outcome | Description |
|---|---|
| LO1 | เชื่อม CSS ภายนอกกับ HTML ได้ |
| LO2 | เขียน CSS rule ด้วย selector, property, value ได้ |
| LO3 | ใช้ type, class, id และ group selector ได้ |
| LO4 | อธิบาย cascade และ specificity เบื้องต้นได้ |
| LO5 | ใช้ CSS custom properties สำหรับ theme ได้ |

---

## 3. CSS Syntax

```css
selector {
  property: value;
}
```

| Part | Meaning | Example |
|---|---|---|
| Selector | เลือก element ที่ต้องการตกแต่ง | `.card` |
| Property | คุณสมบัติที่ต้องการกำหนด | `color` |
| Value | ค่าของ property | `#0f4c81` |
| Declaration | 1 คำสั่ง CSS | `color: #0f4c81;` |
| Rule | selector + declaration block | `.card { ... }` |

---

## 4. Annotated CSS Example

```css
/*
  Universal selector ใช้เลือกทุก element
  box-sizing: border-box ทำให้คำนวณขนาด layout ง่ายขึ้น
*/
*,
*::before,
*::after {
  box-sizing: border-box;
}

/*
  :root ใช้เก็บ CSS custom properties หรือ variables
  เหมาะกับสีหลัก spacing และค่าที่ใช้ซ้ำทั้งเว็บไซต์
*/
:root {
  --color-primary: #0f4c81;
  --color-text: #1f2937;
  --color-bg: #f5f7fb;
  --space-md: 1rem;
  --space-lg: 2rem;
}

/*
  Type selector เลือก element ตามชื่อ tag
  เหมาะกับ style พื้นฐานของทั้งเว็บ
*/
body {
  margin: 0;
  font-family: Arial, sans-serif;
  line-height: 1.6;
  color: var(--color-text);
  background-color: var(--color-bg);
}

/*
  Class selector เลือก element ที่มี class="card"
  class เหมาะกับ component ที่ใช้ซ้ำได้หลายจุด
*/
.card {
  padding: var(--space-lg);
  border: 1px solid #d9e2ec;
  border-radius: 16px;
  background: #ffffff;
}

/*
  Descendant selector เลือก h2 ที่อยู่ภายใน .card เท่านั้น
*/
.card h2 {
  color: var(--color-primary);
  margin-top: 0;
}

/*
  Pseudo-class :hover ทำงานเมื่อผู้ใช้เอา pointer ไปวางเหนือ element
*/
.card:hover {
  box-shadow: 0 12px 30px rgba(15, 76, 129, 0.15);
}
```

---

## 5. Cascade and Specificity

### Cascade คืออะไร

Cascade คือกระบวนการที่ browser ใช้ตัดสินว่า CSS rule ไหนชนะเมื่อมีหลาย rule กำหนด style ให้ element เดียวกัน

### Specificity แบบจำง่าย

| Selector | Example | Power |
|---|---|---:|
| Type selector | `p` | ต่ำ |
| Class selector | `.note` | กลาง |
| ID selector | `#main-title` | สูง |
| Inline style | `style="color:red"` | สูงมาก |

### Example

```css
p {
  color: black;
}

.note {
  color: blue;
}

#special-note {
  color: red;
}
```

```html
<p id="special-note" class="note">ข้อความนี้จะเป็นสีแดง</p>
```

เหตุผล: `#special-note` เป็น ID selector จึงมี specificity สูงกว่า class และ type selector

---

## 6. Teaching Pattern

แนะนำให้สอน CSS ตามลำดับนี้

1. External stylesheet
2. Basic syntax
3. Type selector
4. Class selector
5. Descendant selector
6. Pseudo-class
7. Cascade and specificity
8. CSS variables

ไม่ควรเริ่มจาก layout ทันที เพราะผู้เรียนจะยังไม่เข้าใจว่าทำไม style บางตัวจึงไม่ทำงาน

---

## 7. Workshop

### Task: Create a Course Card Theme

สร้าง card 3 ใบ โดยใช้ class `.card` และกำหนด theme ผ่าน `:root`

Required CSS

- `:root` มี color variables อย่างน้อย 3 ค่า
- `.card` มี padding, border, background, border-radius
- `.card h2` มีสีจาก variable
- `.card:hover` มี effect เล็กน้อย
- ไม่มี inline style ใน HTML

---

## 8. Common Mistakes

| Mistake | Impact | Fix |
|---|---|---|
| ใช้ inline style มากเกินไป | maintain ยาก | ย้ายไป external CSS |
| ใช้ ID selector กับทุกอย่าง | specificity สูงเกินควบคุม | ใช้ class เป็นหลัก |
| ลืม semicolon | rule ถัดไปอาจผิด | ใส่ `;` หลัง declaration |
| selector กว้างเกินไป | กระทบ element อื่นโดยไม่ตั้งใจ | ใช้ class ที่สื่อความหมาย |
| ตั้งชื่อ class จากสี เช่น `.blue` | เปลี่ยน design แล้วยุ่ง | ตั้งตามหน้าที่ เช่น `.card-title` |

---

## 9. Submission Checklist

- [ ] CSS อยู่ในไฟล์แยก
- [ ] HTML ไม่มี inline style โดยไม่จำเป็น
- [ ] ใช้ class selector เป็นหลัก
- [ ] ใช้ CSS variables
- [ ] เข้าใจ rule ที่ชนะเมื่อ style ซ้อนกัน
- [ ] มี hover state อย่างเหมาะสม
- [ ] comment อธิบายส่วนสำคัญ

---

## 10. References

- MDN Web Docs. CSS first steps. https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics
- MDN Web Docs. Cascade and inheritance. https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics/Handling_conflicts
- web.dev. Learn CSS: Cascade. https://web.dev/learn/css/the-cascade
- web.dev. Learn CSS: Specificity. https://web.dev/learn/css/specificity
