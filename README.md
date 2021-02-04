# Json2T - Đọc json chưa bao giờ đơn giản đến thế

## Cấu trúc:

### Constructor
- (String json): void -> json là chuỗi json cần parse
- (Object object): void -> object được parse từ JSONValue.parse(String json): Object

### Method

#### Static Method:
- parse(String json): Json2T -> json là chuỗi json cần parse
- parse(Object object): Json2T -> object được parse từ JSONValue.parse(String json): Object

#### Callback:
- k(String key): Json2T -> key là key muốn get value trong json
- i(int index): Json2T -> vị trí muốn lấy trong 1 mảng
- q(String query): Json2T -> đọc json nhanh như javascript

#### Lấy giá trị:
- toStr(): String -> trả về chuỗi giá trị
- toObj(): Object -> lấy object giá trị
- toInt(): int -> trả về giá trị kiểu int (không thể ép kiểu trả về -1)
- toDouble(): double -> trả về giá trị kiểu double (không thể ép kiểu trả về -1)
- length(): int -> lấy độ dài của mảng, trả về -1 nếu là Object hoặc Null

#### Lấy mảng giá trị:
- toPairObjs(): Json2T[][] -> trả về mảng 2 chiều trong đó [i][0] lày key, và [i][1] là value
- toObjs(): Json2T[] -> trả về mảng đối tượng Json2T
- toStrs(): String[] -> trả về mảng chuỗi 
- toInts(): int[] -> trả về mảng int (không thể ép kiểu trả về -1)
- toDoubles(): double[] -> trả về mảng double (không thể ép kiểu trả về -1)


## Hướng dẫn:
- xem ExampleJson2T.java trong src

## Lưu ý:
- tốc độ code và đọc dữ liệu thì q(String query) nhanh hơn dùng k(String query) và i(String query)
- không tìm thấy key hoặc index sẽ trả về Null
- bất cứ lỗi nào sảy ra sẽ trả về Null

## Cập nhật:

#### v1.0.3.1:
- fix lại function q(String query):Json2T đọc mảng đầu không lỗi

#### v1.0.3:
- thêm function q(String query):Json2T => đọc json nhanh hơn người yêu cũ trở mặt
- đổi function key(String key):Json2T => k(String key):Json2T
- đổi function index(String index): Json2T => i(String index):Json2T

#### v1.0.2:
- bỏ variable length:int thay bằng function length():int 
- bỏ toJsonStr() (sử dụng toStr() hoặc toString() thay thế)
- cập nhật lại source

#### v1.0.1:
- thêm biến length: int để kiểm tra độ dài mảng
- fix lại 1 số hàm cho gọn nhẹ

#### v1.0.0: 
- ra mắt Json2T

## Thông tin:
- Tên: Json2T
- Tác giả: Thiên Đẹp Zaii ( SystemError )
- Phiên bản: 1.0.3
- Thư viện sử dụng: JSON SIMPLE
- Phiên bản thư viện: 1.1.1