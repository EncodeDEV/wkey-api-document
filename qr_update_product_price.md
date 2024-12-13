# Cập nhật thông tin người mua vào mã QR

_API cần gửi các tham số bắt buộc và cần xác thực bằng token [Xem tại đây](README.md)

Gửi request thông qua địa chỉ sau
 ```http
POST https://wkey.mhvn.vn/api/code/update-product-price

Accept: application/json
Content-Type: application/json
```

Các tham số gửi lên ngoài tham số bắt buộc:

| Key | Type | Description |
| :--- | :--- | :--- |
| `serial` | `string` | **Bắt buộc**. Mã serial QR muốn gán thông tin |
| `price` | `string` | **Bắt buộc**. Giá sản phẩm, giá trị là một số nguyên |

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
        "serial": [
            "Mã QR không tồn tại"
        ]
    },
}
```
