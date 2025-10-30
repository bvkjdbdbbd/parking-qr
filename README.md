# Hệ thống Gửi Xe Thông Minh bằng QR (Python)

> MVP: quét QR tại cổng, tính phí theo bảng giá, chốt thu tiền mặt, sinh biên nhận; kèm dashboard báo cáo.

## Nội dung
- Tổng quan
- Kiến trúc & Công nghệ 
- Chạy nhanh 
- Cấu trúc thư mục 
- [Tài liệu BA](https://docs.google.com/document/d/1oC_jUkEc209hjeUTOcHanv7sv8ReyUCzEE5bwnxLk2Y/edit?usp=sharing)
- [Roadmap](#roadmap)

## Tổng quan
- Quy trình vé giấy thủ công → dễ sai, khó theo dõi, thiếu minh bạch.
- Giải pháp: cấp QR cho sinh viên; bảo vệ quét IN/OUT; hệ thống tính phí, ghi thanh toán, sinh e-receipt; admin xem báo cáo/export.
- Phạm vi MVP: thu **tiền mặt** (cash). Ví/CK triển khai giai đoạn sau.

## Kiến trúc & Công nghệ
- **Backend:** Python (Flask **hoặc** FastAPI), JWT cho QR (exp/nonce).
- **DB:** SQLite (dev) / PostgreSQL (prod). Migration: Alembic (tùy chọn).
- **Frontend:** HTML/JS đơn giản hoặc admin template.
- **Triển khai:** `.env`, (tùy chọn) Docker Compose.

## Chạy nhanh
```bash
git clone https://github.com/<your-username>/parking-qr.git
cd parking-qr
python -m venv venv && source venv/bin/activate   # Windows: venv\Scripts\activate
pip install -r requirements.txt
cp .env.example .env
python app.py    # hoặc: uvicorn app:app --reload (nếu dùng FastAPI)
