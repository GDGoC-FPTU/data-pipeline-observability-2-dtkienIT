# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** AI20K-2A202600751
**Name:** Do Trung Kien
**Date:** 10/6/2026

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 10 | Du lieu hop le, ket qua phu hop voi gia tri thuc te. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 1 | Du lieu bi nhiem ban lam agent uu tien outlier thay vi gia tri dung. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Garbage data lam mo hinh tra loi bi lech vi no khong con phan biet duoc dong nao la tin cay. Trong file `garbage_data.csv`, co duplicate ID, kieu du lieu sai, outlier rat lon va gia tri null. Khi agent tim theo category electronics, no van lay dong co gia cao nhat trong tap du lieu, nen "Nuclear Reactor" tro thanh cau tra loi sai. Dieu nay cho thay neu khong co validate va clean data, he thong se co xu huong tra ve ket qua nghe hop ly nhung lai hoan toan sai trong thuc te. Data quality kem lam giam do tin cay, tang noise va co the day agent den nhung quyet dinh nguy hiem.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Dong y. Mot prompt tot chi co the giup mo hinh hoi cau hoi ro hon, nhung neu du lieu dau vao sai thi ket qua van sai. Trong bai nay, clean data giup agent tra loi dung, con garbage data lam agent bi "ao giac" boi outlier va record loi. Vi vay, data quality la nen tang quan trong hon ca cach hoi.
