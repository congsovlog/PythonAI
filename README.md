1. Viết job để lưu dữ liệu daily
- Lưu danh sách
- Lưu chi tiết
- Lưu chỉ số
- Lưu dữ liệu daily OHLCV
- Lưu dữ liệu intraday OHLCV
daily_stock_price

index_components
index_list
daily_index


@fcdata Hãy viết job chạy cập nhật dữ liệu intraday OHLCV của từng mã chứng khoán đã được lưu trong parquet bằng cách sử dụng thư viện ssi_fc_data và hàm model.intraday_ohlc. Chú ý nếu dữ liệu OHLCV của mã chứng khoán đã tồn tại thì lấy từ thời điểm lấy dữ liệu cuối cùng đến thời điểm hiện tại. Chương trình sẽ xử lý từng mã hoàn chỉnh,, lưu xuống Parquest rồi mới thực hiện đến mã tiếp theo.

Parquest
Queue, Threading và callback pattern

2. Viết job lấy dữ liệu streamming
 https://guide.ssi.com.vn/ssi-products/tieng-viet/fastconnect-data/du-lieu-streaming
 F:SSI hoặc F:SSI-PAN hoặc F:ALL   Trạng thái Mã chứng khoán
 X-Quote:SSI hoặc X-Quote:SSI-PAN hoặc X-Quote:ALL  Dữ liệu bid/ask
 X-TRADE:SSI hoặc X-TRADE:SSI-PAN hoặc X-TRADE:ALL  Dữ liệu khớp lệnh
 X:SSI hoặc X:SSI-PAN hoặc X:ALL   Dữ liệu tổng hợp của thông tin bid/ask và thông tin khớp lệnh
 R:SSI hoặc R:SSI-PAN hoặc R:ALL    Dữ liệu Room nước ngoài
 MI:SSI hoặc MI:SSI-PAN hoặc MI:ALL    Dữ liệu chỉ số
 B:SSI hoặc B:SSI-PAN hoặc B:ALL    Dữ liệu OHLCV
 OL:SSI hoặc OL:SSI-PAN hoặc OL:ALL    Dữ liệu Lô lẻ (Odlot)

3. Quản lý job
python job_manager.py --host 0.0.0.0 --port 8080

## Cài đặt

### Yêu cầu hệ thống
- Python 3.8+
- pip package manager

### Cài đặt dependencies
```bash
pip install -r requirements.txt
```

## Sử dụng
cd .\fcdata\
python test_Req_Res.py
python .\test_Streaming_Optimized.py
