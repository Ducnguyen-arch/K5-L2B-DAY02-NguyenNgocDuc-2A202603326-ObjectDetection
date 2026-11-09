# Báo cáo cá nhân — Ngày 2 Object Detection

Đổi tên file theo `MSSV_HoTen.md`, ví dụ `20241234_NguyenVanAn.md`. Điền kết quả thật, xóa dòng hướng dẫn khi nộp. Xem [quy định nộp](../../SUBMISSION.md).

## 1. Thông tin học viên

- Họ tên:Nguyễn Ngọc Đức
- MSSV: 2A202603326
- Email: nnduc1520@gmail.com
- Lớp: L2B
- Link repo bài làm: https://github.com/Ducnguyen-arch/K5-L2B-DAY02-NguyenNgocDuc-2A202603326-ObjectDetection
- Link Colab đã chạy: https://colab.research.google.com/drive/1uAW_9gJl1lpOsBTa2NKDEYkOTiuIEgJr?usp=sharing

## 2. Schema và mini guideline

Dẫn tới [GUIDELINE_MINI.md](../../GUIDELINE_MINI.md). Tóm tắt ba ca mơ hồ đã quyết định, cách áp dụng schema và phần cần giảng viên làm rõ.

## 3. Annotation và self-QC

- Số file nhãn train: 50
- Kết quả checker và lỗi đã xử lý: Xử lí lỗi path khi chạy script từ thư mục tools
- Danh sách ít nhất 10 ảnh đã rà bằng mắt: 4,5,7,12,15,35,46,47,48,50
- Lỗi bỏ sót/box/class phát hiện khi rà và cách sửa: thiếu sót vật đằng xa nhưng vẫn nhìn rõ mà chưa box. Đã box vật thể.
- Commit khóa nhãn ban đầu: git log

## 4. Gold QC và rework

| Chỉ số | Trước sửa | Sau sửa nếu có |
|---|---:|---:|
| TP | 290| |
| FP | |265 |
| FN | |363 |
| Precision |0.522 | |
| Recall | 0.45| |
| F1 | 0.48 | 0.49 |
| mean_iou_of_matches | 0.8702 |  |
| passed | false |  |

Dẫn tới `outputs/annotation_evaluation.json` trong repo. Nếu rework, ghi ảnh, lỗi đã kiểm, quyết định sửa/giữ và lý do. Không suy nguyên nhân chỉ từ FP/FN. Không có rework thì ghi rõ.

## 5. Kết quả YOLO

- Runtime, GPU/CPU, phiên bản Ultralytics và Torch: Google Colab chạy notebook với Python 3.x
- Các tham số thay đổi so với notebook nếu có và lý do: không có
- Đường dẫn best checkpoint trong phiên chạy: ../vehicle_annotation/weights/best.pt

| Chỉ số trên 10 ảnh eval | Giá trị |
|---|---:|
| Precision | | ../eval_predictions/visuals/
| Recall | |
| mAP50 | |
| mAP50–95 | |

Đặt cả 2 folder `assets/eval_predictions/` và `assets/yolo26_runs/` (giải nén từ `day2_colab_outputs.zip`) cạnh báo cáo và dẫn link tương đối. Không chỉ ghi số; chỉ ra ít nhất một ảnh và vật thể cụ thể.

Trả lời bốn câu hỏi cuối notebook:

1. Lớp nào recall thấp nhất? Ảnh nào minh họa?
2. Nếu mAP50 cao nhưng mAP50–95 thấp, cần kiểm điều gì trên box? Kiểm tra độ chính xác và kích thước box xem có rộng/hẹp hay sát vật thể không
3. Lỗi class nào có thể liên quan guideline? Dữ kiện nào hỗ trợ nhận xét? `truck` và `van` về hình dáng và kích thước, `bus` và `van` dựa trên đặc điểm phương tiện chở khách
4. Vì sao không dùng 10 ảnh eval để train? Vì dữ liệu dùng đánh giá tách biệt với dự liệu cập nhật theo với model.
 Vai trò validation của chúng trong notebook là gì? vai trò validation để lựa chọn best.pt

## 6. Khó khăn và cách xử lý

| Bước/thời điểm | Lỗi quan sát | Cách đã thử | Kết quả/còn thiếu |
|---|---|---|---|
|Annotation QC | F1 rất thấp | Đối chiếu với gold label | F1 chưa đạt 0.8|
|Evaluation| Chưa có JSON metric thực tế | check file model_eval_metrics.json| Cần thêm chỉ số để dễ evaluate hơn

## 7. Tự đánh giá theo rubric

Chưa đạt yêu cầu F1.

## 8. Công cụ AI và tài liệu tham khảo

Sử dụng ChatGPT để nghiên cứu thêm kiến thức , giải đáp thắc mắc còn chưa hiểu về mặt lí thuyết và thực hành.
 
