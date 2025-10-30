<div align="center">

# Hệ thống Gửi Xe Thông Minh bằng QR (Python)

MVP: quét QR tại cổng, tính phí theo bảng giá, chốt thu tiền mặt, sinh e-receipt; kèm dashboard báo cáo.
</div>

## Nội dung
- Tổng quan
- Kiến trúc & Công nghệ
- Tính năng chính
- [Tài liệu BA](https://docs.google.com/document/d/1oC_jUkEc209hjeUTOcHanv7sv8ReyUCzEE5bwnxLk2Y/edit?usp=sharing)
- Roadmap 

## Tổng quan
- Bài toán: vé giấy thủ công → dễ sai, khó theo dõi, thiếu minh bạch.  
- Giải pháp: cấp QR cho SV; Guard quét **IN/OUT**; hệ thống **tính phí → chốt thu → e-receipt**; Admin **xem báo cáo/export**.  
- Phạm vi MVP: **thu tiền mặt** (ví/CK để giai đoạn sau).

## Kiến trúc & Công nghệ
**Python** (Flask/FastAPI) · **JWT** cho QR (exp/nonce) · **SQLite/Postgres** · (tuỳ chọn) **Alembic**, **Docker**.  
> Ghi chú ERD: mỗi user **chỉ có 1 phiên đang IN** tại một thời điểm (enforce bằng partial unique index ở DB thật).

## Tài liệu BA
> **Ghi chú Tài liệu BA**  
> - Mô tả bối cảnh & mục tiêu MVP: quét QR IN/OUT, tính phí, thu tiền mặt, e-receipt, báo cáo.  
> - Actors & 5 chức năng chính; FR/NFR rút gọn, Data Flow vào/ra.  
> - Sơ đồ **Use Case** & **Swimlane To-Be** (có nhánh lỗi/Reject).  
> - **ERD**: users, sessions, payments, tickets, tariffs, qr_tokens, audit_logs  
> - 1 **User Story** + **Acceptance Criteria** theo mẫu Given–When–Then.

## Roadmap
- [ ] QR động (nonce + exp theo phiên)  
- [ ] Thanh toán ví/CK + đối soát  
- [ ] Multi-gate & realtime sync  
- [ ] Dashboard/cảnh báo nâng cao  
- [ ] RBAC chi tiết theo ca/khu; observability (metrics/logs)

---
<sub> Châu Anh</sub>
