# OPERATING DASHBOARD — DATA-17

**Loại mô hình:** B2B Enterprise (Sales-Led) · **Cập nhật:** 09/10/2026 · **Trần Đình Hinh – 2A202602399**  
**NORTH STAR:** **Time-to-first-value (TTFV)** — Hiện tại: **45 ngày (ước tính)** — Mục tiêu: **< 25 ngày**

---

### Đèn báo sớm (Leading — nhìn hằng ngày/tuần)

| Đèn | Hiện tại | 🟢 / 🟡 / 🔴 | Nguồn | Báo trước cho |
|---|:---:|:---:|:---:|---|
| **1. Time-to-first-value (TTFV)** ⭐ | 45 ngày | 🟢 < 25d · 🟡 25–45d · 🔴 > 45d | [TB] | POC → Paid & Tỷ lệ tái ký năm đầu |
| **2. % Deal vướng ở Security** | 15% | 🟢 < 10% · 🟡 10–20% · 🔴 > 20% | [BM] (27/08/2026) | Độ dài chu kỳ bán & Tỷ lệ chốt pilot |

### Đèn vận hành (Operating — nhìn hằng tuần/tháng)

| Đèn | Hiện tại | 🟢 / 🟡 / 🔴 | Nguồn | Báo trước cho |
|---|:---:|:---:|:---:|---|
| **3. Chi phí AI ÷ Doanh thu Usage** (AI Cost) | 25.76% | 🟢 ≤ 26% · 🟡 26–40% · 🔴 > 40% | [MH] | Gross Margin & Hòa vốn sử dụng |
| **4. Chi phí triển khai setup ÷ ACV** | 7.94% | 🟢 < 15% · 🟡 15–30% · 🔴 > 30% | [BM] (27/08/2026) | Gross Margin & CAC Payback |
| **5. Usage Depth trong tài khoản** | 60% | 🟢 ≥ 60% · 🟡 40–60% · 🔴 < 40% | [TB] | Mở rộng NRR & Giảm nguy cơ churn |

### Đèn kết quả (Lagging — nhìn hằng quý)

| Đèn | Hiện tại | 🟢 / 🟡 / 🔴 | Nguồn |
|---|:---:|:---:|:---:|
| **6. Gross Margin hợp nhất** | 80.38% | 🟢 ≥ 75% · 🟡 60–75% · 🔴 < 60% | [MH] |
| **7. CAC Payback Period** | 9.48 tháng | 🟢 ≤ 10m · 🟡 10–12m · 🔴 > 12m | [MH] |

---

### 5 luật quyết định (⏹ = luật dừng)

1. ⏹ **[Dừng]** **NẾU** TTFV > 45 ngày, **TRÊN** 2 khách pilot gần nhất, **THÌ** đóng băng tiếp nhận pilot mới, cắt phạm vi tích hợp xuống đúng 1 pipeline Web referral cho đến khi TTFV < 25 ngày. **KHÔNG THÌ** không được tăng ngân sách sales hay mở rộng pilot sang pipeline App logs để bù tiến độ.
2. ⏹ **[Dừng]** **NẾU** % deal chết ở Security/Procurement > 20%, **TRONG** 1 quý, **THÌ** dừng outbound sales 2 tuần, tập trung hoàn thiện Evidence Pack v1 (Holdout F1 ≥95%, DPA, Rollback). **KHÔNG THÌ** không được giảm giá bán hay miễn phí seat để ép chốt deal.
3. **NẾU** Chi phí AI ÷ Doanh thu Usage > 40%, **TRONG** 2 tuần liên tiếp, **VÀ** cặp xử lý ≥ 10,000 cặp, **THÌ** chuyển sang bộ lọc heuristic 2 tầng kết hợp bật prompt caching. **KHÔNG THÌ** không tự ý tăng giá $0.04/cặp với khách hàng hiện tại trong kỳ hợp đồng.
4. ⏹ **[Dừng]** **NẾU** Chi phí triển khai > 30% ACV ($15,120), **TRÊN** 2 khách liên tiếp, **THÌ** đóng băng nhận custom connector, chuyển sang chuẩn hóa schema mapping self-serve. **KHÔNG THÌ** không ký thêm hợp đồng cam kết custom integration theo yêu cầu riêng.
5. **NẾU** Usage Depth < 40%, **SAU** 30 ngày từ bàn giao, **THÌ** cử Technical Account Manager ngồi trực tiếp 3 buổi cùng Data Steward gỡ rào cản Review Queue. **KHÔNG THÌ** không chào bán thêm module Golden Record tự động hóa khi khách chưa thạo tính năng lõi.

---

### Cổng gác 90 ngày

| Ngày | Metric gác cổng (đúng 1) | Ngưỡng qua cổng | Bằng chứng vật lý | Nếu trượt |
|:---:|---|---|---|:---:|
| **30** | Ký pilot & Evidence Pack v1 *(Cổng học)* | 2 thỏa thuận pilot ký + Holdout 10k cặp có nhãn F1 ≥95% & DPA | Thỏa thuận pilot ký điện tử + File Evidence Pack v1 trong repo | **FIX** *(ở lại 30 ngày gỡ bảo mật, cấm nhận khách 3)* |
| **60** | TTFV trên 2 khách pilot | TTFV ≤ 30 ngày trên cả 2 khách & thời gian review ≤ 25s/cặp | Báo cáo telemetry hệ thống có chữ ký xác nhận của Lead Steward | **PIVOT** *(thu hẹp từ AI-decision sang lọc thô rule-based)* |
| **90** | Tỷ lệ chuyển đổi POC → Paid | ≥ 1 khách ký hợp đồng chính thức 1 năm (ACV $50,400, GM ≥ 70%) | Hợp đồng thương mại đã ký và hóa đơn thanh toán kỳ đầu | **KILL** *(dừng dự án, hoàn trả môi trường, điều chuyển nhân lực)* |

**KILL CRITERIA:** Nếu đến ngày 06/01/2027 (hết 90 ngày pilot), không có ít nhất 1 khách hàng ký hợp đồng thương mại ≥$30,000 ARR và Usage GM thực tế đo được < 50% sau 1 lần FIX, dừng hoàn toàn dự án DATA-17 để bảo toàn ngân sách.

**CHƯA ĐO ĐƯỢC:**
1. *NRR (Net Revenue Retention):* Cần khách hàng dùng tối thiểu 12 tháng và có chu kỳ gia hạn/mở rộng; dự kiến có số vào Tháng 10/2027.
2. *% Deal chết ở Security trên diện rộng:* Cần pipeline sales mở rộng tối thiểu 20 enterprise accounts; dự kiến có số vào 31/03/2027.
