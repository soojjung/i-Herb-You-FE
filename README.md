## 🎧 About Project

Project Name: **iHerbYou 🌿**

Introduction: iHerbYou is an online platform designed for health-conscious individuals to **quickly and affordably purchase the supplements they need**. <br />
Inspired by the strengths of iHerb, the project aims to provide a tailored service and seamless payment/shipping experience optimized for domestic users.

## 🚀 Tech Stack

- **Frontend**: React 19.1 + TypeScript + Vite 7.1
- **Routing**: React Router DOM v6.30
- **Styling**: Tailwind CSS (via CDN)
- **Fonts**: SUITE, Noto Sans KR
- **State Management**: React Context API (CartContext, ToastContext)
- **Build/Dev**: Vite Dev Server

## ✨ Installation

1. Node.js Version

   ```bash
   nvm use
   ```

Vite 7 recommends Node.js 20.19+ or 22.12+

2. Install Dependencies

   ```bash
   npm install
   ```

3. Start Development Server

   ```bash
   npm run dev
   ```

Open http://localhost:5173 in your browser

4. Production Build

   ```bash
   npm run build
   npm run preview
   ```

Note: Tailwind is used via CDN. There are no `tailwind.config.js` or `postcss.config.js` files.

## 📁 Project Structure

```text
.
├─ public/
│  ├─ images/                 # Static images (including favicon)
│  └─ policies/               # Terms & policy HTML files
├─ src/
│  ├─ components/             # UI components
│  ├─ contexts/               # Global state
│  ├─ pages/                  # Page components (20 pages)
│  ├─ lib/                    # API and business logic
│  ├─ data/                   # Category and product mock data
│  ├─ hooks/
│  │  └─ useScrollToTop.ts    # Scroll-to-top hook
│  ├─ index.css               # Global styles and font declarations
│  ├─ main.tsx                # Entry file
│  └─ App.tsx                 # Routing configuration
└─ index.html                 # Tailwind CDN and custom config
```

## ✨ Implemented Features

### 🏠 Main Page

- Top banner with "Don't show again today" (sessionStorage) feature
- Main banner carousel (auto-slide, arrows, dot navigation)
- Bestseller section (up to 8 items)
- New arrivals section
- Recommended recipes section

### 🔍 Search & Categories

- Category hover dropdown in header (main/sub/detail categories)
- Real-time search with search history management
- Save and delete recent search terms
- Product filtering and sorting by category
- Full brand list and brand-specific product browsing

### 🛒 Cart & Orders

- Add/edit/remove items from cart
- Quantity adjustment and selective removal
- Coupon application
- Points redemption
- Shipping address management (add/edit/delete/set default)
- Order form and checkout
- Real-time cart quantity badge update

### 👤 User Features

- Sign up (email/password/name/phone number)
- Login/Logout
- Password reset
- Email verification
- Route guards (access control for authenticated pages)

### 📦 My Page

- Order history
- Order details
- Shipping tracking
- Pending reviews list
- Written reviews list
- Edit/delete reviews
- Inquiry history
- Points earned/used history
- Available coupons
- Edit profile
- Account deletion

### 💚 Wishlist

- Add/remove product from wishlist
- View wishlist
- Share wishlist (generate share link)
- View shared wishlists

### 📝 Reviews & Q&A

- Write/edit/delete product reviews
- Upload review photos (up to 5)
- Review ratings (0.5-star increments)
- Report reviews
- Sort reviews (newest/highest rated/lowest rated)
- Write/edit/delete product Q&A
- Private Q&A feature
- Admin reply display

### 🎨 UI/UX

- Responsive design (mobile/tablet/desktop)
- Toast notification system
- Modal components (add to cart, write review, write Q&A, etc.)
- Loading state indicators
- Error handling and user feedback
- Auto scroll-to-top on navigation
- Product card hover effects
- Image lazy loading

## 🏗️ Architecture

### Context API

- **CartContext**: Global cart state management (add/remove/update quantity)
- **ToastContext**: Global toast notification management (success/error/info messages)

### API Layer (`src/lib/`)

All API calls are managed in the `src/lib/` directory, structured for real backend integration.

- Automatic auth token refresh
- Error handling and logout processing
- HttpOnly cookie-based token management

### Route Guards

- **GuestOnly**: Inaccessible when logged in (login/sign-up pages)
- **RequireAuth**: Login required (wishlist/my page)

## 📦 Data Notes

- `src/data/products.ts`: Mock data including categories, ratings, and review counts
- `src/data/categories.ts`: Structured main/sub/detail category data
- API responses follow the actual backend structure (auth, products, orders, etc.)

## 🧩 Known Notes

- **Tailwind CDN**: Since it's CDN-based, classes are applied instantly. Build-time Tailwind is recommended for production environments.
- **Node.js Version**: Vite 7 recommends Node.js 20.19+ or 22.12+.
- **Auth System**: Uses HttpOnly cookie-based JWT tokens (accessToken + refreshToken).
- **Session Management**: Login state managed via sessionStorage.
- **Images**: Product images are stored in the `public/images/` directory.
- **Responsive**: Supports mobile (sm), tablet (md), and desktop (lg, xl) breakpoints.

## 📄 License

This repository is a sample project for learning and experimentation purposes.
