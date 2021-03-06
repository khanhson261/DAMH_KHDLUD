 ## A project for data science and applications in VNU-HCMUS

Thùng chứa này chứa các file của đồ án môn "Khoa học dữ liệu ứng dụng" do nhóm 5 thực hiện.

Thông tin của các thành viên trong nhóm:

1712733 - Trần Phạm Khánh Sơn - [github](https://github.com/khanhson261)

1712495 - Nguyễn Quang Huy - [github](https://github.com/qhuy4119)

1712766 - Nguyễn Chí Thanh - [github](https://github.com/thanhchin)

THÙNG CHỨA GITHUB:
  
Link github: https://github.com/khanhson261/DAMH_KHDLUD

KẾ HOẠCH THỰC HÀNH: https://docs.google.com/spreadsheets/d/1BM-N_UEdI0BctyqZZeaa0Jip3ehevTyRdox7huHvLC4/edit?usp=sharing

LINK GOOGLE COLAB: https://colab.research.google.com/drive/1xPA4Pv_KavS2cBundJDYVVK_63ro7ZYR?usp=sharing

# MÔ TẢ BÀI TOÁN
## Tổng quan
- **Tên cuộc thi**: Restaurant Revenue Prediction

- **Giới thiệu sơ lược về TFI**: 
  -	Với hơn 1.200 nhà hàng phục vụ nhanh trên toàn cầu, TFI là công ty lớn, chỉ đứng sau một số thương hiệu nổi tiếng nhất thế giới: Burger King, Sbarro, Popeyes, Usta Donerci và Arby’s. TFI đã tuyển dụng hơn 20.000 nhân viên ở cả Châu Âu lẫn Châu Á và hiện vẫn đang đầu tư đáng kể vào việc phát triển và mở thêm các nhà hàng mới tại nhiều địa điểm.
Vấn đề gặp phải:
  -	Hiện tại, quyết định mở và đầu tư vào nhà hàng mới khi nào và ở đâu phần lớn là một quá trình chủ quan dựa trên đánh giá cá nhân và kinh nghiệm của các nhóm phát triển. Nguồn dữ liệu chủ quan này rất khó để có thể ngoại suy và đưa ra quyết định với độ chính xác cao do nhiều yếu tố như khu vực địa lý, văn hóa, …
  -	Không chỉ vậy, việc mở và đầu tư một nhà hàng đòi hỏi một lượng lớn về thời gian và tiền bạc để có thể thiết lập và vận hành. Do đó, khi chọn sai địa điểm để đầu tư mở một nhà hàng, địa điểm này khả năng rất cao là sẽ phải đóng cửa trong vòng khoảng 18 tháng sau khi đi vào hoạt động và phát sinh rất nhiều tổn thất cho hoạt động kinh doanh của TFI.
Yêu cầu cần giải quyết:
  -	Việc tìm ra một mô hình máy học có thể dự đoán doanh thu của một nhà hàng tại một địa điểm nào đó là rất cần thiết, đóng vai trò quan trọng trong việc tăng hiệu quả đầu tư cho TFI. Bên cạnh đó, việc đầu tư hiệu quả cho việc mở nhà hàng cũng sẽ đồng thời cho phép TFI có thể có đủ nguồn kinh tế để đầu tư nhiều hơn vào các lĩnh vực kinh doanh quan trọng khác, như tăng tính bền vững của các nhà hàng, đổi mới và đào tạo cho nhân viên mới, … Trong cuộc thi này, chúng ta sẽ sử dụng dữ liệu nhân khẩu học, bất động sản và thương mại để xây dựng nên một mô hình máy học dự đoán doanh số nhà hàng hàng năm của 100.000 địa điểm trong nhiều khu vực.
Phương thức tính điểm trên Kaggle của cuộc thi: Root Mean Square Error. 

- **Input**: TFI đã cung cấp bộ dữ liệu với 137 nhà hàng trong tập train và 100000 nhà hàng trong tập test. Các cột dữ liệu bao gồm ngày mở cửa (open date), vị trí (location), loại thành phố (city type) và ba loại dữ liệu xáo trộn: Dữ liệu nhân khẩu học (Demographic data), Dữ liệu bất động sản (Real estate data) và Dữ liệu thương mại (Commercial data). Cột doanh thu (revenue) cho biết doanh thu (đã chuyển đổi) của các nhà hàng trong một năm nhất định và đây cũng chính là mục tiêu của phân tích dự đoán trong cuộc thi này.

- **Output**: Doanh thu của các nhà hàng trong một năm nhất định.

Lưu ý kèm theo: Kaggle đã thêm khoảng 311,5 điểm dữ liệu "giả" vào bài kiểm tra cho mỗi điểm dữ liệu thực. Chia cho số này sẽ cho số liệu chính xác hơn của dữ liệu "thực" trong tập thử nghiệm.

- **Prize**: $ 30000.

- **Participants**: 2257 teams.

- **Link Kaggle**: https://www.kaggle.com/competitions/restaurant-revenue-prediction

## Solution
Trong đồ án thực hiện lần này, nhóm đã tìm hiểu và cài đặt lại phương pháp nằm trong top 10 Private Leaderboard.

Xếp hạng solution: Top 5 Private Leaderboard với score = 1745878.25648

Tác giả: Team FireFly, bài tham khảo là một phiên bản có sửa đổi rất ít của Ben Solecki and Lin Li.

Thời gian: Tháng 5 năm 2015.

Link Solution: https://github.com/bensolucky/TFI

### Phân tích sơ lược tập dữ liệu:
Như đã nêu ở trên, tập dữ liệu chúng ta sẽ bao gồm có 1 tập train và 1 tập test. Ngoài ra, còn có 1 tập sampleSubmission.csv được bên điều hành cuộc thi thêm vào để cho người tham dự biết được cấu trúc nộp bài dự thi mà nhà điều hành mong muốn là như thế nào.
Sau khi quan sát tập dữ liệu, nhóm rút ra được nhận xét như sau: Tập huấn luyện được cung cấp có khá ít dòng (137 dòng). Mỗi dòng sẽ mô tả một nhà hàng ở Thổ Nhĩ Kỳ do TFI Foods điều hành. Hầu hết các thông tin mà TFI Foods cung cấp đều đã được ẩn danh và được gắn nhãn từ P1 đến P38. Các dữ liệu này có vẻ như có tính phân loại. Có một số cột được mô tả cụ thể hơn, chẳng hạn như ngày khai trương (open date), loại nhà hàng (type) và thành phố (city). Tập train bao gồm 100.000 dòng, nhưng trên thực tế, hầu hết các dòng này được tạo ra bởi Kaggle một cách tự động và có vẻ không thực sự mang ý nghĩa thực tiễn. Theo như tác giả cũng như một số nhóm tham gia khác trong cuộc thi, họ xác định rằng tập test trên thực tế chỉ có 321 hàng. Mục tiêu là dự đoán doanh thu của nhà hàng. Chỉ số cho điểm là RMSE (lỗi bình phương trung bình gốc), rất nhạy cảm với các giá trị ngoại lệ, đặc biệt là trên một tập hợp trainng nhỏ như đã cho trong đề. Vì vậy, chiến lược chung của thuật toán máy học mà tác giả xây dựng là chỉ sử dụng các kỹ thuật tiền xử lý và mô hình hóa đơn giản nhất và tốt nhất, đồng thời tìm cách tránh tối đa overfitting.
Ý nghĩa của các cột dữ liệu trong tập train và test:
-	```Id```: Id nhà hàng.
-	```Open Date```: ngày khai trương nhà hàng
-	```City```: Thành phố mà nhà hàng đang đặt. Lưu ý rằng có unicode trong tên.
-	```City Group```: Loại thành phố. Bao gồm loại thành phố lớn và loại Khác.
- ```Type```: Loại hình nhà hàng. Bao gồm:
  * ```FC```: Khu ăn uống.
  * ```IL```: Nội tuyến.
  * ```DT```: Drive Thru (tức là bán đồ ăn mang đi, người mua thường sẽ ngồi trên ô tô, đặt món và nhận đồ ăn qua cửa kính ô tô, sau đó sẽ lái xe đi mà không cần xuống xe).
  * ```MB```: Di động.
-	```P1, P2 đến P37```: Có ba loại dữ liệu xáo trộn trong các cột này. Dữ liệu nhân khẩu học được thu thập từ các nhà cung cấp bên thứ ba có hệ thống GIS. Các dữ liệu này bao gồm dân số ở bất kỳ khu vực nhất định nào, phân bố theo độ tuổi và giới tính, quy mô phát triển. Dữ liệu bất động sản chủ yếu liên quan đến diện tích (đơn vị m2) của vị trí, mặt tiền của vị trí, chỗ đậu xe ô tô. Dữ liệu thương mại chủ yếu bao gồm sự tồn tại của các điểm chiến lược xung quanh nơi đặt nhà hàng, bao gồm trường học, ngân hàng, các nhà khai thác QSR khác.
-	```Revenue```: Cột doanh thu cho biết doanh thu (đã chuyển đổi) của nhà hàng trong một năm nhất định và là mục tiêu của phân tích dự đoán. Cần lưu ý rằng các giá trị được chuyển đổi để chúng không có nghĩa là giá trị đô la thực.

### Quá trình thực hiện giải cơ bản:
1.	Khám phá dữ liệu
2.	Tiền xử lý dữ liệu (bao gồm việc định dạng lại một số cột, xử lý null, xử lý outlier, …)
3.	Biến đổi dữ liệu (Ưu tiên sử dụng các phép biến đổi đơn giản như đã nói ở trên, chủ yếu là chuyển các cột dạng categorical về numeric)
4.	Huấn luyện các mô hình tiềm năng trên tập train
5.	Đánh giá và lựa chọn mô hình. Ở đây, mô hình được chọn là Ridge Regression vì mô hình này có khả năng thích ứng tốt với dữ liệu dễ bị overfitting và như đã nói ở trên, khi mà dữ liệu của tập train nhỏ thì đơn giản nhất thường sẽ là lựa chọn tốt nhất. Tác giả cũng đã có thử qua các mô hình khác như là SVR, Random Forest, K-nearest Neighbors, … nhưng Ridge Regression đã cho ra được kết quả tốt nhất.

