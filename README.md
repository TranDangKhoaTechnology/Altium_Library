# altium library

thư viện altium phục vụ thiết kế mạch nguyên lý và pcb cho altium designer.

## cách tải

```bash
git clone https://github.com/TranDangKhoaTechnology/Altium_Library.git
cd Altium_Library
git pull
```

hoặc bấm **code > download zip** trên github rồi giải nén vào thư mục cố định.

## cách thêm thư viện vào altium

1. mở altium designer.
2. mở panel **components** hoặc **libraries**.
3. vào phần quản lý **file-based libraries/installed libraries**.
4. bấm **install**.
5. chọn file thư viện trong repository, ví dụ `.intlib`, `.schlib` hoặc `.pcblib`.
6. bấm **apply/ok**.
7. tìm linh kiện trong panel components/libraries để kiểm tra.

## tài liệu đã thêm

- [hướng dẫn đầy đủ cách dùng, phím tắt, từ khóa linh kiện, xuất gerber và nc drill](guide.md)
- [bản quyền](LICENSE)

## quy trình nhanh

1. đặt linh kiện bằng `pp`.
2. nối dây bằng `ctrl+w`.
3. đánh số linh kiện bằng `taa`.
4. update sang pcb bằng `du`.
5. thiết lập rule bằng `dr`.
6. đi dây pcb bằng `ctrl+w`.
7. phủ đồng bằng `pg`.
8. kiểm tra lỗi bằng `td`.
9. xuất gerber và nc drill.

## bản quyền

copyright © 2026 trần đăng khoa / trandangkhoatechnology. all rights reserved.

repository này thuộc quyền sở hữu của trần đăng khoa / trandangkhoatechnology. không được sao chép, phân phối lại, bán lại hoặc sử dụng thương mại nếu chưa được cho phép bằng văn bản.
