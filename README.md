# altium library

thư viện altium phục vụ thiết kế mạch nguyên lý và mạch pcb. repository này dùng để lưu symbol, footprint, thư viện tích hợp và tài liệu thao tác nhanh khi làm việc với altium designer.

> bản quyền thuộc về **trần đăng khoa / trandangkhoatechnology**. toàn bộ nội dung trong repository này được giữ bản quyền, không được sao chép, phân phối lại, bán lại hoặc dùng cho mục đích thương mại nếu chưa có sự cho phép bằng văn bản.

## nội dung chính

- thư viện linh kiện cho altium designer.
- hướng dẫn tải và thêm thư viện vào altium.
- quy trình dùng thư viện khi vẽ schematic và pcb.
- bảng phím tắt, lệnh nhanh và từ khóa tìm linh kiện.
- hướng dẫn xuất gerber và nc drill để gửi nhà sản xuất pcb.
- quy định bản quyền của repository.

## tải repository về máy

cách 1: dùng git

```bash
git clone https://github.com/TranDangKhoaTechnology/Altium_Library.git
```

cập nhật lại thư viện sau này:

```bash
cd Altium_Library
git pull
```

cách 2: tải file zip

1. vào trang repository.
2. bấm **code**.
3. chọn **download zip**.
4. giải nén vào một thư mục cố định, ví dụ:

```text
d:\altium_library\
```

nên đặt thư viện ở thư mục ít thay đổi đường dẫn, vì altium sẽ lưu đường dẫn tới file thư viện.

## cách thêm thư viện vào altium designer

### cách 1: thêm từ panel components hoặc libraries

1. mở **altium designer**.
2. mở panel **components** hoặc **libraries**.
3. chọn phần quản lý thư viện.
4. chọn **file-based libraries** hoặc **installed libraries**.
5. bấm **install**.
6. chọn file thư viện trong repository, thường là một trong các loại sau:
   - `.intlib`: thư viện tích hợp, dễ dùng nhất.
   - `.schlib`: thư viện symbol cho schematic.
   - `.pcblib`: thư viện footprint cho pcb.
7. bấm **apply** hoặc **ok**.
8. tìm linh kiện trong panel components/libraries để kiểm tra.

### cách 2: thêm qua preferences

1. vào **dxp/preferences** hoặc **preferences** tùy phiên bản altium.
2. vào **data management**.
3. chọn **file-based libraries**.
4. bấm **installed** hoặc **install**.
5. chọn thư viện trong repository.
6. bấm **apply** rồi **ok**.

nếu thư viện chưa hiện, hãy đóng altium và mở lại.

## cách dùng thư viện khi thiết kế

### quy trình nhanh

1. tạo hoặc mở project altium dạng `.prjpcb`.
2. tạo/mở file schematic `.schdoc`.
3. thêm thư viện vào altium theo hướng dẫn phía trên.
4. đặt linh kiện vào schematic bằng panel components/libraries hoặc lệnh `pp`.
5. nối dây bằng `ctrl+w`.
6. đánh số linh kiện bằng `taa`.
7. kiểm tra lại tên linh kiện, giá trị, chân nguồn, chân tín hiệu.
8. update sang pcb bằng `du`.
9. mở file pcb `.pcbdoc`.
10. thiết lập rule đi dây bằng `dr`.
11. sắp xếp linh kiện, đặt board shape, đi dây, phủ đồng.
12. kiểm tra lỗi bằng `td`.
13. xuất gerber và nc drill để gửi sản xuất.

### dùng symbol và footprint

- symbol dùng trong schematic để biểu diễn linh kiện.
- footprint dùng trong pcb để tạo pad, kích thước thực tế và vị trí hàn.
- trước khi đặt hàng pcb, cần kiểm tra footprint đúng với datasheet thực tế.
- với linh kiện mới, nên in thử tỉ lệ 1:1 hoặc đo lại pad trước khi sản xuất.

### cập nhật schematic sang pcb

sau khi vẽ schematic xong:

1. lưu toàn bộ project.
2. kiểm tra lỗi schematic.
3. dùng lệnh `du` hoặc vào **design > update pcb document**.
4. xác nhận các thay đổi trong cửa sổ engineering change order.
5. bấm **execute changes**.
6. sang pcb để sắp xếp linh kiện và đi dây.

## bảng lệnh tắt altium hay dùng

### phóng to, thu nhỏ và di chuyển màn hình

| thao tác | lệnh/phím tắt |
|---|---|
| phóng to/thu nhỏ | giữ `ctrl` + lăn chuột |
| phóng to/thu nhỏ kiểu kéo chuột | click bi chuột + kéo chuột lên/xuống |
| di chuyển màn hình sang ngang | giữ `shift` + lăn chuột |
| pan màn hình | giữ chuột phải + di chuyển chuột |

### hiển thị pcb 2d/3d

| thao tác | lệnh/phím tắt |
|---|---|
| chuyển sang chế độ 3d | `3` |
| chuyển về chế độ 2d | `2` |
| xoay bản thiết kế 90 độ | `9` |
| xoay về góc cũ | `0` |
| hiển thị góc chéo | `8` |
| xoay board tự do trong 3d | giữ `shift` + giữ chuột phải + di chuyển chuột |
| hiển thị full toàn mạch | `v` rồi `f` (`vf`) |
| hiển thị mặt sau board | `v` rồi `b` (`vb`) |
| chuyển đổi lớp hiển thị/single layer mode | `shift+s` |

### đặt, xoay, copy linh kiện

| thao tác | lệnh/phím tắt |
|---|---|
| lấy/đặt linh kiện | `p` rồi `p` (`pp`) |
| xoay linh kiện | `space` |
| đối xứng linh kiện qua trục x | `x` |
| đối xứng linh kiện qua trục y | `y` |
| copy một khối linh kiện | quét chọn khối, giữ `shift`, giữ chuột trái, kéo tới vị trí mới rồi thả |

### schematic và pcb

| thao tác | lệnh/phím tắt |
|---|---|
| nối dây trong schematic | `ctrl+w` |
| đi dây pcb/interactive routing | `ctrl+w` |
| đánh số linh kiện | `t` `a` `a` (`taa`) |
| update schematic sang pcb | `d` `u` (`du`) |
| chọn linh kiện schematic rồi chuyển/chọn bên pcb | `t` `s` rồi `t` `o` `l` |
| đo kích thước | `ctrl+m` |
| ẩn/bỏ qua thông báo lỗi theo tài liệu gốc | `t` `m` (`tm`) |
| thiết lập luật đi dây | `d` `r` (`dr`) |
| đi dây tự động | `u` `a` `a` (`uaa`) |
| xóa dây/xóa route | `u` `u`, `u` `u` `c`, `u` `u` `n`, `u` `u` `a` |
| đổi độ rộng dây khi đang đi dây | phím `3` |
| đổi đơn vị mm/mil | `q` |
| vẽ keep-out track | `p` > keepout > track |
| chỉnh lại board shape | `d` `b` `d` (`dbd`) |
| tạo teardrop cho dây vào pad | `t` `e` (`te`) |
| kiểm tra lỗi thiết kế/drc | `t` `d` (`td`) |
| phủ đồng/polygon pour | `p` `g` (`pg`) |
| viết chữ/place string | `p` `s` (`ps`) |
| xóa keep-out sau khi chọn toàn bộ | chọn toàn bộ rồi `d` `s` `d` (`dsd`) |

## từ khóa tìm linh kiện nhanh

| linh kiện | từ khóa gợi ý |
|---|---|
| trở băng | `rn` |
| trở thường | `r`, `res` |
| cuộn cảm | `l-` |
| tụ hóa | `cap p` |
| tụ gốm/tụ không phân cực | `cap n` |
| transistor ngược | `npn` |
| transistor thuận | `pnp` |
| rơ le | `relay` |
| jumper/header/connector | `head`, `con` |
| led | `led` |
| diode | `diode` |
| thạch anh | `cry` |
| biến trở | `var` |
| pin/battery | `bat` |
| nút bấm | `sw` |
| đế ic | `ic` |
| ic ổn áp 5v | `lm78xx` |
| ic âm thanh | `tdaxxxx`, `teaxxxx`, `la4440`, `stk`, `rc4558`, `tlxxxx` |
| ic số | `74xxxx`, `40xx` |
| vi điều khiển 8051 | `at89xxx` |
| vi điều khiển avr | `atmegaxxx` |
| vi điều khiển pic | `picxxx` |
| vi điều khiển stm | `stmxxx` |

## checklist thiết kế pcb trước khi xuất file

- kiểm tra đúng footprint với datasheet.
- kiểm tra hướng chân số 1 của ic, diode, led, tụ hóa, connector.
- kiểm tra net nguồn: vcc, 3v3, 5v, gnd.
- kiểm tra độ rộng dây nguồn và dây tín hiệu.
- kiểm tra clearance theo khả năng sản xuất của nhà làm mạch.
- kiểm tra lỗ khoan, pad, via.
- kiểm tra silk screen có đè lên pad không.
- kiểm tra board outline/keep-out.
- chạy drc bằng `td`.
- xuất gerber và nc drill, sau đó mở lại bằng cam viewer hoặc gerber viewer để kiểm tra.

## cách xuất gerber

1. mở file pcb `.pcbdoc`.
2. vào **file > fabrication outputs > gerber files**.
3. tab **general**:
   - chọn đơn vị theo yêu cầu nhà sản xuất, thường dùng inches hoặc millimeters.
   - format thường dùng `2:4`, nhưng nên theo yêu cầu nhà sản xuất pcb.
4. tab **layers**:
   - chọn **plot layers > all on**.
   - bỏ các lớp mechanical không cần xuất nếu nhà sản xuất không yêu cầu.
   - đảm bảo có các lớp top layer, bottom layer, solder, paste, overlay và keep-out/outline nếu cần.
5. tab **drill drawing**:
   - bật **plot all used drill pairs** nếu cần bản vẽ khoan.
6. tab **apertures**:
   - bật **embedded apertures (rs274x)**.
7. tab **advanced**:
   - nên dùng **separate file per layer**.
   - dùng tọa độ **reference to absolute origin**.
   - dùng **suppress trailing zeroes** nếu đang theo cấu hình trong tài liệu gốc.
   - bật **optimize change location commands**.
8. bấm **ok** để xuất file.

## cách xuất nc drill

1. vào **file > fabrication outputs > nc drill files**.
2. chọn đơn vị và format giống phần gerber, ví dụ `inches` và `2:4` nếu đang dùng cấu hình này.
3. phần leading/trailing zeroes chọn giống gerber, ví dụ **suppress trailing zeroes**.
4. phần coordinate positions chọn **reference to absolute origin**.
5. bật **optimize change location commands**.
6. chỉ bật tách plated/non-plated holes nếu nhà sản xuất yêu cầu.
7. bấm **ok** để xuất file khoan.

## các file thường gửi cho nhà sản xuất pcb

khi xuất xong, nên nén các file sau thành `.zip`:

- top copper: `.gtl`
- bottom copper: `.gbl`
- top solder mask: `.gts`
- bottom solder mask: `.gbs`
- top paste: `.gtp`
- bottom paste: `.gbp`
- top overlay/silkscreen: `.gto`
- bottom overlay/silkscreen: `.gbo`
- board outline/keep-out/mechanical: thường là `.gko`, `.gm1` hoặc file mechanical tùy cấu hình
- nc drill: thường là `.txt`, `.drl` hoặc file drill tương ứng

trước khi gửi sản xuất, hãy mở file zip bằng gerber viewer để kiểm tra đúng kích thước, đúng số lớp, đúng lỗ khoan và đúng outline.

## tài liệu chi tiết

- [bảng lệnh tắt altium](docs/altium-shortcuts.md)
- [hướng dẫn xuất gerber và nc drill](docs/gerber-export.md)

## bản quyền

copyright © 2026 trần đăng khoa / trandangkhoatechnology. all rights reserved.

repository này là tài sản của trần đăng khoa / trandangkhoatechnology. mọi hành vi sao chép, phân phối lại, đăng tải lại, bán lại, chỉnh sửa để phát hành lại hoặc sử dụng thương mại khi chưa được cho phép đều không được chấp thuận.
