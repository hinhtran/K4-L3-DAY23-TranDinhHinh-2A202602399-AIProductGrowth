# Worksheet — DATA-17 (AI Trợ lý thẩm định hồ sơ nghi trùng & kiến tạo Golden Record)

Họ tên: **Trần Đình Hinh** · MSSV: **2A202602399** · Ngày làm: **09/10/2026**

---

## Thông số tài chính nền tảng (Kế thừa từ Day 22)

| Chỉ số | Giá trị | Nguồn / Ý nghĩa |
|---|---|---|
| **Mô hình giá** | Hybrid | Phí nền tảng $1,000/tháng (gồm 5 seats) + $0.04/cặp clean AI-resolved |
| **ARPU** | $4,200 / tháng | Tương đương ACV = $50,400 / năm |
| **Gross Margin (GM)** | 80.38% (Hybrid) | Usage GM = 74.24%; Sàn biên lợi nhuận cam kết: ≥ 60% |
| **Cost/Job** | $0.010302 / cặp | Chi phí inference AI trên 1 clean pair (Clean containment R = 80%) |
| **CAC giả định** | $32,000 | CPO $8,000 ÷ Win rate 25% (Trần CAC nội bộ 12 tháng: $40,510) |
| **CAC Payback mục tiêu** | 9.48 tháng | Giới hạn trần nội bộ: ≤ 12 tháng |
| **Runway** | 9 tháng | Phục vụ giai đoạn pilot 2 khách hàng và GTM đến hết Q1/2027 |

---

## Trạm 1 — Loại mô hình & Bảng đèn B2B (§3.2)

### 1.1. Ba câu hỏi chẩn đoán
1. **Ai trả tiền cho bạn?** Doanh nghiệp (Head of Data / CDO phê duyệt từ ngân sách Data Operations / IT).
2. **Ai dùng sản phẩm?** Chính nhân sự nội bộ của khách hàng: Data Steward rà soát hồ sơ nghi trùng trên console Review Queue.
3. **Có bên trung gian không / Có chạm end-user không?** Không có bên trung gian và hoàn toàn không chạm người dùng cuối tiêu dùng bên ngoài.

**Câu chốt loại mô hình:**  
> **Chúng tôi là B2B Enterprise (Sales-Led) vì tiền đến từ ngân sách Data Operations của doanh nghiệp (Head of Data/CDO phê duyệt), người dùng trực tiếp là Data Steward rà soát hồ sơ nghi trùng trong console MDM / Review Queue, và hệ thống là công cụ nghiệp vụ nội bộ hoàn toàn không có người dùng cuối tiêu dùng bên ngoài.**

### 1.2. Rà soát bảng đèn B2B (§3.2 trong HANDBOOK)

| Đèn | ✅ / 🔧 / ❌ | Số nằm ở đâu / Cần gì để đo |
|---|:---:|---|
| **Time-to-first-value (TTFV)** | 🔧 | Log tích hợp API đến ngày Data Steward nghiệm thu batch 10,000 cặp thật đầu tiên; đo khi pilot bắt đầu. |
| **Pipeline coverage** | 🔧 | Bảng theo dõi CRM: Tổng giá trị cơ hội qualified ÷ Quota $500,000/năm; đo khi triển khai sales tuần. |
| **% deal chết ở security/procurement** | ❌ | Chưa có tập dữ liệu sales enterprise đủ lớn (mới tiếp cận 30 accounts); cần log đàm phán hợp đồng enterprise qua 1–2 quý. |
| **POC → paid (Tỷ lệ chốt pilot)** | 🔧 | Tỷ lệ chuyển đổi từ 2 khách hàng pilot sang hợp đồng hàng năm; có số sau ngày 06/01/2027. |
| **Sales cycle (Độ dài chu kỳ bán)** | 🔧 | CRM: Số ngày từ Qualified Opportunity đến khi chốt hợp đồng (kỳ vọng benchmark ~19 tuần). |
| **Usage depth trong tài khoản** | 🔧 | Event log từ console DATA-17: % Data Steward active hàng tuần thao tác trên Review Queue; đo trong pilot. |
| **Chi phí triển khai ÷ ACV** | ✅ | Bảng tính Day 22: (Giờ công kỹ sư setup pipeline + connector) ÷ ACV $50,400 = 7.94%. |
| **Chi phí AI Inference ÷ Doanh thu Usage** | ✅ | Bảng tính Day 22: Cost/Job $0.010302 ÷ Đơn giá $0.04/cặp = 25.76% (nằm trong tầm kiểm soát). |
| **Tập trung doanh thu** | ✅ | Bảng tính Day 22: Giai đoạn đầu 2 khách pilot chiếm 100% doanh thu; đo hàng tháng khi ký deal. |
| **Gross Margin (Biên lợi nhuận gộp)** | ✅ | Bảng tính Day 22: Hybrid GM = 80.38% (Usage GM = 74.24%). |
| **CAC Payback** | ✅ | Bảng tính Day 22: 9.48 tháng (với CAC = $32,000 và đóng góp lợi nhuận gộp $3,375.96/tháng). |
| **NRR (Net Revenue Retention)** | ❌ | Chưa đo được hôm nay vì sản phẩm mới bắt đầu pilot, cần dữ liệu khách hàng sử dụng tối thiểu 12 tháng. |

---

## Trạm 2 — Cây 3 tầng & Thẻ đèn (7 thẻ)

**NORTH STAR:** **Time-to-first-value (TTFV)** — Hiện tại: **Chưa đo (Ước tính pilot: 45 ngày)** — Mục tiêu: **< 25 ngày**

| # | Tầng | Tên đèn | Định nghĩa (Đếm gì · **KHÔNG** đếm gì) | Công thức | Nhịp · Ai lấy số | Báo trước cho |
|---|:---:|---|---|---|---|---|
| **1** | **L** | **Time-to-first-value (TTFV)** ⭐ | Số ngày từ khi ký hợp đồng/pilot đến khi Data Steward nghiệm thu batch dữ liệu thật đầu tiên (≥10,000 cặp) với revert rate sau 14 ngày ≤1%. **Không đếm** thời gian setup môi trường sandbox/mock data nội bộ trước khi ký. | `Ngày nghiệm thu batch dữ liệu thật đầu tiên − Ngày ký hợp đồng pilot` | Mỗi khách hàng hoàn tất onboarding · Technical Account Manager (TAM) | POC → Paid và Tỷ lệ tái ký hợp đồng năm đầu |
| **2** | **L** | **% Deal tắc/chết ở khâu Security & Procurement** | Tỷ lệ cơ hội bán hàng bị dừng hoặc kéo dài >30 ngày tại bước thẩm định bảo mật (DPA/SOC2/Infosec) hoặc mua hàng. **Không đếm** các deal rớt ở bước discovery do sai thẩm quyền hoặc thiếu ngân sách. | `(Số deal tắc ở Security/Procurement) ÷ (Tổng deal vào giai đoạn đàm phán hợp đồng trong kỳ)` | Hàng tháng · Founder / Enterprise Sales Lead | Độ dài chu kỳ bán (Sales cycle) và Tỷ lệ chuyển đổi POC → Paid |
| **3** | **O** | **Chi phí AI Inference ÷ Doanh thu Usage** (Đèn chi phí AI ⭐) | Tỷ lệ chi phí API token AI (Gemini Flash + Embedding) trên tổng doanh thu phát sinh từ các cặp clean pair. **Không đếm** chi phí token dùng cho R&D thử nghiệm nội bộ, prompt tuning, eval holdout offline. | `(Tổng chi phí token inference trong tháng) ÷ (Tổng doanh thu usage: $0.04 × số clean pair)` | Hàng tuần · Cloud FinOps Lead / trích xuất Google Cloud Billing | Gross Margin toàn công ty và Ngưỡng hòa vốn sử dụng |
| **4** | **O** | **Chi phí triển khai setup ÷ ACV** | Tỷ lệ chi phí nhân công kỹ thuật tích hợp connector/pipeline dữ liệu khách hàng so với ACV. **Không đếm** chi phí phát triển core product roadmap chung và chi phí tiếp khách/bán hàng. | `(Giờ công kỹ sư triển khai × $50/h + Chi phí hạ tầng riêng) ÷ ACV ($50,400)` | Mỗi khách hoàn tất triển khai · Lead Systems Engineer | Gross Margin và Thời gian hoàn vốn CAC Payback |
| **5** | **O** | **Usage Depth trong tài khoản** | % Data Steward (seats) đã mua thực sự đăng nhập và giải quyết ≥50 hồ sơ nghi trùng hàng tuần. **Không đếm** các lượt đăng nhập chỉ để xem báo cáo (read-only) hoặc tài khoản admin IT phân quyền. | `(Số Data Steward active thao tác hàng tuần) ÷ (Tổng số seats đã mua theo hợp đồng, min 5)` | Hàng tuần · Product Analytics trích xuất từ Audit Log console | Khả năng mở rộng tài khoản (Expansion / NRR) và Nguy cơ churn |
| **6** | **G** | **Gross Margin (Biên lợi nhuận gộp hợp nhất)** | Tỷ lệ lãi gộp từ thuê bao cố định và usage sau khi trừ chi phí server hosting, token AI và hỗ trợ kỹ thuật trực tiếp. **Không đếm** chi phí hoa hồng bán hàng (sales commission) và chi phí R&D dài hạn. | `(Tổng doanh thu [Base + Usage] − Tổng COGS) ÷ Tổng doanh thu` | Hàng tháng / Quý · Kế toán trưởng / Mô hình tài chính | Lợi nhuận ròng, Runway tiền mặt và Khả năng sống sót |
| **7** | **G** | **CAC Payback Period** | Số tháng lợi nhuận gộp từ khách hàng tích lũy đủ để hoàn vốn chi phí bán hàng và marketing (CAC). **Không đếm** chi phí Customer Success duy trì tài khoản sau khi đã onboard thành công. | `Chi phí CAC ($32,000) ÷ (Doanh thu tháng $4,200 × Gross Margin 80.38%)` | Hàng quý · Founder / CFO | Runway tài chính và Tốc độ tái đầu tư mở rộng GTM |

> **Đèn chi phí AI là đèn số 3:** Chi phí AI Inference ÷ Doanh thu Usage.

---

## Trạm 3 — Đặt ngưỡng có nguồn & Phụ lục [MH]

### 3.1. Bảng ngưỡng 🟢🟡🔴

| # | Đèn | 🟢 | 🟡 | 🔴 | Nguồn | Lý do (1 câu) · Ngày kiểm tra nếu [BM] |
|---|---|:---:|:---:|:---:|:---:|---|
| **1** | TTFV ⭐ | < 25 ngày | 25–45 ngày | > 45 ngày | **[TB]** | Baseline pilot đặt mục tiêu <25 ngày; quá 45 ngày khách hàng mất kiên nhẫn và nghi ngờ ROI của AI trước ban lãnh đạo. |
| **2** | % Deal chết ở Security | < 10% | 10–20% | > 20% | **[BM]** | Benchmark B2B Enterprise (HANDBOOK §3.2 & ICONIQ 2026, kiểm tra 27/08/2026); >20% chứng tỏ thiếu Evidence Pack và hồ sơ tuân thủ bảo mật chuẩn. |
| **3** | Chi phí AI ÷ Doanh thu Usage | ≤ 26% | 26–40% | > 40% | **[MH]** | Suy từ đơn giá $0.04/cặp và cam kết Usage GM ≥60%; nếu chi phí AI >40% ($0.016/cặp) thì Usage GM vi phạm sàn 60% (xem Phụ lục 1). |
| **4** | Chi phí triển khai ÷ ACV | < 15% | 15–30% | > 30% | **[BM]** | Chuẩn phần mềm B2B (HANDBOOK §3.2, kiểm tra 27/08/2026); vượt 30% ACV ($15,120) biến công ty thành đơn vị gia công dịch vụ tùy biến. |
| **5** | Usage Depth | ≥ 60% | 40–60% | < 40% | **[TB]** | Chuẩn nội bộ pilot DATA-17; dưới 40% (<2/5 seats hoạt động) là tín hiệu cảnh báo Steward bỏ cuộc quay lại làm thủ công. |
| **6** | Gross Margin | ≥ 75% | 60–75% | < 60% | **[MH]** | Suy từ mô hình Hybrid Day 22 (kỳ vọng 80.38%); nếu GM <60% thì phần đóng góp còn lại không bù nổi chi phí cố định (xem Phụ lục 2). |
| **7** | CAC Payback | ≤ 10 tháng | 10–12 tháng | > 12 tháng | **[MH]** | Kế thừa từ ràng buộc tài chính Day 22: Payback tính ra là 9.48 tháng, trần tối đa nội bộ là 12 tháng ứng với CAC cap $40,510 (xem Phụ lục 2). |

---

### 3.2. Phụ lục [MH] — Các phép tính suy ngược từ mô hình tài chính Day 22

#### **[MH] 1 — Trần chi phí AI Inference trên mỗi cặp dữ liệu (Đèn số 3)**

```
Đầu vào (từ Day 22 Cost/Job & Pricing):
- Đơn giá thu khách hàng: P = $0.04 / clean AI-resolved pair.
- Cam kết sàn biên lợi nhuận gộp usage (Usage GM sàn): GM_min = 60.0%.
- Chi phí Cost/Job dự toán hiện tại: $0.010302 / cặp (tương ứng Usage GM = 74.24%).

Phép tính suy ngược:
- Chi phí tối đa cho phép trên mỗi clean pair:
    Cost_max = P × (1 − GM_min) = $0.04 × (1 − 0.60) = $0.016000 / cặp.
- Tỷ lệ chi phí AI Inference tối đa trên doanh thu usage:
    Inference_Ratio_max = Cost_max ÷ P = $0.016000 ÷ $0.04 = 40.0%.
- Mức xanh (🟢): Theo thiết kế hiện tại, Cost/Job = $0.010302 ÷ $0.04 = 25.76% ≤ 26%.

Kết quả ngưỡng:
→ 🟢 Chi phí AI ≤ 26% doanh thu usage (Cost/Job ≤ $0.0104)
→ 🟡 Chi phí AI từ 26% đến 40% (Cost/Job từ $0.0104 đến $0.0160)
→ 🔴 Chi phí AI > 40% doanh thu usage (Cost/Job > $0.0160, vi phạm sàn GM 60%)
```

#### **[MH] 2 — CAC tối đa và Ngưỡng trần hoàn vốn CAC Payback (Đèn số 7)**

```
Đầu vào (từ Day 22 Model Financial & GTM):
- ARPU hợp nhất: $4,200 / tháng (gồm $1,000 base + $3,200 usage).
- Gross Margin hợp nhất: GM = 80.38%.
- Lợi nhuận gộp đóng góp hàng tháng: 
    CM = ARPU × GM = $4,200 × 80.38% = $3,375.96 / tháng.
- Thời gian thu hồi vốn tối đa chấp nhận được (Payback cap nội bộ): 12 tháng.
- CAC giả định hiện tại: $32,000 → Payback hiện tại = $32,000 ÷ $3,375.96 = 9.48 tháng.

Phép tính suy ngược:
- Trần chi phí CAC tối đa tương ứng với thời gian hòa vốn 12 tháng:
    CAC_cap = CM × 12 = $3,375.96 × 12 = $40,511.52 (~ $40,510).
- Nếu CAC vượt quá $40,510, thời gian payback sẽ vượt quá 12 tháng, làm cạn kiệt dòng tiền của runway 9 tháng hiện tại.

Kết quả ngưỡng:
→ 🟢 CAC Payback ≤ 10 tháng (CAC ≤ $33,760, đạt kỳ vọng mô hình 9.48 tháng)
→ 🟡 CAC Payback 10 – 12 tháng (CAC từ $33,760 đến $40,510)
→ 🔴 CAC Payback > 12 tháng (CAC > $40,510, đe dọa runway tiền mặt)
```

#### **[MH] 3 — Trần chi phí triển khai kỹ thuật setup (Đèn số 4)**

```
Đầu vào (từ Day 22 ACV & Delivery Specs):
- Giá trị hợp đồng năm (ACV): $50,400.
- Giờ công kỹ sư dự toán: 80 giờ triển khai setup ban đầu.
- Đơn giá giờ kỹ sư nội bộ: $50 / giờ → Chi phí cơ sở = 80 × $50 = $4,000 (chiếm 7.94% ACV).

Phép tính suy ngược:
- Ngưỡng đỏ khi chi phí triển khai vượt 30% ACV:
    Deployment_cap = $50,400 × 30% = $15,120 (tương đương > 302 giờ công kỹ sư).
- Nếu vượt quá $15,120, lợi nhuận năm đầu tiên bị bào mòn hơn 1/3, mô hình chuyển thành dịch vụ gia công.

Kết quả ngưỡng:
→ 🟢 Chi phí triển khai < 15% ACV (< $7,560)
→ 🟡 Chi phí triển khai 15% – 30% ACV ($7,560 – $15,120)
→ 🔴 Chi phí triển khai > 30% ACV (> $15,120)
```

---

## Trạm 4 — 5 Luật quyết định (≥2 Luật dừng ⏹)

1. **⏹ [Luật dừng]** **NẾU** TTFV > 45 ngày, **TRÊN** 2 khách hàng pilot gần nhất, **THÌ** đóng băng toàn bộ hoạt động tiếp nhận pilot mới, cắt phạm vi tích hợp xuống đúng 1 pipeline dữ liệu duy nhất (Web referral) và 1 use case đối soát đơn giản (họ tên + số điện thoại) cho đến khi TTFV đưa về dưới 25 ngày. **KHÔNG THÌ** không được tăng ngân sách sales hay mở rộng pilot sang các pipeline phức tạp khác để bù tiến độ.

2. **⏹ [Luật dừng]** **NẾU** tỷ lệ deal vướng/chết ở khâu Security & Procurement > 20%, **TRONG** 1 quý liên tiếp, **THÌ** dừng toàn bộ hoạt động outbound sales trong 2 tuần của cả đội ngũ để tập trung hoàn thiện bộ tài liệu Evidence Pack v1 (gồm Holdout Eval Results có nhãn F1 ≥95%, chính sách lưu trữ DPA và quy trình Rollback dữ liệu đã được kiểm duyệt). **KHÔNG THÌ** không được giảm giá bán hợp đồng hay miễn phí seat để thuyết phục khách hàng bỏ qua rào cản bảo mật.

3. **NẾU** Chi phí AI Inference ÷ Doanh thu Usage > 40% (tương đương Cost/Job > $0.016/cặp), **TRONG** 2 tuần liên tiếp, **VÀ** tổng số lượng cặp xử lý ≥ 10,000 cặp, **THÌ** chuyển đổi ngay luồng xử lý từ zero-shot đa tác vụ sang kiến trúc 2 tầng (bộ lọc heuristic regex/Levenshtein cắt bỏ 50% cặp nghi ngờ trước khi gọi LLM) kết hợp bật tính năng Gemini Prompt Caching. **KHÔNG THÌ** không được tự ý tăng giá $0.04/cặp với khách hàng hiện tại trong kỳ hợp đồng để che đậy thuật toán kém hiệu quả.

4. **⏹ [Luật dừng]** **NẾU** Chi phí triển khai setup > 30% ACV ($15,120), **TRÊN** 2 khách hàng liên tiếp, **THÌ** đóng băng việc nhận thêm các yêu cầu tùy biến connector riêng, chuyển giao nhiệm vụ của đội ngũ giải pháp sang chuẩn hóa tài liệu hướng dẫn và schema mapping tự phục vụ (self-serve onboarding). **KHÔNG THÌ** không được ký thêm các hợp đồng cam kết custom integration theo yêu cầu riêng của từng khách hàng.

5. **NẾU** Usage Depth < 40% (dưới 2/5 seats hoạt động), **SAU** 30 ngày kể từ khi bàn giao hệ thống vào vận hành, **THÌ** cử trực tiếp Technical Account Manager ngồi làm việc trực tiếp cùng Data Steward của khách hàng trong 3 buổi rà soát thực tế để gỡ bỏ rào cản giao diện Review Queue và hiệu chỉnh lại ngưỡng tự tin của AI. **KHÔNG THÌ** không được chào bán thêm module Golden Record tự động hóa hay tính năng nâng cao cho tài khoản này khi họ chưa dùng thuần thục tính năng cốt lõi.
