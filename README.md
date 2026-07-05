# 🏔️ Trail Assist
# ![Status](https://img.shields.io/badge/Status-In%20Progress-yellow)

> **Connect. Explore. Adventure.**  
> A modern trekking and adventure platform that connects travelers with trails, local guides, hotels, rental services and travel agencies.

---

## 📱 About the App

Trail Assist is a cross-platform mobile application built for trekkers and adventure travelers. The app bridges the gap between travelers and local service providers. Helping users discover trekking trails, access essential trail information, and connect with nearby services like guides, hotels, rentals and travel agencies all in one place.

### ✨ Key Highlights

-  Discover trekking trails and tourist destinations with maps and essential info
-  Connect with verified local guides for a safe trekking experience
-  Find nearby hotels and accommodation along the trail
-  Access rental services and travel agencies in the area
-  Role-based accounts for Travelers and Partners (Guide, Hotel, Rental, Travel Agency)
-  Secure authentication with JWT
-  Partner profiles with images and verified documents

---

## 📸 Screenshots
### APIs
<p align="center">
  <img src="https://github.com/user-attachments/assets/478e43c4-6d88-41f5-9a40-af9551469569" width="900">
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/853fe32d-4016-430e-8eca-41d3147bfece" width="900">
</p>



<p align="center">
  <img src="https://github.com/user-attachments/assets/d9aaf356-5fea-4f01-aea5-2051f1590609" width="700">
</p>

### MongoDb
<p align="center">
  <img src="https://github.com/user-attachments/assets/e442a0d9-3dba-4ede-b34b-35328c42e028" width="900">
</p>
---

### Mobile ![Status](https://img.shields.io/badge/Status-In%20Progress-yellow)

<p align="center">
  <img src="https://github.com/user-attachments/assets/d46dab87-289b-40ea-944b-478414111909" width="220">
  <img src="https://github.com/user-attachments/assets/2fe89750-8e71-4db3-83f0-f8fc229d6bc2" width="220">
</p>
---

## 🛠️ Tech Stack

### Mobile (Client)
| Technology | Purpose |
|------------|---------|
| Flutter | Cross-platform mobile development |
| Provider | State management |
| Dio | HTTP client / API communication |
| Flutter Secure Storage | Secure JWT token storage |
| Image Picker | Profile image and document uploads |
| Navigator | Screen routing and navigation |
| Shared preferences | Client Side data storage |
| cached_network_image | Image cashing |

### Backend (Server)
| Technology | Purpose |
|------------|---------|
| Node.js | Runtime environment |
| Express.js | REST API framework |
| MongoDB | Database |
| JWT | Authentication |
| Multer | Multipart file handling |
| Cloudinary | Cloud media storage |
| Vercel | Deployment |

---


## 📁 Backend Folder Structure

```
trailassist-backend/
│
├── src/
│   ├── controllers/
│   │   ├── destinationsControllers/
│   │   │   ├── getProfileController.js
│   │   │   ├── hotelController.js
│   │   │   ├── loginPartnerController.js
│   │   │   ├── loginUserController.js
│   │   │   ├── partnerController.js
│   │   │   ├── serviceController.js
│   │   │   └── userController.js
│   │
│   ├── db/
│   │   └── index.js
│   │
│   ├── middlewares/
│   │   ├── auth.middleware.js
│   │   └── multer.middleware.js
│   │
│   ├── models/
│   │   ├── destinations/
│   │   ├── partner.model.js
│   │   └── user.model.js
│   │
│   ├── routes/
│   │   ├── destinations.routes.js
│   │   ├── hotels.routes.js
│   │   ├── partner.routes.js
│   │   ├── services.routes.js
│   │   └── user.routes.js
│   │
│   └── utils/
│       ├── cloudinary.js
│       └── uploadToCloudinary.js
│
├── app.js
├── constants.js
├── index.js
├── vercel.json
└── .env
```

---

## 📁 Flutter Folder Structure

```
trail_assist/
│
├── lib/
│   ├── Api/
│   │   ├── Models/
│   │   │   ├── apiClient.dart
│   │   │   ├── apiConstants.dart
│   │   │   └── authRepo.dart
│   │
│   ├── models/
│   │   ├── destinationsModel.dart
│   │   ├── hotelsModel.dart
│   │   ├── loginResponseModel.dart
│   │   ├── partnersModel.dart
│   │   ├── servicesModels.dart
│   │   └── usersModel.dart
│   │
│   ├── screens/
│   │   ├── HomeScreens/
│   │   ├── LoginScreens/
│   │   ├── RegisterScreens/
│   │   └── Widgets/
│   │       └── splashScreen.dart
│   │
│   ├── Theme/
│   │   ├── colorRes.dart
│   │   └── textStyles.dart
│   │
│   └── utils/
│       ├── animatedDot.dart
│       ├── secureStorage.dart
│       ├── sessionManager.dart
│       ├── constants.dart
│       ├── generalimports.dart
│       └── main.dart
```

---

##  API Overview

### User Routes `/api/v1/users`
| Method | Endpoint | Description | Auth |
|--------|----------|-------------|------|
| POST | `/register` | Register a new user | ❌ |
| POST | `/login` | Login user | ❌ |
| GET | `/me` | Get current user profile | ✅ |

### Partner Routes `/api/v1/partners`
| Method | Endpoint | Description | Auth |
|--------|----------|-------------|------|
| POST | `/register` | Register a new partner | ❌ |
| POST | `/login` | Login partner | ❌ |
| GET | `/me` | Get current partner profile | ✅ |

### Destination Routes `/api/v1/destinations`
| Method | Endpoint | Description | Auth |
|--------|----------|-------------|------|
| GET | `/` | Get all destinations | ✅ |

### Hotel Routes `/api/v1/hotels`
| Method | Endpoint | Description | Auth |
|--------|----------|-------------|------|
| GET | `/` | Get nearby hotels | ✅ |

### Service Routes `/api/v1/services`
| Method | Endpoint | Description | Auth |
|--------|----------|-------------|------|
| GET | `/` | Get nearby services | ✅ |

---

##  User Roles

| Role | Type | Description |
|------|------|-------------|
| User | Traveler | Discovers trails and connects with services |
| Guide | Partner | Offers guided trekking experiences |
| Hotel | Partner | Provides accommodation near trails |
| Rental | Partner | Offers gear and vehicle rentals |
| Travel Agency | Partner | Provides complete travel packages |

---

##  Authentication Flow for mobile app

```
App Launch
    ↓
Read JWT from Secure Storage
    ↓
No Token → Login Screen
    ↓
Token Found → Call /me
    ↓
200 OK → Home Screen
    ↓
401 Unauthorized → Delete Token → Login Screen
```



---

##  Developer

**Shivam Bari**    
📧 shivambari082@gmail.com  
🔗 [LinkedIn](https://linkedin.com/in/shivam-kumar-bari/)  
🐙 [GitHub](https://github.com/ShivamBari2728)

---

>  This repository showcases the project structure and documentation. Source code is kept private.
