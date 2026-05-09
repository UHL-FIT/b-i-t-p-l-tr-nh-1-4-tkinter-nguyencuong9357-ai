[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/rsGH3pBJ)
[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23866296&assignment_repo_type=AssignmentRepo)
# ltpt_bt_1_4
Bài tập lộ trình 1-4
Commit các file bài tập đã làm.
#Bài 1
import tkinter as tk
root = tk.Tk()
root.title("Nguyễn Ngọc Cường - UHL")
root.geometry("500x500")
nhan_chao = tk.Label(root, text="Chào mừng sinh viên Đại học Hạ Long!")
nhan_chao.pack(pady=50) # Đưa nhãn vào cửa sổ và tạo khoảng cách lề
root.mainloop()
#Bài 2
import tkinter as tk
root = tk.Tk()
root.title("Thẻ Sinh Viên Số")
root.geometry("400x300")
root.configure(bg="#f8f9fa")

nhan_truong = tk.Label(
    root, 
    text="TRƯỜNG ĐẠI HỌC HẠ LONG",
    font=("Arial", 14, "bold"), 
    fg="red", 
    bg="#0056b3" # Màu xanh thương hiệu
)
nhan_khoa = tk.Label(
    root, 
    text="Khoa: Công nghệ thông tin",
    font=("Arial", 13, "bold"), 
    fg="green", 
    bg="white" # Màu trắng
)
nhan_truong.pack(fill="x", pady=10) # fill="x" để màu nền trải rộng hết chiều ngang
nhan_khoa.pack(fill="x", pady=10)

nhan_ten = tk.Label(root, text="Họ tên: Nguyễn Văn A", font=("Arial", 12))
nhan_ten.pack(pady=5)

nhan_msv = tk.Label(root, text="MSSV: 22010001", font=("Arial", 12), fg="red")
nhan_msv.pack(pady=5)

nut_thoat = tk.Button(
    root, 
    text="Đóng ứng dụng", 
    command=root.destroy, 
    bg="#dc3545", # Màu đỏ cảnh báo
    fg="white",
    width=30,
    height=3,
)
nut_thoat.pack(pady=20)
root.mainloop()
#Bài 3
import tkinter as tk
root = tk.Tk()
root.title("Quản lý Sinh viên - UHL")
root.geometry("400x250")
root.columnconfigure(1, weight=1)
nhan_ma_sv = tk.Label(root, text="Mã sinh viên:")
o_nhap_ma_sv = tk.Entry(root)

nhan_ho_ten = tk.Label(root, text="Họ và tên:")
o_nhap_ho_ten = tk.Entry(root)

nhan_ma_sv.grid(row=0, column=0, padx=10, pady=10, sticky="w")
o_nhap_ma_sv.grid(row=0, column=1, padx=10, pady=10, sticky="ew")

nhan_ho_ten.grid(row=1, column=0, padx=10, pady=10, sticky="w")
o_nhap_ho_ten.grid(row=1, column=1, padx=10, pady=10, sticky="ew")

root.mainloop()
#Bài 4
import tkinter as tk
from tkinter import messagebox
from datetime import datetime

def xu_ly_du_lieu():
    mssv = o_nhap_ma_sv.get()
    ho_ten = o_nhap_ho_ten.get()

    if mssv == "" or ho_ten == "":
        messagebox.showerror("Lỗi", "Vui lòng không để trống thông tin!")
        return

    if not mssv.isdigit():
        messagebox.showerror("Lỗi", "MSSV phải là số!")
        return
    thoi_gian = datetime.now().strftime("%H:%M:%S")
    print(f"[{thoi_gian}] MSSV: {mssv} - Họ tên: {ho_ten}")
    nhan_ket_qua.config(
        text=f"Thành công: Đã nhận dữ liệu của {ho_ten}",
        fg="green"
    )
    o_nhap_ma_sv.delete(0, tk.END)
    o_nhap_ho_ten.delete(0, tk.END)
root = tk.Tk()
root.title("Quản lý Sinh viên - UHL")
root.geometry("400x350")
root.columnconfigure(1, weight=1)

tk.Label(root, text="Mã sinh viên:").grid(row=0, column=0, padx=10, pady=10, sticky="w")
o_nhap_ma_sv = tk.Entry(root)
o_nhap_ma_sv.grid(row=0, column=1, padx=10, pady=10, sticky="ew")

tk.Label(root, text="Họ và tên:").grid(row=1, column=0, padx=10, pady=10, sticky="w")
o_nhap_ho_ten = tk.Entry(root)
o_nhap_ho_ten.grid(row=1, column=1, padx=10, pady=10, sticky="ew")

nut_xac_nhan = tk.Button(root, text="Xác nhận điểm danh", command=xu_ly_du_lieu)
nut_xac_nhan.grid(row=2, column=0, columnspan=2, pady=10)

nhan_ket_qua = tk.Label(root, text="Hệ thống sẵn sàng", font=("Arial", 10, "italic"))
nhan_ket_qua.grid(row=3, column=0, columnspan=2, pady=20)

root.mainloop()
