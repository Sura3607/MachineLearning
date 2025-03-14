# Pandas Data Analysis - Full Documentation

## 1. Importing Pandas
```python
import pandas as pd
```

## 2. Loading Data
### 2.1. Read CSV
```python
df = pd.read_csv(filepath, sep=',', header=0, names=None, index_col=None, usecols=None, dtype=None, nrows=None)
```
- `filepath`: Đường dẫn file CSV.
- `sep`: Ký tự phân tách (mặc định là `,`).
- `header`: Dòng đầu tiên chứa tên cột (`None` nếu không có).
- `names`: Danh sách tên cột.
- `index_col`: Cột dùng làm index.
- `usecols`: Chọn cột cần đọc.
- `dtype`: Kiểu dữ liệu cho từng cột.
- `nrows`: Số dòng đọc vào.

### 2.2. Read Excel
```python
df = pd.read_excel(filepath, sheet_name=0, header=0, names=None, index_col=None)
```
- `filepath`: Đường dẫn file Excel.
- `sheet_name`: Tên hoặc số sheet cần đọc.
- `header`, `names`, `index_col`: Giống `read_csv`.

### 2.3. Read JSON
```python
df = pd.read_json(filepath, orient='records')
```
- `filepath`: Đường dẫn file JSON.
- `orient`: Định dạng của JSON (`records`, `columns`, `index`, ...).

## 3. Hiển Thị Thông Tin Dữ Liệu
### 3.1. Xem Tổng Quan
```python
df.head(n=5)  # Xem n dòng đầu tiên
df.tail(n=5)  # Xem n dòng cuối cùng
```

### 3.2. Thông Tin Chung
```python
df.info()
df.describe(include='all')
```
- `info()`: Hiển thị thông tin về kiểu dữ liệu và giá trị null.
- `describe(include='all')`: Thống kê các cột số và cột object.

## 4. Xử Lý Dữ Liệu
### 4.1. Xử Lý Giá Trị Thiếu
```python
df.dropna(axis=0, how='any')  # Xóa dòng chứa giá trị null
df.fillna(value, method=None)  # Điền giá trị null
```
- `axis`: `0` (dòng), `1` (cột).
- `how`: `any` (bỏ nếu có ít nhất 1 giá trị null), `all` (bỏ nếu tất cả null).
- `method`: `ffill` (điền theo giá trị trước), `bfill` (điền theo giá trị sau).

### 4.2. Xử Lý Dữ Liệu Trùng Lặp
```python
df.drop_duplicates(subset=None, keep='first')
```
- `subset`: Cột cần kiểm tra.
- `keep`: `first`, `last`, `False` (xóa tất cả).

## 5. Truy Xuất Dữ Liệu
### 5.1. Chọn Cột
```python
df['column_name']
df[['col1', 'col2']]
```

### 5.2. Chọn Dòng
```python
df.loc[row_label, col_label]
df.iloc[row_index, col_index]
```
- `loc`: Chỉ số dựa trên nhãn.
- `iloc`: Chỉ số dựa trên vị trí.

### 5.3. Lọc Dữ Liệu
```python
df[df['column'] > value]
df.query('column > value')
```

## 6. Thống Kê
```python
df.mean()
df.median()
df.mode()
df.std()
df.var()
df.corr()
df.value_counts()
```
- `value_counts()`: Đếm số lần xuất hiện của mỗi giá trị trong một cột.
- `nunique()`: Đếm số lượng giá trị duy nhất trong cột.
- `count()`: Đếm số lượng giá trị không null trong từng cột.

### 6.1. Đếm Giá Trị Duy Nhất
```python
df['column_name'].nunique()
```

### 6.2. Đếm Giá Trị Lặp
```python
df['column_name'].value_counts()
```

### 6.3. Đếm Số Lượng Dữ Liệu
```python
df.shape  # Trả về (số dòng, số cột)
len(df)  # Số dòng
```

## 7. Nhóm Dữ Liệu
```python
df.groupby('column_name').agg({'col1': 'sum', 'col2': 'mean'})
```
- `groupby()`: Nhóm dữ liệu theo cột.
- `agg()`: Tính toán theo nhóm.

## 8. Chuyển Đổi Dữ Liệu
```python
df.apply(func, axis=1)
df['column'].map(lambda x: x * 2)
```
- `apply(func, axis)`: Áp dụng hàm cho từng dòng (`axis=1`) hoặc cột (`axis=0`).
- `map(func)`: Áp dụng hàm cho từng phần tử của cột.

## 9. Xuất Dữ Liệu
### 9.1. Ghi File CSV
```python
df.to_csv(filepath, index=False)
```
- `index`: `False` nếu không muốn ghi index vào file.

### 9.2. Ghi File Excel
```python
df.to_excel(filepath, sheet_name='Sheet1', index=False)
```

### 9.3. Ghi File JSON
```python
df.to_json(filepath, orient='records')
```


