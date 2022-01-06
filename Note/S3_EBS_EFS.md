﻿## Compare AWS Services: Amazon S3 vs EBS vs EFS

<table class="css-km1wvo"><thead><tr class="css-gtj06"><th class="css-5mpffb"></th><th class="css-5mpffb">S3</th><th class="css-5mpffb">EBS</th><th class="css-5mpffb">EFS</th></tr></thead><tbody><tr class="css-gtj06"><td class="css-68ie2q"><strong class="css-1vg6q84">Type of storage</strong></td><td class="css-68ie2q">Object storage. Bạn có thể lưu trữ hầu như mọi loại dữ liệu ở bất kỳ định dạng nào</td><td class="css-68ie2q">Lưu trữ mức khối (block level) liên tục cho các phiên bản EC2</td><td class="css-68ie2q">Lưu trữ tệp tuân thủ POSIX cho các phiên bản EC2</td></tr><tr class="css-gtj06"><td class="css-68ie2q"><strong class="css-1vg6q84">Features</strong></td><td class="css-68ie2q">Có thể truy cập từ bất kỳ đâu hoặc bất kỳ dịch vụ nào có quyền phù hợp</td><td class="css-68ie2q">Mang lại hiệu suất cho các khối lượng công việc yêu cầu quyền truy cập dữ liệu có độ trễ thấp nhất từ một phiên bản EC2 duy nhất</td><td class="css-68ie2q">Có giao diện hệ thống tệp, ngữ nghĩa truy cập hệ thống tệp (chẳng hạn như tính nhất quán mạnh và khóa tệp) và bộ nhớ có thể truy cập đồng thời cho nhiều phiên bản EC2</td></tr><tr class="css-gtj06"><td class="css-68ie2q"><strong class="css-1vg6q84">Max Storage Style</strong></td><td class="css-68ie2q">Gần như không giới hạn</td><td class="css-68ie2q">16 TiB cho một ổ đĩa</td><td class="css-68ie2q">Kích thước hệ thống không giới hạn</td></tr><tr class="css-gtj06"><td class="css-68ie2q"><strong class="css-1vg6q84">Max File Size</strong></td><td class="css-68ie2q">Các đối tượng Amazon S3 riêng lẻ có thể có kích thước tối đa là <strong class="css-1vg6q84">5 terabyte</strong></td><td class="css-68ie2q">Tương đương với kích thước tối đa của các ổ đĩa của bạn</td><td class="css-68ie2q"><strong class="css-1vg6q84">47.9 TiB</strong> cho một tệp duy nhất</td></tr><tr class="css-gtj06"><td class="css-68ie2q"><strong class="css-1vg6q84">Latency</strong></td><td class="css-68ie2q">Thấp, cho các loại yêu cầu hỗn hợp và tích hợp với CloudFront</td><td class="css-68ie2q">Thấp nhất, nhất quán; Các kho lưu trữ được hỗ trợ bởi SSD bao gồm <strong class="css-1vg6q84">Provisioned IOPS SSD</strong> có hiệu suất cao nhất  và <strong class="css-1vg6q84">General Purpose SSD</strong> cân bằng giữa giá cả và hiệu suất</td><td class="css-68ie2q">Thấp, nhất quán; sử dụng chế độ Max I/O để có hiệu suất cao hơn</td></tr><tr class="css-gtj06"><td class="css-68ie2q"><strong class="css-1vg6q84">Throughput</strong></td><td class="css-68ie2q">Nhiều GB mỗi giây; hỗ trợ multi-part upload</td><td class="css-68ie2q">Ổ cứng HDD-backed bao gồm khối lượng công việc chuyên sâu về thông lượng và Cold HDD cho dữ liệu được truy cập ít thường xuyên hơn</td><td class="css-68ie2q"><strong class="css-1vg6q84">Hơn 10 GB mỗi giây</strong>. Chế độ <strong class="css-1vg6q84">Bursting Throughput</strong> thay đổi tỷ lệ với kích thước của hệ thống tệp. Chế độ <strong class="css-1vg6q84">Provisioned throughput</strong> cung cấp thông lượng chuyên dụng cao hơn bustring throughput</td></tr><tr class="css-gtj06"><td class="css-68ie2q"><strong class="css-1vg6q84">Durability</strong></td><td class="css-68ie2q">Được lưu trữ dự phòng trên nhiều AZ; <strong class="css-1vg6q84">99.999999999%</strong> durability</td><td class="css-68ie2q">Được lưu trữ trong một AZ duy nhất</td><td class="css-68ie2q">Được lưu trữ dự phòng trên nhiều AZ</td></tr><tr class="css-gtj06"><td class="css-68ie2q"><strong class="css-1vg6q84">Availability</strong></td><td class="css-68ie2q">- S3 Standard: 99.99% availability <br>- S3 Standard-IA: 99.9% availability<br>- S3 One Zone-IA: 99.5% availability<br>- S3 Intelligent Tiering: 99.9% availability</td><td class="css-68ie2q">99.999% availability</td><td class="css-68ie2q">99.9% SLA (Sevice Level Agreement)</td></tr><tr class="css-gtj06"><td class="css-68ie2q"><strong class="css-1vg6q84">Scalability</strong></td><td class="css-68ie2q">Khả năng mở rộng cao</td><td class="css-68ie2q">Tăng/giảm kích thước bộ nhớ của bạn theo cách thủ công. Đính kèm và tách rời các volume  vào và từ phiên bản EC2 của bạn để chia tỷ lệ</td><td class="css-68ie2q">Hệ thống tệp EFS có tính đàn hồi và tự động phát triển và thu nhỏ khi bạn thêm và xóa tệp</td></tr><tr class="css-gtj06"><td class="css-68ie2q"><strong class="css-1vg6q84">Data Accessing</strong></td><td class="css-68ie2q">Một đến hàng triệu kết nối qua wed; S3 cung cấp giao diện dịch vụ web REST</td><td class="css-68ie2q">Phiên bản EC2 duy nhất trong một AZ <br> Amazon EBS Multi-Attach có thể attach một Provisioned IOPS SSD duy nhất (io1 hoặc io2) cho tối đa 16 phiên bản dựa trên Nitro trong cùng AZ</td><td class="css-68ie2q">Một đến hàng nghìn phiên bản EC2 hoặc máy chủ tại chỗ, từ nhiều AZ, khu vực, VPC và tài khoản đồng thời</td></tr><tr class="css-gtj06"><td class="css-68ie2q"><strong class="css-1vg6q84">Access Control</strong></td><td class="css-68ie2q">Sử dụng bucket policies và IAM user policies. Có cài đặt Block Public Access để giúp quản lý quyền truy cập công khai vào tài nguyên.</td><td class="css-68ie2q">IAM Policies, Roles và Security Groups</td><td class="css-68ie2q">Chỉ các tài nguyên có thể truy cập điểm cuối trong VPC của bạn, được gọi là mục tiêu gắn kết, mới có thể truy cập vào hệ thống tệp của bạn; Người dùng tuân thủ POSIX và quyền level group</td></tr><tr class="css-gtj06"><td class="css-68ie2q"><strong class="css-1vg6q84">Encryption Methods</strong></td><td class="css-68ie2q">Hỗ trợ SSL endpoints bằng giao thức HTTPS, Mã hóa phía máy khách và phía máy chủ (SSE-S3, SSE-C, SSE - KMS)</td><td class="css-68ie2q">Mã hóa cả data-at-rest và data-in-transit thông qua mã hóa EBS sử dụng AWS KMS CMK</td><td class="css-68ie2q">Mã hóa cả data-at-rest và data-in-transit: Mã hóa data-at-rest sử dụng AWS KMS. Mã hóa data-in-transit sử dụng TLS</td></tr><tr class="css-gtj06"><td class="css-68ie2q"><strong class="css-1vg6q84">Backup and Restoration</strong></td><td class="css-68ie2q">Sử dụng versioning hoặc cross-region replication</td><td class="css-68ie2q">Tất cả các loại EBS volume đều cung cấp khả năng snapshot bền bỉ</td><td class="css-68ie2q">Sao chép EFS sang EFS khác thông qua các công cụ của bên thứ ba hoặc AWS DataSync</td></tr><tr class="css-gtj06"><td class="css-68ie2q"><strong class="css-1vg6q84">Pricing</strong></td><td class="css-68ie2q">Giá thanh toán dựa trên vị trí bucket của bạn. Bạn sẽ nhận được giá càng rẻ khi sử dụng càng nhiều dung lượng lưu trữ S3</td><td class="css-68ie2q">Bạn sẽ trả cho mỗi Gb-month dung lượng được cấp phép, provisioned IOPS-month, GB-month của dữ liệu snapshot lưu trữ trên S3</td><td class="css-68ie2q">Bạn phải trả nhiều hơn dung lượng lưu trữ hệ thống tệp được sử dụng mỗi tháng. Khi sử dụng chế độ Provisioned Throughput, bạn phải trả cho thông lượng mà bạn cung cấp mỗi tháng</td></tr><tr class="css-gtj06"><td class="css-68ie2q"><strong class="css-1vg6q84">Use Cases</strong></td><td class="css-68ie2q">Web server và quản lý nội dung, phương tiện giải trí, sao lưu, phân tích dữ liệu lớn, data lake</td><td class="css-68ie2q">Boot volumes, cơ sở dữ liệu giao dịch và NoSQL, data warehousing &amp; ETL</td><td class="css-68ie2q">Web server và quản lý nội dung, ứng dụng doanh nghiệp, phương tiện giải trí, thư mục gia đình, sao lưu cơ sở dữ liệu, công cụ dành cho nhà phát triển, container storage, phân tích dữ liệu lớn</td></tr><tr class="css-gtj06"><td class="css-68ie2q"><strong class="css-1vg6q84">Service endpoint</strong></td><td class="css-68ie2q">Có thể được truy cập bên trong và bên ngoài VPC (thông qua S3 bucket URL)</td><td class="css-68ie2q">Được truy cập trong VPC của một chủ thể</td><td class="css-68ie2q">Được truy cập trong VPC của một chủ thể</td></tr></tbody></table>

Additional notes:
```
S3 rẻ hơn EBS và EFS về chi phí lưu trữ thuần túy
EBS và EFS có hiệu năng cao hơn S3
EBS được sử dụng làm volumes cho EC2 instances
S3 không có hệ thống phân cấp (môi trường phẳng) cho các tệp như EFS
S3 có tính năng truy vấn tích hợp
S3 cung cấp tính nhất quán mạnh mẽ cho tất cả các loại request
```