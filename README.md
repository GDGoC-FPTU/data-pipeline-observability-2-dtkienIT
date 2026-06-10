[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=24112906&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** dotrungkien1382003@gmail.com
**Name:** Do Trung Kien

---

## Mo ta

Day 10 lab tap trung vao viec xay dung mot ETL pipeline don gian bang Python, sau do kiem tra tac dong cua data quality len mot agent tra loi kieu RAG-like. Trong `solution.py`, pipeline se:

- Doc du lieu tu `raw_data.json`
- Kiem tra du lieu khong hop le
- Chuan hoa category va tinh `discounted_price`
- Ghi ket qua ra `processed_data.csv`

Sau do, `agent_simulation.py` duoc dung de so sanh ket qua giua clean data va garbage data. Muc tieu cua bai lab la cho thay du lieu ban co the lam sai ket qua cua agent ngay ca khi logic truy van khong doi.

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

Lenh tren se tao `processed_data.csv` tu `raw_data.json`, loc record loi, va them cac cot `discounted_price` va `processed_at`.

### Chay Agent Simulation (Stress Test)
```bash
python generate_garbage.py
python agent_simulation.py
```

Lenh dau tao `garbage_data.csv` voi duplicate ID, wrong type, outlier va null values. Lenh sau chay thu agent voi ca clean data va garbage data de quan sat su khac biet trong cau tra loi.

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── garbage_data.csv         # Du lieu "poisoned" cho stress test
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

Pipeline da xu ly 5 record trong file goc, giu lai 3 record hop le va loai bo 2 record loi. Ket qua cuoi cung co `discounted_price`, `category` da chuyen sang Title Case, va `processed_at` de theo doi thoi diem xu ly. Khi chay stress test, clean data giup agent tra loi dung voi laptop co gia tot nhat, trong khi garbage data lam agent bi lech sang Nuclear Reactor do outlier va du lieu ban. Dieu nay cho thay data quality la yeu to rat quan trong trong moi he thong AI va data pipeline.
