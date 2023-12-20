Định nghĩa:
  - Gitignore là file có tên là .gitignore do Git quy định. 
  - Nhiệm vụ của nó là liệt kê những file mà mình không mong muốn cho vào git hoặc hiểu nôm na là Git sẽ bỏ qua những file đó đi. 
  - Gitignore hiện nay rất quan trọng trong team work, nên áp dụng ngay vào quy trình làm việc của team.

Cách thức hoạt động:
  - Có thể hiểu đơn giản là git sẽ bỏ qua file hoặc một tập các file trong project của chúng ta khi commit và push lên repository. Ví dụ:
    + Các file mà IDE tự sinh ra trong quá trình build project -> Tránh tốn kém tài nguyên server lưu trữ project.
    + Các file cấu hình đường dẫn của máy cá nhân -> Gây ra việc không build được project khi checkout về ở các máy thành viên khác.
    + Các file cần phải giữ kín nếu như repository của bạn đang để public.
      . . . . .
  - Git quản lý các file mà chúng ta muốn “ignore” bằng file .gitignore được đặt ở trong thư mục root project.
  - Khi add 1 file mới vào git, git sẽ kiểm tra danh sách những file sẽ bỏ qua trong file .gitignore và không add chúng vào git. 
  - Đó mới chỉ là điều kiện cần, điều kiện đủ là files không có trong git cache nữa thì git nó mới bỏ qua, chứ files mà nằm trong git cache thì .gitignore sẽ vô tác dụng.
    
Cú pháp:
  - Để Gitignore có thể nhận dạng chuẩn xác được những File bạn cần bỏ qua đòi hỏi cú pháp phải thật chuẩn.
  - Trong Git Ignore Folder không tồn tại cú pháp trống bởi file nào cũng chứa phần trống. Vì thế tác dụng của nó chỉ là phần cách cho dễ đọc thôi.
  - Nếu muốn add thêm chú thích vào cú pháp, bạn có thể dùng # để mở đầu bình luận đó.
  - Dấu gạch chéo “/” phải được đặt ở cuối cú pháp. Như vậy thì nó mới được nhận định là một Gitignore. Nếu không nó có thể được đọc là một file thường hoặc một symbolic link.
  - Dấu chấm than “!” có nghĩa là phủ định. Do vậy nên nếu bạn thêm ! vào trước một file, nó sẽ không bị bỏ qua nữa mà được thêm vào lại. Tuy nhiên nếu một folder lớn đã bị
     bỏ qua thì cho dù có thêm ! vào các thư mục con ở trong nó thì cũng không thể được thêm vào lại.
  - Hai dấu sao đúp “**” được dùng cho trường hợp không muốn hoặc không thể định rõ tên. Ví dụ nếu bạn sử dụng cú pháp **/abc, nó sẽ có hiệu lực với tất cả các file có chứa
      abc trong tên. Còn nếu bạn sử dụng dạng abc/** thì nó sẽ có hiệu lực với tất cả các tệp con trong thư mục abc.
