# 🧠 Prostate MRI Projects

[![Docker](https://img.shields.io/badge/Docker-ready-blue)](https://hub.docker.com/u/zlzbme)
[![License](https://img.shields.io/badge/license-MIT-green)]()
[![Publication](https://img.shields.io/badge/DOI-10.1002/mp.18053-blue)](https://aapm.onlinelibrary.wiley.com/doi/10.1002/mp.18053)

This repository hosts a suite of **deep learning models for 3D prostate MRI analysis**, developed by the **Emory Empathetic AI for Health Institute / Madabhushi Lab** at *Emory University*.  
Each model is released as a **Dockerized image** for reproducible segmentation and biomarker analysis of prostate zones, gland, and clinically significant prostate cancer (csPCa).

---

## 🧩 Overview

| Model | Purpose | Input Modality | Docker Image | Citation |
|:------|:---------|:---------------|:--------------|:----------|
| **ProZonaNet** | Zonal segmentation (Transitional Zone / Peripheral Zone) | T2w axial MRI | [`zlzbme/zlz_prostate_mri_tzpz_seg`](https://hub.docker.com/r/zlzbme/zlz_prostate_mri_tzpz_seg) | *Zhang et al.*, *Medical Physics*, 2025 ([DOI: 10.1002/mp.18053](https://aapm.onlinelibrary.wiley.com/doi/10.1002/mp.18053)) |
| **ProStaNet (Gland)** | Whole-gland segmentation | T2w axial MRI | [`zlzbme/zlz_prostate_mri_gland_seg`](https://hub.docker.com/r/zlzbme/zlz_prostate_mri_gland_seg) | *Zhang et al.*, *J. Urology*, 2025 ([DOI: 10.1097/01.JU.0001110136.41716.b7.25](https://www.auajournals.org/doi/abs/10.1097/01.JU.0001110136.41716.b7.25)) |
| **ProStaNet (csPCa)** | Clinically significant prostate cancer segmentation | T2w + ADC (co-registered) MRI | [`zlzbme/zlz_prostate_mri_cspca_seg`](https://hub.docker.com/r/zlzbme/zlz_prostate_mri_cspca_seg) | *Zhang et al.*, *J. Urology*, 2025 ([DOI: 10.1097/01.JU.0001110136.41716.b7.25](https://www.auajournals.org/doi/abs/10.1097/01.JU.0001110136.41716.b7.25)) |

---

## 🧪 Model Usage

### 1️⃣ ProZonaNet — Prostate Zonal Segmentation (TZ/PZ)

Performs automatic segmentation of the **transitional (TZ)** and **peripheral (PZ)** zones from T2-weighted MRI.

**Pull the image:**
```bash
docker pull zlzbme/zlz_prostate_mri_tzpz_seg:latest
```

**Run example:**
```bash
docker run -it --name tzpz_seg_test   -v /path/to/your/data/mri:/usr/src/app/data   zlzbme/zlz_prostate_mri_tzpz_seg   --Data_dir /usr/src/app/data
```

**Citation:**
> Zhang, Z., Yang, Q., Shiradkar, R., Mirtti, T., Azamat, S., Xuan, K., Xu, J., & Madabhushi, A.  
> *A deep learning derived prostate zonal biomarker from T2-weighted MRI to distinguish between prostate cancer and benign prostatic hyperplasia.*  
> *Medical Physics*, 2025. DOI: [10.1002/mp.18053](https://aapm.onlinelibrary.wiley.com/doi/10.1002/mp.18053)

---

### 2️⃣ ProStaNet (Gland) — Whole Prostate Gland Segmentation

Performs 3D segmentation of the **entire prostate gland** from T2w axial MRI.

**Pull the image:**
```bash
docker pull zlzbme/zlz_prostate_mri_gland_seg:latest
```

**Run example:**
```bash
docker run -it --name gland_seg_test   -v /path/to/your/data/mri:/usr/src/app/data   zlzbme/zlz_prostate_mri_gland_seg   --Data_dir /usr/src/app/data
```

**Citation:**  
> Zhang et al., *ProStaNet: A multi-scale 3D feature pyramid network for automatic detection and segmentation of clinically significant prostate cancer (csPCa) on MRI.*  
> *Journal of Urology*, 2025. DOI: [10.1097/01.JU.0001110136.41716.b7.25](https://www.auajournals.org/doi/abs/10.1097/01.JU.0001110136.41716.b7.25)

---

### 3️⃣ ProStaNet (csPCa) — Clinically Significant Prostate Cancer Segmentation

Performs detection and segmentation of **clinically significant prostate cancer (csPCa)** using co-registered **T2w + ADC** MRI.

**Pull the image:**
```bash
docker pull zlzbme/zlz_prostate_mri_cspca_seg:latest
```

**Run example:**
```bash
docker run -it --name cspca_seg_test   -v /path/to/your/data:/usr/src/app/data/t2w (and adc)   zlzbme/zlz_prostate_mri_cspca_seg   --Data_dir /usr/src/app/data
```

**Citation:**  
> Zhang et al., *ProStaNet: A multi-scale 3D feature pyramid network for automatic detection and segmentation of clinically significant prostate cancer (csPCa) on MRI.*  
> *Journal of Urology*, 2025. DOI: [10.1097/01.JU.0001110136.41716.b7.25](https://www.auajournals.org/doi/abs/10.1097/01.JU.0001110136.41716.b7.25)

---

## 📚 Citation Summary

If you use these models in your research, please cite the following works:

- **Zonal segmentation (ProZonaNet):**  
  *Zhang et al.*, *Medical Physics*, 2025 — DOI: [10.1002/mp.18053](https://aapm.onlinelibrary.wiley.com/doi/10.1002/mp.18053)
- **Gland and csPCa segmentation (ProStaNet):**  
  *Zhang et al.*, *Journal of Urology*, 2025 — DOI: [10.1097/01.JU.0001110136.41716.b7.25](https://www.auajournals.org/doi/abs/10.1097/01.JU.0001110136.41716.b7.25)

---

## 📜 License

This project is released under the [MIT License](LICENSE).

---

## 🔗 Related Links

- [Docker Hub – zlzbme](https://hub.docker.com/u/zlzbme)
- [Medical Physics Paper (ProZonaNet)](https://aapm.onlinelibrary.wiley.com/doi/10.1002/mp.18053)
- [Journal of Urology Paper (ProStaNet)](https://www.auajournals.org/doi/abs/10.1097/01.JU.0001110136.41716.b7.25)

---

> © 2025 Emory Empathetic AI for Health Institute (https://aihealth.emory.edu/) / Madabhushi Lab (https://med.emory.edu/departments/radiology/research/research-labs/madabhushi-lab/index.html), Emory University  
> For academic and research use only.
























