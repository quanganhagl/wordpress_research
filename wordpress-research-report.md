# Cách thức tạo template của Wordpress

## Khái quát về Wordpress

WordPress là một dạng phần mềm mã nguồn mở được Christine Selleck đề xuất . Mọi người biết đến WordPress đơn giản là để viết Blog, để đăng tải thông tin của mình lên mạng nhưng không đơn giản như vậy, WordPress còn có chức năng như mọi Website khác. Nó có thể làm site tin tức, đánh giá, bán hàng… thậm chí là… mạng xã hội. Các bạn có thể ứng dụng wordpress để tạo cho mình 1 website trên nền wordpress , 1 website được tạo ra nhanh chóng đơn giản mà lại tiện cho việc quảng bá sản phẩm , thông tin , kiến thức ….

## Cấu tạo file nguồn (core file) của Wordpress

Cấu trúc thư mục và tệp WordPress điển hình trông như thế này:

### Folder

- wp-admin
  Thư mục này chịu trách nhiệm cung cấp năng lượng cho các công cụ quản trị trang web WordPress của bạn, chẳng hạn như trang tổng quan và một số tính năng chính như cho phép kết nối với cơ sở dữ liệu của bạn và quản lý quyền của người dùng.

- wp-content
  Thư mục wp-content có hai thư mục con: plugin và chủ đề, lưu trữ dữ liệu liên quan đến các tiện ích bổ sung này trên cài đặt WordPress của bạn. Mỗi plugin và chủ đề bạn cài đặt sẽ tạo một thư mục mới trong cấu trúc này.

- wp-include
  Trong thư mục wp-include là tất cả các tệp cần thiết để làm cho trang web của bạn chạy, chẳng hạn như các chức năng của WordPress, những tệp kiểm soát bài đăng, trang, tiện ích của bạn và các tính năng khác nhau.

### Các tập tin:

1. index.php
2. license.txt
3. readme.html
4. wp-active.php
5. wp-blog-header.php
6. wp-comments-post.php
7. wp-config-sample.php
8. wp-cron.php
9. wp-links-opml.php
10. wp-load.php
11. wp-login.php
12. wp-mail.php
13. wp-settings.php
14. wp-signup.php
15. wp-trackback.php
16. xmlrpc.php
17. .htaccess
18. wp-config.php

## Cách thức kết nối tới database.

- Bước 1: Để lưu trữ dữ liệu website thì chúng ta cần có Database, để tạo được một Database các bạn hãy tìm mục Databases. Vào Hosting, ở mục Databases bấm vào MySQL Databases
- Bước 2: Sau đó bạn sẽ tới phần tạo cơ sở dữ liệu. Đầu tiên tạo Database đặt tên tùy ý → Create Database → Go Back
- Bước 3: Tạo User để quản lý Database. Đặt tên tùy ý khác hay giống với tên của Database đều được, password cần nhập ký tự có chứa chữ và số → Create User → Go Back
- Bước 4: Cấp quyền quản lí, truy cập Database cho User. Ở mục Add User To Database bấm Add để thêm User vào Database
- Bước 5: Bấm tick vào ALL PRIVILEGES để chọn tất cả → Make Changes → Go Back
- Bước 6: Vào lại mục public_html trong File Manager tìm đến file wp-config-sample.php chuột phải chọn Edit
- Bước 7: Chỉnh sửa lại các thông tin User và Password vừa tạo ở Database → Save Changes
- Bước 8: Quay lại file wp-config-sample.php chuột phải chọn Rename bỏ chữ sample đi → Rename File
- Bước 9: Đăng nhập vào website với tên Domain của bạn và điền các thông tin cần thiết vào theo đường dẫn: domain/wp-admin và sau khi bấm enter sẽ xuất hiện giao diện như hình bên dưới để cho các bạn bắt đầu điền các thông tin cần thiết trước khi đăng nhập vào trang quản trị Admin → Cài đặt WordPress
- Bước 10: Đăng nhập vào trang quản trị website WordPress. Trên thanh công cụ của trình duyệt, nhập domain/wp-admin như ở trên mình vừa nói
- Bước 11: Nhập thông tin User và Password bạn vừa tạo ở trên vào → Đăng nhập

## Xử lý vòng lặp (loop) cho bài post cơ bản trong Wordpress theme.

1. Lấy dữ liệu bằng WP_query
2. Hiển thị dữ liệu bằng vòng lặp LOOP
3. Hiển thị phân trang kết quả

## Cấu tạo file template - Các file thiết yếu.

### Hiển thị Home Page

Mặc định WordPress đặt homepage website của bạn để hiển thị các bài viết trên blog mới nhất của bạn. Trang này được gọi là các bài viết index trên blog. Bạn cũng có thể đặt các bài viết trên blog của mình hiển thị trên một trang tĩnh riêng biệt. File template home.php được sử dụng để hiển thị các bài viết index trên blog, cho dù nó đang được sử dụng làm trang đầu hay trên trang tĩnh riêng biệt. Nếu home.php không tồn tại, cấu trúc Theme WordPress sẽ sử dụng index.php.

- home.php.
- index.php.

### Hiển thị Front Page

File template front-page.php được sử dụng để hiển thị trang đầu website của bạn, cho dù trang đầu hiển thị bài viết index trên blog (đã đề cập ở trên) hay một trang tĩnh. Mẫu trang đầu được ưu tiên hơn bài viết index trên blog (home.php). Nếu tệp front-page.php không tồn tại, cấu trúc Theme WordPress sẽ sử dụng tệp home.php hoặc page.php tùy thuộc vào thiết lập trong Setting > Reading. Nếu cả hai file đó đều không tồn tại, nó sẽ sử dụng file index.php.

- front-page.php: Được sử dụng cho cả “bài đăng mới nhất” hoặc “trang tĩnh” được đặt trong phần Display front page của Setting > Reading.
- home.php: Nếu cấu trúc Theme WordPress không thể tìm thấy front-page.php và “bài đăng mới nhất” được đặt trong phần Display front page, nó sẽ tìm home.php. Ngoài ra, cấu trúc Theme WordPress sẽ tìm kiếm file này khi trang bài viết được đặt trong phần Display front page.
- page.php: Khi page.php (front page) được đặt trong phần Display front page.
- index.php: Khi “bài đăng mới nhất” được đặt trong phần hiển thị trang đầu nhưng home.php không tồn tại hoặc khi trang đầu được đặt nhưng page.php không tồn tại.

### Hiển thị Privacy Policy Page

File template privacy-policy.php được sử dụng để hiển thị Chính sách Bảo mật của website bạn. Mẫu trang Chính sách bảo mật được ưu tiên hơn mẫu trang tĩnh (page.php). Nếu tệp privacy-policy.php không tồn tại, WordPress sẽ sử dụng file page.php hoặc singular.php tùy thuộc vào các template có sẵn. Nếu cả hai file đó đều không tồn tại, nó sẽ sử dụng file index.php.

- privacy-policy.php: Sử dụng cho trang Privacy Policy được đặt trong phần Change your Privacy Policy page của bạn trong Setting > Privacy.
- File template tùy chỉnh: Page template được gán cho trang. Xem get_page_templates ( ).
  page- {slug} .php: Nếu slug của trang là privacy, thì WordPress sẽ sử dụng page-privacy.php.
  page- {id} .php: Nếu ID page là 6, WordPress sẽ sử dụng page-6.php.
  page.php.
- singular.php.
- index.php.

### Single Post

File template của single post được sử dụng để hiển thị một bài đăng. WordPress sử dụng đường dẫn sau:

- single- {post-type} – {slug} .php: WordPress tìm kiếm một template cho bài viết cụ thể. Ví dụ: Nếu loại bài viết là product và slug của bài viết là dmc-12, thì WordPress sẽ tìm kiếm single-product-dmc-12.php.
- single- {post-type} .php: Nếu loại bài viết là product, WordPress sẽ tìm kiếm single-product.php.
- single.php.
- singular.php.
- index.php.

### Single Page

File template được sử dụng để hiển thị một trang tĩnh (loại bài viết của trang). Lưu ý rằng không giống như các loại bài viết khác, trang này đặc biệt đối với WordPress và sử dụng đường dẫn sau:

- File template tùy chỉnh: Mẫu trang được gán cho trang. Xem get_page_templates ().
- page- {slug} .php: Nếu slug của trang là recent-news, WordPress sẽ sử dụng page-recent-news.php.
- page- {id} .php: Nếu ID trang là 6, WordPress sẽ sử dụng page-6.php.
- page.php.
- singular.php.
- index.php.

### Category

Hiển thị các phần danh mục lưu trữ sử dụng đường dẫn sau trong WordPress:

- category- {slug} .php: Nếu slug của danh mục là news, WordPress sẽ tìm kiếm category-news.php.
- category- {id} .php: Nếu ID của danh mục là 6, WordPress sẽ tìm category-6.php.
- category.php.
- archive.php.
- index.php.

### Tag

Để hiển thị trang index lưu trữ tag, WordPress sử dụng đường dẫn sau:

- tag- {slug} .php: Nếu slug của tag là sometag, WordPress sẽ tìm kiếm tag-sometag.php.
- tag- {id} .php: Nếu ID của thẻ là 6, WordPress sẽ tìm kiếm tag-6.php.
- tag.php.
- archive.php.
- index.php.

### Phân loại tùy chỉnh

Các đơn vị phân loại tùy tỉnh sử dụng đường dẫn file template hơi khác một chút:

- taxonomy- {taxonomy} – {term} .php: Nếu taxonomy là sometax và term của taxonomy là someterm, WordPress sẽ tìm kiếm taxonomy-sometax-someterm.php. Trong trường hợp các post format, phân loại là “post_format” và các term là “post-format- {format}. Tức là taxonomy-post_format-post-format-link.php cho định dạng bài đăng liên kết.
- taxonomy- {taxonomy} .php: Nếu phân loại là sometax, WordPress sẽ tìm kiếm taxonomy-sometax.php.
- taxonomy.php.
- archive.php.
- index.php.

### Loại bài đăng tùy chỉnh

Loại bài đăng tùy chỉnh sẽ sử dụng đường dẫn sau để hiển thị trang index để lưu trữ thích hợp.

- archive- {post_type} .php: Nếu loại bài viết là product, WordPress sẽ tìm kiếm archive-product.php.
- archive.php.
- index.php.

### Hiển thị tác giả

Dựa trên các ví dụ trên, việc hiển thị các trang index archive của tác giả cũng khá dễ hiểu:

- author- {nicename} .php: Nếu tên của tác giả là Matt, WordPress sẽ tìm kiếm author-matt.php.
- author- {id} .php: Nếu ID của tác giả là 6, WordPress sẽ tìm author-6.php.
- author.php.
- archive.php.
- index.php.

### Ngày, tháng

- date.php.
- archive.php.
- index.php.

### Kết quả tìm kiếm

- search.php.
- index.php.

### 404 (Not Found)

- 404.php.
- index.php.

### Tệp đính kèm

- {MIME-type} .php: Có thể là bất kỳ MIME type nào (Ví dụ: image.php, video.php, pdf.php). Đường dẫn sau được sử dụng cho text/plain (theo thứ tự): video.phppdf.phptext/plain, text-plain.php, plain.php, text.php.
- attachment.php.
- single-attachment- {slug} .php: Ví dụ: nếu slug của tệp đính kèm là holiday, WordPress sẽ tìm kiếm single-attachment-holiday.php.
- single-attachment.php.
- single.php.
- singular.php.
- index.php.

### Nhúng

File template nhúng được sử dụng để hiển thị một bài đăng đang được nhúng. Kể từ phiên bản 4.5, WordPress sử dụng đường dẫn sau:

- embed- {post-type} – {post_format}.php: Đầu tiên WordPress tìm kiếm một template cho bài viết cụ thể. Ví dụ: Nếu loại bài viết của nó là post và nó có format audio, thì WordPress sẽ tìm kiếm file embed-post-audio.php.
- embed- {post-type} .php: Nếu loại bài viết là product, WordPress sẽ tìm kiếm file embed-product.php.
  embed.php.
- wp-include / theme-compat / embed.php.

### Xử lý ký tự không phải ASCII

Kể từ WordPress 4.7, bất kỳ phần động nào của tên template bao gồm các ký tự không phải ASCII trong tên của nó thực sự hỗ trợ cả dạng un-encoded và encoded. Bạn có thể chọn một trong 2 dạng để sử dụng.

- Dưới đây là phân cấp page template cho một trang có tên “Hello World 😀” với ID là 6:

- page-hello-world-😀.php.
- page-hello-world-%f0%9f%98%80.php.
- page-6.php.
- page.php.
- singular.php.

### Lọc phân cấp

System template WordPress cho phép bạn lọc phân cấp (hierarchy). Điều này có nghĩa là bạn có thể chèn và thay đổi mọi thứ tại các điểm cụ thể của hierarchy. Bộ lọc (nằm trong hàm get_query_template ( )) sử dụng tên bộ lọc này: “{$ type} \_template” trong đó $ type là type template.

Đây là danh sách tất cả các bộ lọc có sẵn trong hierarchy:

- embed_template.
- 404_template.
- search_template.
- frontpage_template.
- home_template.
- privacypolicy_template.
- taxonomy_template.
- attachment_template.
- single_template.
- page_template.
- singular_template.
- category_template.
- tag_template.
- author_template.
- date_template.
- archive_template.
- index_template.

## Nội dung hàm số the_title(), get_the_title() và sự khác nhau giữa chúng

- the_title(): Lấy tiêu đề của bài viết.
- get_the_title(): cần phải thêm “echo” phía trước

## Nội dung hàm số get_stylesheet_directory_uri(), get_stylesheet_directory() và sự khác nhau giữa chúng

- get_stylesheet_directory_uri(): tạo URL
- get_stylesheet_directory(): tạo đường dẫn local file hệ thống
