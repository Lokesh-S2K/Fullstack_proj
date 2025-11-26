# AutoPro: Full-Stack Car Dealership Platform

![License](https://img.shields.io/badge/License-MIT-blue.svg)
![React](https://img.shields.io/badge/Frontend-React-61DAFB.svg)
![Django](https://img.shields.io/badge/Backend-Django-092E20.svg)
![Node.js](https://img.shields.io/badge/Service-Node.js-339933.svg)
![Docker](https://img.shields.io/badge/Deployment-Docker-2496ED.svg)

**AutoPro** is a comprehensive, microservices-based web application that facilitates the car buying journey. It connects customers with dealerships through a centralized hub featuring detailed inventory listings, authentic user reviews, and automated sentiment analysis.

---

## 📖 Table of Contents
- [Problem Statement](#-problem-statement)
- [Architecture](#-architecture)
- [Tech Stack](#-tech-stack)
- [Key Features](#-key-features)
- [Getting Started](#-getting-started)
- [Microservices Breakdown](#-microservices-breakdown)
- [Future Roadmap](#-future-roadmap)

---

## 🚀 Problem Statement

The car buying experience is often fragmented. Customers struggle to find reliable dealership information and gauge public opinion through authentic reviews, while dealerships lack modern platforms to manage their reputation. 

**AutoPro solves this by providing:**
1. A centralized platform for dealership discovery.
2. Transparent, user-generated reviews.
3. Instant sentiment feedback using AI to help users gauge reputation at a glance.

---

## 🏗 Architecture

The application utilizes a **Microservices Architecture** to ensure scalability and separation of concerns.

```mermaid
graph TD
    User[User Browser] <-->|HTTP| Frontend[React Frontend]
    Frontend <-->|REST API| Django[Django Backend / API Gateway]
    Django <-->|Authentication| SQLite[(Auth DB)]
    Django <-->|Internal API| Node[Node.js Inventory Service]
    Django <-->|Internal API| Flask[Python Sentiment Service]
    Node <-->|Mongoose| Mongo[(MongoDB Cluster)]
    Flask -- Analysis --> NLTK[NLTK Library]
