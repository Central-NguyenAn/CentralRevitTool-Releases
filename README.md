# BIM Central Tools - Revit Add-in Suite

BIM Central Tools là bộ công cụ tự động hóa mạnh mẽ dành cho Revit 2023 & 2024. Dự án được triển khai theo cấu trúc mã nguồn MVVM chuẩn mực và tách biệt rõ ràng giữa giao diện và logic xử lý API của Revit.

## 🌟 Cấu trúc Tính năng (Ribbon UI)

Toàn bộ các tính năng được tích hợp gọn gàng trong Tab **Central**, chia thành 7 nhóm công cụ Panel chuyên biệt:

### 🏗️ 1. Panel Modeling
*Tập hợp các công cụ dựng hình, tinh chỉnh hình học và định vị cấu kiện.*
- **Grids & Levels**:
  - **Draw Grid**: Tạo và rải lưới trục tọa độ tự động.
  - **Scope/Grid Manager**: Trình quản lý hiển thị và cắt tự động Lưới trục/Level trên View.
- **Smart Walls**:
  - **Attach to Floor/Roof**: Tự động Attach chân và đỉnh tường vào Dầm/Sàn/Mái.
  - **Wall from Slab**: Dựng tường tự động bao theo biên dạng của Sàn.
  - **Split Wall Layers**: Tách các lớp cấu tạo của tường phức hợp thành tường độc lập.
  - **Smart Wall Cut**: Tự động cắt khối rỗng tường bị vướng với các cấu kiện khác.
  - **Attach to Ceiling**: Gắn tường lên trần trong file host (Zero-UI).
- **Geometry Modifiers**:
  - **Split Elements**: Cắt chia nhỏ các phần tử dài theo tỷ lệ hoặc lưới.
  - **Sync Floor to Walls**: Tự động nới/co đường bao của Sàn bám theo khi vị trí Tường di chuyển.
- **Structural Snaps**:
  - **Snap Column to Grid**: Dịch chuyển cột đảm bảo khoảng cách định vị làm tròn đến 10mm.
  - **Snap Beam to Grid**: Dịch chuyển dầm bắt dính chính xác vào lưới trục.

### 🔍 2. Panel Navigation
*Quản lý tổng thể mô hình và kiểm tra chất lượng (QA/QC).*
- **Management**:
  - **Worksets**: Quản lý Worksets và thiết lập hiển thị Worksets.
  - **Phase Views**: Tạo nhanh các View 3D/Mặt bằng theo Phase.
  - **WBS Manager**: Quản lý mã WBS và phân chia công việc cấu kiện.
- **QA & QC**:
  - **Clash Nav**: Đọc file XML báo cáo va chạm từ Navisworks và định vị trên Revit.
  - **Error Nav**: Quản lý và định vị các lỗi Warning của Revit.
  - **Audit Beam**: Kiểm tra cao độ, kích thước Dầm và các lỗi khai báo thông số.

### 📊 3. Panel Data
*Công cụ xử lý, gán và xuất dữ liệu ra ngoài.*
- **Data Exporter**:
  - **Export Schedules**: Xuất Schedule từ Revit ra file Excel.
  - **Model Comparer**: So sánh 2 mô hình Revit để tìm sự khác biệt.
- **Data Manager**:
  - **Copy Parameter**: Copy giá trị giữa các Parameter một cách hàng loạt.
  - **Batch Material**: Đổi vật liệu hàng loạt cho nhiều Type (Category) cùng lúc.
  - **Gán TANG**: Gán giá trị vào Shared Parameter TANG cho các đối tượng giữa 2 Level.
- **Quick Comment**: Gắn chú thích (Comment) nhanh cho đối tượng được chọn.

### ⚙️ 4. Panel Management
*Tự động hóa luồng công việc và bảo trì mô hình dự án.*
- **Model Maintenance**:
  - **Clean SectionBox**: Xóa và dọn dẹp các Section Box dư thừa.
  - **Purge Tool**: Công cụ Purge nâng cao giúp làm nhẹ file mô hình.
- **Workflow Automation**:
  - **Batch NWC**: Xuất hàng loạt file NWC từ file hiện tại hoặc nhiều file .rvt.
- **View & Selection**:
  - **Toggle Links**: Bật/Tắt hiển thị của các Revit Links trong View.
  - **Adv. Selection**: Bộ lọc và công cụ chọn đối tượng nâng cao.

### 📐 5. Panel CAD Tools
*Tự động hóa dựng hình 3D từ các bản vẽ 2D CAD.*
- **Shaft from CAD**: Tạo lỗ mở Shaft tự động từ các đường line đánh dấu trên CAD.
- **Floor/Ceiling CAD**: Tạo Sàn và Trần đồng thời từ ranh giới bản vẽ CAD.
- **Col/Wall CAD**: Tự động dựng Cột và Tường cùng lúc từ bản vẽ CAD.
- **Place Family**: Đặt family tự động theo block/point tọa độ từ CAD.
- **Batch Export DWG**: Xuất hàng loạt bản vẽ Sheet ra định dạng DWG/DXF (Multi-layout).

### 🛠️ 6. Panel Utilities
*Các tiện ích hỗ trợ nhanh trong quá trình làm việc.*
- **Select By Parameter**: Chọn hàng loạt đối tượng trong mô hình theo giá trị Parameter.
- **Project Info**: Quản lý và cập nhật nhanh các thông tin dự án.
- **Import Shared Params**: Nhập hàng loạt Shared Parameters từ file .txt vào dự án.

### 🛣️ 7. Panel Infrastructure Tool
- **Model Road**: Tạo khối 3D hạ tầng kỹ thuật (đường, cống, rãnh) bằng SweptBlend.

---

## 🔒 Kiến trúc Hệ thống (Bảo mật & Ổn định)
- **Zero-warning Codebase**: Mã nguồn đã được dọn dẹp hoàn toàn cảnh báo (0 warnings).
- **MVVM Pattern**: Toàn bộ tính năng giao diện (UI) được viết lại theo chuẩn MVVM (WPF) nhằm tách biệt logic và hiển thị.
- **Revit API Safety**: Quản lý chặt chẽ Transaction thông qua External Event Handlers. Tránh hoàn toàn việc sử dụng API trong ViewModels hay Background Threads.
- **Code Security**: Hỗ trợ tích hợp Obfuscar để làm rối mã nguồn bảo vệ bản quyền trước khi xuất bản thành Bundle (.dll obfuscation).

---

## 📥 Tải Xuống Bản Phát Hành
Vui lòng truy cập kho lưu trữ chính thức dành cho việc tải xuống và cài đặt Add-in:
👉 [CentralRevitTool-Releases](https://github.com/Central-NguyenAn/CentralRevitTool-Releases/releases)
