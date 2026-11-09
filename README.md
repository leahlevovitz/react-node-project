# 🛍️ Online Store: React + Node.js (MERN)

> A full-stack e-commerce web app: product catalog, shopping cart, checkout and an admin area, built with **React 19, Redux Toolkit, Node.js / Express 5 and MongoDB**.

![React](https://img.shields.io/badge/React-19-61DAFB?logo=react&logoColor=black)
![Redux](https://img.shields.io/badge/Redux_Toolkit-RTK_Query-764ABC?logo=redux&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-Express_5-339933?logo=nodedotjs&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-Mongoose-47A248?logo=mongodb&logoColor=white)
![JWT](https://img.shields.io/badge/Auth-JWT_%2B_bcrypt-000000?logo=jsonwebtokens&logoColor=white)

## ✨ Features
- 🏠 Home page and product catalog with images
- 🛒 Shopping cart: add, remove and update quantities, then checkout
- 🔐 Register and login with **JWT** authentication and **bcrypt**-hashed passwords
- 🛡️ **Role-based access**: admin-only routes for adding and managing products
- 🎨 Responsive UI with **PrimeReact** (DataView, Dialogs, Toasts)

## 🏗️ Architecture
```
client/  (React 19)                         server/  (Node.js + Express 5)
├── app/store.js        Redux store          ├── server.js          app entry, CORS, static images
├── app/apislice.js     RTK Query base       ├── routes/            auth · home (products) · basket
├── features/auth       login, register      ├── conroler/          controllers (business logic)
├── features/products   catalog, add product ├── middleware/        verifyJWT · admin (roles)
└── features/products/Bascet  cart, payment  ├── models/            User · Product · Basket (Mongoose)
                                             └── config/            DB connection, CORS options
```

**REST API**
| Method | Endpoint | Description |
|---|---|---|
| POST | `/api/authRout/register` | Create a user |
| POST | `/api/authRout/login` | Login and receive a JWT |
| GET | `/api/home` | List products |
| POST | `/api/bascet/addToBascet` | Add to cart 🔒 |
| PUT | `/api/bascet/updateQuentity` | Update quantity 🔒 |
| DELETE | `/api/bascet/:id` | Remove from cart 🔒 |

## 🚀 Run locally
```bash
# server
cd server
npm install
# create .env with: PORT, DATABASE_URI, TOKEN_SECRET
npm start

# client
cd ../client
npm install
npm start
```

---
👩‍💻 Built by **Leah Levovitz** · [LinkedIn](https://www.linkedin.com/in/leahlevovitz) · [GitHub](https://github.com/leahlevovitz)
