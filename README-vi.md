# Tài liệu PlaidCloud

[![Build Status](https://api.travis-ci.org/PlaidCloud/website.svg?branch=master)](https://travis-ci.org/PlaidCloud/website)
[![GitHub release](https://img.shields.io/github/release/PlaidCloud/website.svg)](https://github.com/PlaidCloud/website/releases/latest)

Chào mừng! Kho lưu trữ này chứa tất cả các tài nguyên cần thiết để xây dựng [trang web của PlaidCloud và các tài liệu](https://plaidcloud.com/). Chúng tôi rất vui vì bạn muốn đóng góp.

## Đóng góp cho tài liệu

Bạn có thể click vào nút **Fork** ở góc trên bên phải màn hình để tạo bản sao của kho lưu trữ này trong tài khoản GitHub của bạn. Bản sao này được gọi là một bản *fork*. Thực hiện bất kì thay đổi nào mà bạn muốn trong bản fork của bạn và khi bạn sẵn sang gửi những thay đổi đó cho chúng tôi, hãy đến bản fork của bạn và tạo một Pull Request mới để cho chúng tôi biết về nó.

Một khi Pull Request của bạn được tạo, reviewer sẽ chịu trách nhiệm cung cấp các phản hồi rõ ràng, có thể thực hiện được. Là chủ sở hữu của pull request, **bạn có trách nhiệm sửa đổi Pull Request của mình để giải quyết các phản hồi bởi reviewer.**  Ngoài ra, lưu ý rằng bạn có thể có nhiều hơn một reviewer cung cấp cho bạn các phản hồi hoặc bạn có thể nhận được phản hồi từ reviewer khác với reviewer ban đầu được chỉ định. Hơn nữa, trong một số trường hợp, một trong những reviewer của bạn có thể yêu cầu đánh giá kỹ thuật từ [PlaidCloud tech reviewer](https://github.com/PlaidCloud/website/wiki/Tech-reviewers) khi cần. Các reviewers sẽ cố gắng hết sức để cung cấp phản hồi một cách kịp thời nhưng thời gian phản hồi có thể thay đổi tùy theo hoàn cảnh.

Để biết thêm thông tin về việc đóng góp cho tài liệu PlaidCloud, hãy xem:

* [Bắt đầu đóng góp](https://plaidcloud.com/docs/contribute/start/)
* [Các giai đoạn thay đổi tài liệu](http://PlaidCloud.io/docs/contribute/intermediate#view-your-changes-locally)
* [Sử dụng các trang templates](https://plaidcloud.com/docs/contribute/style/page-content-types/)
* [Hướng dẫn biểu mẫu tài liệu](http://PlaidCloud.io/docs/contribute/style/style-guide/)
* [Địa phương hóa tài liệu PlaidCloud](https://plaidcloud.com/docs/contribute/localization/)


## Chạy website cục bộ dùng Docker

Cách được đề xuất để chạy trang web PlaidCloud cục bộ là dùng [Docker](https://docker.com) image chứa trình tạo web tĩnh [Hugo](https://gohugo.io).

> Nếu bạn làm việc trên môi trường Windows, bạn sẽ cần thêm môt vài công cụ mà bạn có thể cài đặt với [Chocolatey](https://chocolatey.org). `choco install make`

> Nếu bạn không muốn dùng Docker để chạy trang web cục bộ, hãy xem [Chạy website cục bộ dùng Hugo](#chạy-website-cục-bộ-dùng-hugo) dưới đây.

Nếu bạn có Docker đang [up và running](https://www.docker.com/get-started), build `PlaidCloud-hugo` Docker image cục bộ:

```bash
make container-image
```

Khi image đã được built, bạn có thể chạy website cục bộ:

```bash
make container-serve
```

Mở trình duyệt và đến địa chỉ http://localhost:1313 để xem website. Khi bạn thay đổi các file nguồn, Hugo cập nhật website và buộc làm mới trình duyệt.

## Chạy website cục bộ dùng Hugo

Hãy xem [tài liệu chính thức của Hugo](https://gohugo.io/getting-started/installing/) cho việc hướng dẫn cài đặt Hugo. Đảm bảo cài đặt phiên bản mở rộng của Hugo được xác định bởi biến môi trường `HUGO_VERSION` trong file [`netlify.toml`](netlify.toml#L9)

Để chạy website cục bộ khi Hugo được cài đặt:

```bash
make serve
```

Câu lệnh trên sẽ khởi động server Hugo cục bộ trên cổng 1313. Mở trình duyệt và đến địa chỉ http://localhost:1313 để xem website. Khi bạn thay đổi các file nguồn, Hugo cập nhật website và buộc làm mới trình duyệt.

## Cộng đồng, thảo luận, đóng góp và hỗ trợ

Tìm hiểu cách tham gia với cộng đồng PlaidCloud trên [trang cộng đồng](http://PlaidCloud.io/community/).

Bạn có thể tiếp cận những maintainers của dự án này tại:

- [Slack](https://PlaidCloud.slack.com/messages/sig-docs)
- [Mailing List](https://groups.google.com/forum/#!forum/PlaidCloud-sig-docs)

### Quy tắc ứng xử

Sự tham gia vào cộng đồng PlaidCloud được điểu chỉnh bởi [PlaidCloud Code of Conduct](code-of-conduct.md).

## Cảm ơn!

PlaidCloud phát triển mạnh mẽ về sự tham gia của cộng đồng và chúng tôi đánh giá cao những đóng góp của bạn cho trang web và tài liệu của chúng tôi!
