+++
title = "Savings Plans Recommendation"
date = 2020-04-18T00:38:32+07:00
weight = 2
chapter = false
pre = "<b>2. </b>"
+++

Để hỗ trợ người dùng tiết kiệm tối đa chi phí khi sử dụng dịch vụ, AWS cung cấp các đề xuất gọi là **Savings Plan Recommendation** dựa trên quá khứ sử dụng dịch vụ của bạn.  
Bạn có thể sử dụng những đề xuất này để tối ưu mức cam kết sử dụng dịch vụ giúp giảm bớt chi phí. 
- Monthly On-Demand Spend: Chi tiêu ước tính theo dạng On-Demand dựa trên việc sử dụng trong khoảng thời gian được chọn. Nó bao gồm cả những khoản thanh toán cho Gói Tiết kiệm đang hoạt động tại thời điểm tính.  
    Giá trị này diễn tả Chi tiêu cơ bản trong một tháng sử dụng theo kiểu On-Demand, dựa trên quá khứ sử dụng dịch vụ và những cam kết Savings Plan hiện tại. 

- Estimated Monthly Spend: chi tiêu dự kiến dựa theo những cam kết sử dụng dịch vụ theo đề xuất của Savings Plan. Giá trị này bao gồm những cam kết đã được đề xuất và bất cứ mức sử dụng dự kiến nào để duy trì hoạt động của On-Demand Instance thay đổi từng giờ trong quá trình sử dụng. 
- Estimated Monthly Savings: số tiền tiết kiệm ròng hàng tháng dựa trên việc sử dụng trong khoảng thời gian đã chọn khi bạn mua các gói Savings Plan được đề xuất.

Để truy cập Savings Plan Recommendation, 
- Đăng nhập vào **AWS Management Console** rồi mở **AWS Cost Management console** tại địa chỉ https://console.aws.amazon.com/cost-management/home

- Ở thanh điều hướng bến trái, bên dưới **Savings Plan**, chọn **Recommendation**

![Saving Plans](/images/SP/001.png?featherlight=false&width=90pc)

Bảng Recommendation Savings Plan hiển thị chi tiết các lựa chọn của gói Savings Plan. Bạn cũng có thể xem được thông tin Savings Plan Recommmendation thông qua [AWS Cost Explorer API](https://docs.aws.amazon.com/aws-cost-management/latest/APIReference/API_GetSavingsPlansPurchaseRecommendation.html)


![Saving Plans](/images/SP/002.png?featherlight=false&width=90pc)


{{% notice info %}}
Lưu ý : Các bước dưới đây chỉ thực hiện khi bạn muốn mua Savings Plan dựa theo Recommendations của hệ thống. Để tìm hiểu cách  mua Savings Plan tuỳ chỉnh bạn có thể chuyển sang Bước 3.
{{% /notice %}}


#### Tùy chỉnh SP Recommendation
Các thông tin tùy chỉnh gồm: 
- **Savings Plan Type** – loại Savings Plan. Có thể chọn Compute hoặc Amazon EC2 Instance.

- **Savings Plan term** – kì hạn cam kết tính theo năm. Chọn 1-year hoặc 3-years.
- **Payment option** – các lựa chọn thanh toán cho gói Savings Plan. Có thể là Trả hết trước toàn bộ (All-Upfront), Trả trước một phần(Partial upfront), hoặc Trả sau (No upfront)
- **Based on the past** – số ngày trong quá khứ được sử dụng để tính toán đề xuất gói tiết kiệm hay không
- **Filter by** – lựa chọn xác định member account nào được xem các gói Savings Plan. 

Cụ thể các bước thực hiện tùy chỉnh SP Recommmendation như sau: 
- Truy cập AWS Cost Management console tại địa chỉ https://console.aws.amazon.com/cost-management/home

- Ở thanh điều hướng bên trái, bên dưới **Savings Plans**, chọn **Recommendations**.
- Phần **Savings Plan type**, chọn **EC2 Instance** hoặc **Compute**.
- Chọn kỳ hạn trong phần **Savings Plan term**.
- Chọn kiểu thanh toán trong phần **Payment option**.
- Nhập số ngày trong phần **Based on the past** để dựa vào đó tính toán đề xuất SP 
- (Chỉ áp dụng với Management Account) Bấm vào tab **Linked Accounts**, chọn Account IDs mà bạn muốn Account đó nhìn thấy đề xuất SP.
- (Optional) Để thanh toán, bấm vào check box bên cạnh gói SP mong muốn, rồi chọn **Add Savings Plans to cart**.

#### Đánh giá Savings Plan được đề xuất trên Recommendations page
Một số trường hợp khi truy cập Recommendations page không thấy hiển thị bất cứ đề xuất nào cho Savings Plan. Điều đó bởi 1 trong 2 nguyên nhân sau đây: 
- Thứ nhất: có thể do hiện tại AWS không tính toán được bất cứ đều xuất nào khả dụng cho Savings Plan. 

- Thứ hai: do chi tiêu cho việc sử dụng dịch vụ dạng On-Demand quá thấp, dưới 0.1$/giờ trong khoảng thời gian được chọn. 

Các đề xuất này được tính toán tự động giúp bạn dễ dàng cần nhắc để mua các Gói Savings Plan tối ưu và bạn có thể thêm trực tiếp các Gói Savings Plan được đề xuất cho Account của mình vào giỏ hàng.

Để bắt đầu thanh toán cho Savings Plans được đề xuất trên Recommendations page, thực hiện các bước sau đây: 
- Sign in vào AWS Management Console và truy cập AWS Cost Management console tại địa chỉ https://console.aws.amazon.com/cost-management/home

- Ở khung điều hướng bên trái, dưới Savings Plans, chọn Recommendations.
- Trong phần tùy chọn của **Recommendation**, chọn **Savings Plans type**, **Savings Plans term**, **Payment option**, và lookback period.
- Trong bảng **Recommended Savings Plan**, bấm vào check boxes bên cạnh the Savings Plans mà bạn muốn thanh toán.
- Chọn **Add selected Savings Plan(s) to cart**.
- Để hoàn thành thanh toán, bấm vào **Cart** ở góc trái.
- Tại trang Cart, review lại order rồi bấm **Submit order**.

#### Thanh toán Savings Plan trên trang Purchase Savings Plans
Để thanh toán **Savings Plan cho EC2 Instance**: 
- Truy cập AWS Cost Management console tại địa chỉ https://console.aws.amazon.com/cost-management/home

- Ở khung điều hướng bên trái, dưới **Savings Plans**, chọn **Purchase Savings Plans**.
- Dưới **Savings Plans type**, chọn **EC2 Instance**.
- Lựa chọn Kỳ hạn **Term**, khu vực **Region**, rồi chọn họ Instance hay **Instance Family**.
- Trong phần cam kết thời gian **Hourly commitment**, nhập thời gian chạy SP
- Chọn kiểu thanh toán **Payment option**.
- Nếu chọn kiểu thanh toán **Partial Upfront** thì nhập số tiền sẽ trả trước cho SP. 
- (Optional) Để đưa Savings Plan vào danh sách đợi để chạy gói Tiết kiệm trong tương lai, thực hiện thiết lập the **Start date**.
- Chọn **Add to cart**.
- Ở trang giỏ hàng Cart page, review lại order, rồi chọn Submit order.

Để thanh toán **Savings Plan cho Compute**:
- Truy cập AWS Cost Management console tại địa chỉ https://console.aws.amazon.com/cost-management/home

- Ở khung điều hướng bên trái, dưới **Savings Plans**, chọn **Purchase Savings Plans**.
- Dưới **Savings Plans type**, chọn **Compute**.
- Chọn kỳ hạn **Term**.
- Trong phần **Hourly commitment**, nhập vào thời gian chạy SP.
- Chọn kiểu thanh toán **Payment option**.
- Nếu chọn thanh toán kiểu **Partial Upfront**, nhập số tiền sẽ trả trước cho SP.
- (Optional) Để đưa Savings Plan vào danh sách đợi để chạy gói Tiết kiệm trong tương lai, thực hiện thiết lập the **Start date**.
- Chọn **Add to cart**.
- Ở trang giỏ hàng Cart page, review lại order, rồi chọn **Submit order**.

#### Đưa SP vào danh sách chờ trong trang Giỏ hàng Cart 
Bạn có thể đưa vào danh sách chờ hoặc lên lịch cho việc thanh toán Savings Plan. Ngày kích hoạt gói tiết kiệm có thể cụ thể chính xác đến từng giây. Mọi khoản phí trả trước hoặc phí định kỳ chỉ được tính khi SP trong hàng đợi được kích hoạt vào ngày đã chọn.  
Bạn có thể hủy hoặc xóa SP trong danh sách chờ này bất kỳ lúc nào trước ngày bắt đầu.

Để đưa SP vào danh sách chờ thanh toán, ta thực hiện các bước sau đây: 
- Truy cập AWS Cost Management console tại địa chỉ https://console.aws.amazon.com/cost-management/home

- Thêm Savings Plans từ trang **Purchase Savings Plans** hoặc trang **Recommendations**.
- Từ khung điều hướng bên trái, bên dưới **Savings Plans**, chọn **Cart**
- Chọn **Savings Plans**.
- Chọn **Set start date**.
- Chọn Ngày và Thời điểm chạy SP.
- Bấm **Confirm**.
- Bấm **Submit order**.

#### Review và hoàn tất thanh toán trên trang Giỏ hàng Cart
Giỏ hàng Savings Plans sẽ giữ những cam kết cho tới khi bạn thực hiện việc thanh toán.  
Để thực hiện review và hoàn tất thanh toán từ trang Giỏ hàng Cart, lần lượt làm các bước sau đây: 
- Truy cập AWS Cost Management console tại địa chỉ https://console.aws.amazon.com/cost-management/home

- Ở khung điều hướng bên phải, dưới **Savings Plans**, chọn **Cart**.
- Review nội dung theo các thông tin dưới đây:
	- **Type**: loại Savings Plan.

	- **Term**: kỳ hạn cam kết tính theo năm. Chọn kỳ hạn 1-year hoặc 3-years.
	- **Region**: (chỉ phù hợp với loại EC2 Instance Savings Plans) loại Region mà bạn cam kết sử dụng. 
	- **Instance Family**: họ instance (for example, M5, C5, R5, C5d, etc.) mà bạn cam kết sử dụng.
	- **Purchase option**: các lựa chọn thanh toán. Các lựa chọn gồm All Upfront, Partial Upfront, hoặc No Upfront.
	- **Start date**: xác định ngày giờ thanh toán cam kết. Mặc định ngày thanh toán là ngay tại thời điểm khởi tạo order (Now).
	- **Commitment**: cam kết sử dụng tính theo giờ mà liên kết với gói Savings Plan và kỳ hạn.
	- **Upfront payment**: lựa chọn thanh toán trước một phần hoặc tất cả đơn hàng dựa theo lựa chọn thanh toán ở trên. 
	- **Monthly payment**: chi phí phải trả hàng tháng cho gói Savings Plans.
	- **Total cost**: tổng chi phí cho mức cam kết gói Savings Plan. Nó bao gồm chi phí trả trước và thanh toán định kỳ hàng tháng trong suốt kỳ hạn sử dụng. 
- Review nội dung trong phần the Summary:
	- **Total Commitment**: tổng chi phí cho tất cả các gói Savings Plans hiện tại trong rỏ hàng, bất kể ngày bắt đầu hoặc cách thanh toán như thế nào.

	- **Total upfront payment due now**: Tổng số tiền phải trả trước một phần (Upfront payment) cho gói Savings Plan với ngày bắt đầu được thiết lập Now.
- Xóa bỏ một Savings Plan khỏi Giỏ hàng bằng cách chọn từng item rồi bấm **Remove from cart**.
- Để bắt đầu lại từ đầu, và xóa bỏ toàn bộ item có trong giỏ hàng bấm **Clear cart**.
- Để thêm một cam kết mới, bấm chọn **Add another Savings Plan**.
- Thực hiện thanh toán, bấm **Submit order**.