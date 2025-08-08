# YouTube Clone – Full Stack Video Sharing Platform

This project is a **full-stack YouTube clone** demonstrating scalable cloud architecture, automated video processing, and modern web development practices. Built with **TypeScript**, **Next.js**, and **Google Cloud Platform**, it allows users to upload, process, and stream videos with secure authentication and dynamic metadata management.

In addition to core video sharing features, the platform includes an **AI-powered content generation system** that automatically creates optimized video titles, descriptions, and thumbnails to improve discoverability and user engagement.

---

## Features
- **Cloud Storage Integration**  
  - Stores both raw and processed videos in Google Cloud Storage.
- **Automated Video Processing**  
  - Uses FFmpeg hosted on Cloud Run for video transcoding.
- **Event-Driven Workflow**  
  - Triggers processing pipelines via Google Cloud Pub/Sub.
- **Metadata Management**  
  - Stores and retrieves structured video details in Firestore.
- **Authentication**  
  - Secures user accounts with Firebase Auth.
- **Serverless Backend APIs**  
  - Handles business logic using Firebase Functions.
- **Modern Frontend**  
  - Built with Next.js and deployed on Cloud Run for a responsive YouTube-like experience.
- **AI Content Generation**  
  - Auto-generates engaging video titles, SEO-friendly descriptions, and thumbnails.

---

## Tech Stack
- **Frontend:** Next.js, TypeScript  
- **Backend:** Express.js, Firebase Functions  
- **Video Processing:** FFmpeg, Docker, Cloud Run  
- **Database:** Firestore  
- **Storage:** Google Cloud Storage  
- **Messaging:** Google Cloud Pub/Sub  
- **Authentication:** Firebase Auth  
- **AI Integration:** OpenAI API (titles/descriptions), custom thumbnail generation model  

---

## System Architecture
1. User uploads raw video → stored in Google Cloud Storage.  
2. Pub/Sub sends an event to the processing service.  
3. Cloud Run (private instance) processes/transcodes video with FFmpeg.  
4. Processed video is re-uploaded to Google Cloud Storage.  
5. AI service generates title, description, and thumbnail → stored in Firestore.  
6. Next.js frontend (on Cloud Run) requests video data from Firebase Functions.  
7. Firebase Functions return metadata and video stream to the client.

---

## Setup
- **Clone the repository**
  ```bash
  git clone https://github.com/your-username/youtube-clone.git
  cd youtube-clone
Install dependencies

bash
Copy
Edit
npm install
Configure environment variables

Set up Firebase, Google Cloud, Pub/Sub, and AI API keys in .env.

Run locally

bash
Copy
Edit
npm run dev
