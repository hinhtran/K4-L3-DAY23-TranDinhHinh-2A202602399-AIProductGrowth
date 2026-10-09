# Day 23 — Đèn nào bật trước? · Operating Dashboard

- **Học viên:** Trần Đình Hinh
- **MSSV:** 2A202602399
- **Sản phẩm:** DATA-17 (AI Trợ lý thẩm định hồ sơ nghi trùng & chuẩn hóa Golden Record)
- **Câu chốt loại mô hình:** Chúng tôi là **B2B Enterprise (Sales-Led)** vì tiền đến từ ngân sách Data Operations/IT của doanh nghiệp (Head of Data/CDO ký), người dùng trực tiếp là Data Steward nội bộ thao tác trên Review Queue, và hệ thống giải quyết bài toán nghiệp vụ dữ liệu nội bộ không chạm người dùng cuối tiêu dùng bên ngoài.

---

## Cấu trúc thư mục nộp bài

```
K4-L3-DAY23-TranDinhHinh-2A202602399-AIProductGrowth/
├── README.md        # Thông tin học viên, sản phẩm và câu chốt mô hình
├── worksheet.md     # Trạm 1–4: Rà soát đèn B2B, thẻ đèn, bảng ngưỡng, phụ lục [MH], 5 luật
├── dashboard.md     # Trạm 5: Operating Dashboard 1 trang chuẩn chỉnh
└── dashboard.pdf    # Bản in PDF 2 trang: Trang 1 = Dashboard, Trang 2 = Phụ lục phép tính [MH]
```

## Tóm tắt thông số tài chính nền tảng (Kế thừa Day 22)
- **Mô hình định giá:** Hybrid ($1,000/tháng cho 5 seats + $0.04/cặp clean AI-resolved).
- **ARPU:** $4,200/tháng (~$50,400/năm ACV).
- **Gross Margin (GM):** Hybrid GM = 80.38% (Usage GM = 74.24%, Target GM ≥ 60%).
- **Cost/Job:** $0.010302 / clean pair (với Clean Containment R = 80%).
- **CAC giả định:** $32,000 (CAC cap nội bộ 12 tháng = $40,510).
- **Payback Period:** 9.48 tháng (Mục tiêu: ≤ 12 tháng).
- **Runway & Kế hoạch:** 08/10/2026 – 06/01/2027 (Pilot 2 khách hàng doanh nghiệp).
