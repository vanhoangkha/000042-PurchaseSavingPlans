+++
title = "Giới thiệu về Savings Plan"
date = 2020
weight = 1
chapter = false
pre = "<b>1. </b>"
+++

**Savings Plan** là một mô hình tính giá linh hoạt giúp chung ta tiết kiệm đc tới 72% chi phí khi sử dụng các dịch vụ như **EC2**, **Fargate** hay **Lambda**.  
SP đem tới chi phí sử dụng EC2, Fargate và Lambda thấp hơn nhiều so với bình thường, đổi lại bằng sự cam kết sử dụng dịch vụ lâu dài (tính theo giờ) trong vòng ít nhất 1 năm tới 3 năm.   
SP có thể được cài đặt ở bất cứ Account nào, có thể là Management Account hoặc Member Account. SP sau khi được cài đặt sẽ áp dụng với Account sở hữu SP trước, 
sau đó nó đc áp dụng cho các Account khác nằm cùng hệ quản trị tổ chức *AWS Organization*.   

Khi SP đã được thiết lập, chi phí sử dụng dịch vụ theo giờ sẽ luôn được giữ nguyên trong suốt thời gian hoạt động của SP. Bạn có thể thanh toán với 3 lựa chọn là: 
- All Upfront

- Partial upfront 
- No upfront

Để bắt đầu, truy cập [AWS Cost Explorer](https://console.aws.amazon.com/billing/home?region=us-west-1#/costexplorer) để tham khảo các kiểu SP được đề xuất, cách tính phí SP, quản lý SP và lịch sử sử dụng các dịch vụ AWS. Những đề xuất này giúp bạn dễ dàng lựa chọn được mức cam kết SP phù hợp với mình. 
Từ đó có thể tối ưu để đáp ứng hơn nữa nhu cầu sử dụng thực tế.  

Để xem danh sách các dịch vụ AWS phù hợp với SP, truy cập [Working with supported services](https://docs.aws.amazon.com/savingsplans/latest/userguide/sp-services.html)

### Plan Types
- **Compute Savings Plan**: giải pháp sử dụng dịch vụ với chi phí tốt nhất và linh hoạt nhất, tiết kiệm 60% so với chi phí sử dụng dịch vụ kiểu **On-Demand**.   
  SP tự động áp dụng cho các EC2 instance, bất kể họ của Instance, kích thước Instance, region nào, hệ điều hành, hoặc kiểu tenancy là gì. Điều này cũng đúng với các dịch vụ như Fargate và Lambda.  
  Với kiểu tính phí này, chúng ta có thể chuyển workload từ C5 lên M5, chuyển lưu lượng từ Ireland sang London, hoặc chuyển ứng dụng từ EC2 sang Fargate bất cứ khi nào.   
  Bạn vẫn duy trì được lợi ích từ cách tính chi phí thấp của Savings Plan khi bạn thực hiện thay đổi với các dịch vụ của hệ thống. 


- **EC2 Instance Savings Plan**: giải pháp tiết kiệm chi phí lên tới 72%, đổi bằng việc cam kết sử dụng một họ Instance cụ thể tại 1 Regions cụ thể. 
  Những kế hoạch này tự động áp dụng bất kể dung lượng , hệ điều hành hay loại tenancy là gì, miễn là giữ nguyên họ của Instance và không được thay đổi Regions. 

### Savings Plan và Reserved Instances

Savings Plan giống với RIs ở chỗ chúng đều đem lại giải pháp tính giá chi phí thấp hơn khi sử dụng dịch vụ như E2, tuy nhiên Savings Plan bổ sung thêm một số đặc điểm linh hoạt hơn.  
Với SP bạn có thể giảm chi phí bằng việc cám kết sử dụng dịch vụ tính toán một cách nhất quán thay vì cấu hình cụ thể cho Instance.  
SP cho phép bạn lựa chọn các loại Instance sao cho phù hợp nhất với nhu cầu mà chi phí thấp mà không phải trao đổi hoặc thay đổi gì nhiều.   


|  Comparing Savings Plans và RIs                                                            |      Compute Savings Plans     |      EC2 Instance Savings Plans     |      Convertible RIs*     |      Standard RIs     |
|--------------------------------------------------------------------------------------------|--------------------------------|-------------------------------------|---------------------------|-----------------------|
| Tiết kiệm so với On-Demand                                                                 |     Lên đến 66%                |     Lên đến 72%                     |     Lên đến 66%           |     Lên đến 72%       |
| Giá thấp hơn với các kiểu cam kết thanh toán                                               |     ✓                          |     ✓                               |     —                     |     —                 |
| Tự động áp dụng chi phí tiết kiệm cho mọi Instance thuộc cùng họ                           |     ✓                          |     —                               |     ✓                     |     —                 |
| Tư động áp dụng chi phí tiết kiệm cho mọi kích thước Instance                              |     ✓                          |     ✓                               |     ✓                     |     ✓               |
| Tự động áp dụng chi phí tiết kiệm cho mọi hệ điều hành và mọi kiểu tenancy của Instance    |     ✓                          |     ✓                               |     ✓                     |     ✓                 |
| Tự động áp dụng chi phí tiết kiệm đối với Amazon ECS sử dụng Fargate                       |     ✓                          |     —                               |     —                     |     —                 |
| Tự động áp dụng chi phí tiết kiệm khi sử dụng dịch vụ Lambda                               |     ✓                          |     —                               |     —                     |     —                 |
| Tự động áp dụng chi phí tiết kiệm trên tất cả các AWS Regions                              |     ✓                          |     —                               |     —                     |     —                 |
| Tùy chọn thời hạn áp dụng chi phí tiết kiệm từ 1 tới 3 năm                                 |     ✓                          |     ✓                               |     ✓                     |     ✓                 |


Như vậy so với Reserved Instance thì AWS Saving Plans có những lợi thế đó là:
- Với Reserved Instance, bạn sẽ bị bắt buộc phải giữ instance type đó trong 1 hoặc 3 năm. Nhưng yêu cầu có thể thay đổi trong thời gian đó, có thể là up size hoặc down size.  
  Tất nhiên bạn cũng có thể chống chế bằng cách Bán Reserve Instance và mua cái khác hoặc thay mua thêm RIs hợp với RIs cũ như phần note ở mục trên.

  
- Bạn có thể nhìn thấy hiệu quả ngay lập tức về việc discount ở Saving Plan.
- Saving Plans có thể áp dụng cho Fargate, Lambda như EC2 nhưng nó không thể áp dụng cho RDS
- Sự phức tạp của RIs đã được loại bỏ với Saving Plan - có rất ít kế hoạch kiểu xoay quanh instance Type nào, instance family nào và sau đó bạn sẽ muốn chuyển đổi RI hoặc bán nó lên Marketplace.
- Việc lên kế hoạch sử dụng infra ít tốn công hơn, chúng ta không cần phải lập kế hoách quá chi tiết về việc sử dụng trong vòng 1-3 năm nữa. Chỉ cần cam kết sử dụng theo số liệu đã tính toán nhất định.
- Với Saving Plans, cho phép bạn linh hoạt chuyển đổi workload giữa các instance type để đáp ứng nhu cầu và tận dụng chi phí, mặc dù không có lợi thế khi down time. Với RIs, thì không thấy được sự linh động này vì đã cam kết sử dụng trong 1 thời gian nhất định rồi.

Một vài lưu ý khác: 
- Savings Plans không cung cấp giải pháp dự trữ dung lượng, nhưng bạn có thể phân bổ ODCR (On-Demand Capacity Reservation) nếu có nhu cầu và Savings Plans sẽ áp dụng theo. 

- Giá SP cho Instance chạy SLES có thể khác với giá tính cho RI tương ứng. 
- SP hiện không khả dụng tại China và Osaka-Local
- Giá của SP không thay đổi dựa trên số lượng giờ sử dụng được cam kết.
- SP không áp dụng đối với Spot Instance và RIs Instance.
- Convertible RIs có thể bị tính phí khi thay đổi Họ, kích thước, OS hoặc kiểu tenancy của Instance, ngoài ra chúng ta phải thực hiện sự thay đổi này thủ công. 
- Regional convertible RIs và Regional standard RIs cho phép tùy chỉnh linh hoạt kích thước Instance.
- Compute Savings Plan giúp tiết kiệm 66% chi phí so với On-Demand, tương đương với Convertible RIs.  
- EC2 Instance Savings Plan thì giúp tiết kiệm 72% chi phí so với On-Demand, tương đương với Standard RIs.