# Phân tích tình hình vắng mặt

Sử dụng bộ dữ liệu về tình hình vắng mặt tại một công ty, repo này sẽ tiến hành phân tích bộ dữ liệu này. Quá trình phân tích sẽ bao gồm các quy trình như phía dưới. Ngoài ra, đường dẫn tới vị trí thực hiện quy trình cũng đã được để ở cạnh tên quy trình: 
1. [Hiểu bài toán kinh tế](#Bài-toán-kinh-tế) 
2. [Thu thập dữ liệu](https://github.com/hinmfm/absenteeism-prediction/blob/main/processing-raw-data/processed/absenteeism-data-processing.ipynb)
3. [Tiền xử lý dữ liệu](https://github.com/hinmfm/absenteeism-prediction/blob/main/processing-raw-data/processed/absenteeism-data-processing.ipynb)
4. [Làm sạch dữ liệu](https://github.com/hinmfm/absenteeism-prediction/tree/main/analysis)
5. [Phân tích dữ liệu](https://github.com/hinmfm/absenteeism-prediction/tree/main/analysis/pbi-visualization)
   - Khám phá dữ liệu.
   - Phân tích mô tả.
   - Dự đoán.
6. [Kể chuyện qua dữ liệu](https://github.com/hinmfm/absenteeism-prediction/tree/main/analysis/pbi-visualization)

Trong file README.md này sẽ là giải thích thứ tự file nên đọc theo và giải thích tổng quan về mỗi file sẽ bao gồm những gì. File cũng sẽ có một danh mục nội dung phía dưới đây để phục vụ cho việc tra cứu.
## Danh mục nội dung
- [Hiểu bài toán kinh tế](#Bài-toán-kinh-tế)
- [Giải thích file](#Giải-thích-file)

## Bài toán kinh tế
### Định nghĩa sự vắng mặt
"Sự vắng mặt" đề cập đến việc vắng mặt (trong thời gian dài) khỏi công việc vượt quá mức hợp lý và thông thường do nghỉ phép, thời gian cá nhân hoặc bệnh tật, ốm đau. (nguồn: https://www.investopedia.com/terms/a/absenteeism.asp)
