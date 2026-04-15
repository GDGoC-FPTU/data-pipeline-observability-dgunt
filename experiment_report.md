# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** AI20K-XXXX  
**Name:** Vũ Đức Minh  
**Date:** 2026-04-15  

---

## 1. Ket qua thi nghiem

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 9 | Du lieu hop le, ket qua hop ly |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Du lieu bi nhieu, co gia tri bat thuong |

---

## 2. Phan tich va nhan xet

Agent tra loi sai khi dung garbage data vi no phu thuoc truc tiep vao chat luong du lieu dau vao. Khi bo du lieu chua cac gia tri bat thuong nhu "Nuclear Reactor" voi gia $999999, agent se coi day la lua chon tot nhat neu chi dua tren logic don gian. Ngoai ra, garbage data co the chua duplicate IDs, sai kieu du lieu, null values hoac category khong hop le. Nhung loi nay lam sai lech qua trinh xu ly va dan den quyet dinh khong dang tin cay. Dieu nay cho thay validation va data cleaning la buoc rat quan trong truoc khi dua du lieu vao he thong AI.

---

## 3. Ket luan

**Quality Data > Quality Prompt?**  
Toi dong y. Prompt tot khong the sua duoc du lieu xau. Neu du lieu dau vao sai, AI se dua ra ket qua sai. Nguoc lai, du lieu sach va hop le giup he thong tra loi on dinh va dang tin cay hon.