+++
title = "Reserved Instance type"
weight = 1
chapter = false
pre = "<b>4.1 </b>"
+++


#### Các loại Reserved Instance
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

{{% notice info %}}
Lưu ý :  
. RI không chỉ áp dụng cho EC2 mà còn áp dụng cho cả RDS.  
. Với hình thức RI Chuẩn (Standard), bạn càng dùng nhiều cùng 1 dòng Instance thì càng dễ mua RI.  
. Tương tự Savings Plan, có 3 phương thức thanh toán là:  
**All Upfront**: trả trước toàn bộ –> cái này sẽ giúp bạn tiết kiệm nhiều nhất
**Partial Upfront**: trả trước 1 phần. Giảm giá sẽ ít hơn All Upfront nhưng nhiều hơn No Upfront  
**No Upfront**: không trả trước mà chỉ commit là sẽ trả sau khi kết thúc kỳ hạn. Hình thức này có giảm giá ít nhất trong 3 loại

{{% /notice %}}

So với On Demand Instance, RI thực sự là 1 cách làm hay mà đơn giản để giúp người dùng tiết kiệm chi phí cho các máy chủ ảo. Tất cả những gì bạn cần làm chỉ là đăng ký mua theo 1 năm (hoặc 3 năm) để nhận được ưu đãi về chi phí.