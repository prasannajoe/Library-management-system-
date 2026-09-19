# Smart Library Management System

A single-page library management system built with HTML, CSS and JavaScript. It runs fully in the browser: an SQL database (sql.js / SQLite) stores everything locally, and QR codes make issuing and returning books fast.

No server, build step or install is needed. Open `index.html` or host it on GitHub Pages or Netlify.

## Features

**Admin**
- Dashboard with totals, overdue books and unpaid fines
- Books: add, search, delete, cover image upload, category, shelf, QR code per book
- Students: add students, QR ID card
- Issue and return with a camera QR scanner
- Requests: approve (issues the book automatically) or reject
- Fines: collect cash or waive, plus payment history
- Reviews, reports (most issued books, top borrowers, category totals), CSV export of issue history
- Settings: library name, fine per day, loan days, max books, Razorpay Key ID
- SQL console for running queries on the database

**Student**
- Home dashboard: books held, due soon, overdue, unpaid fines
- Browse books, request, rate and read reviews
- My books with one-time 7-day renewal and CSV download
- My requests with cancel
- Fines and payments (demo payment or Razorpay test checkout)
- Profile, password change and ID QR code

**Other**
- Light and dark mode
- Fine: ₹50 per day after the due date (editable in Settings)

## Demo logins

| Role | ID | Password |
| --- | --- | --- |
| Admin | `admin` | `admin123` |
| Student | `STU001` (also `STU002`, `STU003`) | `student123` |

## Host on GitHub Pages

1. Create a new repository on GitHub.
2. Upload `index.html` and `README.md` to the top level of the repository (not inside a folder, and not as a zip).
3. Go to **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then save.
5. Wait a minute or two. The site link appears at the top of the Pages screen.

## Host on Netlify

Drag the folder that contains `index.html` onto https://app.netlify.com/drop.

## Razorpay (optional)

1. In the Razorpay dashboard, switch to Test Mode and copy the Key ID (starts with `rzp_test_`).
2. Log in as admin, open **Settings**, paste the Key ID and save.
3. Students will then see Razorpay as a payment option under **Fines & Payments**.

Only the Key ID is used. Never put the Key Secret in this project.

## Important limits

- Data is stored in the visitor's own browser (localStorage). It is not shared between devices or users.
- Logins are for demonstration only and are not secure. Do not store real personal data.
- Payments are not verified on a server. Use Razorpay test keys only, or add a small backend that creates orders and verifies signatures before using live keys.
- Libraries load from cdnjs (sql.js, qrcode.js, jsQR), so an internet connection is required.
- Camera scanning needs HTTPS, which GitHub Pages and Netlify both provide.

## Tech

HTML, CSS, vanilla JavaScript, [sql.js](https://github.com/sql-js/sql.js), [qrcodejs](https://github.com/davidshimjs/qrcodejs), [jsQR](https://github.com/cozmo/jsQR), Razorpay Checkout (optional).
