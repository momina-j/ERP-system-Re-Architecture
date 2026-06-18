# ERP-system-Re-Architecture (Cloud → Offline)

A complete architectural overhaul of a cloud-based ERP system, re-engineered to run fully offline on a local server — built for a poultry farm business client.

## The Problem

The client was using a Supabase-powered ERP to manage their entire business — orders, vendors, deliveries, employees, brokers, and daily profits. The critical issue: **no internet = no system**. They needed the platform to run across 3 laptops with zero internet dependency, without losing any existing functionality or data.

## What I Did

This wasn't a simple migration. It was a **full architectural rethink** of the backend infrastructure.

### 🔄 Re-Architected the Database Layer
Replaced Supabase (cloud-hosted PostgreSQL) with **PGlite** — a full PostgreSQL engine that runs in-process with no server setup required. The entire schema (30+ tables) was preserved exactly, meaning all existing SQL queries continued to work without modification.

### 🔒 Retained Multi-Tenant Architecture
The original system used owner-based data isolation. This was fully preserved in the offline version — no data leakage between users or organizations.

### 📦 Built a Data Export/Import Pipeline
Designed and implemented a full export/import system enabling seamless data portability across 3 machines — ensuring no data loss during transfers between laptops.

### 📱 Mobile Responsive Overhaul
Optimized the entire UI from 320px to large desktop screens — touch-friendly buttons, responsive tables, and adaptive layouts across all pages.

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React, Tailwind CSS |
| Backend | Node.js, Express |
| Offline Database | PGlite (PostgreSQL WASM) |
| Original Cloud DB | Supabase (PostgreSQL) |
| Auth | bcryptjs, Role-Based Access Control |

## System Modules

The re-architected system manages 30+ database tables across these modules:

- **Order Management** — Create, track, and manage poultry orders with vendor and component breakdown
- **Vendor & Broker Management** — Track balances, payments, and transaction logs
- **Live Delivery Tracking** — Shopkeeper deliveries with weight, rate, and payment records
- **Employee Management** — Attendance, daily wages, and expense tracking
- **Daily Profit Dashboard** — Automated profit computation from deliveries and components
- **Freezer Stock Management** — Track stock by component with daily open/close records
- **Trader Management** — Jahangir traders ledger and entry tracking

## Key Takeaway

> Migration is never just a copy-paste job. Sometimes it's a full architectural rethink — replacing an entire infrastructure layer while keeping everything else intact.

## Project Context

Freelance client project for **Milad Solutions** — a poultry farm business in Pakistan.

> **Note:** Source code is confidential (client project). This README is for portfolio documentation purposes.
