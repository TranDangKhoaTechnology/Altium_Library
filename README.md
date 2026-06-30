<div align="center">

# altium library

**professional altium designer component library for schematic and pcb design**

![altium designer](https://img.shields.io/badge/altium-designer-0a66c2?style=for-the-badge)
![pcb library](https://img.shields.io/badge/pcb-library-2ea44f?style=for-the-badge)
![schematic library](https://img.shields.io/badge/schematic-library-6f42c1?style=for-the-badge)
![license](https://img.shields.io/badge/license-all_rights_reserved-red?style=for-the-badge)

**owner:** tran dang khoa technology  
**author:** trần đăng khoa

</div>

---

## overview

`altium_library` là bộ thư viện linh kiện dành cho **altium designer**, hỗ trợ quá trình thiết kế mạch nguyên lý, layout pcb, kiểm tra footprint và chuẩn bị file sản xuất.

repository này được xây dựng để dùng lâu dài cho các dự án điện tử, nhúng, robot, vi điều khiển, nguồn, module giao tiếp và các mạch thực hành/kỹ thuật.

---

## features

- thư viện linh kiện dùng cho **schematic** và **pcb layout**.
- hỗ trợ các định dạng thư viện altium phổ biến như `.schlib`, `.pcblib`, `.intlib`.
- tài liệu hướng dẫn cài đặt và thêm thư viện vào altium.
- bảng phím tắt altium designer thường dùng khi vẽ mạch.
- từ khóa tìm nhanh linh kiện trong thư viện.
- hướng dẫn xuất **gerber** và **nc drill** để gửi nhà sản xuất pcb.
- checklist kiểm tra pcb trước khi đặt mạch.
- bản quyền rõ ràng thuộc **tran dang khoa technology**.

---

## repository structure

```text
altium_library/
├── readme.md          # trang giới thiệu chính
├── guide.md           # hướng dẫn đầy đủ cách dùng thư viện
├── license            # thông tin bản quyền
└── library files      # schlib, pcblib, intlib và các file liên quan
```

> cấu trúc thư mục có thể thay đổi theo từng phiên bản của thư viện.

---

## quick start

### 1. clone repository

```bash
git clone https://github.com/TranDangKhoaTechnology/Altium_Library.git
cd Altium_Library
```

### 2. update library

```bash
git pull
```

### 3. install library in altium designer

1. mở **altium designer**.
2. mở panel **components** hoặc **libraries**.
3. vào phần quản lý **file-based libraries** hoặc **installed libraries**.
4. chọn **install**.
5. chọn file thư viện trong repository:
   - `.intlib` cho thư viện tích hợp.
   - `.schlib` cho symbol schematic.
   - `.pcblib` cho footprint pcb.
6. bấm **apply** hoặc **ok**.
7. tìm thử linh kiện trong panel để kiểm tra.

---

## typical workflow

```mermaid
flowchart lr
    a[create project] --> b[add schematic]
    b --> c[place components]
    c --> d[wire schematic]
    d --> e[annotate components]
    e --> f[update pcb]
    f --> g[set design rules]
    g --> h[route pcb]
    h --> i[run drc]
    i --> j[export gerber]
```

quy trình nhanh khi thiết kế:

1. tạo project `.prjpcb`.
2. tạo schematic `.schdoc` và pcb `.pcbdoc`.
3. đặt linh kiện bằng `pp`.
4. nối dây bằng `ctrl+w`.
5. đánh số linh kiện bằng `taa`.
6. update sang pcb bằng `du`.
7. thiết lập luật đi dây bằng `dr`.
8. đi dây pcb bằng `ctrl+w`.
9. phủ đồng bằng `pg`.
10. kiểm tra lỗi bằng `td`.
11. xuất gerber và nc drill.

---

## essential altium shortcuts

| action | shortcut |
|---|---|
| place component | `pp` |
| wire / interactive routing | `ctrl+w` |
| rotate component | `space` |
| mirror x axis | `x` |
| mirror y axis | `y` |
| annotate components | `taa` |
| update schematic to pcb | `du` |
| design rules | `dr` |
| design rule check | `td` |
| polygon pour | `pg` |
| place string/text | `ps` |
| measure distance | `ctrl+m` |
| switch mm/mil | `q` |
| 2d view | `2` |
| 3d view | `3` |
| fit board view | `vf` |
| bottom view | `vb` |
| single layer mode | `shift+s` |

xem bảng đầy đủ trong file [guide.md](guide.md).

---

## component search keywords

| component | keyword |
|---|---|
| resistor | `r`, `res` |
| resistor network | `rn` |
| capacitor polarized | `cap p` |
| capacitor non-polarized | `cap n` |
| inductor | `l-` |
| diode | `diode` |
| led | `led` |
| transistor npn | `npn` |
| transistor pnp | `pnp` |
| relay | `relay` |
| connector/header | `head`, `con` |
| switch/button | `sw` |
| crystal | `cry` |
| battery | `bat` |
| 8051 mcu | `at89xxx` |
| avr mcu | `atmegaxxx` |
| pic mcu | `picxxx` |
| stm mcu | `stmxxx` |

---

## gerber export checklist

trước khi gửi pcb đi sản xuất, nên kiểm tra:

- footprint đúng với datasheet thực tế.
- hướng chân số 1 của ic, diode, led, tụ hóa và connector.
- rule clearance, độ rộng dây nguồn, dây tín hiệu và khoảng cách an toàn.
- board outline và keep-out layer.
- silk screen không đè lên pad.
- đã chạy drc bằng `td`.
- đã xuất đủ gerber và nc drill.
- đã mở lại bằng gerber viewer để kiểm tra kích thước, số lớp và lỗ khoan.

đường dẫn xuất gerber trong altium:

```text
file > fabrication outputs > gerber files
file > fabrication outputs > nc drill files
```

---

## documentation

| document | description |
|---|---|
| [guide.md](guide.md) | hướng dẫn đầy đủ cách cài, dùng thư viện, phím tắt, tìm linh kiện và xuất gerber |
| [license](LICENSE) | thông tin bản quyền repository |

---

## recommended usage

- nên đặt thư viện trong một thư mục cố định, tránh đổi đường dẫn sau khi đã thêm vào altium.
- nên kiểm tra footprint trước khi đặt pcb thật.
- với linh kiện smd nhỏ, nên đối chiếu lại kích thước pad với datasheet.
- với project quan trọng, nên lưu một bản thư viện theo từng phiên bản dự án.
- không nên sửa trực tiếp footprint đang dùng trong nhiều project nếu chưa kiểm tra ảnh hưởng.

---

## author

**tran dang khoa technology**  
created and maintained by **trần đăng khoa**.

---

## license

copyright © 2026 **trần đăng khoa / trandangkhoatechnology**. all rights reserved.

repository này thuộc quyền sở hữu của **trần đăng khoa / trandangkhoatechnology**. không được sao chép, phân phối lại, bán lại, chỉnh sửa để phát hành lại hoặc sử dụng thương mại nếu chưa được cho phép bằng văn bản.
