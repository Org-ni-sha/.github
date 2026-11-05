<div align="center">

# DATAra

**A Machine Learning-Based Mobile Data Depletion Prediction System for Prepaid Users**

*BSIT Capstone Project — University of Science and Technology of Southern Philippines, Cagayan de Oro City*

</div>

---

## About

DATAra forecasts when your mobile data use will reach an amount you choose. You set a quota in MB or GB, the app measures the mobile data this phone actually uses (uploads and downloads, including promo freebies, never Wi-Fi), and it estimates the **PET (predicted time to quota)**: when your usage will reach that quota.

DATAra does not read your carrier balance, does not read SMS, and never blocks or limits your connection. Reaching a quota is information, not a cutoff.

**How the forecast works:**

- A **Global XGBoost model**, trained on data from study participants, predicts how much mobile data you will use in the next hour. It uses time of day and week, your recent hourly usage, and network conditions: signal strength, radio generation (2G–5G) and how much of the time you are on mobile data.
- The app steps forward hour by hour from your remaining quota until the predicted usage reaches it. That hour is the PET, capped at 30 days.
- A **local personalization layer** learns from your own hourly prediction errors and corrects the global prediction. The app switches to it after about 7 days, only while it is more accurate than the global model, and switches back when it is not.
- All prediction runs **on the phone** with ONNX Runtime. No usage data is sent anywhere to get a forecast.

---

## Repositories

| Repo | Description | Status |
|---|---|---|
| [`datara-android`](https://github.com/Org-ni-sha/datara-android) | The Android app: Kotlin, Jetpack Compose, Room, Supabase. Quota cycles, usage tracking and on-device forecasting are working. | 🚧 In development |
| [`data-harvester`](https://github.com/Org-ni-sha/data-harvester) | Standalone Android app that collects the training dataset from study participants (v1.6.8) | ✅ Complete · data collection ongoing |
| [`datara-ml`](https://github.com/Org-ni-sha/datara-ml) | Python pipeline: harvester data cleaning, the model's feature definitions, XGBoost training and ONNX export | 🚧 In development · interim model trained |

---

## Tech Stack

- **App:** Kotlin, Jetpack Compose (Material 3), MVVM, Hilt, Room, WorkManager, Vico charts
- **On-device ML:** ONNX Runtime (Android), running the exported XGBoost model
- **Backend:** Supabase (Postgres with row-level security, Auth, Storage)
- **ML pipeline:** Python, pandas, NumPy, XGBoost, onnxmltools
- **Design:** Figma / Google Stitch

---

## Team

| Name |
|---|
| Obial, Gilliand M. |
| Omongos, Charlie C. |
| Montejo, Cyber Storm V. |
| Gamayon, Dennis P. |
| De La Peña, Kristine Nicole C. |

**BS Information Technology — S.Y. 2025–2026**
University of Science and Technology of Southern Philippines, Cagayan de Oro City

---

## Getting Started

Each repo has its own setup instructions in its README. For contribution conventions (branching, commit format, PR process) shared across all repos, see [`CONTRIBUTING.md`](https://github.com/Org-ni-sha/datara-android/blob/main/CONTRIBUTING.md) in `datara-android`.
