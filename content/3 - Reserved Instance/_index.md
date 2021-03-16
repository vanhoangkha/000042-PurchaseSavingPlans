+++
title = "Reserved Instance"
date = 2020
weight = 4
chapter = false
pre = "<b>3. </b>"
+++

Ngoài Savings Plan thì Reserved Instances cũng là một cách giúp bạn tiết kiệm đáng kể chi phí so với khi sử dụng dịch vụ Amazon EC2 kiểu On-Demand. 

### Các loại Reserved Instance
RI có 2 loại chính: loại Chuẩn (**Standard**) và loại Khả chuyển (**Convertible**)

| Đặc tính                                                                                                | Standard                                            | Convertible                                         |
|---------------------------------------------------------------------------------------------------------|-----------------------------------------------------|-----------------------------------------------------|
| Khả năng tiết kiệm (so với On-Demand)                                                                   | 1 năm (40%), 3 năm (60%)                            | 1 năm (31%), 3 năm (54%)                            |
| Thay đổi Availability Zone, kích cỡ instance (Linux OS), networking type. V/d: từ t2.medium –> t2.large | OK (Sử dụng ModifyReservedInstances API và console) | OK (Sử dụng ModifyReservedInstances API và console) |
| Thay đổi dòng Instance, hệ điều hành, tenancy, và phương thức thanh toán. V/d: từ t2 –> sang c4         | Không thể                                           | OK                                                  |
| Hưởng lợi từ chương trình giảm giá của AWS                                                              |                                                     | Có                                                  |
| Có khả năng bán lại trên Marketplace                                                                    | OK (Sau khi liên kết tài khoản với 1 NH Mỹ)         | Chưa có                                             |

Như vậy, so với Savings Plan thì Reserved Instance có những điểm lợi thế hơn đó là 
- Bạn có thể mua 1 RIs ngắn hạn trên Marketplace điều này không làm được với Saving Plan.

- Bạn có thể discount được với RDS như EC2 (nhưng không áp dụng với Fargate)
- Khoản discount sẽ lớn khi bạn chọn thời hạn 3 năm và trả trước tất cả, lên tới 60% 
- Có thể bán Reserved Instance đã mua lên marketplace.

Lưu ý 
- RI không chỉ áp dụng cho EC2 mà còn áp dụng cho cả RDS

- Với hình thức RI Chuẩn (Standard), bạn càng dùng nhiều cùng 1 dòng Instance thì càng dễ mua RI
- Tương tự Savings Plan, có 3 phương thức thanh toán là
	- **All Upfront**: trả trước toàn bộ –> cái này sẽ giúp bạn tiết kiệm nhiều nhất

	- **Partial Upfront**: trả trước 1 phần. Giảm giá sẽ ít hơn All Upfront nhưng nhiều hơn No Upfront
	- **No Upfront**: không trả trước mà chỉ commit là sẽ trả sau khi kết thúc kỳ hạn. Hình thức này có giảm giá ít nhất trong 3 loại

So với ODI, RI thực sự là 1 cách làm hay mà đơn giản để giúp người dùng tiết kiệm tiền mua server. Tất cả những gì bạn cần làm chỉ là đăng ký mua cả năm (hoặc 3 năm) để nhận được phiếu giảm giá. 

### Cách thức mua một Reserved Instance
Để mua Reserved Instance, truy cập trang chủ AWS tìm kiếm Reserved Instance offerings, điều chỉnh các thông số tìm kiếm của bạn cho đến khi bạn tìm thấy kết quả phù hợp.  
Khi tìm kiếm Reserved Instance, bạn sẽ thấy báo giá về chi phí của các kết quả tương ứng.   
Trước khi bạn xác nhận giao dịch mua, hãy review chi tiết Reserved Instance mà bạn định mua và đảm bảo rằng tất cả các thông số đều chính xác.   
Sau khi thanh toán hoàn tất, bạn không thể hủy giao dịch mua của mình.

### Lựa chọn Nền tảng cho Instance
Amazon EC2 hỗ trợ Reserved Instances chạy trên các nền tảng Linux như bên dưới:
- Linux/UNIX

- Linux with SQL Server Standard
- Linux with SQL Server Web
- Linux with SQL Server Enterprise
- SUSE Linux
- Red Hat Enterprise Linux

### Đưa thanh toán vào danh sách Chờ (Queue)
Mặc định, khi bạn mua Reserved Instances, việc thanh toán sẽ được thực hiện ngay lập tức.   
Tuy nhiên bạn có thể thiết lập việc thanh toán này vào ngày giờ nào đó trong tương lai bằng cách đưa nó vào danh sách chờ thanh toán.   
Một đơn hàng có thể nằm trong danh sách chờ tối đa ba năm. Vào ngày giờ đã định, đơn hàng sẽ được thanh toán và cách tính giá cho Reserved Instances sẽ được áp dụng.  
Bạn có thể xem các giao dịch mua nằm thuộc danh sách hàng đợi trong bảng điều khiển Amazon EC2.   
Bạn có thể hủy giao dịch mua đã nằm trong hàng đợi bất cứ lúc nào, miễn là trước thời gian đã định. Để biết chi tiết, bạn có thể xem thêm tại [Cancel a queued purchase](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ri-market-concepts-buying.html#cancel-queued-purchase)

### Tiến hành mua Reserved Instances loại Chuẩn (Standard)
- Truy cập **Amazon EC2 console** tại địa chỉ https://console.aws.amazon.com/ec2/

- Ở khung điều hướng bên trái, chọn **Reserved Instances**, rồi tiếp tục chọn **Purchase Reserved Instances**.
- Với **Offering class**, chọn **Standard** để hiển thị tất cả các loại Reserved Instances loại Standard.
- Nếu Instance đặt trước đã xác định nằm trong một vùng cụ thể, bật **Only show offerings that reserve capacity** ở góc phải trên của màn hình thanh toán. Sau khi bật, trường Availability Zone sẽ xuất hiện.
- Điều chỉnh thêm một số lựa chọn khác, rồi bấm **Search**.
- Với từng Reserved Instance mà bạn muốn mua, nhập rõ ràng số lượng mong muốn rồi bấm **Add to cart**.
- Để mua Standard Reserved Instance từ **Reserved Instance Marketplace**, tìm tới 3rd party trong cột **Seller** ở phần kết quả tìm kiếm. Cột Term hiển thị những kỳ hạn non-standard.
- Để xem thông tin tổng hợp của loại Reserved Instances mà bạn đã chọn, bấm **View cart**.
- Nếu thời gian thanh toán Order là **Now**, thì việc thanh toán sẽ diễn ra ngay sau khi bạn bấm chọn **Order all**. 
  Để đưa Order vào danh sách chờ, bấm Now rồi chọn ngày giờ sẽ thanh toán.
- Để hoàn thành thanh toán cho các đơn hàng, bấm **Order all**.
- Nếu tại thời điểm đặt hàng, có một đề xuất mua Instance tương tự nhưng với chi phí thấp hơn, AWS sẽ gợi ý để bạn mua với chi phí thấp hơn. 
- Bấm **Close**.
- Trạng thái của đơn hàng sẽ được liệt kê ở cột **State**. Khi dơn hàng được thanh toán, trạng thái State sẽ chuyển từ **Payment-pending** sang **Active**. Khi Reserved Instance được Active thì nghĩa là nó đã sẵn sàng để sử dụng.

### Tiến hành mua Reserved Instances loại Khả chuyển (Convertible)
- Truy cập Amazon EC2 console tại địa chỉ https://console.aws.amazon.com/ec2/

- Ở khung điều hướng bên trái, chọn Reserved Instances, rồi tiếp tục chọn **Purchase Reserved Instances**.
- Với **Offering class**, chọn **Convertible** để hiển thị tất cả các loại Reserved Instances loại Convertible.
- Nếu Instance đặt trước đã xác định nằm trong một vùng cụ thể, bật **Only show offerings that reserve capacity** ở góc phải trên của màn hình thanh toán. Sau khi bật, trường Availability Zone sẽ xuất hiện.
- Điều chỉnh thêm một số lựa chọn khác, rồi bấm **Search**.
- Với từng Reserved Instance mà bạn muốn mua, nhập rõ ràng số lượng mong muốn rồi bấm **Add to cart**.
- Để xem thông tin tổng hợp của loại Reserved Instances mà bạn đã chọn, bấm **View cart**.
- Nếu thời gian thanh toán Order là Now, thì việc thanh toán sẽ diễn ra ngay sau khi bạn bấm chọn Order all. 
  Để đưa Order vào danh sách chờ, bấm Now rồi chọn ngày giờ sẽ thanh toán.
- Để hoàn thành thanh toán cho các đơn hàng, bấm **Order all**.
- Nếu tại thời điểm đặt hàng, có một đề xuất mua Instance tương tự nhưng với chi phí thấp hơn, AWS sẽ gợi ý để bạn mua với chi phí thấp hơn. 
- Bấm **Close**.
- Trạng thái của đơn hàng sẽ được liệt kê ở cột **State**. Khi dơn hàng được thanh toán, trạng thái State sẽ chuyển từ **Payment-pending** sang **Active**. Khi Reserved Instance được Active thì nghĩa là nó đã sẵn sàng để sử dụng.

### Tiến hành mua từ Reserved Instance Marketplace
Bạn có thể mua Reserved Instance từ một bên thứ ba, những người sở hữu Reserved Instance nhưng họ không còn cần sử dụng chúng nữa.  
Tiến trình mua cũng khá tương tự như khi bạn thực hiện mua Instance trên AWS. 

Một vài điểm khác biệt giữa việc mua Reserved Instance trên Reserved Instance Marketplace với mua trực tiếp trên AWS đó là 
- **Term** – Reserved Instances mua từ bên thứ ba sẽ có kỳ hạn còn lại ngắn hơn so với khi mua trực tiếp trên AWS. Kỳ hạn cho môt Reserved Instance khi mua trên AWS là khoảng từ 1 tới 3 năm.

- **Upfront price** – Reserved Instances của bên thứ ba có thể được bán với yêu cầu thanh toán trước khác với khi mua trực tiếp trên AWS. Việc sử dụng hay chi phí định kỳ còn lại vẫn được giữ nguyên giống như khi mua Reserved Instance trực tiếp từ AWS.
- **Types of Reserved Instances** – chỉ có thể mua được Amazon EC2 Standard Reserved Instances trên Reserved Instance Marketplace. Tất cả các loại khác như Convertible Reserved Instances, Amazon RDS, và Amazon ElastiCache Reserved Instances đều không cung cấp trên nền tảng này.

### Kiểm tra các Reserved Instance

- Truy cập Amazon EC2 console tại địa chỉ https://console.aws.amazon.com/ec2/

- Ở khung điều hướng bên trái, chọn **Reserved Instances**.
- Thông tin về danh sách đợi thanh toán, những RI đang active, và nhưng RI đã hết hạn sẽ được liệt kê tại đây. Cột **State** hiển thị trạng thái của các RI. 

### Hủy bỏ đơn hàng trong dnah sách đợi thanh toán
Một đơn hàng có thể nằm trong danh sách đợi thanh toán lên tới 3 năm. Do vậy bạn có thể hủy bỏ đơn hàng bât cứ khi nào, miễn là đơn hàng chưa tới thời điểm kích hoạt. 
Cách hủy bỏ thực hiện như sau: 
- Truy cập Amazon EC2 console tại địa chỉ https://console.aws.amazon.com/ec2/

- Tại khung điều hướng bên trái, bấm chọn **Reserved Instances**.
- Chọn một hoặc nhiều Reserved Instances.
- Bấm **Actions**, rồi chọn **Delete queued Reserved Instances**.
- Khi một thông báo hiện lên yêu cầu Confirm, bấm **Delete**, rồi **Close**.