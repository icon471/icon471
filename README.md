# termux-sms-spam-simple.py
# Author: icon471
# Tahun: 2025

import os, time, requests

def banner():
    os.system("clear")
    print("""
╔══════════════════════════════╗
║   📱 SMS SPAMMER SIMPLE      ║
║        Termux 2025           ║
╚══════════════════════════════╝
""")

def kirim_sms(nomor):
    # Simulasi via API dummy (ganti sesuai endpoint asli bila punya)
    try:
        r = requests.get(f"https://api.icon471.net/sms?nomor={nomor}")
        if r.status_code == 200:
            print(f"✅ SMS terkirim ke {nomor}")
        else:
            print(f"❌ Gagal mengirim ke {nomor} (kode {r.status_code})")
    except Exception as e:
        print(f"❌ Error: {e}")

def main():
    banner()
    nomor = input("📞 Masukkan nomor target (format: 628xxxxx): ")
    jumlah = int(input("🔢 Jumlah spam SMS: "))

    print("\n🔃 Memulai spam SMS...\n")
    for i in range(jumlah):
        print(f"[{i+1}] Mengirim SMS ke {nomor}...")
        kirim_sms(nomor)
        time.sleep(1)  # jeda 1 detik antar spam

    print("\n✅ Selesai spam SMS!")

if __name__ == "__main__":
    main()

# 📱 Termux SMS Spammer Simple (2025)

Tool Spam SMS Sederhana berbasis Python untuk Termux. Dirancang untuk pembelajaran & uji API dummy.

## 📥 Cara Install

```bash
pkg update && pkg install python git -y
git clone https://github.com/icon471/termux-sms-tools
cd termux-sms-tools
python termux-sms-spam-simple.py

# 📱 Termux SMS Spammer Simple (2025)

Tool Spam SMS Sederhana berbasis Python untuk Termux. Simulasi aman untuk pembelajaran, uji API dummy, dan demo fitur input terminal.

## 📦 Cara Install di Termux

```bash
pkg update && pkg install python git -y
git clone https://github.com/username/termux-sms-tools
cd termux-sms-tools
python termux-sms-spam-simple.py

import requests

headers = {
    "User-Agent": "MultiSpammer471/1.0 (by icon471)",
    "Content-Type": "application/json"
}
data = {"nomor": "628xxx", "pesan": "Halo!"}
r = requests.post("https://api.icon471.net/sms", json=data, headers=headers)

