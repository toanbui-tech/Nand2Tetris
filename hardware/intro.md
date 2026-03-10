# Phần I: Phần cứng

*"Hành trình khám phá đích thực không nằm ở việc đi đến những vùng đất mới,
mà ở việc có một đôi mắt mới."* – Marcel Proust (1871–1922)

Cuốn sách này là một hành trình khám phá. Bạn sắp học được ba điều:

- Cách các hệ thống máy tính hoạt động  
- Cách chia nhỏ những vấn đề phức tạp thành các mô-đun có thể quản lý được  
- Cách xây dựng các hệ thống phần cứng và phần mềm quy mô lớn

Đây sẽ là một hành trình **thực hành**, nơi bạn tự tay tạo ra một hệ thống máy tính hoàn chỉnh và có thể hoạt động được từ con số 0. Những bài học bạn thu được — vốn quan trọng hơn nhiều so với chính chiếc máy tính — sẽ xuất hiện như **những hệ quả tự nhiên** của quá trình xây dựng này.

Theo nhà tâm lý học Carl Rogers:

> "Kiểu học duy nhất có ảnh hưởng đáng kể đến hành vi là sự học do chính bản thân khám phá hoặc chiếm lĩnh — chân lý đã được hấp thụ thông qua trải nghiệm."

Chương giới thiệu này phác họa sơ lược một số khám phá, chân lý và trải nghiệm đang chờ đợi phía trước.

## Hello, World

Nếu bạn đã từng có kinh nghiệm lập trình, có lẽ bạn đã gặp một chương trình giống như chương trình dưới đây ngay từ những buổi học đầu tiên. Và ngay cả khi chưa từng lập trình, bạn vẫn có thể đoán chương trình này làm gì: nó hiển thị dòng chữ **"Hello World"**, rồi kết thúc.

Chương trình cụ thể dưới đây được viết bằng **Jack** – một ngôn ngữ lập trình cấp cao đơn giản, có cú pháp giống **Java**:

```java
// Ví dụ đầu tiên trong Programming 101:
class Main {
    function void main() {
        do Output.printString("Hello World");
        return;
    }
}
```

Những chương trình đơn giản như **Hello World** thực ra đánh lừa chúng ta vì vẻ ngoài quá đơn giản của chúng. Bạn đã bao giờ dừng lại để nghĩ xem cần những gì để **thực sự chạy được một chương trình như vậy trên máy tính** chưa?

Hãy thử nhìn **bên trong cỗ máy**.

Trước hết, hãy lưu ý rằng chương trình trên thực chất chỉ là **một chuỗi ký tự thông thường**, được lưu trong **một tệp văn bản (text file)**. Nhưng đối với máy tính, dạng biểu diễn này hoàn toàn vô nghĩa, bởi vì máy tính **chỉ hiểu các lệnh được viết bằng ngôn ngữ máy (machine language)**.

Vì vậy, nếu muốn thực thi chương trình này, điều đầu tiên chúng ta phải làm là:

1. **Phân tích (parse)** chuỗi ký tự tạo nên mã nguồn cấp cao  
2. **Xác định ngữ nghĩa (semantics)** của nó – tức là hiểu chương trình muốn làm gì  
3. **Sinh ra mã cấp thấp (low-level code)** diễn đạt lại ngữ nghĩa này bằng **ngôn ngữ máy của máy tính mục tiêu**

Kết quả của quá trình dịch phức tạp này, được gọi là **biên dịch (compilation)**, sẽ là **một chuỗi các lệnh ngôn ngữ máy có thể thực thi được**.

Tất nhiên, **ngôn ngữ máy (machine language)** cũng chỉ là một dạng **trừu tượng** – một tập hợp các mã nhị phân được quy ước. Để biến sự trừu tượng này thành thứ gì đó cụ thể, nó phải được hiện thực hóa bằng **một kiến trúc phần cứng (hardware architecture)**.

Và kiến trúc này, đến lượt nó, được triển khai bằng **một tập hợp các con chip** – như thanh ghi (registers), bộ nhớ (memory units), bộ cộng (adders), v.v.

Mỗi thiết bị phần cứng này lại được xây dựng từ **các cổng logic cơ bản ở mức thấp hơn**. Và các cổng này, tiếp tục được tạo ra từ những **cổng nguyên thủy** như **Nand** và **Nor**.

Những cổng nguyên thủy này nằm rất thấp trong hệ phân cấp, nhưng ngay cả chúng cũng được tạo nên từ **nhiều thiết bị chuyển mạch (switching devices)**, thường được hiện thực bằng **transistor**.

Và mỗi transistor lại được làm từ – à, chúng ta sẽ không đi sâu hơn nữa, bởi vì đó là điểm mà **khoa học máy tính kết thúc và vật lý bắt đầu**.

Bạn có thể đang nghĩ:  
*"Trên máy tính của tôi, việc biên dịch và chạy chương trình dễ hơn nhiều – tôi chỉ cần nhấp vào biểu tượng này hoặc gõ một lệnh nào đó!"*

Đúng vậy. Một hệ thống máy tính hiện đại giống như **một tảng băng trôi chìm dưới nước**, và hầu hết mọi người chỉ nhìn thấy **phần nổi phía trên**.

Kiến thức của họ về hệ thống máy tính thường **mơ hồ và bề mặt**. Tuy nhiên, nếu bạn muốn khám phá **phần nằm dưới bề mặt**, thì **chúc mừng bạn!**

Ở dưới đó là **một thế giới vô cùng hấp dẫn**, được tạo nên từ những ý tưởng đẹp nhất trong khoa học máy tính.

Sự hiểu biết sâu sắc về thế giới ngầm này chính là điều **phân biệt giữa những lập trình viên ngây thơ và những nhà phát triển tinh thông** – những người có khả năng tạo ra các công nghệ phần cứng và phần mềm phức tạp.

Và cách tốt nhất để hiểu cách các công nghệ này hoạt động – hiểu chúng **đến tận trong xương tủy** – chính là **tự tay xây dựng một hệ thống máy tính hoàn chỉnh từ con số 0**.

## Nand to Tetris

Giả sử chúng ta muốn xây dựng một hệ thống máy tính **từ con số 0**, vậy cụ thể chúng ta nên xây dựng **máy tính nào**?

Thực ra, mọi máy tính đa dụng – mọi **PC, smartphone, hay server** – đều có thể xem là một **cỗ máy "Nand to Tetris"**.

Thứ nhất, ở tầng thấp nhất, tất cả các máy tính đều được xây dựng dựa trên **các cổng logic cơ bản**, trong đó **Nand** là loại cổng được sử dụng rộng rãi nhất trong công nghiệp (chúng ta sẽ giải thích chính xác **cổng Nand là gì** trong chương 1).

Thứ hai, mọi máy tính đa dụng đều có thể được **lập trình để chạy trò chơi Tetris**, cũng như bất kỳ chương trình nào khác mà bạn muốn.

Vì vậy, **không có gì đặc biệt** ở bản thân **Nand** hay **Tetris**.

Điều thực sự tạo nên hành trình kỳ diệu của cuốn sách này chính là **từ "to" (đến)** trong cụm **"Nand to Tetris"**.

Nó đại diện cho một hành trình đi **từ một đống các thiết bị chuyển mạch cơ bản** đến **một cỗ máy có thể tương tác với trí óc con người** thông qua:

- văn bản (text)
- đồ họa (graphics)
- hoạt hình (animation)
- âm nhạc (music)
- video
- phân tích (analysis)
- mô phỏng (simulation)
- trí tuệ nhân tạo (artificial intelligence)

và tất cả những khả năng mà chúng ta mong đợi từ **các máy tính đa dụng hiện đại**.

Do đó, thực ra **không quan trọng lắm** việc chúng ta xây dựng **nền tảng phần cứng cụ thể nào** hay **hệ phân cấp phần mềm nào**, miễn là chúng được xây dựng dựa trên **những ý tưởng và kỹ thuật cốt lõi** vốn đặc trưng cho mọi hệ thống máy tính tồn tại ngày nay.

Hình I.1 mô tả các **cột mốc quan trọng** trong lộ trình *Nand to Tetris*.

Bắt đầu từ tầng thấp nhất của hình, mọi máy tính đa dụng đều có một **kiến trúc phần cứng** bao gồm:

- **CPU (Central Processing Unit – bộ xử lý)**
- **RAM (Random Access Memory – bộ nhớ)**

Tất cả các thiết bị CPU và RAM này đều được xây dựng từ **các cổng logic cơ bản**.

Và điều khá bất ngờ nhưng cũng rất may mắn là – như chúng ta sẽ sớm thấy – **tất cả các cổng logic đều có thể được xây dựng chỉ từ các cổng Nand**.

Xét về **hệ phân cấp phần mềm**, mọi ngôn ngữ lập trình cấp cao đều dựa vào một **tập hợp các bộ dịch (translators)** để chuyển mã cấp cao xuống **các lệnh ở mức ngôn ngữ máy**. Các bộ dịch này bao gồm:

- **Compiler / Interpreter**
- **Virtual Machine**
- **Assembler**

Một số ngôn ngữ cấp cao được **thông dịch (interpreted)** thay vì **biên dịch (compiled)**, và một số ngôn ngữ **không sử dụng máy ảo (virtual machine)**, nhưng **bức tranh tổng thể về kiến trúc vẫn cơ bản giống nhau**.

Nhận xét này phản ánh một nguyên lý cơ bản của khoa học máy tính, được gọi là **giả thuyết Church–Turing (Church–Turing conjecture)**:

> Ở tầng bản chất nhất, **mọi máy tính đều tương đương về khả năng tính toán**.

![Hình I.1](public/1.1.png)

Hình I.1: Các mô-đun chính của một hệ thống máy tính điển hình, bao gồm một **nền tảng phần cứng (hardware platform)** và một **hệ phân cấp phần mềm (software hierarchy)**.

Mỗi mô-đun đều có:

- một **cách nhìn trừu tượng (abstract view)** – còn gọi là **giao diện của mô-đun (module interface)**
- và một **phần hiện thực (implementation)**

Các **mũi tên hướng sang phải** cho thấy rằng mỗi mô-đun được **xây dựng bằng cách sử dụng các khối xây dựng trừu tượng (abstract building blocks)** từ **tầng bên dưới**.

Mỗi **hình tròn** trong sơ đồ đại diện cho **một dự án và một chương trong Nand to Tetris** – tổng cộng có **12 dự án và 12 chương**.

Chúng tôi đưa ra những nhận xét này nhằm nhấn mạnh **tính tổng quát của phương pháp tiếp cận** trong cuốn sách. Những thách thức, hiểu biết, mẹo, kỹ thuật và thuật ngữ mà bạn sẽ gặp trong cuốn sách này **chính là những thứ mà các kỹ sư phần cứng và phần mềm chuyên nghiệp phải đối mặt trong thực tế**.

Ở khía cạnh đó, *Nand to Tetris* giống như **một nghi thức nhập môn**: nếu bạn hoàn thành được hành trình này, bạn sẽ có **một nền tảng rất vững chắc để trở thành một chuyên gia máy tính thực thụ**.

Vậy trong *Nand to Tetris*, chúng ta sẽ xây dựng **nền tảng phần cứng nào** và **ngôn ngữ lập trình cấp cao nào**?

Một khả năng là xây dựng **một mô hình máy tính mạnh mẽ đang được sử dụng rộng rãi trong công nghiệp**, và viết **một compiler cho một ngôn ngữ lập trình phổ biến**. Tuy nhiên, chúng tôi đã **không chọn hướng này**, vì ba lý do:

1. **Các mô hình máy tính thay đổi theo thời gian**, và những ngôn ngữ lập trình “hot” cũng sẽ dần bị thay thế bởi những ngôn ngữ mới. Vì vậy, chúng tôi không muốn gắn bó với bất kỳ cấu hình phần cứng/phần mềm cụ thể nào.

2. Các máy tính và ngôn ngữ được sử dụng trong thực tế chứa **rất nhiều chi tiết phức tạp không mang nhiều giá trị giảng dạy**, nhưng lại **tốn rất nhiều thời gian để triển khai**.

3. Chúng tôi muốn tạo ra **một nền tảng phần cứng và một hệ phân cấp phần mềm** có thể **dễ kiểm soát, dễ hiểu và dễ mở rộng**.

Những cân nhắc này đã dẫn đến việc tạo ra:

- **Hack** – nền tảng máy tính được xây dựng trong **Phần I của cuốn sách**
- **Jack** – ngôn ngữ lập trình cấp cao được triển khai trong **Phần II**

Thông thường, các hệ thống máy tính được mô tả theo **cách tiếp cận từ trên xuống (top-down)**, cho thấy cách các **khái niệm trừu tượng cấp cao** có thể được **giảm xuống hoặc hiện thực hóa bằng các thành phần đơn giản hơn**.

Ví dụ, ta có thể mô tả cách **các lệnh máy nhị phân** chạy trên kiến trúc máy tính được **phân tách thành các micro-code**, di chuyển qua các dây dẫn trong kiến trúc và cuối cùng thao tác lên **các chip ALU và RAM ở mức thấp hơn**.

Ngược lại, ta cũng có thể tiếp cận **từ dưới lên (bottom-up)**, mô tả cách **các chip ALU và RAM** được thiết kế cẩn thận để thực thi **các micro-code**, và khi các micro-code này kết hợp lại, chúng tạo thành **các lệnh máy nhị phân**.

Cả hai cách tiếp cận **top-down** và **bottom-up** đều mang lại nhiều hiểu biết, mỗi cách cung cấp **một góc nhìn khác nhau** về hệ thống mà chúng ta sắp xây dựng.

Trong **Hình I.1**, hướng của các mũi tên gợi ý **cách nhìn từ trên xuống (top-down)**. Với bất kỳ cặp mô-đun nào, sẽ có **một mũi tên đi xuống** nối mô-đun cấp cao với mô-đun cấp thấp hơn.

Ý nghĩa của mũi tên này rất cụ thể: **mô-đun cấp cao được hiện thực hóa bằng các khối xây dựng trừu tượng từ tầng bên dưới**.

Ví dụ:

- Một **chương trình cấp cao** được hiện thực bằng cách **dịch mỗi câu lệnh cấp cao** thành một tập hợp **các lệnh VM (Virtual Machine) trừu tượng**.
- Mỗi **lệnh VM** lại tiếp tục được **dịch xuống thành một tập hợp các lệnh ngôn ngữ máy trừu tượng**.

Và quá trình này tiếp tục lặp lại qua các tầng khác nhau.

Sự phân biệt giữa **trừu tượng (abstraction)** và **hiện thực (implementation)** đóng vai trò **rất quan trọng trong thiết kế hệ thống**, và đó là chủ đề mà chúng ta sẽ tiếp tục thảo luận tiếp theo.

## Trừu tượng và Hiện thực (Abstraction and Implementation)

Bạn có thể tự hỏi làm thế nào con người có thể **xây dựng một hệ thống máy tính hoàn chỉnh từ con số 0**, chỉ bắt đầu với những **cổng logic cơ bản**. Điều này hẳn phải là một công việc khổng lồ!

Chúng ta xử lý sự phức tạp này bằng cách **chia hệ thống thành các mô-đun**. Mỗi mô-đun được:

- mô tả riêng trong **một chương riêng biệt**
- và được xây dựng riêng trong **một dự án độc lập**

Bạn có thể tiếp tục thắc mắc: làm sao có thể **mô tả và xây dựng các mô-đun này một cách độc lập**, trong khi rõ ràng chúng có liên quan đến nhau?

Như chúng ta sẽ thấy xuyên suốt cuốn sách, **một thiết kế mô-đun tốt chính là như vậy**:  
bạn có thể **làm việc trên từng mô-đun riêng lẻ**, trong khi **hoàn toàn bỏ qua phần còn lại của hệ thống**.

Thực tế, nếu hệ thống được thiết kế tốt, bạn thậm chí có thể:

- xây dựng các mô-đun **theo bất kỳ thứ tự nào**
- hoặc **xây dựng song song**, nếu làm việc theo nhóm.

Khả năng nhận thức giúp chúng ta **"chia để trị" (divide and conquer)** một hệ thống phức tạp thành các mô-đun dễ quản lý được hỗ trợ bởi một khả năng nhận thức khác: **khả năng phân biệt giữa trừu tượng và hiện thực của mỗi mô-đun**.

Trong khoa học máy tính, hai khái niệm này có ý nghĩa rất cụ thể:

- **Abstraction (trừu tượng)** mô tả *mô-đun làm gì*  
- **Implementation (hiện thực)** mô tả *mô-đun làm điều đó như thế nào*

Với sự phân biệt này trong đầu, ta có **quy tắc quan trọng nhất trong kỹ thuật hệ thống**:

> Khi sử dụng một mô-đun làm **khối xây dựng**, bạn chỉ tập trung vào **trừu tượng của mô-đun**, và **hoàn toàn bỏ qua chi tiết hiện thực của nó**.

---

### Ví dụ

Hãy nhìn vào tầng thấp nhất của **Hình I.1**, bắt đầu từ mức **kiến trúc máy tính (computer architecture)**.

Như hình cho thấy, việc hiện thực kiến trúc này sử dụng nhiều **khối xây dựng từ tầng bên dưới**, trong đó có **RAM (Random Access Memory)**.

RAM là một thiết bị đáng kinh ngạc. Nó có thể chứa **hàng tỷ thanh ghi**, nhưng **bất kỳ thanh ghi nào cũng có thể được truy cập trực tiếp và gần như ngay lập tức**.

Hình I.1 cho thấy rằng **người thiết kế kiến trúc máy tính** nên sử dụng thiết bị truy cập trực tiếp này **ở mức trừu tượng**, **không cần quan tâm đến cách nó được hiện thực bên trong**.

Tất cả công sức, sự thông minh và kịch tính đã đi vào việc xây dựng **phép màu RAM truy cập trực tiếp** – tức là **phần "how"** – cần phải **bị bỏ qua hoàn toàn**, vì thông tin này **không liên quan khi chúng ta chỉ sử dụng RAM vì tác dụng của nó**.

---

### Đi xuống một tầng

Nếu đi xuống **một tầng nữa trong Hình I.1**, chúng ta sẽ ở vị trí **phải thực sự xây dựng chip RAM**.

Chúng ta nên làm điều đó như thế nào?

Theo **mũi tên sang phải**, ta thấy việc hiện thực RAM sẽ dựa trên **các cổng logic cơ bản và các chip từ tầng thấp hơn**.

Cụ thể:

- **khả năng lưu trữ của RAM** sẽ được hiện thực bằng **registers (thanh ghi)**
- **khả năng truy cập trực tiếp** sẽ được hiện thực bằng **multiplexors**

Và một lần nữa, **nguyên lý abstraction–implementation lại được áp dụng**:

Chúng ta sẽ sử dụng các chip này như **những khối xây dựng trừu tượng**, chỉ tập trung vào **giao diện của chúng**, và **không quan tâm đến cách chúng được hiện thực bên trong**.

Và quá trình này **tiếp tục lặp lại**, từng tầng một, **cho đến tận mức cổng Nand**.

## Tóm lại

Bất cứ khi nào phần hiện thực của bạn sử dụng một mô-đun phần cứng hoặc phần mềm ở tầng thấp hơn, bạn nên xem mô-đun đó như **một sản phẩm có sẵn (off-the-shelf)**, một **hộp đen (black box)** ở mức **trừu tượng**.

Điều duy nhất bạn cần là **tài liệu mô tả giao diện của mô-đun**, cho biết **mô-đun có thể làm gì**, và bạn có thể sử dụng nó ngay lập tức.

Bạn **không cần quan tâm chút nào** đến việc **mô-đun thực hiện những gì mà giao diện của nó quảng cáo bằng cách nào**.

Mô hình **abstraction–implementation (trừu tượng–hiện thực)** này giúp các nhà phát triển:

- **quản lý sự phức tạp**
- **giữ được sự tỉnh táo khi xây dựng hệ thống lớn**

Bằng cách chia một hệ thống khổng lồ thành **những mô-đun được định nghĩa rõ ràng**, chúng ta:

- tạo ra **những phần công việc triển khai có thể quản lý được**
- **cô lập việc phát hiện và sửa lỗi**

Nói một cách đơn giản, đây chính là **nguyên lý thiết kế quan trọng nhất trong các dự án xây dựng phần cứng và phần mềm**.

---

Tất nhiên, toàn bộ câu chuyện này phụ thuộc vào **nghệ thuật tinh vi của thiết kế mô-đun (modular design)**:

đó là khả năng của con người trong việc **tách một vấn đề phức tạp thành một tập hợp các mô-đun được định nghĩa rõ ràng và thanh lịch**.

Mỗi mô-đun:

- có **giao diện rõ ràng**
- đại diện cho **một khối công việc triển khai độc lập hợp lý**
- có thể được **kiểm thử riêng bằng unit test**

Thực tế, **thiết kế mô-đun chính là “cơm ăn nước uống” của khoa học máy tính ứng dụng**.

Mọi **kiến trúc sư hệ thống (system architect)** đều thường xuyên:

1. **định nghĩa các trừu tượng** (thường gọi là *modules* hoặc *interfaces*)
2. **hiện thực chúng**, hoặc **giao cho người khác hiện thực**

Các trừu tượng này thường được **xây dựng thành nhiều tầng**, lớp này chồng lên lớp kia, tạo ra **những mức chức năng ngày càng cao hơn**.

Nếu **kiến trúc sư hệ thống thiết kế được một tập hợp mô-đun tốt**, công việc triển khai sẽ **diễn ra trôi chảy như nước chảy**.

Ngược lại, nếu thiết kế **cẩu thả**, việc triển khai gần như **chắc chắn thất bại**.

---

**Thiết kế mô-đun là một nghệ thuật phải học được qua trải nghiệm**, được rèn luyện bằng cách **quan sát và hiện thực nhiều trừu tượng được thiết kế tốt**.

Và đó chính xác là điều bạn sắp trải nghiệm trong **Nand to Tetris**:

- Bạn sẽ học cách **đánh giá vẻ đẹp và chức năng của hàng trăm trừu tượng phần cứng và phần mềm**
- Sau đó bạn sẽ được **hướng dẫn cách hiện thực từng trừu tượng một**

Từng bước một, bạn sẽ **tạo ra những khối chức năng ngày càng lớn hơn**.

Khi tiếp tục hành trình này, từ **chương này sang chương khác**, sẽ rất thú vị khi **nhìn lại và thấy hệ thống máy tính dần dần hình thành từ chính những nỗ lực của bạn**.

## Phương pháp (Methodology)

Hành trình **Nand to Tetris** bao gồm việc xây dựng **một nền tảng phần cứng** và **một hệ phân cấp phần mềm**.

### Phần cứng

Nền tảng phần cứng được xây dựng dựa trên **khoảng 30 cổng logic và chip**, được phát triển trong **Phần I của cuốn sách**.

Mỗi cổng và chip này – bao gồm cả **kiến trúc máy tính hoàn chỉnh ở tầng cao nhất** – sẽ được xây dựng bằng **Hardware Description Language (HDL)**.

Ngôn ngữ HDL mà chúng ta sử dụng được mô tả trong **Phụ lục 2**, và bạn có thể **học nó chỉ trong khoảng một giờ**.

Bạn sẽ kiểm tra tính đúng đắn của các chương trình HDL bằng **một trình mô phỏng phần cứng (hardware simulator)** chạy trên máy tính cá nhân của bạn.

Đây chính xác là cách **các kỹ sư phần cứng làm việc trong thực tế**:

1. Họ **thiết kế và kiểm thử chip bằng các trình mô phỏng phần mềm**.
2. Khi đã hài lòng với hiệu năng mô phỏng của chip, họ **gửi đặc tả (các chương trình HDL)** đến **công ty chế tạo chip**.
3. Sau khi được **tối ưu hóa**, các chương trình HDL trở thành **đầu vào cho các cánh tay robot**, những thiết bị sẽ **xây dựng phần cứng trên silicon**.

---

### Phần mềm

Tiếp tục hành trình **Nand to Tetris**, trong **Phần II của cuốn sách**, chúng ta sẽ xây dựng **một ngăn xếp phần mềm (software stack)** bao gồm:

- **Assembler**
- **Virtual Machine**
- **Compiler**

Các chương trình này có thể được triển khai bằng **bất kỳ ngôn ngữ lập trình cấp cao nào**.

Ngoài ra, chúng ta cũng sẽ xây dựng **một hệ điều hành cơ bản (basic operating system)**, được viết bằng **ngôn ngữ Jack**.

---

### Làm sao có thể hoàn thành trong một khóa học?

Bạn có thể thắc mắc làm thế nào có thể thực hiện **những dự án đầy tham vọng này trong phạm vi một khóa học hoặc một cuốn sách**.

Bên cạnh **thiết kế mô-đun**, bí quyết của chúng tôi là **giảm sự không chắc chắn trong thiết kế xuống mức tối thiểu**.

Chúng tôi sẽ cung cấp **hệ thống hỗ trợ chi tiết (scaffolding)** cho từng dự án, bao gồm:

- **API được mô tả chi tiết**
- **các chương trình khung (skeletal programs)**
- **các script kiểm thử (test scripts)**
- **hướng dẫn triển khai theo từng giai đoạn**

---

### Bộ công cụ Nand to Tetris

Tất cả các công cụ phần mềm cần thiết để hoàn thành **12 dự án (Projects 1–12)** đều có trong **Nand to Tetris software suite**, có thể tải miễn phí tại:

www.nand2tetris.org

Bộ công cụ này bao gồm:

- **Hardware simulator**
- **CPU emulator**
- **VM emulator**
- Các phiên bản thực thi của:
  - **hardware chips**
  - **assembler**
  - **compiler**
  - **operating system**

Sau khi tải bộ phần mềm này về máy tính, **tất cả các công cụ cần thiết sẽ sẵn sàng trong tầm tay của bạn**.

## Con đường phía trước (The Road Ahead)

Hành trình **Nand to Tetris** bao gồm **12 dự án xây dựng phần cứng và phần mềm**.

Hướng phát triển tổng thể của các dự án này, cũng như **mục lục của cuốn sách**, cho thấy một hành trình **từ dưới lên (bottom-up)**: chúng ta bắt đầu từ **các cổng logic cơ bản**, rồi dần dần đi lên cho đến **một ngôn ngữ lập trình cấp cao hướng đối tượng**.

Tuy nhiên, **bên trong mỗi dự án**, quá trình phát triển lại diễn ra theo hướng **từ trên xuống (top-down)**.

Cụ thể, mỗi khi chúng ta giới thiệu **một mô-đun phần cứng hoặc phần mềm**, chúng ta sẽ luôn:

1. Bắt đầu bằng **mô tả trừu tượng** về **mô-đun làm gì** và **tại sao nó cần thiết**
2. Sau khi bạn hiểu rõ **trừu tượng của mô-đun** (một thế giới phong phú tự nó), bạn sẽ **tiến hành hiện thực mô-đun đó**, sử dụng các **khối xây dựng trừu tượng từ tầng bên dưới**

---

## Kế hoạch tổng thể của Phần I

Đây là kế hoạch tổng thể của **Phần I** trong hành trình của chúng ta:

### Chương 1
Chúng ta bắt đầu với **một cổng logic duy nhất – Nand**.

Từ đó, chúng ta xây dựng **một tập hợp các cổng logic cơ bản và phổ biến**, như:

- And
- Or
- Xor
- và nhiều cổng khác

---

### Chương 2 và 3

Chúng ta sử dụng các khối xây dựng này để tạo ra:

- **Chương 2:** **Arithmetic Logic Unit (ALU)**
- **Chương 3:** **các thiết bị bộ nhớ**

---

### Chương 4

Chúng ta **tạm dừng hành trình xây dựng phần cứng**, và giới thiệu **một ngôn ngữ máy cấp thấp**, ở hai dạng:

- **dạng ký hiệu (symbolic)**
- **dạng nhị phân (binary)**

---

### Chương 5

Chúng ta sử dụng **ALU và các đơn vị bộ nhớ đã xây dựng trước đó** để tạo ra:

- **Central Processing Unit (CPU)**
- **Random Access Memory (RAM)**

Sau đó, các thiết bị này sẽ được **tích hợp thành một nền tảng phần cứng hoàn chỉnh**, có khả năng **chạy các chương trình viết bằng ngôn ngữ máy đã giới thiệu ở chương 4**.

---

### Chương 6

Chúng ta sẽ mô tả và xây dựng **Assembler** – một chương trình có nhiệm vụ:

- **dịch các chương trình viết bằng ngôn ngữ máy ký hiệu**
- thành **mã nhị phân có thể thực thi**

Sau bước này, **nền tảng phần cứng sẽ hoàn thành**.

---

## Bước sang Phần II

Nền tảng phần cứng này sẽ trở thành **điểm xuất phát cho Phần II của cuốn sách**, nơi chúng ta sẽ mở rộng phần cứng cơ bản này bằng **một hệ phân cấp phần mềm hiện đại**, bao gồm:

- **Virtual Machine**
- **Compiler**
- **Operating System**

---

Chúng tôi hy vọng rằng phần giới thiệu này đã giúp bạn hình dung **những gì đang chờ phía trước**, và rằng bạn **đang háo hức bắt đầu hành trình khám phá vĩ đại này**.

Vậy nếu bạn đã **sẵn sàng**, hãy bắt đầu đếm ngược:

3…  
2…  
1…  
0…  

**Go!**