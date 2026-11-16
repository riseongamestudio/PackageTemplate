# RiseOn.PackageName

<!-- Hai, ba câu cho dev dùng pack: pack làm gì, dùng trong trường hợp nào. -->

Package `com.riseon.packagename`, namespace `RiseOn.PackageName`.

## Mục lục

- [Yêu cầu](#yêu-cầu)
- [Cài đặt](#cài-đặt)
- [Tổng quan](#tổng-quan)
- [Hướng dẫn nhanh](#hướng-dẫn-nhanh)
- [Thành phần](#thành-phần)
- [Lịch sử thay đổi](#lịch-sử-thay-đổi)
- [Giấy phép](#giấy-phép)

## Yêu cầu

| Phụ thuộc | Cách có | Dùng cho |
|---|---|---|
| Unity 6000.3 | | Bản đang dùng để phát triển |
| [Odin Inspector](https://odininspector.com) | Cài tay từ Asset Store | <!-- Phần nào của pack dùng Odin --> |

Odin không có trên UPM nên phải cài vào project trước. Thiếu Odin thì project báo một lỗi từ
`RiseOn.PackageName.Requirements`.

<!--
Mỗi gói trong `dependencies` của package.json một hàng, cùng version, cột "Cách có" ghi "Tự cài theo `package.json`".
Pack không dùng Odin: xóa hàng Odin và câu dưới bảng, xóa thư mục `Editor/Requirements/`, bỏ `ODIN_INSPECTOR` khỏi
`defineConstraints` của `Runtime/RiseOn.PackageName.asmdef`.
-->

## Cài đặt

**Registry RiseOn** (khuyên dùng): thêm registry RiseOn với scope `com.riseon` vào
`Packages/manifest.json`, rồi thêm package:

```json
{
  "scopedRegistries": [
    {
      "name": "RiseOn",
      "url": "https://upm.riseongamestudio.com",
      "scopes": ["com.riseon"]
    }
  ],
  "dependencies": {
    "com.riseon.packagename": "1.0.0"
  }
}
```

<!-- Phụ thuộc lấy từ registry khác (OpenUPM...) thì thêm registry đó với scope của nó vào ví dụ trên. -->

**Git URL**: *Package Manager → + → Add package from git URL*:

```
https://github.com/riseongamestudio/PackageName.git#v1.0.0
```

<!-- Git URL không kéo theo phụ thuộc com.riseon: liệt kê ở đây những gói phải cài trước. -->

**Thư mục local**: `"com.riseon.packagename": "file:D:/path/to/PackageName"`.

## Tổng quan

<!-- Các phần của pack và việc của từng phần; những interface, lớp mà code bên ngoài dùng tới. -->

## Hướng dẫn nhanh

<!-- Các bước ngắn nhất để dùng được pack trong một project. -->

## Thành phần

| Thành phần | Việc | Chi tiết |
|---|---|---|

<!--
Mỗi khái niệm một thư mục ngang hàng trong Runtime/, mỗi thư mục có README riêng chỉ ghi những điều không suy ra được
khi đọc từng file. Mỗi thư mục một hàng ở bảng trên, cột Chi tiết link tới README đó.
-->

## Lịch sử thay đổi

Xem [CHANGELOG.md](CHANGELOG.md).

## Giấy phép

MIT, xem [LICENSE.md](LICENSE.md).
