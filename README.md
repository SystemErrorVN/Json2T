# Json2T - Đọc json nhanh như người yêu cũ trở mặt!

## Cấu trúc:

### Constructor
- `(String json): void` -> json là chuỗi json cần parse
- `(Object object): void` -> object được parse từ `JSONValue.parse(String json): Object`

### Method

#### Static Method:
- `parse(String json): Json2T` -> json là chuỗi json cần parse
- `parse(Object object): Json2T` -> object được parse từ `JSONValue.parse(String json): Object`

#### Callback:
- `k(String key): Json2T` -> key là key muốn get value trong json
- `i(int index): Json2T` -> vị trí muốn lấy trong 1 mảng
- `q(String query): Json2T` -> query là chuỗi truy cập object như javascript (query="" tương đương this)
- `min(): Json2T` -> lấy giá trị nhỏ nhất trong mảng (ép về `giá trị`)
- `max(): Json2T` -> lấy giá trị lớn nhất trong mảng (ép về `giá trị`)
- `reverse(): Json2T` -> trả về mảng số đảo ngược (ép về `mảng giá trị`)
- `sum(): Json2T` -> trả về tổng các phần tử trong mảng (ép về `giá trị`)
- `avg(): Json2T` -> trả về trung bình cộng các phần tử trong mảng (ép về `giá trị`)

#### Lấy giá trị:
- `toObj(): Object` -> lấy object giá trị
- `toStr(): String` -> trả về chuỗi giá trị
- `toChar(): char` -> trả về kiểu kí tự (có lỗi sảy ra trả về (`0`))
- `toInt(): int` -> trả về giá trị kiểu int (không thể ép kiểu trả về 0)
- `toLong(): long` -> trả về giá trị kiểu long (không thể ép kiểu trả về 0)
- `toDouble(): double` -> trả về giá trị kiểu double (không thể ép kiểu trả về 0)
- `toFloat(): float` -> trả về giá trị kiểu float (không thể ép kiểu trả về 0)
- `length(): int` -> lấy độ dài của mảng, trả về -1 nếu là Object hoặc Null

#### Lấy mảng giá trị:
- `toPairObjs(): Json2T[][]` -> trả về mảng 2 chiều trong đó `[i][0]` lày key, và `[i][1]` là value
- `toKeys(): String[]` -> lấy mảng key trong json (tương đương `[i][0]` trong `toPairObjs():Json2T[][]` nhưng là chuỗi)
- `toValues(): Json2T[]` -> lấy mảng value trong json (tương đương `[i][1]` trong `toPairObjs():Json2T[][]`)
- `toObjs(): Json2T[]` -> trả về mảng đối tượng Json2T
- `toStrs(): String[]` -> trả về mảng chuỗi 
- `toChars(): char[]` -> trả về mảng kí tự (có lỗi sảy ra trả về (`_`))
- `toInts(): int[]` -> trả về mảng int (không thể ép kiểu trả về 0)
- `toLongs(): long[]` -> trả về mảng long (không thể ép kiểu trả về 0)
- `toDoubles(): double[]` -> trả về mảng double (không thể ép kiểu trả về 0)
- `toFloats(): float[]` -> trả về mảng float (không thể ép kiểu trả về 0)


## Hướng dẫn:
- xem `ExampleJson2T.java` trong src

## Lưu ý:
- tốc độ code và đọc dữ liệu thì callback `q` nhanh hơn dùng callback `k` và `i`
- nếu lấy giá trị ở xa hãy dùng callback `q`, ngược lại dùng callback `k` và `i`
- không tìm thấy key hoặc index sẽ trả về Null
- bất cứ lỗi nào sảy ra sẽ trả về Null

## Cập nhật:

#### v1.0.6
- fix `sort():Json2T` sắp sếp được cả chuỗi, và số (có lỗi trả về mảng -1)
- fix `reverse():Json2T` đảo được cả mảng chuỗi và số (có lỗi trả về mảng -1)
- update lại có lỗi sảy ra trả về 0 thay vì -1 hoặc `_`
- update lại `toString():String` tương đương `toStr():String`
- add note vào các hàm (sử dụng tốt trên netbean)

#### v1.0.5
- thêm hàm `avg(): Json2T` trả về trung bình cộng một mảng (cần ép về giá trị gì thì dùng các hàm `Lấy giá trị` ở trên)
- thêm hàm `sum(): Json2T` trả về tổng một mảng (cần ép về giá trị gì thì dùng các hàm `Lấy giá trị` ở trên)
- thêm hàm `min():Json2T` lấy số nhỏ nhất trong mảng (cần ép về giá trị gì thì dùng các hàm `Lấy giá trị` ở trên)
- thêm hàm `max():Json2T` lấy số lớn nhất trong mảng (cần ép về giá trị gì thì dùng các hàm `Lấy giá trị` ở trên)
- thêm hàm `reverse():Json2T` đảo ngược mảng số (cần ép về giá trị gì thì dùng các hàm `Lấy mảng giá trị` ở trên)
- sửa lỗi không thể đẩy chuỗi số thực về số nguyên (fix toInt(), toLong(), toInts(), toLongs())

#### v1.0.4
- thêm các hàm lấy giá trị (`toChar():char`, `toLong():long`, `toFloat():float`)
- thêm các hàm lấy mảng giá trị (`toChars():char[]`, `toLongs():long[]`, `toFloats():float[]`)
- thêm hàm `toKeys():String[]` lấy tất cả key trong json
- thêm hàm `toValues():Json2T[]` lấy tất cả value trong json

#### v1.0.3.1
- fix lại function `q(String query):Json2T` đọc json có mảng đầu tiên không lỗi

#### v1.0.3
- thêm function `q(String query):Json2T` => đọc json nhanh hơn người yêu cũ trở mặt
- đổi function `key(String key):Json2T` => `k(String key):Json2T`
- đổi function `index(String index): Json2T` => `i(String index):Json2T`

#### v1.0.2
- bỏ variable `length:int` thay bằng function `length():int`
- bỏ `toJsonStr(): String` (sử dụng `toStr():String` hoặc `toString():String` thay thế)
- cập nhật lại source

#### v1.0.1
- thêm biến `length: int` để kiểm tra độ dài mảng
- fix lại 1 số hàm cho gọn nhẹ

#### v1.0.0
- ra mắt `Json2T.java`

## Thông tin:
- Tên: Json2T
- Tác giả: Thiên Đẹp Zaii ( SystemError )
- Phiên bản: 1.0.6
- Thư viện sử dụng: JSON SIMPLE
- Phiên bản thư viện: 1.1.1