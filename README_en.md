# SODA: Social Platform Frontend

**Note:** This README documents my (Yiming Wang's) personal contributions to the soda-frontend module.  
> It is based on my fork of the original repository and is intended **solely for showcasing my work** for MS CS applications.  
> This is not an official documentation of the original project.

## Project Overview
SODA is a full-stack, small-scale social media platform featuring user authentication, posts, private messaging, and content recommendations. This repository contains the **frontend client** I designed and built, which is a Vue.js 3 application that communicates with a Django REST backend via API.

**Live Demonstration:** The complete system was deployed on a self-hosted Raspberry Pi server and successfully demonstrated to peers in a final course presentation, where users performed real-time registration, posting, searching, and chatting.

## My Role & Contributions
I was solely responsible for the design and implementation of the entire user authentication and profile management module, which formed the core user journey of the application. My key contributions include:

*   **Authentication System:** Built the complete login and registration workflows from scratch. Implemented client-side password hashing (SHA-256) as a basic security measure, inspired by concepts from a concurrent modern cryptography course.
*   **Profile Management:** Created the user profile view to display user-specific data and interact with backend services.
*   **Routing & Access Control:** Implemented application routing and navigation guards using Vue Router to prevent authenticated users from accessing auth pages.
*   **State & Session Management:** Engineered a lightweight session persistence system using localStorage to enable rapid development and minimal setup overhead for a small-scale application.
*   **UI/UX Implementation:** Developed all related views with a focus on usability, employing Tailwind CSS for responsive and consistent styling.

## Technology Stack & Implementation
*   **Framework:** Vue 3 (Composition API with `<script setup>`) to better organize reactive state and logic across multi-step authentication and profile-related views.
*   **Build Tool:** Vue CLI
*   **Routing:** Vue Router
*   **HTTP Client:** Axios for robust API communication
*   **Styling:** Utility-first Tailwind CSS
*   **Security:** CryptoJS for client-side SHA-256 hashing prior to credential transmission
*   **Deployment:** Served as static files alongside a separated backend service

## Key Features (Frontend)
1.  **User Authentication:** Secure login and registration flows with client-side hashing and session management.
2.  **Profile Interface:** Dedicated view for user profile presentation and interaction.
3.  **Client-Side Routing:** Seamless single-page application navigation with route protection.
4.  **Responsive UI:** Fully responsive interfaces built with Tailwind CSS.

## System Architecture Context
This frontend operates as an independent client within a **decoupled architecture**. It consumes a RESTful API from a separately maintained Django backend. My development process involved close coordination with backend developers to define and integrate API contracts for user data and authentication.

## Deployment & Outcome
The frontend was bundled and deployed with the backend onto a Raspberry Pi, serving as the project's demonstration environment. During the live presentation, multiple concurrent users validated the system's functionality by:
*   Creating accounts and logging in
*   Publishing and searching for posts
*   Initiating private chats
*   Exploring the recommendation feature

This demonstrated the robustness and usability of the implemented frontend features.

## Future Improvements
- Integrate a state management library (e.g., Pinia) to better handle complex and shared application states.
- Enhance security by deploying over HTTPS and introducing a more robust authentication mechanism, such as refresh token rotation.
- Formalize frontend–backend API contracts and introduce schema validation to improve long-term maintainability and team collaboration.
- Improve frontend observability by adding structured error logging and user-friendly failure recovery mechanisms.
- Automate frontend build and deployment processes to reduce manual configuration overhead and deployment errors.
- Conduct comprehensive accessibility auditing and improvements to ensure inclusive user experience.
- Add unit and component testing using Vitest or Vue Test Utils to improve reliability and regression safety.
---
**Backend Repository:** The corresponding Django backend API for this project can be found [here](https://github.com/oxygen-anoxia/soda-backend).
