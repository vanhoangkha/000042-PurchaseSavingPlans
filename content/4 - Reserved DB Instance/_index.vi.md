+++
title = "Reserved DB Instances"
date = 2020
weight = 5
chapter = false
pre = "<b>4. </b>"
+++

Sử dụng reserved DB instances, bạn có thể đặt trước thời hạn một hoặc ba năm. Reserved DB instances đem tới lợi ích là một khoản chiết khấu đáng kể so với việc sử dụng On-Demand DB.  
Tùy thuộc mỗi phiên bản và mỗi khu vực mà mức giảm giá cho các reserved DB là khác nhau. 

Nói chung quy trình làm việc với reserved DB instances bao gồm các bước là: đầu tiên lấy thông tin những reserved DB khả dụng, sau đó thực hiện mua reserved DB instance đã chọn, và cuối cùng finally lấy thông tin về reserved DB instances đang chạy. 

### Tổng quan về reserved DB instances
Khi mua reserved DB instances, bạn sẽ nhận được discount tương ứng với loại DB instance và thời gian sử dụng loại Instance đó. Để sử dụng reserved DB instances, ta thực tạo Instance giống như tạo  một On-Demand DB Instance.  
Tuy nhiên lưu ý khi tạo DB Instance phải đặt các cấu hình đúng với cấu hình đã mua Reserved DB Instance. Nếu có sự sai khác trong việc tạo DB Instance, lập tức bạn sẽ bị tính phí theo dạng tạo On-Demand DB Instance.  

Tương tự với Savings Plan hay RI, việc thanh toán cho Reserved DB Instance cũng được chia làm 3 dạng: 
- **All Upfront**: trả trước toàn bộ –> cái này sẽ giúp bạn tiết kiệm nhiều nhất

- **Partial Upfront**: trả trước 1 phần. Giảm giá sẽ ít hơn All Upfront nhưng nhiều hơn No Upfront
- **No Upfront**: không trả trước mà chỉ commit là sẽ trả sau khi kết thúc kỳ hạn. Hình thức này có giảm giá ít nhất trong 3 loại

Khi mua một Reserved DB Instance, có một thứ mà bạn cần phải chỉ rõ đó là lớp Instance của Reserved DB Instance. Bởi sau khi mua reserved DB Instance, thông tin này là không thể thay đổi.  
Kích thước của Instance có thể thay đổi khi Instance tự động scale, hoặc Instance có thể được di chuyển sang một region khác, kể cả khi Instance được cấu hình Multi-AZ hay Single-AZ thì việc tính giá cho Reserved DB Instance là không thay đổi.  
Tuy nhiên nếu thực hiện thay đổi Instance Class, ví dụ từ db.m4.large sang db.m5.large, việc tính phí sẽ hoàn toàn không được áp dụng. Giá Instance lúc này được tính theo giá của On-Demand DB Instance.  

Những loại RDS DB engine mà khả dụng với Reserved DB Instance là: 
- MariaDB

- MySQL
- Oracle, Bring Your Own License
- PostgreSQL

Một cam kết sử dụng  sẽ có kỳ hạn từ một tới 3 năm. Trong khoảng thời gian này, bạn sẽ không thể cancel được DB Instance, mà chỉ có thể xóa bỏ DB Instance.
Việc xóa bỏ nó cũng tương tự như đối với các DB Instance khác.  
Sau khi đã xóa DB Instance mà được áp dụng tính giá theo Reserved DB Instance, bạn hoàn toàn có thể tạo một DB Instance khác mà vẫn giữ được mức tính giá được chiết khấu tương ứng như cam kết ban đầu.   
Tuy nhiên phải đảm bảo DB Instance mới vẫn phải thuộc cùng Instance Class, và cùng DB engine.   

### Làm việc với reserved DB instances 

Để thực hiện mua Reserved DB Instance khả dụng , ta thực hiện theo các bước sau đây: 
- Truy cập AWS Management Console và mở Amazon RDS console theo địa chỉ https://console.aws.amazon.com/rds/

- Tại khung điều hướng bên phải, chọn **Reserved instances**.
- Tiếp tục chọn **Purchase Reserved DB Instance**.
- Phần **Product description**, Chọn **DB engine** và **licensing type**.
- Với **DB instance class**, chọn DB instance class mà bạn mong muốn sử dụng.
- Với lựa chọn triển khai **Multi-AZ**, tích chọn nếu bạn muốn triển khai cấu hình này. 
- Với **Term**, chọn quãng thời gian bạn muốn sử dụng DB instance reserved.
- Với **Offering type**, chọn kiểu thanh toán. Ngay sau đó bạn sẽ nhìn thấy thông tin chi phí tương ứng với kiểu thanh toán mà bạn đã chọn. 
- Bấm tiếp **Continue**. Một hộp thoại **Purchase Reserved DB Instance** xuất hiện, với cấu hình tổng hợp về reserved DB instance mà bạn đã lựa chọn cùng với khoản thanh toán đến hạn. 
- Tại trang **Confirmation**, review lại reserved DB instance lần cuối. Nếu các thông tin là chính xác, bấm **Purchase** để mua reserved DB instance.
- Ngược lại, bấm vào **Back** để chỉnh sửa cấu hình của reserved DB instance sẽ mua.