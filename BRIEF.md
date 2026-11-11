# Đề bài thiết kế softaz.vn — vòng 1 (từ mockup 5.0)

> Bản 0.1 · 11/11/2026 · nguồn : bố cục 3.0 «Cửa hàng phần mềm» + mockup 5.0 của SoftAZ. Câu hỏi về đề bài : ghi vào phiếu bàn giao hoặc bình luận PR.

## 1. Mục tiêu

softaz.vn là web công ty SoftAZ và **cửa hàng chung** của các phần mềm SoftAZ : khách chọn phần mềm (= **sản phẩm**) → chọn gói (= **biến thể**) → giỏ hàng
→ thanh toán ; hoặc **dùng thử miễn phí** ngay trên web.

Năm yêu cầu của SoftAZ (11/11/2026) : (1) hai tông sáng / tối ; (2) nhiều hình ảnh thay chữ — chừa sẵn khung ảnh thật ; (3) bảng các gói, đặt hàng và dùng
thử ngay trên softaz.vn ; (4) nút, khung bo cong mềm mại ; (5) nhiều sơ đồ thể hiện liên kết các chức năng.

Mockup 5.0 đã có cấu trúc và nội dung ; SoftAZ đánh giá «khá hơn, chưa hoàn toàn ưng ý». Việc của bạn : nâng chất lượng thị giác — bố cục, nhịp, hình ảnh,
minh hoạ, kiểu chữ, chuyển động gợi ý — **giữ** cấu trúc trang, luồng mua / dùng thử và nội dung chữ.

## 2. Trang và khung

| Mã khung | Trang | Đường dẫn | Mockup 5.0 | Bề rộng | Trên Figma (11/11) |
|---|---|---|---|---|---|
| `Home` | Trang chủ | `/` | Main · MainDark · MainMobile | 1440 + 390 | ✓ 1440 Light + Dark · ✓ 390 |
| `Product-pos` `Product-tax` `Product-crm` `Product-wty` | Trang phần mềm — **một khuôn**, bốn bộ nội dung | `/san-pham/<mã>` | ProductPos · ProductTax · ProductCrm · ProductWty · ProductMobile | 1440 + 390 | ✓ pos 1440 + 390 · tax / crm / wty : nhân khuôn, đổi nội dung |
| `Pricing` | Bảng giá | `/bang-gia` | Pricing | 1440 + 390 | ✓ 1440 · 390 chưa |
| `Register-<mã>` | **Đăng ký** (gói, quy mô theo phần mềm, thông tin) → thanh toán QR → hoàn tất — nút «Đăng ký ngay» dẫn tới đây, **không qua giỏ** | `/dang-ky/<mã>` | — | 1440 + 390 | ✓ bán hàng 1440 · còn lại chưa |
| `Cart-1` … `Cart-4` | Giỏ hàng — **không còn trong luồng** (SoftAZ 11/11), giữ tham khảo | `/gio-hang` | Cart · CartMobile | 1440 + 390 | ✓ bước 1 (1440 + 390) |
| `Trial-1` … `Trial-4` | Dùng thử : chọn phần mềm + ngành → thông tin → chuẩn bị → sẵn sàng | `/dung-thu` | Trial | 1440 + 390 | ✓ bước 1 (1440) · còn lại chưa |
| `Platform` | Nền tảng — các sơ đồ liên kết | `/nen-tang` | Platform | 1440 + 390 | chưa |
| `About` | Về SoftAZ | `/ve-softaz` | About | 1440 + 390 | chưa |
| `News` `Contact` `Policy` | Tin tức · Liên hệ · 5 trang chính sách | `/tin-tuc` · `/lien-he` · … | chưa có | 1440 + 390 | — (vòng sau) |
| — | Sơ đồ trang (tham khảo, không phải trang web) | — | SiteMap | — | — |

Menu : **Sản phẩm · Bảng giá · Nền tảng · Dùng thử · Về SoftAZ** | nút ☀ / ☾ · giỏ hàng · Đăng nhập · nút «Dùng thử miễn phí».
Chính sách (5 trang) : bảo mật – dữ liệu cá nhân · điều khoản sử dụng · điều kiện giao dịch chung · thanh toán · hoàn tiền.

## 3. Khối trên từng trang

**Trang chủ (12 khối, theo thứ tự)** : đầu trang (dải ưu đãi mua theo bộ + menu) → mở đầu (câu H1 + ảnh máy tính, điện thoại, ba thẻ nổi) → kệ sản phẩm
(4 thẻ có ảnh màn hình, tên gói, «giá từ», nút «Chọn gói» / «Dùng thử» ; 2 thẻ «sắp ra mắt») → sơ đồ sáu phần mềm quanh một nền → «Bạn kinh doanh gì?»
(5 khung ảnh theo loại hình : «bắt đầu với» → «thêm khi cần») → bảng gói (bấm từng phần mềm xem các gói) → sơ đồ đặt mua + dùng thử → sơ đồ một đơn hàng đi
qua những đâu → dải mua theo bộ → làm việc với ai (pháp nhân, nhãn hiệu, giá + hoá đơn, người tư vấn) → tin mới (ảnh bìa) → dùng thử miễn phí (biểu mẫu + thẻ
người tư vấn có ảnh) → chân trang.

**Trang phần mềm** : khối mua (chọn gói, kỳ trả, tuỳ chọn thêm, giá, nút **«Đăng ký ngay»** / «Dùng thử» — **không nhập số lượng** : phần mềm đăng ký ngay, khác bán hàng hoá — SoftAZ 11/11) · ảnh màn hình + video · sơ đồ chuỗi
chức năng của phần mềm và phần mềm khác nhận / gửi dữ liệu · bảng so sánh các gói · mua kèm · hỏi đáp · thanh mua dính đáy màn hình (điện thoại).

**Giỏ hàng (4 bước)** : giỏ (nhiều phần mềm, giảm giá bộ, tổng — không có ô số lượng) → thông tin người mua + xuất hoá đơn → thanh toán (mã QR chuyển khoản, tự xác nhận) →
hoàn tất (mã đơn, việc tiếp theo). **Dùng thử (4 bước)** tương tự, không thanh toán.

## 4. Luật thiết kế

- Màu chỉ lấy từ biến `color/*` ; mỗi khung trang có bản Light + Dark (đổi mode, không vẽ lại).
- Tương phản đạt WCAG AA ở **cả hai mode** : chữ thường ≥ 4,5 : 1 ; chữ ≥ 24 px hoặc ≥ 18,5 px đậm ≥ 3 : 1.
- Máy tính 1440 (nội dung rộng `layout/content` 1104) ; điện thoại 390 (lề 16), **không cuộn ngang** ; vùng bấm ≥ 44 px ; nút cao 48 px.
- Bo cong : nút, chip, nhãn `radius/pill` ; thẻ `radius/card` – `radius/card-lg` ; khung ảnh `radius/frame` ; thẻ sơ đồ `radius/node` ; khối mở đầu `radius/hero`.
- Mỗi trang **một** tiêu đề cấp 1 (H1) ; tiêu đề khối là cấp 2.
- Chữ tiếng Việt có dấu, câu ngắn ; không dùng lorem ipsum — dùng chữ của mockup 5.0.
- Màu từng phần mềm : `color/product/*` (TaxAZ, CRMAZ, bán hàng, bảo hành ; DMSAZ, ERPAZ «sắp ra mắt»).
- Bóng (effect style, Figma chưa nhận bóng làm biến) : **L** `0 24 48 -24` màu `#0F1E33` 32 % · **S** `0 10 24 -16` `#0F1E33` 30 % ; bản tối : đen 70 % / 65 %.
- Viền tiêu điểm bàn phím : 3 px `#3D97E8`, cách 3 px.

## 5. Phần mềm — gói — giá

Giá đã gồm thuế GTGT ; số dưới đây SoftAZ đã chốt — **không đổi số** ; chỗ «(chờ)» giữ nguyên.

| Phần mềm (sản phẩm) | Gói (biến thể) | Tính theo | Kỳ | Tuỳ chọn thêm | Dùng thử |
|---|---|---|---|---|---|
| Phần mềm bán hàng | Cơ bản 150.000 (3 người dùng) · Chuyên nghiệp 250.000 (không giới hạn người dùng) · Chuỗi 390.000 + 190.000 mỗi cửa hàng thêm — đ / tháng | số cửa hàng | trả theo năm | hạn mức hoá đơn điện tử trong gói (chờ) | 14 ngày |
| TaxAZ | Hộ 490.000 · Hộ + 1.490.000 · Siêu nhỏ 2.490.000 · Tiêu chuẩn 3.990.000 · Nâng cao 7.990.000 · Doanh nghiệp 9.990.000 — đ / năm | số bộ sổ | năm | thêm người dùng 790.000 đ / năm | 30 ngày |
| CRMAZ | Đội nhỏ 390.000 · Đội vừa 890.000 · Đội lớn 1.690.000 — đ / tháng, trả năm ; trả tháng 470.000 / 1.070.000 / 2.030.000 | — | năm / tháng | nhập dữ liệu hộ 1.000.000 đ / lần | 14 ngày |
| Phần mềm bảo hành | Tới 5 người 390.000 · tới 15 người 690.000 · tới 30 người 1.290.000 — đ / tháng ; mã 10.000 / 50.000 / 200.000 | — | trả theo năm | tin nhắn, tem : theo lượng dùng (chờ) | 14 ngày |
| DMSAZ · ERPAZ | sắp ra mắt — không hiện giá | | | | |

Bấm «Đăng ký ngay» → trang Đăng ký : khối **Quy mô** hỏi đúng số lượng của phần mềm đó (bán hàng : số kho, số người dùng ; TaxAZ : số bộ sổ, số người dùng ; CRMAZ : số người dùng ; bảo hành : số người dùng, số mã / năm) — component `Register/Scale`.

Giảm giá mua theo bộ (2 phần mềm khác nhau − 15 %, 3 phần mềm − 25 %, tính trên tổng đơn) : **(chờ)** — vẽ được, ghi chú «(chờ)».

## 6. Khung ảnh thật (thiết kế sau — vẽ khung có nhãn «Ảnh : …» + kích thước)

| Trang | Khung |
|---|---|
| Trang chủ | ảnh / video mở đầu (máy tính + điện thoại) · 4 ảnh màn hình sản phẩm · 5 ảnh loại hình (hộ kinh doanh tại quầy, thu ngân chuỗi, đội kinh doanh, kho dán tem QR, kế toán làm sổ) · ảnh bộ phần mềm · 3 ảnh bìa tin · ảnh chân dung người tư vấn |
| Trang phần mềm (×4) | ảnh màn hình lớn · ảnh điện thoại · video giới thiệu 60 giây · 3 ảnh dùng thật |
| Về SoftAZ | đội ngũ · văn phòng · làm việc cùng khách · giấy chứng nhận nhãn hiệu (che mọi dữ liệu cá nhân) |
| Giỏ hàng | mã QR chuyển khoản (máy sinh tự động — chỉ vẽ khung) |

## 7. Sơ đồ (vẽ lại đẹp hơn, giữ ý)

| Sơ đồ | Ở đâu |
|---|---|
| Sáu phần mềm quanh một nền (kênh ở trên, hạ tầng ở dưới) | trang chủ |
| Đặt mua 5 bước + dùng thử 5 bước | trang chủ |
| Một đơn hàng đi qua những đâu (6 bước, nét đứt = chờ xác nhận) | trang chủ |
| Chuỗi chức năng của từng phần mềm + phần mềm khác nhận / gửi dữ liệu | 4 trang phần mềm |
| Các lớp của nền (kênh → phần mềm → dữ liệu chung → hạ tầng) | nền tảng |
| Liên kết chức năng bốn phần mềm (4 dải, mũi tên sang dải khác) | nền tảng |
| Dữ liệu dùng chung — phần mềm nào tạo, phần mềm nào dùng | nền tảng |
| Kết nối bên ngoài (ngân hàng, hoá đơn điện tử, tờ khai, Zalo, email / SMS, máy in tem) | nền tảng |
| Đặt mua : việc khách làm / việc SoftAZ làm | nền tảng |
| Các bước giỏ hàng, dùng thử ; dòng thời gian SoftAZ | giỏ hàng, dùng thử, về SoftAZ |

Sơ đồ dựng bằng component (`sz/Diagram/*`) và đường nối có mũi tên — không dán ảnh chụp ; Claude dựng lại sơ đồ bằng mã.

## 8. Thông tin cố định (chân trang, «Về SoftAZ», trang chính sách)

CÔNG TY CỔ PHẦN CÔNG NGHỆ SOFTAZ · MST 0109839971 · Số 7, ngõ 116 Đội Cấn, Phường Đội Cấn, Quận Ba Đình, Thành Phố Hà Nội · info@softaz.vn ·
điện thoại 0933332107 · tư vấn / Zalo 0397770035 · thành lập năm 2021 · nhãn hiệu SOFTAZ (giấy chứng nhận nhãn hiệu số 576322).
