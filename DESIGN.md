# DESIGN.md — Sen Đá Spa & Wellness

Landing page spa Sen Đá Spa & Wellness. Repo: `m-software-sen-da-spa-wellness`.
Task thiết kế: TEC-148 (Epic TEC-147, yêu cầu MSR-20). Tài liệu này là quyết định thiết kế
duy nhất cho sprint: Dev dựng đúng các thông số dưới đây, QA đối chiếu đúng các thông số
này (OPERATIONS.md mục 16.2, 16.4). Mọi màu, font, tỉ lệ khung đều chốt bằng số —
không dùng mô tả cảm tính thay cho thông số.

## 1. Phong cách tham chiếu (chỉ một)

**Spa retreat tối giản, nhiều khoảng thở** — không gian spa yên tĩnh kiểu retreat:
ảnh lớn chiếm chủ đạo, nền sáng dịu, mỗi section chỉ một ý chính, khoảng trắng rộng
để mắt nghỉ giữa các khối nội dung. Toàn bộ lựa chọn màu/font/bố cục dưới đây phục vụ
đúng phong cách này, không trộn thêm phong cách khác.

## 2. Bảng màu (mã hex + vai trò từng màu)

| Mã hex | Tên gọi trong dự án | Vai trò — dùng ở đâu, không dùng ở đâu |
|---|---|---|
| `#EDF0E9` | Nền sương | Màu nền chính toàn trang, nền mọi section. Không dùng làm màu chữ. |
| `#2E2A26` | Chữ than nâu | Màu chữ duy nhất cho nội dung đọc: tiêu đề, đoạn văn, nhãn nút phụ. Không dùng làm nền khối lớn. |
| `#55684C` | Xanh rêu nhấn | Màu nhấn chính: nút đặt lịch chính, tiêu đề section (dạng eyebrow/kicker), đường gạch chân tiêu đề, icon. Không dùng làm màu chữ đoạn văn dài (chỉ dùng cho chữ ngắn: nút, kicker). |
| `#FFFFFF` | Trắng sứ | Nền phụ cho thẻ dịch vụ và form đặt lịch, để tách khỏi nền sương `#EDF0E9`. |
| `#8A9B7E` | Xanh rêu nhạt | Màu phụ thứ cấp: viền thẻ, đường chia section, nền khối trích dẫn. Không thay thế `#55684C` cho nút chính. |
| `#D8D2C4` | Be đá | Màu phụ thứ ba, chỉ dùng cho chi tiết nhỏ: viền ảnh, nền badge giá. Không dùng làm nền section. |

Quy tắc tương phản: chữ `#2E2A26` trên nền `#EDF0E9` hoặc `#FFFFFF`; chữ trắng
`#FFFFFF` chỉ đặt trên nút nền `#55684C`. Không đặt chữ `#55684C` lên nền `#8A9B7E`.

## 3. Font chữ (tên font thật)

- **Tiêu đề: Cormorant Garamond** — serif, dùng cho: tên thương hiệu, tiêu đề hero,
  tiêu đề section. Trọng lượng: 500 cho tiêu đề section, 600 cho tiêu đề hero.
  Cỡ: hero 56px desktop / 40px mobile; tiêu đề section 40px desktop / 30px mobile;
  tên dịch vụ 24px.
- **Nội dung: Be Vietnam Pro** — sans-serif, dùng cho: đoạn văn, mô tả dịch vụ, nhãn,
  nút, form, footer. Trọng lượng: 400 cho đoạn văn, 500 cho nhãn/nút, 700 chỉ cho giá.
  Cỡ: đoạn văn 17px, line-height 1.7; nhãn/kicker 13px, viết hoa, giãn chữ 0.12em;
  nút 16px.
- Không dùng font thứ ba. Tiêu đề không dùng Be Vietnam Pro, nội dung không dùng
  Cormorant Garamond.

## 4. Bố cục visual-first (mục 16.1)

Ảnh là nội dung chính, chữ phục vụ ảnh. Cấu trúc trang, theo thứ tự:

1. **Hero** — ảnh toàn chiều ngang, tiêu đề Cormorant Garamond chồng lên vùng tối nhẹ
   của ảnh, một nút đặt lịch `#55684C` duy nhất.
2. **Giới thiệu** — 1 ảnh lớn + tối đa 2 đoạn văn ngắn (mỗi đoạn ≤ 3 câu).
3. **Dịch vụ** — lưới thẻ: mỗi thẻ 1 ảnh + tên dịch vụ + 1 câu mô tả + giá.
4. **Không gian** — băng ảnh ngang (gallery), không chèn đoạn văn dài.
5. **Trích dẫn khách** — 1 câu trích dẫn trên nền `#8A9B7E` nhạt, không liệt kê dài.
6. **Đặt lịch** — form ngắn (tên, số điện thoại, dịch vụ, ngày giờ) trên nền `#FFFFFF`.
7. **Footer** — địa chỉ, giờ mở cửa, liên hệ; không thêm section khác.

Khoảng trắng: padding section 96px desktop / 56px mobile (trên + dưới);
khoảng cách giữa các thẻ 24px; chiều rộng nội dung tối đa 1120px, căn giữa.
Mỗi section tối đa 1 tiêu đề + 1 đoạn dẫn ngắn; không xếp 2 khối chữ dài liền nhau.

## 5. Quy tắc hình ảnh

- **Kiểu ảnh: ảnh thật** (không gian spa, liệu trình, chi tiết đá/lá/cây xanh) —
  không dùng minh họa vẽ tay hay icon thay ảnh.
- **Tông ảnh: dịu mát, đồng tông** — ánh sáng tự nhiên mềm, gam xanh lá + be + trắng
  khớp bảng màu mục 2; ảnh phải cùng độ sáng và độ bão hòa (không trộn ảnh rực rỡ,
  tối gắt, hay lọc màu mạnh). Ảnh mẫu lúc đầu phải tuân đúng tông này (mục 16.3).
- **Tỉ lệ khung (bắt buộc, Dev cắt đúng tỉ lệ này):**
  - Hero: 16:9 desktop, 4:5 mobile (cắt từ cùng một ảnh, giữ chủ thể ở giữa).
  - Ảnh giới thiệu: 4:3.
  - Ảnh thẻ dịch vụ: 4:3, mọi thẻ cùng tỉ lệ.
  - Ảnh gallery không gian: 3:2, băng ngang cuộn hoặc lưới 3 cột.
  - Ảnh trích dẫn (nếu có): không dùng ảnh nền chữ — trích dẫn đặt trên nền màu `#8A9B7E`.
- **Chất lượng:** ảnh tối thiểu 1600px chiều ngang cho hero, 1200px cho ảnh thẻ/gallery;
  không kéo giãn, không cắt mất chủ thể chính.

## 6. Thành phần giao diện (thông số chốt)

- **Nút chính:** nền `#55684C`, chữ `#FFFFFF` Be Vietnam Pro 500 16px, bo góc 999px
  (viên thuốc), padding 14px 32px.
- **Nút phụ:** viền 1px `#55684C`, nền trong suốt, chữ `#55684C`.
- **Thẻ dịch vụ:** nền `#FFFFFF`, bo góc 16px, viền 1px `#8A9B7E`, ảnh 4:3 bo góc trên 16px.
- **Form:** ô nhập nền `#FFFFFF`, viền 1px `#D8D2C4`, bo góc 12px, nhãn Be Vietnam Pro
  500 14px màu `#2E2A26`.
- **Header:** nền `#EDF0E9`, logo chữ Cormorant Garamond 600 28px màu `#2E2A26`,
  link điều hướng Be Vietnam Pro 500 15px màu `#2E2A26`; header dính trên cùng khi cuộn.
- **Footer:** nền `#2E2A26`, chữ `#EDF0E9` Be Vietnam Pro 400 15px.

## 7. Checklist đối chiếu OPERATIONS.md mục 16.2 (Designer tự kiểm trước bàn giao)

- [x] Bảng màu mã hex kèm vai trò từng màu — mục 2: nền chính `#EDF0E9`, chữ
  `#2E2A26`, nhấn `#55684C` (cả ba mã bắt buộc đều có) + 3 màu phụ có vai trò riêng.
- [x] Font tiêu đề + font nội dung cụ thể — mục 3: Cormorant Garamond + Be Vietnam Pro,
  kèm trọng lượng và cỡ chữ.
- [x] MỘT phong cách tham chiếu có tên gọi rõ — mục 1: "spa retreat tối giản,
  nhiều khoảng thở" (chỉ một, không trộn phong cách khác).
- [x] Quy tắc hình ảnh — mục 5: tỉ lệ khung (16:9 / 4:5 / 4:3 / 3:2), tông ảnh dịu mát
  đồng tông, kiểu ảnh thật, độ phân giải tối thiểu.
- [x] Ưu tiên visual-first (mục 16.1) — mục 4: bố cục ảnh lớn + khoảng trắng 96px/56px,
  7 section chốt thứ tự, giới hạn chữ mỗi section.
- [x] Không mô tả thẩm mỹ chung chung không kèm thông số — mọi tính từ trong tài liệu
  này đều đi kèm mã hex, tên font, cỡ chữ hoặc tỉ lệ khung cụ thể.
