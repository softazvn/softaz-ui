# Thiết kế web softaz.vn trên Figma — hướng dẫn cho bộ phận UI

> Bản 0.1 · 11/11/2026 · SoftAZ soạn (phiên Claude AZUI). Đọc hết trang này và [`BRIEF.md`](BRIEF.md) trước khi mở Figma.

Kho này là chỗ **giao việc và nhận bàn giao** giữa bộ phận UI và SoftAZ cho website **softaz.vn**. Bản vẽ nằm trên **Figma** ; kho chỉ giữ đề bài,
bộ biến màu / kích thước (token), phiếu bàn giao kèm link khung Figma và ảnh đã xuất. Khi bạn mở Pull request, Claude (phiên AZUI của SoftAZ) đọc
phiếu bàn giao và đọc thẳng file Figma để dựng thành trang web.

## 0. Một vòng làm việc

```
SoftAZ giao đề bài (nhánh main của kho này)
  1. Bạn mở file Figma SoftAZ đã dựng sẵn (biến, thành phần, trang)   (README §1 – §3)
  2. Bạn thiết kế lại theo BRIEF.md                                    (README §4)
  3. Bạn tạo nhánh ui/<tên>-<việc>, đẩy token + phiếu + ảnh, mở PR     (README §5)
  4. SoftAZ duyệt trên Figma ; Claude đọc Figma + PR, dựng web thử,
     báo chỗ lệch bằng bình luận trong PR
  5. SoftAZ gộp PR → vòng sau
```

## 1. Cần có

| | |
|---|---|
| Tài khoản GitHub | tài khoản **miễn phí** của bạn. Kho công khai : SoftAZ **không** cần mời — bạn làm trên bản **Fork** của mình rồi gửi Pull request (§5). Không cần cài Git : mọi thao tác làm trên web GitHub. |
| Tài khoản Figma | ghế **Full** trong **team trả phí của SoftAZ** (gói Professional trở lên). |
| File Figma | **«SoftAZ.vn — Web 2026»** — SoftAZ đã dựng sẵn ; SoftAZ mời bạn quyền sửa và gửi link **riêng** (Zalo / email — link không ghi vào kho công khai). File phải nằm trong team trả phí — team miễn phí chỉ cho một mode biến (không có sáng / tối) và Claude chỉ đọc được vài lượt mỗi tháng. |
| Phông | Be Vietnam Pro (Google Fonts, miễn phí) ; số và mẫu biểu : JetBrains Mono. |
| Logo | thư mục [`brand/logo/`](brand/logo/) (SVG, PNG). Không tự vẽ lại logo. |

## 2. Token (biến màu, kích thước)

**Đã có sẵn trong file Figma** : collection **SoftAZ Màu** (mode Light / Dark, 54 biến) và **SoftAZ Kích thước** (66 biến), kiểu chữ `SZ/*`, bóng
`SZ/Shadow L` / `SZ/Shadow S` — trang `01 Nền tảng thiết kế`. Ba tệp dưới đây là bản sao của các biến đó trên GitHub : chỉ dùng khi cần nhập lại vào
file khác, và khi bạn **xuất trả** sau khi đổi token (§5 bước 2).

Thư mục [`tokens/`](tokens/) có ba tệp JSON theo chuẩn DTCG (chuẩn token mà Figma nhập được) :

| Tệp | Nhập vào |
|---|---|
| `softaz.light.tokens.json` | collection **SoftAZ Màu**, mode **Light** |
| `softaz.dark.tokens.json` | cùng collection, mode **Dark** |
| `softaz.base.tokens.json` | collection **SoftAZ Kích thước** (một mode) : khoảng cách, bo góc, cỡ chữ, khung trang |

Cách nhập : mở bảng Variables → nhập tệp light ; thêm mode Dark → bấm phải tên mode → **Import mode** → chọn tệp dark. Hướng dẫn chính thức :
https://help.figma.com/hc/en-us/articles/15343816063383-Modes-for-variables. Figma báo lỗi định dạng → dùng plugin **TokensBrücke** (nhập JSON → Variables,
hiểu khoá `$value` / `$type`) hoặc báo SoftAZ xuất lại.

- Giữ nguyên tên biến (vd `color/text/default`, `radius/card`) — Claude dựng CSS theo đúng tên này. Mỗi biến có mô tả (ô Description) cho biết dùng ở đâu.
- Thêm biến mới được. Đổi tên / xoá biến có sẵn : ghi vào phiếu bàn giao kèm lý do.

## 3. Trong file Figma đã có gì (dựng 11/11/2026 từ mockup 5.0)

| Trang Figma | Nội dung |
|---|---|
| `00 Bìa` | Tên file, quy tắc, bản đồ khung |
| `01 Nền tảng thiết kế` | Bảng màu Light / Dark, thang chữ `SZ/*`, bo góc |
| `02 Thành phần` | Button · Chip · Frame/Photo · Screen · Card/Product · Card/Plan · Card/Type · Option · Field · Stepper · Diagram/Node · Diagram/Step · Arrow · Section/Head · Logo (tạm) · Header · Header/Mobile · Footer · Footer/Mobile — mọi màu, bo góc, khoảng cách gắn biến |
| `03 Trang — máy tính` | `SZ/Home/1440/Light` + `/Dark` · `SZ/Product-pos/1440/Light` · `SZ/Pricing/1440/Light` · `SZ/Cart-1/1440/Light` · `SZ/Trial-1/1440/Light` |
| `04 Trang — điện thoại` | `SZ/Home/390/Light` · `SZ/Product-pos/390/Light` · `SZ/Cart-1/390/Light` |

- Đây là **điểm xuất phát** : bạn được đổi bố cục, nhịp, minh hoạ ; giữ cấu trúc trang và nội dung chữ ở BRIEF. Sửa thành phần ở trang `02` thì mọi trang dùng nó tự đổi.
- Bản tối : chọn khung trang → bảng bên phải *Layer → Variable mode* → SoftAZ Màu = Dark (không vẽ lại).
- **Logo đang là bản tạm** : kéo thả [`brand/logo/softaz-logo.svg`](brand/logo/) vào hai biến thể của component `Logo` (giữ cao 36).
- «Ảnh màn hình» trong thẻ là hình vẽ tạm (`Screen`) ; ảnh thật đặt vào các khung `Frame/Photo`.
- Trang chưa vẽ : xem BRIEF §2 cột «Trên Figma».

## 4. Thiết kế và đặt tên

- Trang Figma : `00 Bìa` · `01 Thành phần` · `02 Trang — máy tính` · `03 Trang — điện thoại` · `09 Lưu trữ`.
- Khung trang : **`SZ/<Mã>/<rộng>/<Light|Dark>`** — Mã theo BRIEF §2. Ví dụ `SZ/Home/1440/Light`, `SZ/Product-pos/390/Dark`, `SZ/Cart-2/1440/Light` (bước 2 giỏ hàng).
- Component : **`sz/<Loại>/<Biến thể>`** — vd `sz/Button/Primary`, `sz/Card/Product`, `sz/Frame/Photo`, `sz/Diagram/Node`.
- Lớp chữ mang nội dung đặt tên theo vai : `title`, `lead`, `price`, `cta`, `note`… (Claude dựa vào tên để tách nội dung khỏi khuôn).
- Auto layout cho mọi khối ; khoảng cách lấy `space/*`, bo góc `radius/*`, màu `color/*` — không gõ mã màu rời.
- Mỗi khung trang có bản Light và Dark : nhân bản khung rồi đổi mode biến, không vẽ lại.
- Luật chi tiết (tương phản, điện thoại, bo, bóng) : BRIEF §4.

## 5. Bàn giao qua GitHub (mỗi vòng)

0. **Fork (làm một lần)** : trang kho `softazvn/softaz-ui` → nút **Fork** (góc phải trên) → *Create fork* — được bản sao kho trong tài khoản của bạn. Trước mỗi vòng mới bấm **Sync fork** trên bản fork để lấy đề bài mới nhất.
1. **Tạo nhánh trên bản fork** : nút chọn nhánh (đang ghi `main`) → gõ `ui/<tên bạn>-<việc>` (vd `ui/lan-trang-chu`) → *Create branch*.
2. **Token** : Figma Variables → xuất các mode (*Export modes* → tệp `.zip`, mỗi mode một JSON) → giải nén, đặt lại đúng ba tên ở §2 → trên GitHub
   (đang ở nhánh của bạn) mở `tokens/` → *Add file → Upload files* → *Commit changes*. Không đổi token thì bỏ bước này.
3. **Phiếu bàn giao** : chép [`ban-giao/_MAU.md`](ban-giao/_MAU.md) thành `ban-giao/<yyyymmdd>-<việc>.md`, điền **node-id** từng khung
   (Figma : bấm phải khung → *Copy link to selection* → chép phần sau `node-id=`, vd `12-34`) — không dán cả link file vào kho công khai.
4. **Ảnh** : xuất WebP (ảnh chụp, ≤ 400 KB) / SVG (icon, minh hoạ) vào `assets/<mã trang>/` ; tên tệp không dấu, nối bằng gạch ngang.
5. **Mở Pull request** : trên bản fork bấm **Contribute → Open pull request** → đích `softazvn/softaz-ui` nhánh `main` → mẫu kiểm tự hiện, đánh dấu đủ rồi *Create pull request*.
6. Theo dõi bình luận trong PR ; sửa trên Figma, đẩy lại **cùng nhánh trên bản fork** (PR tự cập nhật). Bạn không gộp PR — SoftAZ gộp sau khi duyệt.

## 6. Không được

- Kho **công khai** : mọi tệp, PR, bình luận ai cũng đọc được. Không đưa vào : mật khẩu, khoá, mã truy cập, dữ liệu khách hàng thật, ảnh giấy tờ tuỳ thân, tệp `.fig`, **link file Figma**, số điện thoại / email cá nhân.
- Dùng tên, logo, ảnh màn hình phần mềm của hãng khác.
- Tự đặt số liệu (số khách hàng, % tăng trưởng, số sao đánh giá) — chưa có số thì để `[cần số]`.
- Đổi giá : giá lấy đúng BRIEF §5 ; chỗ ghi «(chờ)» giữ nguyên chữ «(chờ)».
- Sửa thẳng nhánh `main`, xoá tệp của người khác.

## 7. Tuỳ chọn : đẩy token thẳng từ Figma lên GitHub

Plugin **Tokens Studio** đồng bộ token với GitHub (bản miễn phí đồng bộ một tệp ; đổi nhánh ngay trong plugin là tính năng trả phí). Chỉ dùng khi team đã
quen plugin — cách mặc định là §5 bước 2. Dùng thì báo SoftAZ để thống nhất tên tệp.

## Tệp trong kho

| Tệp | Là gì |
|---|---|
| [`BRIEF.md`](BRIEF.md) | Đề bài : trang, khối, luật, giá, khung ảnh, sơ đồ |
| [`tokens/`](tokens/) | Ba tệp token (§2) |
| [`ban-giao/`](ban-giao/) | Phiếu bàn giao mỗi vòng (mẫu `_MAU.md`) |
| `assets/` | Ảnh bạn xuất (tạo khi bàn giao lần đầu) |
| [`brand/logo/`](brand/logo/) | Logo SoftAZ |
| `.github/pull_request_template.md` | Mẫu kiểm khi mở PR |

Bản quyền : © 2026 CÔNG TY CỔ PHẦN CÔNG NGHỆ SOFTAZ. Kho công khai để làm việc — không cấp phép dùng lại thiết kế, logo, nội dung.
