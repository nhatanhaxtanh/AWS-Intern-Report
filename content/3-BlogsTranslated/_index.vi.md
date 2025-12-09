---
title: "Các bài blogs đã dịch"
date:
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

Tại đây sẽ là phần liệt kê, giới thiệu các blogs mà các bạn đã dịch. Ví dụ:

###  [Blog 1 - Phân tích nội dung media bằng các dịch vụ AI của AWS￼](3.1-Blog1/)
Bài viết trình bày một kiến trúc AWS hướng sự kiện giúp tự động chuyển đổi dữ liệu âm thanh/video thô thành thông tin có cấu trúc và có thể tìm kiếm. Khi media được tải lên S3, Step Functions sẽ kích hoạt Amazon Transcribe để chuyển giọng nói thành văn bản và Amazon Bedrock để phân tích bằng AI, xác định quảng cáo, phỏng vấn và các phân đoạn quan trọng. Kết quả được lưu trong data lake, truy vấn bằng Athena, trực quan hóa bằng QuickSight và tìm kiếm bằng ngôn ngữ tự nhiên thông qua Amazon Q. Bài viết nhấn mạnh yêu cầu bảo mật mạnh, kiểm thử, tối ưu hóa và khả năng mở rộng. Giải pháp phù hợp cho các lĩnh vực như phát thanh – truyền hình, quản lý tri thức doanh nghiệp, giáo dục, pháp lý, y tế và dịch vụ khách hàng.

###  [Blog 2 - Cải thiện thời gian phản hồi của AI hội thoại cho ứng dụng doanh nghiệp với Amazon Bedrock streaming API và AWS AppSync](3.2-Blog2/)
Bài viết mô tả cách giảm độ trễ của AI hội thoại bằng cách stream phản hồi của LLM trên Amazon Bedrock thông qua AWS AppSync. Pipeline Lambda–SNS–Lambda gọi API converse_stream, sau đó đẩy các token phản hồi từng phần lên frontend thông qua AppSync subscriptions, giúp người dùng thấy câu trả lời ngay khi mô hình tạo ra. Cơ chế buffer giúp giảm số lượng cuộc gọi mạng, tăng tốc độ trong khi vẫn tuân thủ yêu cầu bảo mật cấp doanh nghiệp (VPC, OAuth, kiểm soát luồng dữ liệu). Một tập đoàn tài chính toàn cầu đã giảm thời gian phản hồi ban đầu từ ~10 giây xuống còn 2–3 giây. Terraform và mã mẫu cho phép triển khai nhanh chóng.

###  [Blog 3 - Nâng cao quyền riêng tư dữ liệu y tế thông qua hệ thống khử định danh ảnh y khoa dựa trên AI](3.3-Blog3/)
PixelGuard là hệ thống khử định danh hình ảnh y khoa trên AWS, sử dụng hơn 75 mô hình AI để loại bỏ hoặc làm mờ thông tin nhận dạng trong metadata và pixel mà vẫn bảo toàn giá trị lâm sàng. Giải pháp hỗ trợ nhiều định dạng (DICOM, JPEG, PNG, NIfTI), phát hiện văn bản burned-in bằng OCR và ML, và tạo file ánh xạ được mã hóa cho phép truy xuất ngược khi được ủy quyền. PixelGuard đảm bảo bảo mật thông qua SSO, API Gateway, Cognito và AWS KMS. Giải pháp giúp tổ chức tuân thủ HIPAA/GDPR, chia sẻ dữ liệu nghiên cứu an toàn và thúc đẩy phát triển AI trong lĩnh vực hình ảnh y khoa.