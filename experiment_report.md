# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** 2A202600292
**Name:** Tran Dang Quang Huy
**Date:** 15/04/2026

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Based on my data, the best choice is Laptop at $1200. | 10 | Du lieu sach, schema on dinh, gia tri hop le, ket qua hop ly va dung voi logic tim max price trong electronics. |
| Garbage Data (`garbage_data.csv`) | Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Du lieu rac co duplicate IDs, outlier cuc lon, missing category, va price sai kieu du lieu nen agent bi dan den ket qua vo ly. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Garbage data lam agent tra loi sai vi no khong con duoc “neo” vao thong tin tin cay. Trong file xau, co duplicate IDs, gia tri outlier rat lon nhu `999999`, dong co `price` sai kieu du lieu nhu chuoi `ten dollars`, va co record bi thieu `category`. Pipeline/agent hien tai khong co buoc validate du lieu du manh de loai bo het cac truong hop nay, nen khi tim trong nhom `electronics` va chon gia cao nhat, no bi lech sang san pham vo ly la `Nuclear Reactor`. Du lieu sach thi dong nhat hon, schema ro rang hon, va cac gia tri gia ca phu hop nen ket qua cua agent moi hop li. Ngan gon lai, du lieu ban se lam retrieval sai, va khi retrieval sai thi cau tra loi cua agent se sai theo.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Dong y. Prompt tot khong the cuu mot knowledge base bi hong, vi agent cua bai nay phu thuoc truc tiep vao du lieu dau vao. Neu du lieu co duplicate, null, sai kieu va outlier, ket qua suy luan se bi meo, cho du cau hoi co viet ro den dau. Vi vay, chat luong du lieu la dieu kien tien quyet; prompt chi giup huong dan mo hinh, con du lieu moi quyet dinh do tin cay cua cau tra loi.
