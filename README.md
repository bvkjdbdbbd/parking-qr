# Hệ thống Gửi Xe Thông Minh bằng QR (Python)

> MVP: quét QR tại cổng, tính phí theo bảng giá, chốt thu tiền mặt, sinh biên nhận; kèm dashboard báo cáo.

## Nội dung
- [Tổng quan](#tổng-quan)
- [Kiến trúc & Công nghệ](#kiến-trúc--công-nghệ)
- [Cấu trúc thư mục](#cấu-trúc-thư-mục)
- [Sơ đồ & Tài liệu BA](#sơ-đồ--tài-liệu-ba)
- [Roadmap](#roadmap)

## Tổng quan
- Bài toán: quy trình vé giấy thủ công → dễ sai, khó theo dõi, thiếu minh bạch.
- Giải pháp: cấp QR cho sinh viên; bảo vệ quét IN/OUT; hệ thống tính phí, ghi thanh toán, sinh e-receipt; admin xem báo cáo/export.
- Phạm vi MVP: thu **tiền mặt** (cash). Ví/CK triển khai giai đoạn sau.

## Kiến trúc & Công nghệ
- **Backend:** Python (Flask/FastAPI), JWT cho QR (exp/nonce).
- **DB:** SQLite (dev) / PostgreSQL (prod). Migration: Alembic (tùy chọn).
- **Frontend:** HTML/JS (hoặc admin template tùy nhóm).
- **Triển khai:** `.env`, (tùy chọn) Docker Compose.

## Chạy nhanh
```bash
git clone https://github.com/<your-org>/<repo>.git
cd <repo>
python -m venv venv && source venv/bin/activate   # Windows: venv\Scripts\activate
pip install -r requirements.txt
cp .env.example .env
python app.py    # hoặc: uvicorn app:app --reload
