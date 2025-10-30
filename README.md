<div align="center">

# 🚗 Hệ thống Gửi Xe Thông Minh bằng QR (Python)

[![status](https://img.shields.io/badge/status-MVP-green)](#)
[![python](https://img.shields.io/badge/Python-3.10%2B-blue)](#)

*MVP: Quét QR IN/OUT • Tính phí theo bảng giá • Thu **tiền mặt** • Sinh e-receipt • Dashboard báo cáo*
</div>

## Nội dung
- [Tổng quan](#tổng-quan)
- [Kiến trúc & Công nghệ](#kiến-trúc--công-nghệ)
- [Tài liệu BA](#tài-liệu-ba)
- [Roadmap](#roadmap)

## Tổng quan
- Bài toán: vé giấy thủ công → dễ sai, khó theo dõi, thiếu minh bạch.  
- Giải pháp: cấp QR cho SV; Guard quét **IN/OUT**; hệ thống **tính phí → chốt thu → e-receipt**; Admin **xem báo cáo/export**.  
- Phạm vi MVP: **thu tiền mặt** (ví/CK để giai đoạn sau).

## Kiến trúc & Công nghệ
**Python** (Flask/FastAPI) · **JWT** cho QR (exp/nonce) · **SQLite/Postgres** · (tuỳ chọn) **Alembic**, **Docker**.  
> Ghi chú ERD: mỗi user **chỉ có 1 phiên đang IN** tại một thời điểm (enforce bằng partial unique index ở DB thật).

## Tài liệu BA
- **Google Docs:** https://docs.google.com/document/d/1oC_jUkEc209hjeUTOcHanv7sv8ReyUCzEE5bwnxLk2Y/edit?usp=sharing

## Roadmap
- [ ] QR động (nonce + exp theo phiên)  
- [ ] Thanh toán ví/CK + đối soát  
- [ ] Multi-gate & realtime sync  
- [ ] Dashboard/cảnh báo nâng cao  
- [ ] RBAC chi tiết theo ca/khu; observability (metrics/logs)

---
<sub>MIT © 2025 — Your Name/Team</sub>
