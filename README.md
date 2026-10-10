# PORTWISE — Frontend Application
> **Integrated Port Logistics Management System (React SPA)**
> Built with **React 18**, **TypeScript 5.6**, **Vite 5.4**, **Tailwind CSS 3.4**, **Lucide Icons**, and **Recharts**.

---

## ⚓ Application Features & Views
- **Role-Based Access Control (RBAC)**: Dynamic UI rendering and navigation for 5 personas:
  - `ADMIN`
  - `PORT_AUTHORITY`
  - `SHIPPING_AGENT`
  - `CARGO_OWNER`
  - `LOGISTICS_OPERATOR`
- **One-Click Demo Logins**: Instant access to pre-seeded roles or full custom registration stored in the database.
- **Operational Dashboard (`/dashboard`)**: Key performance indicators, throughput charts, vessel distribution, and urgent alert center.
- **Vessel Operations (`/vessels`)**: Vessel directory, technical specs (LOA, draft, DWT), and vessel creation.
- **Berth Scheduling (`/schedules`)**: Interactive scheduling board with conflict warnings, approval/rejection workflows.
- **Cargo Tracking & Timeline (`/cargo`)**: Real-time milestone tracker (`REGISTERED` ➔ `CUSTOMS_CLEARED` ➔ `LOADED` ➔ `IN_TRANSIT` ➔ `DISCHARGED` ➔ `DELIVERED`).
- **Resource Management (`/resources`)**: Equipment allocation for quay cranes, tugboats, and harbor pilots.
- **Reports & Analytics (`/reports`)**: Operational throughput and CSV export.
- **Administration (`/users`, `/audit-logs`)**: User management and immutable audit history.

---

## 🔑 Pre-Seeded Demo Credentials
All seeded demo accounts share the password: **`Demo@12345`**

| Role | Email ID |
| :--- | :--- |
| **Administrator** | `admin@portwise.demo` |
| **Port Authority** | `portauthority@portwise.demo` |
| **Shipping Agent** | `agent@portwise.demo` |
| **Cargo Owner** | `cargo@portwise.demo` |
| **Logistics Operator** | `operator@portwise.demo` |

*(You can also use the **"Register New User"** tab on the login screen to create custom accounts stored directly in the database!)*

---

## 🚀 Getting Started

### 1. Install Dependencies
```powershell
npm install
```

### 2. Run in Development Mode
```powershell
npm run dev
```
The app will start at `http://localhost:5173` with Hot Module Replacement (HMR).

### 3. Production Build
```powershell
npm run build
```
Generates production assets in `dist/`.

---

## ⚙️ Environment Configuration
The frontend automatically proxies API calls to the backend on `http://localhost:8080/api/v1`.
You can customize the API endpoint via `.env`:
```env
VITE_API_BASE_URL=http://localhost:8080/api/v1
```

---

## 📁 Repository Structure
```
├── src/
│   ├── components/      # Reusable UI widgets (DemoBanner, Modal, StatusBadge, etc.)
│   ├── context/         # AuthContext (JWT session, RBAC helpers)
│   ├── layouts/         # DashboardLayout (Sidebar, Navbar, Outlet)
│   ├── pages/           # 18 Application views
│   ├── services/        # Axios API client with automatic Bearer tokens
│   ├── types/           # Domain TypeScript definitions
│   ├── App.tsx          # React Router v6 tree with route guards
│   ├── main.tsx
│   └── index.css
├── Dockerfile
├── nginx.conf
├── package.json
├── tailwind.config.js
├── tsconfig.json
└── vite.config.ts
```
