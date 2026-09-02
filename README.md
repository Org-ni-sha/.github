<div align="center">

# DATAra

**A Machine Learning-Based Mobile Data Depletion Prediction System for Prepaid Users**

*BSIT Capstone Project — University of Science and Technology of Southern Philippines, Cagayan de Oro City*

</div>

---

## About

Most prepaid mobile users know how much data they have left, but not how fast it's actually disappearing. DATAra predicts a user's **Probable Exhaustion Time (PET)** — when their mobile data will actually run out — by learning from real usage behavior, time-based patterns, and network conditions like signal strength and internet speed, instead of relying on static balance checks and promo expiry dates.

The system uses a dual-layer prediction model: a pre-trained **Global XGBoost model** provides baseline predictions for new users, which is then personalized over time by a **Local model** trained on each user's own consumption history.

---

## Repositories

| Repo | Description | Status |
|---|---|---|
| [`datara-android`](../../datara-android) | The main Android app — Kotlin, Jetpack Compose, Supabase backend | 🚧 In development |
| [`data-harvester`](../../data-harvester) | Standalone Android app used to collect the initial training dataset from real users | ✅ Complete |
| `datara-ml` | Python pipeline for data cleaning, XGBoost training, and model export | 📋 Planned |

---

## Tech Stack

- **App:** Kotlin, Jetpack Compose, Room, Hilt, MVVM
- **Backend:** Supabase (Postgres, Auth, Storage)
- **ML:** Python, pandas, scikit-learn, XGBoost, ONNX Runtime (on-device inference)
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

Each repo has its own setup instructions in its README. For contribution conventions (branching, commit format, PR process) shared across all repos, see [`CONTRIBUTING.md`](../../datara-android/blob/main/CONTRIBUTING.md) in `datara-android`.
