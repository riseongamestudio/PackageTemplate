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

Odin không có trên UPM nên phải cài vào project trước. Thiếu Odin thì project báo một
lỗi từ `RiseOn.PackageName.Requirements`.

<!--
Mỗi gói trong `dependencies` của package.json một hàng, cùng version, cột "Cách có" ghi "Tự cài theo
`package.json`", thêm nơi lấy (", từ OpenUPM", ", từ registry RiseOn"...) khi gói cần một registry hay scope
ngoài `com.riseon` và Unity Registry.
Có hàng "Tự cài" như vậy, trừ khi mọi hàng đó là module có sẵn của Unity, thì đoạn dưới bảng mở đầu bằng: "Tự cài"
là Package Manager tự lấy theo version từ Unity Registry và các registry khai trong manifest, cả khi cài pack bằng
git URL.
Mọi pack RiseOn đều cần Odin, kể cả pack không dùng nó, để khỏi phải xét asmdef nào phụ thuộc Odin: mọi asmdef thêm
sau (Editor, từng nền tảng...) cũng thêm `ODIN_INSPECTOR` vào `defineConstraints`, giữ các constraint khác như
`UNITY_EDITOR`; chỉ `Editor/Requirements/` không có. Thiếu một chỗ thì assembly đó vẫn compile khi project không có
Odin; nếu nó dùng Sirenix hoặc tham chiếu assembly đã gate thì báo lỗi CS0246. Pack không dùng Odin vẫn giữ hàng
Odin, cột "Dùng cho" ghi "Pack không dùng Odin, nhưng mọi pack RiseOn đều cần nó, để cài đặt như nhau".
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
https://github.com/riseongamestudio/PackageName.git
```

<!--
Có phụ thuộc thì câu trên mở đầu bằng "phụ thuộc vẫn lấy theo version từ registry", vì Package Manager
lấy phụ thuộc của gói cài bằng git URL từ Unity Registry và các registry khai trong manifest như mọi gói khác:
- có gói từ registry khác (OpenUPM...): nói manifest cần registry đó như ví dụ trên;
- có gói com.riseon: liệt kê cả gói gián tiếp, theo thứ tự cài, "lấy từ registry RiseOn, hoặc cài bằng git URL
  trước theo thứ tự này";
- có SDK chỉ ở registry RiseOn (Firebase, AppsFlyer): nói manifest cần đủ các registry như ví dụ trên.
-->

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
