# Cập nhật thông tin sản phẩm vào mã QR

_API cần gửi các tham số bắt buộc và cần xác thực bằng token [Xem tại đây](README.md)

Gửi request thông qua địa chỉ sau
 ```http
POST https://wkey.mhvn.vn/api/code/update-product

Accept: application/json
Content-Type: application/json
```

Các tham số gửi lên ngoài tham số bắt buộc:

| Key | Type | Description |
| :--- | :--- | :--- |
| `serials` | `array` | **Bắt buộc**. Danh sách các serial muốn gán thông tin |
| `sku` | `string` | **Bắt buộc**. Mã sản phẩm |
| `update` | `boolean` | Ghi đè dữ liệu nếu đã có. Giá trị gửi là `1` hoặc `0` |


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
    "message": "Cập nhật thành công",
    "updated": 0
}
```

- `updated` Số mã cập nhật thành công

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
            "Mã sản phẩm không tồn tại"
        ]
    },
}
```
