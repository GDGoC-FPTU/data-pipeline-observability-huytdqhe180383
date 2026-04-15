[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23574009&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** huytdqhe180383@fpt.edu.vn / 26ai.huytdq@vinuni.edu.vn
**Name:** Tran Dang Quang Huy

---

## Mo ta

Bai lab nay xay dung mot ETL pipeline don gian de doc du lieu JSON, kiem tra hop le, chuan hoa du lieu va ghi ra CSV. Sau do, minh chay them mot bai stress test voi `agent_simulation.py` de so sanh hanh vi cua agent khi dung du lieu sach va du lieu rac. Muc tieu cua bai nay la cho thay chat luong du lieu anh huong truc tiep den chat luong cau tra loi cua agent.

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

Script se:
- Doc du lieu tu `raw_data.json`
- Loai bo record khong hop le
- Tao cot `discounted_price` va `processed_at`
- Luu ket qua vao `processed_data.csv`

### Chay Agent Simulation (Stress Test)
```bash
python agent_simulation.py
```

Khi chay stress test, ban se thay ket qua voi 2 bo du lieu:
- Clean data: agent tra loi hop ly hon
- Garbage data: agent bi anh huong boi duplicate, outlier, va wrong type

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

### ETL Pipeline
- Tong so record dau vao: 5
- Record hop le sau validation: 3
- Record bi loai: 2
- Cac cot moi: `discounted_price`, `processed_at`

### Stress Test
- Clean data (`processed_data.csv`): agent chon `Laptop` voi gia `$1200`
- Garbage data (`garbage_data.csv`): agent chon `Nuclear Reactor` voi gia `$999999`

### Nhan xet
Du lieu sach giup agent tim duoc thong tin hop ly va on dinh hon. Nguoc lai, du lieu rac co the lam sai logic tim kiem va dan den cau tra loi vo ly, ngay ca khi prompt khong doi. Vi vay, chat luong du lieu la nen tang quan trong cho moi he thong AI/ETL.
