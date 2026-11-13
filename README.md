# Bài Tập: Khắc Phục Lỗi Khai Báo Biến Số Trong Prompt Mẫu

---

## Phần 1: Phân tích lỗi của Prompt cũ

Câu lệnh lỗi: *"Hãy viết một bài chia sẻ về Cấu trúc Prompt Tiêu chuẩn & Định dạng bằng ngôn ngữ [language]. Dành cho đối tượng {audience}."*

**Lý do cách đặt biến lộn xộn gây khó khăn cho tự động hóa:**
1. **Sự nhầm lẫn của công cụ lập trình (Parser/Template Engine):** Khi dùng các hệ thống tự động hóa (như Python, Zapier, Make.com) để thay thế dữ liệu, các hệ thống này thường chỉ quét một loại ký tự đặc thù (hoặc chỉ `{}` hoặc chỉ `[]`). Việc lẫn lộn giữa ngoặc vuông `[language]` và ngoặc nhọn `{audience}` sẽ khiến phần mềm không tìm thấy biến để điền dữ liệu, dẫn đến lỗi cú pháp hoặc giữ nguyên chuỗi biến trong prompt.
2. **AI hiểu nhầm ngữ nghĩa cú pháp:** Khi đọc prompt, mô hình ngôn ngữ lớn (AI) có thể bị nhầm lẫn về mặt cấu trúc văn bản vì các loại ngoặc khác nhau thường mang các ý nghĩa kỹ thuật khác nhau (ví dụ: ngoặc vuông dùng cho cú pháp tùy chọn hoặc đánh dấu khối, ngoặc nhọn dùng cho biến truyền dữ liệu).
3. **Mất tính đồng bộ và chuyên nghiệp:** Biến số được đặt lộn xộn giữa tiếng Anh viết thường (`language`, `audience`) và thiếu quy chuẩn đặt tên sẽ gây khó khăn cho đội ngũ bảo trì code hoặc các thành viên khác khi cần mở rộng hệ thống prompt mẫu.

---

## Phần 2: Đồng bộ biến số

Để khắc phục triệt để, ta đồng bộ toàn bộ biến về một định dạng nhất quán duy nhất, sử dụng chữ in hoa và dấu gạch dưới để phân tách rõ ràng.

### Prompt đã được chuẩn hóa và sửa lỗi:
```text
Hãy viết một bài chia sẻ về Cấu trúc Prompt Tiêu chuẩn & Định dạng bằng ngôn ngữ [NGÔN_NGỮ]. Dành cho đối tượng [ĐỐI_TƯỢNG].
