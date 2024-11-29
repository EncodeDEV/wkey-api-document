# Cập nhật thông tin người mua vào mã QR

_API cần gửi các tham số bắt buộc và cần xác thực bằng token [Xem tại đây](README.md)

Gửi request thông qua địa chỉ sau
 ```http
POST https://wkey.mhvn.vn/api/code/update-customer-bulk

Accept: application/json
Content-Type: application/json
```

Các tham số gửi lên ngoài tham số bắt buộc:

| Key | Type | Description |
| :--- | :--- | :--- |
| `serials` | `array` | **Bắt buộc**. Danh sách các serial muốn gán thông tin |
| `phone` | `string` | **Bắt buộc**. Số điện thoại người mua không bao gồm mã quốc gia |
| `name` | `string` | **Bắt buộc**. Tên người mua |
| `address` | `string` | **Bắt buộc**. Địa chỉ người mua |
| `sold_at` | `string` | Ngày bán sản phẩm (Y-m-d) |

### Kết quả trả về
Kết quả dữ liệu hợp lệ:
 ```http
STATUS: 200 OK
Content-Type: application/json
```
```javascript
{
    "status": "OK",
    "status_code": 200,
    "message": "Cập nhật thành công"
}
```

Dữ liệu không hợp lệ:
 ```http
STATUS: 200 OK
Content-Type: application/json
```
```javascript
{
    "status": "INVALID_FIELD",
    "status_code": 422,
    "message": "Có dữ liệu không hợp lệ",
    "errors": {
        "serias": [
            "Có mã đã có thông tin người mua"
        ]
    },
    "invalid_serials": [
        "24T0TFYV"
    ]
}
```
