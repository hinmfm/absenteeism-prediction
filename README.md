# Phân tích tình hình vắng mặt

Sử dụng bộ dữ liệu về tình hình vắng mặt tại một công ty, repo này sẽ tiến hành phân tích bộ dữ liệu này. Quá trình phân tích sẽ bao gồm các quy trình như phía dưới, các quy trình này có thể được truy cập thông qua việc bấm vào tên quy trình.
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
- [Bài toán kinh tế](#Bài-toán-kinh-tế)
- [Mục tiêu phân tích](#Mục-tiêu-phân-tích)
- [Giải thích](#Giải-thích)
- [Lời kết](#Lời-kết)

## Bài toán kinh tế
### Định nghĩa sự vắng mặt
"Sự vắng mặt" đề cập đến việc vắng mặt (trong thời gian dài) khỏi công việc vượt quá mức hợp lý và thông thường do nghỉ phép, thời gian cá nhân hoặc bệnh tật, ốm đau. - [investopedia.com](https://www.investopedia.com/terms/a/absenteeism.asp)
### Ảnh hưởng - Tại sao cần hạn chế sự vắng mặt?
Nghiên cứu của [Mehmet et al., 2016](https://www.researchgate.net/profile/Mehmet-Kocakulah/publication/301796227_Absenteeism_Problems_And_Costs_Causes_Effects_And_Cures/links/592c90a1aca27295a81599aa/Absenteeism-Problems-And-Costs-Causes-Effects-And-Cures.pdf?origin=journalDetail&_tp=eyJwYWdlIjoiam91cm5hbERldGFpbCJ9) cho rằng sự vắng mặt gây áp lực lớn về mặt chi phí lên các doanh nghiệp. Nhiều nguồn thông tin từ Canada, trong đó bao gồm cả [Statistics Canada](https://www.statcan.gc.ca/en/start) cho rằng sự vắng mặt chiếm tới xấp xỉ 15-20% chi phí lương được trả cho mỗi nhân viên. Nhật báo [Canada Newswire](https://www.newswire.ca/) cho rằng sự vắng mặt tương ứng với hơn 16 tỷ đô chi phí lương mất mát.

Mức độ ảnh hưởng của sự vắng mặt thường được tính dưới dạng chi phí. Có nhiều công thức được các nhà quản lý sử dụng để tính loại chi phí này. Theo [Kristina et al., 2017](https://journals.sagepub.com/doi/pdf/10.1177/0890117117725842#page=11), CIPROMS Inc. - một doanh nghiệp tầm trung chuyên về hóa đơn y tế và lập trình có trụ sở tại Indianapolis, trong khoảng thời gian từ 2013 tới 2015, đã tính chi phí vắng mặt như sau:

![image](https://github.com/user-attachments/assets/5c7e4572-29d1-4bd1-82d6-2334177876bd)

Trong đó, * là chi phí vắng mặt của mỗi nhân viên, Cost of employer paid sick days số tiền lương doanh nghiệp trả nhân viên nghỉ phép, § là tổng số nhân viên làm việc tại CIPROMS Inc. từ 2013 tới 2015.

## Mục tiêu phân tích
Vì sự vắng mặt có thể dẫn đến mất mát về mặt chi phí cho các doanh nghiệp, bài phân tích sau sẽ phân tích tổng quan các lý do vắng của các nhân viên đối với một công ty, tìm hiểu sức ảnh hưởng của các yếu tố đối với sự văng mặt. Ngoài ra, những dự đoán cũng sẽ được đưa ra sử dụng mô hình học máy [SVR (Supported Vector Regression)](https://scikit-learn.org/stable/modules/generated/sklearn.svm.SVR.html) có giám sát để tìm hiểu trọng số của mỗi yếu tố gây vắng mặt đối với giờ vắng mặt, đồng thời tìm yếu tố ảnh hưởng nặng nhất và đưa ra những quyết định, chính sách phù hợp dựa trên dự đoán khớp nhất với dữ liệu.

## Giải thích
Các giải thích về cách đọc repo có thể được tìm thấy trong phần này.
1. File đầu tiên cần đọc là phần tiền xử lý dữ liệu, hay <b>processing raw data </b>. Tại đây, có hai tệp chính: dữ liệu gốc – dùng để kiểm tra dữ liệu ban đầu, và dữ liệu đã qua xử lý – giúp theo dõi cách dữ liệu được biến đổi thông qua tệp .ipynb. Tiếp theo là <b>prediction data</b>, nơi dữ liệu được tinh chỉnh và làm giàu để chuẩn bị cho quá trình phân tích. Đồng thời, file này cũng mô tả các bước chạy thuật toán của mô hình học máy SVR và xuất dữ liệu để kiểm tra chi tiết hơn. Cuối cùng là <b>analysis</b>, nơi chứa các bảng dimensions-facts được tạo ra khi phân tích bằng PBI nhằm tối ưu hiệu suất phần mềm. Tại đây, có thể tìm thấy dữ liệu gốc ban đầu cùng với cơ sở dữ liệu quan hệ mới được xây dựng. Quan trọng nhất, phần phân tích, kể chuyện, mô tả và đề xuất đều được trình bày trong cùng một file này.
2. Mỗi file đều có kèm một <b>file README nên được đọc trước khi nghiên cứu các nội dung bên trong</b> file đó.
3. Các công nghệ được sử dụng trong bài bao gồm:
- Excel (.csv): chứa tệp dữ liệu gốc (nếu phát triển thêm có thể sử dụng Power Query để tổng hợp dữ liệu từ nhiều file khác nhau)
- Python: công nghệ chính được sử dụng nhằm làm sạch, làm giàu dữ liệu cũng như áp dụng thuật toán học máy, đưa ra dự đoán.
- PowerBI: được sử dụng nhằm trực quan hóa dữ liệu và làm tinh gọn cơ sở dữ liệu, tối ưu năng suất hoạt động.

## Lời kết
Tác giả của bài phân tích là Đỗ Quang Minh, sinh viên năm cuối chuyên ngành HTTTQL của Đại học Kinh tế Quốc dân, hiện đã nhận bằng tốt nghiệp. Em làm dự án này với mục đích để nghiên cứu thêm về sự ảnh hưởng của các yếu tố kinh tế đối với các doanh nghiệp, tiếp thu thêm kiến thức về các ngành kinh tế, mài giũa kỹ năng phân tích dữ liệu sẵn có của bản thân, học thêm nhiều kiến thức khác và sau cùng để thỏa mãn niềm đam mê với phân tích, xử lý và nghiên cứu thông tin với hy vọng có thể có một công việc trong ngành dữ liệu, ngách phân tích. 

Tất cả những kiến thức trong bài đều đến từ việc nghiên cứu, tham khảo và tự học. Những đường link trích dẫn đều được đính kèm trong bài.
Em cảm ơn các độc giả đã đọc tới phần này của file. 
Cảm ơn hơn nữa nếu mọi người đã đọc hết.

<b>Liên hệ</b>: minhsatwork@gmail.com
