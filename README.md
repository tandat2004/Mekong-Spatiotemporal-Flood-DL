# Mekong-Spatiotemporal-Flood-DL

Dự án nghiên cứu khoa học của sinh viên Khoa học máy tính, Đại học Cần Thơ.

## Môi trường Python

Đã kiểm tra trên Windows 64-bit với Python 3.12 và PyTorch CPU.
Mở Miniforge Prompt tại thư mục repository:

```powershell
conda env create -f environment.yml --solver libmamba
conda activate mekong-flood
python -m pip check
```

Nếu môi trường đã được tạo, chỉ cần chạy `conda activate mekong-flood`.

- `environment.yml`: cấu hình tạo môi trường bằng Conda từ conda-forge.
- `requirements.txt`: phiên bản các thư viện Python trực tiếp đã dùng để đối chiếu.
  Cách cài riêng bằng pip chưa được kiểm thử; trên Windows dùng YAML để cài đồng bộ GDAL và thư viện native.

Google Earth Engine cần credentials và quyền sử dụng project của từng thành viên:

```powershell
# Chỉ xác thực nếu chưa có credentials hợp lệ:
earthengine authenticate
python -c "import ee; ee.Initialize(project='YOUR_PROJECT_ID'); print(ee.Number(1).add(1).getInfo())"
```

Thay `YOUR_PROJECT_ID` bằng project được cấp quyền; kết quả phép tính phải là `2`.
