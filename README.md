[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23573999&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** 26ai.minhvd2@vinuni.edu.vn
**Name:** Vũ Đức Minh

---

## Mô tả

Bài lab này xây dựng một ETL Pipeline đơn giản để xử lý dữ liệu sản phẩm từ file JSON.

Pipeline bao gồm 4 bước chính:
- **Extract:** Đọc dữ liệu từ file `raw_data.json`
- **Validate:** Loại bỏ các record không hợp lệ (price <= 0, category rỗng)
- **Transform:** 
  - Tính giá giảm 10% (`discounted_price`)
  - Chuẩn hóa category về Title Case
  - Thêm timestamp (`processed_at`)
- **Load:** Lưu dữ liệu ra file `processed_data.csv`

Ngoài ra, thực hiện thí nghiệm để đánh giá ảnh hưởng của chất lượng dữ liệu đến kết quả của AI Agent.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
python generate_garbage.py
python agent_simulation.py
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── raw_data.json            # Dữ liệu đầu vào
├── processed_data.csv       # Output sạch
├── garbage_data.csv         # Dữ liệu nhiễu
├── generate_garbage.py      # Script tạo dữ liệu lỗi
├── agent_simulation.py      # Test AI Agent
├── experiment_report.md     # Báo cáo thí nghiệm
└── README.md                # File này
```

---

## Ket qua

ETL Pipeline
Tổng records ban đầu: 5
Records hợp lệ: 3
Records bị loại: 2

Pipeline chạy thành công, không lỗi.

Agent Simulation
Với Clean Data:
Agent: Based on my data, the best choice is Laptop at $1200.

→ Kết quả hợp lý, phản ánh đúng dữ liệu.

Với Garbage Data:
Agent: Based on my data, the best choice is Nuclear Reactor at $999999.

→ Kết quả sai hoàn toàn do dữ liệu bị nhiễu.

Nhận xét

Thí nghiệm cho thấy AI Agent không có khả năng tự phân biệt dữ liệu đúng hay sai. Khi dữ liệu đầu vào bị lỗi hoặc chứa giá trị bất thường (outliers), Agent sẽ đưa ra quyết định sai lệch.

Điều này chứng minh rằng:

Data Quality ảnh hưởng trực tiếp đến kết quả của AI
ETL Pipeline và bước Validation là cực kỳ quan trọng




