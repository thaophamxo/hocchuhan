# Vườn Chữ Hán — HSK 1–3 cho người Việt

Web học tiếng Trung (giản thể) giải nghĩa bằng tiếng Việt, theo chuẩn **HSK 3.0, cấp 1–3 (2.209 từ)**:
bài học (20 từ/bài), từ điển, thẻ ghi nhớ, ôn tập ngắt quãng (1-2-4-8-16 ngày), theo dõi tiến độ và
**6 dạng luyện tập**: từ→nghĩa, nghĩa→từ, sắp xếp câu, dịch Trung→Việt, dịch Việt→Trung, nghe và gõ chữ Hán. Không cần backend; tiến độ lưu bằng `localStorage`.

## Đưa lên GitHub Pages
1. Tạo repo mới, tải **toàn bộ thư mục này** lên nhánh `main` (cần cả thư mục `data/`).
2. Settings → Pages → Source: *Deploy from a branch* → `main` / `(root)` → Save.
3. Sau 1–2 phút web chạy tại `https://<tên-github>.github.io/<tên-repo>/`.

Chạy thử trên máy: `python3 -m http.server` rồi mở `http://localhost:8000`.

## Cấu trúc dữ liệu
- `data/hsk-data.js`: dữ liệu web đọc, mỗi dòng `[cấp, chữ, pinyin, nghĩa tiếng Việt, từ loại]`.
- `data/hsk-3.0-vi-levels-1-3.json`: bản gốc đầy đủ (kèm nghĩa tiếng Anh từ CC-CEDICT) để đối chiếu.
- `data/sentences.js`: 76 câu ví dụ `[cấp, câu, các từ, pinyin, tiếng Việt, tiếng Anh]`.
- `HV` trong `hsk-data.js`: âm Hán Việt, chỉ có 76 từ (do bản nháp trước nhập tay, chưa kiểm chứng).

## Nguồn và giấy phép
- Danh sách từ: [complete-hsk-vocabulary](https://github.com/drkameleon/complete-hsk-vocabulary) (MIT) và danh sách HSK 3.0.
- Nghĩa gốc: [CC-CEDICT](https://www.mdbg.net/chinese/dictionary?page=cc-cedict) (CC BY-SA 4.0).
- Nghĩa tiếng Việt: bộ dữ liệu [HocChu](https://github.com/leiinc/hocchu) (CC BY-SA 4.0). Xem `NOTICE.md`.
- Câu ví dụ: [Tatoeba](https://tatoeba.org) (CC BY 2.0 FR), lọc từ kho [ChineseWordSeg-SentencesExamples](https://github.com/mcodelook/ChineseWordSeg-SentencesExamples) bằng cách giữ câu chỉ gồm chữ nằm trong từ vựng HSK 1–3 của bộ dữ liệu trên.
- Vì dữ liệu dịch dùng CC BY-SA 4.0, phần dữ liệu trong repo của bạn cũng phải giữ giấy phép này và ghi nguồn.

## Những điểm chưa được xác minh
- Nghĩa tiếng Việt do HocChu ghi rõ là **bản nháp biên tập bằng AI, chưa có người bản ngữ duyệt**. Mình đã gộp các nghĩa lặp và viết hoa sai, chứ không sửa nội dung. Bạn nên rà lại trước khi dùng giảng dạy.
- Số từ trong dữ liệu là 506 / 750 / 953 (HSK 1 / 2 / 3). Các trang tổng hợp ghi chuẩn 3.0 là 500 / 772 / 973 từ mỗi cấp, nên có lệch nhỏ. Mình chưa đối chiếu được với bản gốc trên [chinesetest.cn](https://www.chinesetest.cn/); hãy so sánh trước khi coi đây là danh sách chính thức.
- Thứ tự từ trong bài theo thứ tự của nguồn dữ liệu, không theo chủ đề.
- **Câu luyện tập không phải câu trong giáo trình HSK Standard Course** (có bản quyền, không được chép). Cấp của câu = cấp cao nhất trong các từ của câu, theo danh sách từ ở trên, không phải theo bài của sách.
- Bản dịch tiếng Việt của 76 câu do trợ lý AI viết từ câu tiếng Trung, **chưa có người bản ngữ duyệt**.
- Kho nguồn tự ghi là CC0 và dịch tiếng Anh bằng Google Translate, nhưng câu gốc từ Tatoeba vẫn cần ghi nguồn theo CC BY. Pinyin gợi ý lấy từ kho nguồn, một vài câu có thể tách âm chưa chuẩn.
- Bài nghe dùng giọng đọc có sẵn của trình duyệt/thiết bị (Web Speech API); nếu máy không có giọng tiếng Trung thì sẽ không nghe được.

## Thêm câu mới
Thêm một dòng vào `data/sentences.js` theo đúng định dạng trên. Các từ (mảng thứ 3) ghép lại phải bằng đúng phần chữ Hán của câu.
