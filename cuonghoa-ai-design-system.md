# Cường Hóa AI — Claude Design System

> File này dùng để paste vào phần đầu System Prompt khi làm việc với Claude trên các task thiết kế giao diện, landing page, component, hoặc bất kỳ output visual nào thuộc thương hiệu Cường Hóa AI / EGANY.

---

## 1. Brand context

**Thương hiệu:** Cường Hóa AI (thuộc EGANY)  
**Đối tượng:** Chủ shop, hộ kinh doanh nhỏ, người bán hàng online không rành kỹ thuật  
**Giọng điệu:** Thẳng thắn, gần gũi, nói đúng vấn đề — không hoa mỹ, không hứa hẹn quá đà  
**Mục tiêu trang:** Chuyển đổi mua hàng — không phải branding chung chung

---

## 2. Màu sắc (Color tokens)

```
--color-primary:      #264D3C   /* Forest green — background hero, section dark */
--color-accent:       #EE9702   /* Amber — CTA button, highlight chính */
--color-accent-warm:  #F38D3F   /* Orange — gradient, hover state, badge phụ */
--color-surface:      #FFFFFF   /* Trắng — card, content block */
--color-surface-alt:  #F5F4F0   /* Kem nhạt — background section xen kẽ */
--color-text-primary: #1A1A1A   /* Gần đen — body text */
--color-text-muted:   #6B6B6B   /* Xám trung — caption, label phụ */
--color-text-inverse: #FFFFFF   /* Trắng — text trên nền tối */
--color-border:       #E2E0D8   /* Xám nhạt — border card, divider */
--color-success:      #2E7D52   /* Xanh lá đậm — checkmark, positive indicator */
```

**Quy tắc dùng màu:**
- Nền section chính: xen kẽ `--color-surface` và `--color-surface-alt`
- Section hero / dark: `--color-primary` làm nền, text dùng `--color-text-inverse`
- CTA button duy nhất: `--color-accent` (#EE9702), text trắng
- Accent phụ (badge, icon, highlight): `--color-accent-warm`
- Không dùng quá 3 màu trong 1 component

---

## 3. Typography

**Font chữ:**
- Display / Heading: `Be Vietnam Pro` — weight 600, 700
- Body / UI: `Nunito` — weight 400, 600
- Fallback: `system-ui, sans-serif`

**Type scale:**

| Role | Font | Size | Weight | Line-height |
|---|---|---|---|---|
| H1 — Hero headline | Be Vietnam Pro | 40–48px | 700 | 1.15 |
| H2 — Section heading | Be Vietnam Pro | 28–34px | 600 | 1.2 |
| H3 — Card / sub-heading | Be Vietnam Pro | 20–24px | 600 | 1.3 |
| Body large | Nunito | 18px | 400 | 1.7 |
| Body | Nunito | 16px | 400 | 1.7 |
| Caption / label | Nunito | 13–14px | 400 | 1.5 |
| Button | Nunito | 16–18px | 600 | 1 |
| Blockquote | Nunito | 17px | 400 italic | 1.6 |

**Quy tắc:**
- Headline dùng font Be Vietnam Pro, không dùng Nunito cho H1/H2
- Không dùng ALL CAPS trừ badge nhỏ (ví dụ: "ƯU ĐÃI")
- Blockquote có `border-left: 3px solid --color-accent`, padding-left 16px

---

## 4. Spacing scale

```
--space-xs:   4px
--space-sm:   8px
--space-md:   16px
--space-lg:   24px
--space-xl:   40px
--space-2xl:  64px
--space-3xl:  96px

Section padding (trên/dưới): 80px desktop / 48px mobile
Card padding (trong): 24px desktop / 16px mobile
Gap giữa card trong grid: 20–24px
```

---

## 5. Component patterns

### 5.1 CTA Button (primary)

```
background: #EE9702
color: #FFFFFF
font: Nunito 600 17px
padding: 16px 36px
border-radius: 8px
border: none
box-shadow: 0 2px 12px rgba(238, 151, 2, 0.35)
```

Hover state: `background: #F38D3F`, shadow tăng nhẹ  
Không dùng outline button làm CTA chính — chỉ dùng cho action phụ

### 5.2 Pain card (Problem agitation block)

Cấu trúc:
```
[Icon hoặc emoji nhỏ]
[Tiêu đề H3 — câu hỏi hoặc phát biểu pain]
[1–3 dòng mô tả — ngôi thứ 2, kể situation cụ thể]
[Blockquote — phát biểu nội tâm của người dùng]
```

Style:
- Nền: `--color-surface-alt`
- Border-left: `3px solid --color-accent-warm`
- Không có border xung quanh
- Padding: 24px

### 5.3 Solution card (Trước / Sau)

Cấu trúc:
```
[Thumbnail YouTube — tỉ lệ 16:9, border-radius 8px]
[Tên video — H3]
[Cột TRƯỚC] [Cột SAU]  ← 2 cột trên desktop, stack trên mobile
[Checklist 4 dòng — icon ✓ màu success, text 15px]
```

Style:
- Card nền trắng, border `1px solid --color-border`, border-radius 12px
- Nhãn "Trước": text xám muted, italic
- Nhãn "Sau": text primary, weight 600
- Checklist icon: `--color-success`

### 5.4 Pricing comparison row

Cấu trúc:
```
[Bảng 3 cột: Tên việc | Thuê người | Combo AI]
[Row cuối: Tổng chi phí — in đậm]
```

Style:
- Header row: nền `--color-primary`, text trắng
- Cột "Combo AI": nền `rgba(238, 151, 2, 0.08)`, badge "ĐƯỢC ĐỀ XUẤT" màu amber
- Cell "Thuê người": text xám có strikethrough gợi ý
- Cell "Combo AI": text `--color-accent`, font weight 600

### 5.5 Guarantee badge

```
[Icon khiên — stroke, không fill]
[Tiêu đề: "Cam kết hoàn tiền 48h"]
[Dòng phụ: "Không cần giải thích lý do"]
```

Style:
- Border: `1.5px solid --color-success`
- Border-radius: 12px
- Padding: 20px 24px
- Icon màu `--color-success`
- Nền: `rgba(46, 125, 82, 0.06)`

### 5.6 Social proof — video testimonial card

```
[Thumbnail YouTube — có play button overlay]
[Tên + nghề nghiệp — H3 nhỏ]
```

Style:
- Grid 3 cột desktop / 2 cột tablet / 1 cột mobile
- Thumbnail border-radius 8px
- Play button: hình tròn nền amber, icon tam giác trắng
- Caption text: 14px, muted

### 5.7 FAQ accordion

```
[Câu hỏi — H3 nhỏ, weight 600]
[Icon mũi tên xoay khi mở]
[Nội dung — body 16px, hiện/ẩn]
[Divider giữa các mục]
```

Style:
- Không có border ngoài accordion
- Chỉ có `border-bottom: 1px solid --color-border` giữa mỗi item
- Padding trên/dưới mỗi item: 20px
- Không dùng card wrapper cho FAQ

---

## 6. Layout

### Grid system

```
Max-width container: 1100px
Padding ngang (desktop): 40px
Padding ngang (mobile): 20px

Breakpoints:
- Mobile:  < 768px
- Tablet:  768px – 1024px
- Desktop: > 1024px
```

### Cấu trúc section chuẩn

```
[Section label — 12px uppercase, letter-spacing 2px, màu accent]  ← tuỳ chọn
[Heading H2 — căn giữa hoặc trái]
[Sub-text — tối đa 2 dòng, muted]
[Content area]
[CTA — nếu cần]
```

### Thứ tự block trên landing page

1. Hero — headline + sub + CTA
2. Pain agitation — 6–8 pain points
3. Giải pháp — danh sách sản phẩm/video
4. Bonus / giá trị thêm
5. Social proof — testimonial + kết quả
6. Pricing + so sánh
7. Guarantee
8. FAQ
9. CTA cuối + Order form

---

## 7. Quy tắc viết copy (Voice & Tone)

- Dùng ngôi **"bạn"** — không dùng "quý khách"
- Câu ngắn, đứng riêng một dòng khi muốn nhấn mạnh
- Pain points: viết như đang kể lại situation — không phán xét
- Benefit: nói kết quả cụ thể — không nói tính năng
- CTA: bắt đầu bằng động từ hành động — "Tôi muốn...", "Bắt đầu...", "Sở hữu..."
- Không dùng: "giải pháp toàn diện", "đột phá", "hàng đầu", "tối ưu vượt trội"
- Số liệu cụ thể ưu tiên hơn tính từ: "789.000đ" tốt hơn "giá rất hợp lý"

---

## 8. Những gì KHÔNG làm

- Không dùng gradient nhiều màu trên hero
- Không dùng animation chạy liên tục (chỉ dùng khi scroll trigger)
- Không để section trắng hoàn toàn liên tiếp — phải xen kẽ `surface-alt`
- Không đặt 2 CTA button cùng màu gần nhau
- Không dùng màu đỏ cho bất kỳ element nào — không phù hợp tone
- Không dùng border-radius > 12px cho card lớn
- Không để H2 dài quá 2 dòng trên desktop

---

## 9. Ví dụ dùng file này với Claude

Paste đoạn sau vào đầu prompt khi giao task thiết kế:

```
Dùng design system sau khi thiết kế: [paste toàn bộ nội dung file này]

Task: [mô tả task cụ thể]
```

Hoặc lưu file này vào Project Instructions trong Claude Projects để áp dụng tự động cho toàn bộ conversation.

---

*Last updated: 06/2026 — dựa trên phân tích landing page go.cuonghoa.ai/combo-7in1*
