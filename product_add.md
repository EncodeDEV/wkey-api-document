# Thêm thông tin sản phẩm mới

_API cần gửi các tham số bắt buộc và cần xác thực bằng token [Xem tại đây](README.md)

Gửi request thông qua địa chỉ sau
 ```http
POST https://wkey.mhvn.vn/api/product/add

Accept: application/json
Content-Type: application/json
```

Các tham số gửi lên ngoài tham số bắt buộc:

| Key | Type | Description |
| :--- | :--- | :--- |
| `sku` | `string` | **Bắt buộc**. Mã sản phẩm |
| `name` | `string` | **Bắt buộc**. Tên sản phẩm |
| `excerpt` | `string` | Mô tả ngắn về sản phẩm |
| `descriptions` | `array` | Mô tả chi tiết về sản phẩm |
| `descriptions.*.name` | `string` | Tiêu đề mô tả chi tiết sản phẩm |
| `descriptions.*.content` | `string` | Nội dung mô tả chi tiết sản phẩm |

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
    "message": "Thêm thông tin thành công"
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
        "sku": [
            "Mã sản phẩm đã tồn tại"
        ]
    }
}
```
