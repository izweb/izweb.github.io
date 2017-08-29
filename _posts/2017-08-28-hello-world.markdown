> Octopress is an obsessively designed toolkit for writing and deploying Jekyll blogs. Pretty sweet, huh?
– [Octopress](https://github.com/octopress/octopress)

**Octopress** là một ***framework*** design cho Jekyll. Gọi là ***framework*** nghe có hơi to tát - một cách ngắn gọn, **Octopress** là một bộ `template/tools/plugin` giúp cho việc generate static site đơn giản hơn. 

Trong khuôn khổ bài viết này, mình xin hướng dẫn các bạn sử dụng **Octopress** để tạo 1 blog đơn giản, thêm bài viêt, page.

Xong màn dạo đầu... Tiến hành luôn cho nó nóng.

# Cài đặt và sử dụng
**Yêu cầu:**
>Hệ điều hành Linux hoặc Mac OS. 
>Máy cần cài sẵn Ruby, RubyGems, NodeJS (để hộ trợ CoffeeScript, còn không dùng CoffeeScript thì không có cũng được).

Đầu tiên, chúng ta cần cài đặt octopress gem từ Teminal:
```
gem install octopress
```

### Tạo mới project
Tạo một project mới với Octopress CLI commands::
```
octopress new izweb
```
Kết quả thu được sau khi chạy lên trên như thế này là bạn đã thành công:
```
$ cd izweb
$ tree
.
├── 404.html
├── about.md
├── _config.yml
├── Gemfile
├── Gemfile.lock
├── index.md
├── _posts
│   └── 2017-08-28-welcome-to-jekyll.markdown
└── _templates
    ├── draft
    ├── page
    └── post

2 directories, 10 files
```
### Thêm bài viết
Để tạo bài viết mới, các bạn dùng Octopress CLI commands:
```
octopress new post Hello World
```
Comand trên sẽ tạo mới 1 bài viết với tiêu đề`Hello World`và thêm vào thư mục`_posts`file`2017-08-28-hello-world.markdown`với nội dung như sau:
```
$ cat _posts/2017-08-28-hello-world.markdown 
---
layout: post
title: "Hello World"
date: 2017-08-28T16:28:42+07:00
---
```
Mặc định nội dung của bài post được viết dưới dạng [markdown](https://daringfireball.net/projects/markdown/)  file. Nội dung bài post sẽ nằm phía dưới `YAML front matter`  (phần nội dung nằm giữa cú pháp `---`, tại đây bạn cũng có thể đặt được các biến xác định trước và biến tùy chỉnh, chẳng hạn như Categories, Tags và permalink. Chi tiết các bạn tham khảo thêm tại [Jekyll Documentation](http://jekyllrb.com/docs/frontmatter/)).

### View bài viết
Để view được bài viết vừa thêm, trước tiên cần chạy lệnh:
```
$ jekyll build
```
Jekyll sẽ tự động kiểm tra mọi thay đổi trên các file trong project của bạn và build vào trong thư mục`_site`

Bây giờ chúng ta chạy lệnh:
```
$ jekyll serve
```
Access vào địa chỉ [http://127.0.0.1:4000](http://127.0.0.1:4000) bạn sẽ thấy trang web của mình :D

### Tạo page
Khi chạy lệnh `jekyll build`Octopress mặc định tạo ra **About** page tại địa chỉ `http://127.0.0.0:4000/about/`. Các bạn có thể tìm thấy nó trong thư mục `_site/about`
Để tạo page cũng tương tự như tạo post, các bạn sử dụng Octopress CLI commands:
```
$ octopress new page contact.md
```
Thao tác này sẽ tạo một trang mới trong thư mục chính của project. Nội dung file được tạo ra như sau:
```
---
layout: page
title: ""
---
```
Nhập title của page nếu bạn muốn.
Bạn có thể nhập nội dung cho trang bên dưới phần đầu của YAML. Giống như trong trường hợp của bài viết, nội dung được viết bằng định dạng markdown. Bạn cũng có thể chọn một đường dẫn để tạo trang. Ví dụ:
```
$ octopress new page news/index.md
```
Thao tác này sẽ tạo ra một thư mục mới có tên news và một tệp index.md bên trong nó.

> Khi bạn chạy`jekyll build`và`jekyll serve`, tệp .html được tạo ra giống như nội dụng có trong trang "about". F5 web, link tới trang sẽ tự động hiển thị trong navigation bar.


# Kết luận
Trong bài viết này mình đã giới thiệu cơ bản các thao tác đề tạo được 1 blog, thêm bài viết mới, thêm page với `Octopress 3`. Bài viết tiếp theo mình sẽ hướng dẫn các bạn thêm tính năng chia sẻ lên mạng xã hội (Twitter) và deploy lên môi trường production - ở đây chúng ta sẽ dùng `Github Pages` (đối với các bạn chưa biết về `Gihub Pages`.
Hẹn gặp lại ở kỳ sau! Chào thân ái và quyết thắng!

Nguồn: https://github.com/octopress/octopress