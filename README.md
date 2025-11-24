# Expense Application – Dockerized 3-Tier Deployment  
A fully containerized Expense Tracking application built using a **3-Tier Architecture**:

- **Frontend:** Static web app served through **Nginx**
- **Backend:** Node.js REST API
- **Database:** MySQL 8
- **Reverse Proxy:** Nginx routes `/api/*` to backend service

This project demonstrates how to deploy a complete web application using **Docker**, custom **Dockerfiles**, Docker networking, and Nginx reverse proxy.

---

## 🚀 Architecture Overview

Browser → Nginx (Frontend) → Backend (Node.js API) → MySQL Database


- The **frontend** container serves the React/Vite static content.
- The **backend** container exposes REST APIs for creating and retrieving transactions.
- The **mysql** container stores all expense data.
