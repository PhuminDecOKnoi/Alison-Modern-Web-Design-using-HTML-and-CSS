# Week 07 — Flexbox Layout

> บทเรียนที่ 7: ใช้ Flexbox สร้าง layout แนวเดียว เช่น navbar, button group, card row และ alignment

---

## 1. Lesson Goal

ให้ผู้เรียนเข้าใจว่า Flexbox เหมาะกับ layout แบบหนึ่งมิติ หรือ one-dimensional layout ซึ่งควบคุมการจัดวางตามแกนหลักและแกนตัดได้ดี เช่น menu แนวนอน, ปุ่มเรียงกัน, card row และการจัดกึ่งกลาง

---

## 2. Learning Outcomes

| Outcome | Description |
|---|---|
| LO1 | อธิบาย main axis และ cross axis ได้ |
| LO2 | ใช้ `display: flex` ได้ถูกต้อง |
| LO3 | ใช้ `justify-content`, `align-items`, `gap` ได้ |
| LO4 | ใช้ `flex-wrap` เพื่อป้องกัน layout ล้นจอได้ |
| LO5 | สร้าง responsive navbar ด้วย Flexbox ได้ |

---

## 3. Flexbox Mental Model

| Concept | Meaning |
|---|---|
| Flex container | element แม่ที่กำหนด `display: flex` |
| Flex items | element ลูกโดยตรงของ flex container |
| Main axis | แกนหลักตาม `flex-direction` |
| Cross axis | แกนตัดกับ main axis |
| `gap` | ระยะห่างระหว่าง flex items |

```css
.container {
  display: flex;
}
```

เมื่อกำหนด `display: flex` ให้ element แม่ ลูกโดยตรงจะถูกจัดวางด้วยระบบ Flexbox

---

## 4. Annotated Navbar Example

### HTML

```html
<header class="site-header">
  <nav class="navbar" aria-label="เมนูหลัก">
    <a class="logo" href="index.html">HTML CSS Course</a>

    <ul class="nav-menu">
      <li><a href="#lessons">Lessons</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>
</header>
```

### CSS

```css
.site-header {
  background: #0f4c81;
  color: #ffffff;
}

/*
  navbar คือ flex container
  ลูกโดยตรงคือ .logo และ .nav-menu
*/
.navbar {
  width: min(100% - 2rem, 1100px);
  margin-inline: auto;

  display: flex;
  /* จัด logo กับ menu ให้อยู่คนละฝั่งของแกนหลัก */
  justify-content: space-between;

  /* จัดให้อยู่กึ่งกลางในแกนตั้ง */
  align-items: center;

  /* ระยะห่างเมื่อพื้นที่แคบ */
  gap: 1rem;
  padding: 1rem 0;
}

.logo {
  font-weight: 800;
  color: inherit;
  text-decoration: none;
}

/*
  nav-menu ก็เป็น flex container อีกชั้น
  ลูกโดยตรงคือ li แต่ละตัว
*/
.nav-menu {
  display: flex;
  gap: 1rem;
  margin: 0;
  padding: 0;
  list-style: none;
}

.nav-menu a {
  color: inherit;
  text-decoration: none;
}

.nav-menu a:hover {
  text-decoration: underline;
  text-underline-offset: 0.35rem;
}
```

---

## 5. Responsive Flexbox

```css
/*
  เมื่อหน้าจอแคบกว่า 720px
  เปลี่ยน navbar จากแนวนอนเป็นแนวตั้ง
*/
@media (max-width: 720px) {
  .navbar {
    flex-direction: column;
    align-items: flex-start;
  }

  .nav-menu {
    flex-wrap: wrap;
  }
}
```

---

## 6. Flexbox Properties Quick Reference

| Property | Use on | Purpose |
|---|---|---|
| `display: flex` | Container | เปิด Flexbox |
| `flex-direction` | Container | กำหนดแกนหลัก เช่น row/column |
| `justify-content` | Container | จัดตำแหน่งตาม main axis |
| `align-items` | Container | จัดตำแหน่งตาม cross axis |
| `gap` | Container | ระยะห่างระหว่าง items |
| `flex-wrap` | Container | ให้ items ขึ้นบรรทัดใหม่เมื่อพื้นที่ไม่พอ |
| `flex` | Item | กำหนดการยืด/หดของ item |

---

## 7. Workshop

### Task: Build a Responsive Navigation Bar

สร้าง navigation bar โดยมี

- logo ด้านซ้าย
- menu ด้านขวา 4 รายการ
- ใช้ Flexbox
- มี hover state
- เมื่อจอเล็กให้ menu เรียงหรือ wrap ได้โดยไม่ล้น

### Bonus

เพิ่ม button “Start Learning” ใน navbar และทำให้ยัง responsive ได้

---

## 8. Common Mistakes

| Mistake | Impact | Fix |
|---|---|---|
| ใส่ `display:flex` ที่ item แทน container | layout ไม่ทำงานตามคาด | ใส่ที่ parent ของ items |
| ใช้ margin-right กับทุก item | maintain ยาก | ใช้ `gap` |
| ไม่ใช้ `flex-wrap` | menu ล้นจอบนมือถือ | เพิ่ม `flex-wrap: wrap` |
| ใช้ Flexbox กับ layout 2 มิติซับซ้อน | code ยุ่ง | ใช้ CSS Grid กับ rows + columns |
| fixed width ปุ่มมากเกินไป | mobile ล้น | ใช้ padding และ min-height แทน |

---

## 9. Submission Checklist

- [ ] ใช้ `display: flex` กับ container ถูกจุด
- [ ] ใช้ `gap` แทน margin ซ้ำ ๆ
- [ ] ใช้ `justify-content` ได้เหมาะสม
- [ ] ใช้ `align-items` ได้เหมาะสม
- [ ] มี responsive behavior
- [ ] ไม่มี horizontal overflow บนมือถือ
- [ ] nav ใช้ semantic `<nav>` และมี link text ชัดเจน
- [ ] มี comment ภาษาไทยอธิบาย Flexbox

---

## 10. References

- MDN Web Docs. Flexbox. https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/CSS_layout/Flexbox
- web.dev. Learn CSS: Flexbox. https://web.dev/learn/css/flexbox
- MDN Web Docs. Basic concepts of flexbox. https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Basic_concepts_of_flexbox
