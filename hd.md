# HƯỚNG DẪN SỬ DỤNG BỘ THƯ VIỆN FRONT-END (HTML / CSS / JS)

Chào bạn 👋
Đây là tài liệu **Markdown** hướng dẫn chi tiết cách sử dụng và tùy biến các thư viện front-end đã được tích hợp trong file HTML của bạn.

---

## MỤC LỤC

1. [Typed.js – Hiệu ứng gõ chữ](#1-typedjs--hiệu-ứng-gõ-chữ)
2. [AOS – Hiệu ứng khi cuộn trang](#2-aos--hiệu-ứng-khi-cuộn-trang-scroll)
3. [Animate.css – Hiệu ứng động CSS](#3-animatecss--hiệu-ứng-động-css)
4. [Tippy.js – Tooltip chú thích](#4-tippyjs--chú-thích-khi-rê-chuột)
5. [LottieFiles – Hoạt hình JSON](#5-lottiefiles--hoạt-hình-json)
6. [Swiper – Slider chạy ảnh](#6-swiper--slider-chạy-ảnh)
7. [OverlayScrollbars – Thanh cuộn custom](#7-overlayscrollbars--thanh-cuộn-custom)
8. [MicroModal – Popup cửa sổ](#8-micromodal--popup-cửa-sổ)

---

## 1. Typed.js – Hiệu ứng gõ chữ

Tạo hiệu ứng máy đánh chữ tự động.

### Cách dùng

**HTML**

```html
<h1>Xin chào, tôi là <span class="element"></span></h1>
```

**JavaScript (đặt ở cuối trang)**

```js
var typed = new Typed(".element", {
  strings: ["Designer.", "Developer.", "Gamer."],
  typeSpeed: 50,
  backSpeed: 30,
  backDelay: 1000,
  startDelay: 500,
  loop: true,
  showCursor: true,
  cursorChar: "_",
});
```

---

## 2. AOS – Hiệu ứng khi cuộn trang (Scroll)

Khi cuộn trang xuống, nội dung sẽ xuất hiện kèm hiệu ứng.

### Cách dùng

```html
<div data-aos="fade-up">Tôi bay từ dưới lên</div>
<div data-aos="flip-left">Tôi xoay vòng</div>
<div data-aos="zoom-in">Tôi phóng to ra</div>
```

### Hiệu ứng phổ biến

`fade-up`, `fade-down`, `fade-left`, `fade-right`, `flip-up`, `zoom-in`, `zoom-out`

### Custom trực tiếp trên HTML

```html
<div
  data-aos="fade-up"
  data-aos-offset="200"
  data-aos-delay="50"
  data-aos-duration="1000"
  data-aos-once="true"
>
  Nội dung
</div>
```

---

## 3. Animate.css – Hiệu ứng động CSS

Hiệu ứng nảy, rung, thu hút sự chú ý (thường dùng cho nút hoặc cảnh báo).

### Cách dùng

```html
<button class="animate__animated animate__bounce">Nhấn tôi đi</button>
<div class="animate__animated animate__shakeX">Sai mật khẩu!</div>
```

### Custom

Các class hỗ trợ:

- `animate__infinite`
- `animate__delay-2s`
- `animate__faster`
- `animate__slower`

```html
<div class="animate__animated animate__pulse animate__infinite">
  Đập thình thịch
</div>
```

---

## 4. Tippy.js – Chú thích khi rê chuột (Tooltip)

Hiển thị tooltip gọn gàng, hiện đại.

### Cách dùng

```html
<button data-tippy-content="Đây là nút Home nè!">Trang chủ</button>
<a href="#" data-tippy-content="Click để gửi mail">Liên hệ</a>
```

### Custom JavaScript

```js
tippy("[data-tippy-content]", {
  placement: "right",
  animation: "scale",
  theme: "light",
  arrow: true,
  delay: [200, 0],
});
```

---

## 5. LottieFiles – Hoạt hình JSON

Hoạt hình vector siêu nhẹ, siêu nét.

### Cách dùng

```html
<lottie-player
  src="https://assets.lottiefiles.com/packages/lf20_abc123.json"
  background="transparent"
  speed="1"
  style="width: 300px; height: 300px;"
  loop
  autoplay
>
</lottie-player>
```

### Custom

- `autoplay` → `hover`: chạy khi rê chuột
- `speed="0.5"` chậm – `2` nhanh
- Thêm `controls` để hiện thanh điều khiển

---

## 6. Swiper – Slider chạy ảnh

Dùng cho banner, gallery, sản phẩm.

### Cấu trúc HTML (bắt buộc)

```html
<div class="swiper">
  <div class="swiper-wrapper">
    <div class="swiper-slide">Slide 1</div>
    <div class="swiper-slide">Slide 2</div>
    <div class="swiper-slide"><img src="anh.jpg" /></div>
  </div>

  <div class="swiper-pagination"></div>
  <div class="swiper-button-prev"></div>
  <div class="swiper-button-next"></div>
</div>
```

### Custom JavaScript

```js
const swiper = new Swiper(".swiper", {
  direction: "horizontal",
  loop: true,
  effect: "fade",
  autoplay: {
    delay: 3000,
    disableOnInteraction: false,
  },
  pagination: {
    el: ".swiper-pagination",
    clickable: true,
  },
  navigation: {
    nextEl: ".swiper-button-next",
    prevEl: ".swiper-button-prev",
  },
});
```

---

## 7. OverlayScrollbars – Thanh cuộn custom

Thay thế scrollbar mặc định của trình duyệt.

```js
OverlayScrollbars(document.querySelector("body"), {
  scrollbars: {
    autoHide: "leave",
    theme: "os-theme-dark",
  },
});
```

Giá trị `autoHide`:

- `never`
- `leave`
- `scroll`

---

## 8. MicroModal – Popup cửa sổ

Popup hiển thị giữa màn hình.

### HTML mẫu

```html
<div class="modal micromodal-slide" id="modal-1" aria-hidden="true">
  <div class="modal__overlay" tabindex="-1" data-micromodal-close>
    <div class="modal__container" role="dialog" aria-modal="true">
      <header class="modal__header">
        <h2 class="modal__title">Tiêu đề Popup</h2>
        <button class="modal__close" data-micromodal-close></button>
      </header>
      <main class="modal__content">
        <p>Nội dung thông báo ở đây...</p>
      </main>
    </div>
  </div>
</div>

<button data-micromodal-trigger="modal-1">Mở Popup</button>
```

### CSS bắt buộc

```css
.modal {
  display: none;
}
.modal.is-open {
  display: block;
}
```

### Custom JavaScript

```js
MicroModal.init({
  onShow: (modal) => console.log(`${modal.id} đang mở`),
  onClose: (modal) => console.log(`${modal.id} đã đóng`),
  openTrigger: "data-micromodal-trigger",
  closeTrigger: "data-micromodal-close",
  disableScroll: true,
});
```

---

## 9. Bulma – CSS Framework (Layout & Giao diện)

Bulma là framework CSS **nhẹ, hiện đại**, dựa trên **Flexbox**.
Đặc biệt: **không có JavaScript đi kèm**, chỉ dùng CSS để style.

---

### Cách dùng (Cài đặt)

Dán link CDN sau vào thẻ `<head>`:

```html
<link
  rel="stylesheet"
  href="https://cdn.jsdelivr.net/npm/bulma@1.0.2/css/bulma.min.css"
/>
```

---

### Các class thông dụng

Bulma sử dụng tên class tiếng Anh rất **tự nhiên, dễ nhớ**.

---

### 1. Nút bấm (Button)

```html
<button class="button">Nút thường</button>
<button class="button is-primary">Nút màu chính</button>
<button class="button is-danger is-rounded">Nút báo lỗi (bo tròn)</button>
<button class="button is-loading">Nút đang tải</button>
```

---

### 2. Chia cột (Columns)

Dùng để chia layout (bố cục) web.

```html
<div class="columns">
  <div class="column">Cột 1</div>
  <div class="column">Cột 2</div>
  <div class="column">Cột 3</div>
  <div class="column is-one-quarter">Cột nhỏ (1/4)</div>
</div>
```

---

### 3. Khung thông báo (Notification)

```html
<div class="notification is-info">
  <button class="delete"></button>
  Xin chào, đây là thông báo màu xanh!
</div>
```

---

### 4. Hero Banner (Banner to đầu trang)

```html
<section class="hero is-info is-large">
  <div class="hero-body">
    <p class="title">Tiêu đề lớn</p>
    <p class="subtitle">Mô tả ngắn gọn súc tích</p>
  </div>
</section>
```

---

### Lưu ý quan trọng (Xử lý JavaScript)

Vì Bulma **chỉ có CSS**, nên các thành phần như:

- Menu mobile (hamburger)
- Nút đóng notification

👉 Bạn cần tự viết **JavaScript nhỏ** để bật/tắt class `is-active`.

#### Ví dụ: Bật menu mobile (Navbar Burger)

```js
const burger = document.querySelector(".navbar-burger");
const menu = document.querySelector(".navbar-menu");

burger.addEventListener("click", () => {
  burger.classList.toggle("is-active");
  menu.classList.toggle("is-active");
});
```

---

### Tóm tắt nhanh cho bạn

- Bulma rất đẹp, class như `is-primary`, `is-large` cực dễ nhớ
- Không phá vỡ HTML cũ nhiều
- Không phụ thuộc JavaScript framework
- **Bulma 1.0+ tự hỗ trợ Dark Mode** theo hệ điều hành người dùng

---

✅ **Tài liệu này có thể dùng trực tiếp để lưu `.md`, up GitHub, xuất PDF hoặc làm docs cho project.**
