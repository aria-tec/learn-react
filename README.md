# 🚀 Kubernetes Dev Container Template

Template ini dirancang untuk memberikan lingkungan pengembangan Kubernetes yang instan, konsisten, dan otomatis di dalam **GitHub Codespaces**.

## 🏗️ Struktur Proyek & Fungsi File

| File / Folder | Fungsi |
| :--- | :--- |
| **`.devcontainer/`** | Folder utama konfigurasi lingkungan pengembangan. |
| 📄 `devcontainer.json` | **Pusat Kendali.** Mengatur fitur (Docker-in-Docker), reservasi port otomatis, ekstensi VS Code, dan perintah otomatis setelah container dibuat. |
| 📄 `Dockerfile` | **Blueprint Mesin.** Berisi instruksi dasar sistem operasi (Ubuntu Noble) dan tempat untuk instalasi kustom di masa depan. |
| **`yaml/`** | Folder penyimpanan manifest Kubernetes. |
| 📄 `nginx-lengkap.yaml` | Contoh manifest yang menggabungkan *Deployment* (aplikasi) dan *Service* (akses jaringan). |
| 📄 `README.md` | Dokumentasi panduan penggunaan template. |

---

## 🛠️ Fitur Utama

1.  **Port Reservation (VIP Access):**
    * Port `30000` & `30001` sudah dipesan untuk **Kubernetes NodePort**.
    * Port `8080` & `8081` disiapkan untuk fitur `kubectl port-forward`.
2.  **Auto-Scaling & Self-Healing:** Menggunakan objek *Deployment* untuk memastikan aplikasi selalu berjalan.
3.  **Infrastructure as Code:** Semua alat (kubectl, minikube, helm) terpasang otomatis melalui fitur *Dev Container*.

---

## 🚀 Cara Menggunakan

### 1. Memulai Cluster
Saat Codespace berhasil dibuka, cluster Minikube biasanya akan berjalan otomatis. Jika tidak, jalankan:
```bash
minikube start --driver=docker