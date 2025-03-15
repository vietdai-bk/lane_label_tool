# lane_label-_tool

Để cài đặt và chạy dự án từ GitHub sử dụng các lệnh mà bạn đã đưa ra, bạn có thể làm theo các bước dưới đây:

## 1. Clone Repository từ GitHub
Đầu tiên, bạn cần clone repository về máy của mình. Mở terminal (hoặc PowerShell trên Windows) và chạy lệnh sau:

```bash
git clone https://github.com/viethung2002/lane_label_tool.git
```
Lệnh này sẽ tải về toàn bộ mã nguồn của dự án và tạo một thư mục lane_label_tool trong thư mục hiện tại của bạn.

## 2. Cài đặt Virtual Environment (Môi trường ảo)
Để đảm bảo các thư viện được cài đặt riêng biệt cho dự án này mà không làm ảnh hưởng đến các dự án khác, bạn nên sử dụng môi trường ảo.

Trên Windows:

```bash
python -m venv myenv
```
Trên macOS/Linux:

```bash
python3 -m venv myenv
```
Sau đó, kích hoạt môi trường ảo:

Trên Windows:

```bash
.\myenv\Scripts\Activate
```
Trên macOS/Linux:

```bash
source myenv/bin/activate
```
## 3. Cài đặt các thư viện yêu cầu
Sau khi đã kích hoạt môi trường ảo, bạn cần cài đặt các thư viện phụ thuộc từ tệp requirements.txt. Đảm bảo bạn đã có tệp requirements.txt trong thư mục dự án.

Chạy lệnh sau để cài đặt tất cả các thư viện cần thiết:

```bash
pip install -r requirements.txt
```
Lệnh này sẽ tự động cài đặt tất cả các thư viện có trong ``requirements.txt``.

## 4. Chạy Dự Án

Chương trình ``video2frame`` giúp bạn trích xuất các frame từ một video và lưu chúng dưới dạng các file hình ảnh (PNG) trong thư mục chỉ định. Mỗi giây của video sẽ được trích xuất một frame.

Chạy chương trình từ dòng lệnh:
```
python video2frame.py --video_path <đường_dẫn_video> --output_frames <thư_mục_lưu_frames>
```
Tham số:  
**--video_path:** Đường dẫn đến video bạn muốn trích xuất frames.  
**--output_frames:** Đường dẫn đến thư mục nơi các frame sẽ được lưu.  
VD: ``python video2frame.py --video_path example.mp4 --output_frames output_frames/``

Sau khi đã cài đặt xong các thư viện, bạn có thể chạy ứng dụng. Mở terminal trong thư mục ``lane_label_tool`` và chạy lệnh:
```
tool_label.py
```

## 📌 Hướng Dẫn Sử Dụng

### 🖼️ Mở ảnh
Nhấn **"Mở ảnh"** để chọn thư mục chứa ảnh cần chú thích.

### ✏️ Chế độ vẽ
Chọn chế độ vẽ phù hợp:
- **Line** (đường thẳng)
- **Curve** (đường cong)
- **Polygon** (đa giác)
- **Polyline** (chuỗi đường)

### 🛠️ Chỉnh sửa
Sử dụng chế độ **"Chỉnh sửa"** để **thêm/xóa** các đối tượng đã vẽ.

### 💾 Lưu chú thích
Nhấn **"Lưu ảnh"** để lưu ảnh đã chú thích **cùng với tệp JSON**.

### 📂 Tạo Tệp Train/Valid/Test
Nhấn **"Tạo Train/Valid/Test"** để tạo các tệp dữ liệu huấn luyện.

---

## ⌨️ Phím Tắt

| Phím Tắt        | Chức Năng |
|-----------------|-----------|
| `Ctrl + O`      | Mở thư mục ảnh |
| `Ctrl + S`      | Lưu ảnh |
| `M`             | Chuyển chế độ vẽ (line, curve, polygon, polyline) |
| `Tab`           | Chuyển giữa chế độ **Label**, **Pan**, **Edit** |
| `Return ↵`      | Hoàn thành đối tượng vẽ |
| `Z`             | Hủy đối tượng vẽ gần nhất |
| `C`             | Xóa tất cả các đối tượng chú thích |
| `N`             | Xem ảnh tiếp theo |
| `P`             | Xem ảnh trước |

---

## ⚠️ Lưu ý
- Chương trình **tự động tạo** các thư mục để lưu kết quả:
  - `gt_image`
  - `gt_binary_image`
  - `gt_instance_image`
  - `annotations`
- Tệp **point** sẽ nằm cùng với thư mục `gt_image`, mỗi **lane** nằm trên một hàng trong file `.txt`.

