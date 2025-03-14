# Matplotlib Data Visualization - Full Documentation

## 1. Importing Matplotlib
```python
import matplotlib.pyplot as plt
```

## 2. Basic Plotting
```python
plt.plot(x, y, linestyle='-', marker='o', color='b', label='Line')
plt.xlabel('X-axis Label')
plt.ylabel('Y-axis Label')
plt.title('Plot Title')
plt.legend()
plt.grid(True)
plt.show()
```
- `linestyle`: Kiểu đường (`'-'`, `'--'`, `'-.'`, `':'`).
- `marker`: Dấu điểm (`'o'`, `'s'`, `'^'`, `'D'`).
- `color`: Màu sắc (`'r'`, `'g'`, `'b'`, `'#FF5733'`).
- `label`: Nhãn của đường.
- `grid(True)`: Hiển thị lưới.

## 3. Multiple Plots
```python
plt.plot(x1, y1, label='Line 1')
plt.plot(x2, y2, label='Line 2')
plt.legend()
plt.show()
```

## 4. Scatter Plot
```python
plt.scatter(x, y, color='r', marker='x', alpha=0.5)
plt.show()
```
- `alpha`: Độ trong suốt (0-1).

## 5. Bar Chart
```python
plt.bar(categories, values, color='blue', width=0.6)
plt.show()
```

## 6. Histogram
```python
plt.hist(data, bins=10, color='green', edgecolor='black')
plt.show()
```

## 7. Pie Chart
```python
plt.pie(sizes, labels=labels, autopct='%1.1f%%', startangle=140)
plt.show()
```
- `autopct`: Hiển thị phần trăm.
- `startangle`: Góc bắt đầu.

## 8. Subplots
```python
fig, axs = plt.subplots(2, 2)
axs[0, 0].plot(x, y)
axs[1, 1].bar(categories, values)
plt.show()
```

## 9. Customizing Plots
```python
plt.figure(figsize=(10, 5))  # Kích thước hình
plt.xlim(0, 100)  # Giới hạn trục X
plt.ylim(0, 200)  # Giới hạn trục Y
plt.xticks(rotation=45)  # Xoay nhãn trục X
```

## 10. Saving Figures
```python
plt.savefig('plot.png', dpi=300, bbox_inches='tight')
```
- `dpi`: Độ phân giải ảnh.
- `bbox_inches='tight'`: Giữ nội dung không bị cắt.

---

Tài liệu này liệt kê các hàm phổ biến nhất trong Matplotlib để vẽ biểu đồ và trực quan hóa dữ liệu.

