

---

## Overview

**Ecom** is a fashion e-commerce website I built using the MERN stack (MongoDB, Express, React, Node.js). It has three parts: a customer storefront, a separate admin panel, and a REST API backend.

## What I Built

**Storefront**
On the customer side, users can browse products by category and subcategory, search and filter the collection, and open a product to see its details and available sizes. They can add items to the cart, register or log in, and place an order using Cash on Delivery, Stripe, or Razorpay. There's also an order history page where they can track what they've ordered.

**Admin Panel**
I made the admin panel as a separate React app. The admin logs in and can add or remove products, upload up to four images per product, and mark products as bestsellers. The admin can also see all orders placed on the site and update their status as they move along.

**Backend**
The backend is an Express server that handles authentication, products, cart operations, orders, and payments. Data is stored in MongoDB, and product images are uploaded to Cloudinary.

## Tech Stack

| Area | What I Used |
|---|---|
| Frontend | React 18, JavaScript (JSX), HTML, CSS |
| Admin panel | React 18, JavaScript (JSX) |
| Routing | React Router DOM |
| Styling | Tailwind CSS, PostCSS, Autoprefixer |
| Build tool | Vite |
| API calls | Axios |
| Notifications | React Toastify |
| Backend | Node.js, Express |
| Database | MongoDB (Atlas), with Mongoose |
| Authentication | JWT |
| Password hashing | bcrypt |
| Validation | Validator |
| File uploads | Multer |
| Image storage | Cloudinary |
| Payments | Stripe Checkout, Razorpay |
| Config | dotenv |
| CORS | cors package |
| Dev server | Nodemon |
| Deployment | Vercel |
| Linting | ESLint |

## How Everything Connects

```text
React Storefront ──┐
                   ├── Axios requests ──► Express REST API
React Admin Panel ─┘                          │
                                              ├── MongoDB (Mongoose)
                                              ├── Cloudinary
                                              ├── Stripe
                                              └── Razorpay
```

In the storefront, I used React Context to manage shared state like products, the cart, search, the auth token, and navigation. All requests to the backend go through Axios.

MongoDB stores users, products, orders, and carts. I used Cloudinary for images so I didn't have to store files on my own server.

For security, I used JWT to protect the cart and order routes, and bcrypt to hash passwords before saving them. The admin login works separately: the credentials are kept in environment variables and the admin gets their own JWT.

The storefront and admin panel each run on their own through Vite, and the backend runs as a separate Express server.

---

