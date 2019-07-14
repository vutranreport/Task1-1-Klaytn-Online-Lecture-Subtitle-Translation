4. Phát triển thêm một game bằng bộ công cụ của Klaytn
4.1 Giới thiệu

Chào mọi người. Trong hướng dẫn này, tôi sẽ cố gắng phát triển BApp được gọi là một trò chơi bổ sung đơn giản bằng cách sử dụng blockchain Klaytn. Để tham khảo, BApp là từ viết tắt của Ứng dụng Blockchain (Blockchain Application). Hãy tạo một trò chơi pop-up đơn giản, sẽ trả 0,1 Klay miễn phí nếu bạn giải quyết vấn đề bổ sung trong 3 giây.

Hãy xem cách nó hoạt động. Đầu tiên, đăng nhập vào tài khoản người điều hành. Chúng ta sẽ xác minh tài khoản bằng cách sử dụng kết hợp tệp kho khóa và mật khẩu. Vì vậy, chọn tệp kho khóa và nhập mật khẩu. Sau khi tài khoản được xác minh, hãy sử dụng nút Gửi KLAY đến Hợp đồng để đặt tổng số tiền sẽ được sử dụng cho sự kiện này. Lý do chúng ta gửi KLAY đến địa chỉ hợp đồng là để cho người dùng thấy số tiền sẽ được sử dụng cho sự kiện này một cách minh bạch. Lưu ý rằng điều này chỉ có thể được thực hiện với tài khoản nhà điều hành.

Tôi đang gửi nó cho hợp đồng bây giờ. Tôi gửi khoảng 1 KLAY. Sau khi giao dịch hoàn tất, người dùng sẽ được hiển thị số tiền phải chi cho sự kiện. Như thế này. Bây giờ người dùng có thể bắt đầu trò chơi bổ sung. Nếu bạn đặt nó trong 3 giây, 0,1 KLAY sẽ được gửi đến tài khoản người dùng từ hợp đồng. Băt đâu nào. Nếu giải pháp sai trong khi thực hiện việc này, nó sẽ được đặt lại. Nếu bạn thử lại và nếu bạn giải quyết được, bạn có thể nhận được KLAY bằng cách nhấn nút OK. Khi giao dịch hoàn thành, số dư giảm 0,1 trong hợp đồng. Như bạn có thể thấy, xử lý giao dịch rất nhanh. Nó có một điểm mạnh của Klaytn. Nếu bạn nhấp vào liên kết bên dưới, nó sẽ đưa bạn đến phạm vi Klaytn nơi bạn có thể xem thông tin của giao dịch vừa tạo.

Nếu bạn có kinh nghiệm phát triển Ethereum DApp, khóa học sắp tới sẽ khá dễ dàng cho bạn. Klaytn là một nền tảng được phân tách từ các phiên bản Byzantine của Ethereum, vì vậy bạn sẽ cảm thấy quen thuộc theo nhiều phương diện. Ví dụ: thư viện JavaScript, caver.js, có thể giao tiếp với blockchain Klaytn, tương tự như Ethereum của web3.js. Ngoài ra, chúng ta hỗ trợ ngôn ngữ Solidity được sử dụng phổ biến nhất để phát triển hợp đồng thông minh.

Bởi vì nó sử dụng bộ framework Truffle, bạn có thể nhanh chóng thích nghi với sự phát triển của BApp. Những người không có kinh nghiệm phát triển BApp có thể phát triển BApp trong nền tảng blockchain Klaytn với bài tập này. Nhưng trước hết, thật tốt khi hiểu blockchain cơ bản và Solidity - một ngôn ngữ phát triển hợp đồng thông minh. Tôi đặt một liên kết để tìm hiểu. Vâng, chúng ta sẽ phát triển với một số công cụ hỗ trợ Klaytn, Đầu tiên, tôi sử dụng một IDE có thể kiểm tra sự phát triển thông minh, một ví có thể quản lý tài khoản. và Klaytn Scope, một công cụ tìm kiếm để tìm thông tin giao dịch.


4.2 Ví Klaytn Wallet & quản lý tài khoản

Để sử dụng mạng blockchain, bạn phải có tài khoản của riêng bạn. Bạn cần có tài khoản ngân hàng để quản lý mã thông báo (token) KLAY của bạn. Vì vậy, tôi sẽ sử dụng Ví từ Klaytn. Nó thân thiện với người dùng và rất dễ sử dụng. 

https://baobab.klaytnwallet.com/

Nếu bạn đến địa chỉ này, bạn có thể kết nối với mạng Baobab để tạo và quản lý tài khoản của bạn. Để bạn tham khảo, Ví này dành cho mục đích thử nghiệm và token Klay được sử dụng ở đây không có giá trị tiền tệ. Đầu tiên, hãy tạo một tài khoản mới. Nhấp vào Tạo ví mới. Nó là một quá trình tạo mật khẩu và tệp Keystore (kho khóa). Trước đó, tôi sẽ giải thích tập tin Keystore là gì. Nó giống như chúng ta hiện đang trong quá trình đến ngân hàng để làm một cuốn sổ ngân hàng và đặt cuốn sổ ngân hàng này vào nơi an toàn để những người khác không thể sử dụng nó. Vault này là một tổ hợp mật khẩu và tệp kho khóa, bảo vệ khóa bí mật cần thiết để ký xác thực giao dịch khỏi tin tặc (hacker) và các cuộc xâm nhập từ bên ngoài.

Bây giờ, hãy tiếp tục và tạo một tệp kho khóa. Nhập mật khẩu của bạn vào đây, nhấp vào bước tiếp theo và tải xuống tệp kho khóa. Tải xuống, sau đó tôi sẽ nói với màn hình tiếp theo của tôi để lưu khóa bí mật của tôi ở đâu đó. Khóa bí mật ở đây là một yêu cầu thiết yếu để ký một giao dịch trong BApp trên Klaytn. Chìa khóa bí mật này không bao giờ được lộ ra bên ngoài. Một khi lộ ra, nó giống như việc mất mật khẩu ngân hàng và sổ tiết kiệm của tôi và mất tất cả tiền.

Đó là lý do tại sao tôi tạo một tệp kho khóa để bảo vệ khóa bí mật của mình. Phải biết tệp kho khóa và mật khẩu lưu trữ khóa trước khi truy cập khóa bí mật. Ngay cả khi tin tặc có được tệp kho khóa, khóa bí mật không thể truy cập được nếu không có mật khẩu. Vì vậy, hacker không thể lấy được tiền. Điều đó không có nghĩa là bạn có thể dễ dàng để lộ kho khóa. Đừng để nó ra bên ngoài. Bây giờ tôi sẽ lưu khóa bí mật này trong Notepad. Bạn không được làm điều này ,, nhưng nó chỉ là một mạng thử nghiệm và tôi sẽ làm nó cho thuận tiện ngay bây giờ. Bạn có thể lưu khóa riêng của mình ở nơi bạn cảm thấy an toàn. Khi bạn đã lưu, nhấp vào xem thông tin ví bên trái. Bây giờ tôi có thể truy cập vào ví của mình. Có hai cách để tiếp cận nó. Đầu tiên là sử dụng khóa bí mật và thứ hai là truy cập vào tệp và mật khẩu của kho khóa. Đầu tiên, hãy truy cập nó bằng khóa bí mật. Sao chép và dán nó trong Notepad.

Thông tin Ví của tôi hiện có sẵn. Đây là địa chỉ công khai tài khoản của tôi và khóa bí mật của tôi dưới đây. Tôi có thể xem danh sách giao dịch của tôi. Tôi không phải để tâm tới điều này vì tôi chưa tạo giao dịch. Ở bên phải, tôi có thể thấy tôi có bao nhiêu KLAY và tôi cũng có thể thêm token vào Ví của mình bằng cách nhấp vào nút dấu cộng. 

Bây giờ, hãy lấy KLAY trên tài khoản của tôi. Nhấp vào tab van KLAY để nhận klay miễn phí. Địa chỉ tài khoản hiện tại của tôi có số dư bằng không. Nếu bạn nhấn nút Run van, bạn sẽ nhận được 5 KLAY. Khi bạn nhận được nó, bạn có thể nhận lại lần nữa sau 24 giờ. Vì bạn không thể nhận được nhiều KLAY trong một thời gian ngắn, bạn nên chia KLAY càng nhiều càng tốt khi thử nghiệm. Lý do chúng ta chỉ cho phép được nhận sau 24 giờ là vì một số người đã sử dụng các token KLAY này cho mục đích xấu. Klaytn nói rằng họ đang đối phó với gian lận, vì vậy sẽ tốt hơn. Bây giờ, hãy chuyển KLAY sang tài khoản khác.

Nếu bạn đi đến tab Gửi klay & token, bạn có thể gửi tiền từ địa chỉ của tôi đến địa chỉ khác. Nhập địa chỉ người nhận. Tôi sẽ gửi một KLAY ở phía dưới để quyết định chi bao nhiêu. Nó nói rằng 0,000625 KLAY sẽ đi ra ngoài với giới hạn phí giao dịch dưới đây. Nó giống như trả tiền hoa hồng. Làm thế nào chi phí này được đo bằng giá gas (xăng) nhân với gas limit. Bạn có thể nghĩ về giá gas là tiền trả cho việc yêu cầu giao dịch đến nút đồng thuận. Giá gas của Klaytn luôn cố định, không giống như Ethereum. Rất khó để dự đoán tổng chi phí hoa hồng vì giá gas của Ethereum đang dao động. Tuy nhiên, giá gas của Klaytn luôn cố định ở mức 25 ston, bất kể bạn xử lý giao dịch nào.

Gas limit là chi phí tối đa của gas đối với với giao dịch này. Ví dụ: giả sử chúng ta có một số vòng lặp vô hạn trong giao dịch này mà chúng ta đang gửi. Sau đó, giao dịch đơn giản này sẽ tiếp tục chạy trong mạng lưới. Điều này gây ra sự suy giảm hiệu suất của mạng. Bạn không nên làm ảnh hưởng đến tất cả mọi người. Vì vậy, nếu bạn có hơn 25.000 gas, Klaytn nghĩ rằng có gì đó lạ và nó sẽ ngừng xử lý.
Và tôi đã nói giá gas là 25 test_ston, ston là một trong những đơn vị tiền tệ của KLAY. Giống như một đô la ở Hoa Kỳ là 100 xu, có rất nhiều đơn vị KLAY. 

https://docs.klaytn.com/klaytn/design/computing/exec_model 

Tài liệu chính thức của Klaytn hiển thị các đơn vị KLAY. Có nhiều thứ. Có một đơn vị KLAY tiêu chuẩn ở giữa và peb ở trên cùng là đơn vị tối thiểu đại diện cho KLAY. Đơn vị được sử dụng cho vòng 10 của peb là ston. Vì vậy, 25 ston sẽ được chuyển đổi thành klay là gì?

https://blockchains.tools/pebConverter?l=KLAY 

Nếu bạn đến trang web này, bạn sẽ chuyển đổi nhiều đơn vị. Nếu bạn đặt 25 trên ston, hãy xem chúng ta nhận được bao nhiêu KLAY. Nếu giới hạn khí 25000 được nhân với điều này, 0,000625 KLAY sẽ xuất hiện. Nó được sử dụng như một khoản phí giao dịch. Hãy thử nó với một máy tính. Nếu bạn sao chép nó và nhân nó với gas limit là 25000, chi phí giao dịch sẽ xuất hiện. Đây là chi phí xử lý giao dịch.
Lưu ý rằng khi bạn gửi các khoản chuyển tiền đơn giản này từ Klaytn, chi phí giao dịch luôn được cố định ở mức 0,000625 KLAY. Tuy nhiên, chi phí giao dịch không cố định trong giao dịch thông qua chức năng hợp đồng thông minh vì giới hạn gas thay đổi theo mức độ phức tạp của giao dịch. Tôi sẽ giải thích thêm về điều này sau.Bạn có thể tự thay đổi giá bằng cách nhấp vào nút Chỉnh sửa (Edit) bên cạnh. Nhưng tôi khuyên bạn nên tiến hành cài đặt mặc định. Hãy thử gửi giao dịch ngay bây giờ. Trên trang tiếp theo, bạn sẽ thấy thông tin về số tiền bạn gửi cho ai đó và chi phí giao dịch sẽ đi là bao nhiêu. Nhấp vào có cho câu hỏi Bạn có muốn tiếp tục không? Sau đó, giao dịch được hoàn thành trong chớp mắt. Sau đó nhấp vào xem thông tin giao dịch và nội dung chúng ta gửi cho bạn sẽ được lưu trong khối và hiển thị cho người dùng. Tôi sẽ giải thích điều này sau chi tiết hơn. Cho đến bước này, tôi đã sử dụng Ví Klaytn.


4.3 Klaytn IDE & Hợp đồng thông minh 1

Với IDE do Klaytn cung cấp, hãy tạo một hợp đồng thông minh đơn giản cho trò chơi bổ trợ của chúng ta. Thay vì tập trung vào các hợp đồng thông minh, tôi sẽ tập trung vào các công cụ Klaytn. Bạn có thể tạo và kiểm tra hợp đồng thông minh bằng cách truy cập 

http://ide.klaytn.net/. 

Nó tương tự như IDE phối lại của Ethereum, nhưng ở đây, nó được sử dụng để kết nối với nút Klaytn, chứ không phải với nút Ethereum. Bây giờ, hãy xem các tính năng của IDE Klaytn bằng cách tạo các hợp đồng thông minh của riêng chúng ta cho các trò chơi bổ trợ của chúng ta.

Để tham khảo, một hợp đồng thông minh được gọi là hợp đồng thông minh bằng tiếng Anh. Tôi sẽ gọi nó là “Hợp đồng” trong bài giảng của tôi. Nếu bạn nhìn vào đây, bạn đã có một hợp đồng đếm được tạo theo mặc định. Tôi sẽ xóa cái này và bắt đầu. Làm ơn xóa nó. Và như bạn có thể thấy trong các bình luận ở trên cùng, Klaytn IDE viết trên phiên bản Solidity 0.4.24, vì vậy bạn phải tiếp tục với phiên bản này.

Hợp đồng của chúng ta có ba chức năng. Đầu tiên là gửi KLAY vào hợp đồng, lần thứ hai để tải số dư của hợp đồng và cuối cùng là chức năng gửi KLAY từ hợp đồng đến tài khoản người dùng. Chúng ta sẽ làm từng cái một và sử dụng các công cụ để kiểm tra nó. Đầu tiên, hãy đặt tên hợp đồng là trò chơi AdditionGame, Contract Edition. 
(Mã) Tại thời điểm triển khai, bạn tạo một biến trạng thái có thể lưu trữ địa chỉ của tài khoản nhà điều hành. Và tôi đang tạo ra một nhà xây dựng. Trước đó, các nhà xây dựng thường làm gì? Vâng. Nó chủ yếu chịu trách nhiệm cho việc khởi tạo. Trong trường hợp Solidity, bạn không thể viết hoặc tải lại hàm tạo, đặc biệt vì nó là hàm tạo được tải lần đầu tiên khi bạn triển khai. Tôi có thể tận dụng điều này và thiết lập một tài khoản cho chủ sở hữu của hợp đồng. Đầu tiên, chúng ta tạo chủ sở hữu biến trạng thái. Loại là một loại địa chỉ. 

Tôi đang xây dựng một nhà xây dựng. Chủ sở hữu là tin nhắn. Người gửi. 

(Mã) Tôi vừa tạo một constructor. dir.sender là người hiện đang gọi hợp đồng này. Msg.sender trong hàm tạo có nghĩa là tài khoản đang được sử dụng để triển khai. Vì vậy, tôi sẽ gán tài khoản đó cho biến trạng thái chủ sở hữu và ghi lại nó vào blockchain mãi mãi. Đây là sự khởi đầu. Vì vậy, hãy kiểm tra mã chúng tôi vừa thêm. Bạn cần biên dịch trước. Nhấp vào hộp kiểm Tự động ở đầu bảng bên phải để tự động biên dịch mỗi khi bạn viết mã. Đầu tiên, bạn phải bấm vào nút biên dịch để xem nó có biên dịch không. Có, thông tin tổng hợp ở phía dưới. 

Hãy thiết lập lại môi trường. Môi trường Có một số tùy chọn để lựa chọn: DEV NODE và Baobab. Và tôi có thể thêm một mạng mới. Chức năng Thêm mạng mới kết nối với địa chỉ RPC nơi nút Klaytn hiện đang chạy và kiểm tra nó. Tôi sẽ bỏ qua phần này bây giờ. Nút dev là một tùy chọn để kết nối và kiểm tra nút phát triển được cung cấp bởi Klaytn. Nó tạo một tài khoản ngẫu nhiên và cho phép bạn đặt hàng trước 100 KLAY. Và nó được thiết lập để hết xăng để thử nghiệm. Vì vậy, nếu bạn thấy Từ Tài khoản bên dưới, đã có 100 KLAY thử nghiệm trong tài khoản này. Tùy chọn kết nối với Baobab cũng được kết nối với mạng thử nghiệm chính thức. Và thời điểm bạn chọn Baobab, KLAY trong tài khoản bên dưới thay đổi thành không. Các nút dev và nút baobab hoạt động độc lập với nhau, vì vậy các tài khoản tại cùng một địa chỉ được nhận dạng bởi nhau, nhưng trạng thái của tài khoản khác nhau vì các nút khác nhau. Vì vậy, sự cân bằng sẽ thay đổi.

Hãy thử làm mới trang với nút Dev được chọn lại. Tiếp theo, để Tải tài khoản, không có tài khoản nào tôi đã sử dụng trước đây và tôi tạo một tài khoản mới khác. Điều thú vị là bạn có thể tải xuống tài khoản này dưới dạng tệp kho khóa riêng hoặc khóa bí mật và sử dụng lại. Nếu bạn đang thử nghiệm trên một máy tính khác, bạn có thể muốn tiếp tục với tài khoản bạn đã sử dụng. Bạn có thể sử dụng tùy chọn này tại thời điểm đó. Ví dụ: nếu bạn nhấp vào tài khoản, bạn có tài khoản hiện tại dự phòng. Khi bạn chọn nó, một cửa sổ sẽ mở ra và bạn có tùy chọn nhận kho khóa hoặc khóa bí mật của mình. Đơn giản chỉ cần sao lưu chìa khóa bí mật của bạn. Khi bạn nhấp vào Sao chép vào bảng tạm, bạn đã sao lưu khóa bí mật cho tài khoản này.

Sau đó làm mới trang một lần nữa (Refresh). Khi tài khoản được tạo, nhấp lại và chọn tùy chọn nhập tài khoản. Chuyển đến tab Khóa riêng và dán khóa bí mật đã sao lưu. Nhãn hiển thị sẽ được gọi là tài khoản thử nghiệm. Nhập khẩu. Nếu bạn chọn lại tài khoản, bạn sẽ có tài khoản thử nghiệm mà chúng tôi đã nhập bên dưới. Vì vậy, khi bạn quay lại trang này theo cách này hoặc trên một máy tính khác, bạn có thể thực hiện kiểm tra một cách nhất quán.

Thay vì giải thích Giá trị Tx, tôi sẽ cố gắng triển khai nó trước. Triển khai. Sau khi bạn nhấp vào nút biên dịch, bạn có tùy chọn triển khai AdditionGame của chúng tôi. Nhấn vào triển khai. Sau đó, việc triển khai đã hoàn thành trong vòng chưa đầy 3 giây. Có một băm TX trong bảng giữa, phải không? Đây là thông tin băm giao dịch được tạo ra bởi việc triển khai. Trên hết, nó cho thấy địa chỉ hợp đồng nào đã được triển khai.

Nếu bạn nhìn vào bảng điều khiển bên cạnh nó, bạn sẽ thấy địa chỉ nào hiện đang có hợp đồng được triển khai và bên dưới bạn có tùy chọn tải giá trị của biến trạng thái chủ sở hữu. Đây là một chức năng getter. Vì chúng tôi đã khai báo mức độ hiển thị của công khai chủ sở hữu biến trạng thái, chúng tôi có thể tự động tạo ra một hàm getter để lấy giá trị của biến chủ sở hữu. Khi bạn nhấn nút Gọi, địa chỉ bên dưới sẽ xuất hiện. Địa chỉ này là gì?

Có, đây là địa chỉ tài khoản của người đã triển khai Hợp đồng này. Tôi đã triển khai hợp đồng với tài khoản hiển thị trong tài khoản từ tài khoản, vì vậy tài khoản này được lưu dưới dạng giá trị của chủ sở hữu biến trạng thái. Có, tôi đã viết mã vững chắc thông qua IDE Klaytn và đã kiểm tra chủ sở hữu hợp đồng. Tiếp theo, chúng ta sẽ viết và kiểm tra hai hàm còn lại trong lớp tiếp theo.

---------------- to be updated later -------------------------
