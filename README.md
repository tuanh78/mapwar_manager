# mapwar_manager

Công cụ theo dõi trạng thái video (`index.html`).

- 2 bảng riêng: Video thường và Video basic
- Cột: STT, Tên video, Trạng thái, Ngày bắt đầu, Ngày hoàn thành
- Biểu đồ thống kê theo tháng: số video Thường / Basic làm xong (theo ngày hoàn thành), xem theo năm, có dạng bảng
- Trạng thái: Chưa làm → Đang sửa → Hoàn thành video → Đã đăng
- Lọc theo trạng thái (mặc định: Tất cả), thêm / sửa / xóa video
- Ngày bắt đầu / hoàn thành tự điền khi chuyển trạng thái (nếu đang trống)

## Lưu dữ liệu

Danh sách video được lưu online trong Firebase Realtime Database
(`mwmanager-5bde1`, đường dẫn `/videos`). Ai mở trang cũng xem và sửa được, không cần đăng nhập;
thay đổi của người khác tự hiện ra ngay. Lần mở đầu tiên, trang tự đưa danh sách có sẵn trong
`index.html` lên database.

Rules của database:

```json
{ "rules": { "videos": { ".read": true, ".write": true } } }
```
