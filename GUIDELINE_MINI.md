# Mini guideline — bài làm cá nhân

> Điền nội dung này trước khi bắt đầu gán nhãn. Giữ lại các quyết định sau khi self-QC.

## Định nghĩa lớp

| Lớp | Định nghĩa của bạn | Ví dụ/điểm phân biệt |
| --- | --- | --- |
| `car` |	Phương tiện giao thông chở người, thường có 4 bánh và tối đa khoảng 5 chỗ ngồi | Sedan, SUV. Phân biệt kích thước nhỏ và số chỗ ngồi. |
| `truck` |Phương tiện chủ yếu để vận chuyển hàng hóa, có thùng hoặc khoang chở hàng | Xe tải nhỏ, xe tải lớn, xe ben. Điểm phân biệt là xe chở hàng. |
| `bus` | Phương tiện có kích thước lớn, chở nhiều người cùng lúc.| Xe buýt công cộng, xe khách, xe buýt trường học. Thường có nhiều hàng ghế và sức chứa lớn.|
| `van` | Phương tiện có thân xe dạng hộp, kích thước trung bình, dùng để chở người hoặc hàng hóa |Minivan, cargo van, passenger van, khoang xe rộng, thân cao, thường nhỏ hơn bus và truck |

## Quy tắc chung

- Box bám sát vật thể nghĩa là: Bounding box phải bao quanh toàn bộ phần vật thể nhìn thấy, sát các mép ngoài của vật thể, không lấy thừa quá nhiều vùng nền.
- Vật thể bị che khuất: Vật thể bị một đối tượng khác che mất một phần. Chỉ vẽ box theo phần vật thể thực sự nhìn thấy, không đoán phần bị che khuất.
- Vật thể bị cắt bởi rìa ảnh: Vật thể nằm một phần ngoài khung hình. Vẽ box đến sát rìa ảnh, bao quanh phần vật thể còn nhìn thấy.
- Vật thể rất nhỏ/mơ hồ: chỉ gán nhãn khi có thể nhận diện chắc chắn; nếu không, đánh dấu cần kiểm tra hoặc bỏ qua theo guideline

## Ghi lại quyết định cho ít nhất ba ca mơ hồ

| Ảnh | Tình huống | Quyết định cuối | Lý do theo schema |
| --- | --- | --- | --- |
| `drive_003` |Xe bus bị cắt bởi rìa ảnh | gán nhãn `bus`, box đến sát rìa ảnh | Phần nhìn thấy đủ để xác định |
| `drive_003` |Xe nhỏ mờ không xác định được loại xe gì | Không gán nhãn, đưa vào QC | Không đủ bằng chứng để xác định class theo schema |
| `drive_004` |Xe car bị che khuất 1 phần | Gán nhãn `car`, vẽ box phần nhìn thấy |Vật thể vẫn nhận diện được |
