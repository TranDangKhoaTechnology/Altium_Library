# hướng dẫn sử dụng altium library

đây là tài liệu hướng dẫn nhanh cho repository altium library của trần đăng khoa / trandangkhoatechnology.

## 1. tải thư viện

```bash
git clone https://github.com/TranDangKhoaTechnology/Altium_Library.git
cd Altium_Library
```

cập nhật về bản mới nhất:

```bash
git pull
```

nếu không dùng git, có thể bấm **code > download zip** trên github rồi giải nén vào thư mục cố định.

## 2. thêm thư viện vào altium designer

1. mở altium designer.
2. vào panel **components** hoặc **libraries**.
3. vào phần quản lý **file-based libraries** hoặc **installed libraries**.
4. chọn **install**.
5. chọn file thư viện trong repository:
   - `.intlib`: thư viện tích hợp.
   - `.schlib`: thư viện symbol.
   - `.pcblib`: thư viện footprint.
6. bấm **apply/ok**.
7. tìm thử linh kiện trong panel components/libraries.

nếu thư viện chưa hiện, hãy tắt altium rồi mở lại.

## 3. quy trình thiết kế nhanh

1. tạo project `.prjpcb`.
2. tạo schematic `.schdoc` và pcb `.pcbdoc`.
3. đặt linh kiện bằng `pp`.
4. nối dây bằng `ctrl+w`.
5. đánh số linh kiện bằng `taa`.
6. update sang pcb bằng `du`.
7. thiết lập luật đi dây bằng `dr`.
8. đi dây bằng `ctrl+w`.
9. phủ đồng bằng `pg`.
10. kiểm tra lỗi bằng `td`.
11. xuất gerber và nc drill.

## 4. phím tắt và lệnh nhanh

### phóng to, thu nhỏ, di chuyển

| thao tác | lệnh/phím |
|---|---|
| phóng to/thu nhỏ | `ctrl` + lăn chuột |
| phóng to/thu nhỏ bằng bi chuột | click bi chuột + kéo lên/xuống |
| di chuyển ngang | `shift` + lăn chuột |
| pan màn hình | giữ chuột phải + di chuyển chuột |

### hiển thị pcb

| thao tác | lệnh/phím |
|---|---|
| chế độ 3d | `3` |
| chế độ 2d | `2` |
| xoay board 90 độ | `9` |
| xoay về góc cũ | `0` |
| hiển thị chéo | `8` |
| xoay tự do trong 3d | `shift` + giữ chuột phải + di chuyển chuột |
| hiển thị full board | `vf` |
| hiển thị mặt sau board | `vb` |
| đổi chế độ hiển thị lớp | `shift+s` |

### linh kiện

| thao tác | lệnh/phím |
|---|---|
| lấy linh kiện | `pp` |
| xoay linh kiện | `space` |
| đối xứng qua trục x | `x` |
| đối xứng qua trục y | `y` |
| copy khối linh kiện | chọn khối, giữ `shift`, kéo bằng chuột trái rồi thả |

### schematic và pcb

| thao tác | lệnh/phím |
|---|---|
| nối dây schematic | `ctrl+w` |
| đi dây pcb | `ctrl+w` |
| đánh số linh kiện | `taa` |
| update sang pcb | `du` |
| chọn linh kiện schematic rồi chuyển/chọn bên pcb | `ts` rồi `tol` |
| đo kích thước | `ctrl+m` |
| thiết lập luật đi dây | `dr` |
| đi dây tự động | `uaa` |
| xóa dây/xóa route | `uu`, `uuc`, `uun`, `uua` |
| đổi độ rộng dây khi đang đi dây | `3` |
| đổi đơn vị mm/mil | `q` |
| vẽ keep-out track | `p` > keepout > track |
| chỉnh board shape | `dbd` |
| tạo teardrop | `te` |
| kiểm tra lỗi/drc | `td` |
| phủ đồng | `pg` |
| viết chữ | `ps` |
| xóa keep-out sau khi chọn toàn bộ | `dsd` |

## 5. từ khóa tìm linh kiện

| linh kiện | từ khóa |
|---|---|
| trở băng | `rn` |
| trở thường | `r`, `res` |
| cuộn cảm | `l-` |
| tụ hóa | `cap p` |
| tụ gốm | `cap n` |
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
| 8051 | `at89xxx` |
| avr | `atmegaxxx` |
| pic | `picxxx` |
| stm | `stmxxx` |

## 6. xuất gerber

1. mở file `.pcbdoc`.
2. vào **file > fabrication outputs > gerber files**.
3. tab **general**: chọn đơn vị và format, thường dùng `2:4` nếu nhà sản xuất hỗ trợ.
4. tab **layers**: chọn **all on**, sau đó bỏ các lớp mechanical không cần thiết.
5. tab **drill drawing**: bật **plot all used drill pairs** nếu cần.
6. tab **apertures**: bật **embedded apertures (rs274x)**.
7. tab **advanced**:
   - chọn **separate file per layer**.
   - chọn **suppress trailing zeroes** nếu cấu hình đang dùng yêu cầu.
   - chọn **reference to absolute origin**.
   - bật **optimize change location commands**.
8. bấm **ok** để tạo file gerber.

## 7. xuất nc drill

1. vào **file > fabrication outputs > nc drill files**.
2. chọn đơn vị và format giống gerber, ví dụ `inches` và `2:4`.
3. chọn **suppress trailing zeroes** nếu đang dùng cùng cấu hình với gerber.
4. chọn **reference to absolute origin**.
5. bật **optimize change location commands**.
6. chỉ tách plated/non-plated holes nếu nhà sản xuất yêu cầu.
7. bấm **ok** để xuất file khoan.

## 8. checklist trước khi gửi sản xuất

- kiểm tra đúng footprint với datasheet.
- kiểm tra hướng ic, diode, led, tụ hóa, connector.
- kiểm tra dây nguồn, dây gnd, độ rộng dây, clearance.
- kiểm tra board outline và keep-out.
- kiểm tra silk screen không đè lên pad.
- chạy drc bằng `td`.
- mở lại file gerber bằng gerber viewer để kiểm tra kích thước, số lớp và lỗ khoan.
- nén gerber + nc drill thành file `.zip` rồi gửi nhà sản xuất.

## bản quyền

copyright © 2026 trần đăng khoa / trandangkhoatechnology. all rights reserved.

toàn bộ tài liệu, thư viện, symbol, footprint, nội dung hướng dẫn và các file trong repository này thuộc quyền sở hữu của trần đăng khoa / trandangkhoatechnology. không được sao chép, phân phối lại, bán lại, đăng tải lại hoặc sử dụng thương mại nếu chưa được cho phép bằng văn bản.
