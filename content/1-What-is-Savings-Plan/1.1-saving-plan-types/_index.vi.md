+++
title = "Saving Plan Types"
weight = 1
chapter = false
pre = "<b>1.1 </b>"
+++

#### Compute Savings Plan
**Compute Savings Plan** Là giải pháp sử dụng dịch vụ với chi phí tốt nhất và linh hoạt nhất, tiết kiệm 60% so với chi phí sử dụng dịch vụ kiểu **On-Demand**.   
  SP tự động áp dụng cho các EC2 instance, bất kể family  của Instance, kích thước Instance, region nào, hệ điều hành, hoặc kiểu tenancy là gì. Điều này cũng đúng với các dịch vụ như Fargate và Lambda.  

  Với kiểu tính phí này, chúng ta có thể chuyển workload từ C5 lên M5, chuyển lưu lượng từ Ireland sang London, hoặc chuyển ứng dụng từ EC2 sang Fargate bất cứ khi nào.   
  Bạn vẫn duy trì được lợi ích từ cách tính chi phí thấp của Savings Plan khi bạn thực hiện thay đổi với các dịch vụ của hệ thống. 

#### EC2 Instance Savings Plan
**EC2 Instance Savings Plan** giải pháp tiết kiệm chi phí lên tới 72%, đổi bằng việc cam kết sử dụng một họ Instance cụ thể tại 1 Regions cụ thể. 
  Những kế hoạch này tự động áp dụng bất kể dung lượng , hệ điều hành hay loại tenancy là gì, miễn là giữ nguyên họ của Instance và không được thay đổi Regions. 

{{% notice tip %}}
Chúng ta có thể thấy , EC2 Instance Savings Plan cho mức discount cao hơn và Compute Savings Plan cho chúng ta sự lựa chọn chuyển đổi loại tài nguyên linh hoạt hơn.
{{% /notice %}}
