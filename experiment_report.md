# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600459  
**Name:** Vũ Đức Minh  
**Date:** 2026-04-15  

---

## 1. Kết quả thí nghiệm

Chạy `agent_simulation.py` với 2 bộ dữ liệu và ghi lại kết quả:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 9 | Dữ liệu hợp lệ, giá hợp lý, agent đưa ra kết quả chính xác |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Dữ liệu bị nhiễu, giá trị bất thường, agent chọn sai hoàn toàn |

---

## 2. Phân tích & nhận xét

### Tại sao Agent trả lời sai khi dùng Garbage Data?

Agent AI phụ thuộc hoàn toàn vào dữ liệu đầu vào. Khi sử dụng Garbage Data, dữ liệu chứa nhiều vấn đề như giá trị bất thường (outliers), dữ liệu không hợp lệ, hoặc thông tin sai lệch. Trong trường hợp này, giá của "Nuclear Reactor" là $999999, vượt xa các sản phẩm khác, khiến agent ưu tiên chọn nó dù không hợp lý.

Ngoài ra, Garbage Data có thể chứa duplicate records, sai kiểu dữ liệu (ví dụ giá là string thay vì số), hoặc category không hợp lệ. Những lỗi này làm cho quá trình phân tích dữ liệu bị sai lệch, dẫn đến kết quả không đáng tin cậy.

Việc thiếu bước validation và data cleaning sẽ khiến hệ thống AI đưa ra quyết định sai, dù model hoặc logic xử lý có đúng.

---

## 3. Kết luận

**Quality Data > Quality Prompt?** → Đồng ý.

Dữ liệu chất lượng cao là yếu tố quan trọng nhất. Một prompt tốt không thể cứu được dữ liệu sai. Ngược lại, nếu dữ liệu sạch và đáng tin cậy, ngay cả một logic đơn giản cũng có thể đưa ra kết quả chính xác. Vì vậy, trong hệ thống AI, cần ưu tiên xây dựng pipeline xử lý và kiểm soát chất lượng dữ liệu trước khi tối ưu model hoặc prompt.