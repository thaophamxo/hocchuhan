# Vườn Chữ Hán — HSK 1–3 cho người Việt

Web học tiếng Trung (giản thể) giải nghĩa bằng tiếng Việt, theo chuẩn **HSK 3.0, cấp 1–3 (2.209 từ)**:
bài học (20 từ/bài), từ điển, thẻ ghi nhớ, ôn tập ngắt quãng (1-2-4-8-16 ngày), luyện tập trắc nghiệm,
theo dõi tiến độ. Không cần backend; tiến độ lưu bằng `localStorage`.

## Đưa lên GitHub Pages
1. Tạo repo mới, tải **toàn bộ thư mục này** lên nhánh `main` (cần cả thư mục `data/`).
2. Settings → Pages → Source: *Deploy from a branch* → `main` / `(root)` → Save.
3. Sau 1–2 phút web chạy tại `https://<tên-github>.github.io/<tên-repo>/`.

Chạy thử trên máy: `python3 -m http.server` rồi mở `http://localhost:8000`.

## Cấu trúc dữ liệu
- `data/hsk-data.js`: dữ liệu web đọc, mỗi dòng `[cấp, chữ, pinyin, nghĩa tiếng Việt, từ loại]`.
- `data/hsk-3.0-vi-levels-1-3.json`: bản gốc đầy đủ (kèm nghĩa tiếng Anh từ CC-CEDICT) để đối chiếu.
- `HV` trong `hsk-data.js`: âm Hán Việt, chỉ có 76 từ (do bản nháp trước nhập tay, chưa kiểm chứng).

## Nguồn và giấy phép
- Danh sách từ: [complete-hsk-vocabulary](https://github.com/drkameleon/complete-hsk-vocabulary) (MIT) và danh sách HSK 3.0.
- Nghĩa gốc: [CC-CEDICT](https://www.mdbg.net/chinese/dictionary?page=cc-cedict) (CC BY-SA 4.0).
- Nghĩa tiếng Việt: bộ dữ liệu [HocChu](https://github.com/leiinc/hocchu) (CC BY-SA 4.0). Xem `NOTICE.md`.
- Vì dữ liệu dịch dùng CC BY-SA 4.0, phần dữ liệu trong repo của bạn cũng phải giữ giấy phép này và ghi nguồn.

## Những điểm chưa được xác minh
- Nghĩa tiếng Việt do HocChu ghi rõ là **bản nháp biên tập bằng AI, chưa có người bản ngữ duyệt**. Mình đã gộp các nghĩa lặp và viết hoa sai, chứ không sửa nội dung. Bạn nên rà lại trước khi dùng giảng dạy.
- Số từ trong dữ liệu là 506 / 750 / 953 (HSK 1 / 2 / 3). Các trang tổng hợp ghi chuẩn 3.0 là 500 / 772 / 973 từ mỗi cấp, nên có lệch nhỏ. Mình chưa đối chiếu được với bản gốc trên [chinesetest.cn](https://www.chinesetest.cn/); hãy so sánh trước khi coi đây là danh sách chính thức.
- Thứ tự từ trong bài theo thứ tự của nguồn dữ liệu, không theo chủ đề.
