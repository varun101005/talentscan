# talentscan

# TalentScan – AI-Powered Resume Analyzer

## 🔧 Technologies Used
- **Android App**: Java (Resume upload, feedback display, recruiter dashboard)
- **Backend**: Spring Boot (Resume API, mocked NLP scoring, Firebase Firestore)
- **Database**: Firebase Firestore
- **NLP**: Mocked logic with hardcoded feedback (can be extended with spaCy/BERT)
- **Architecture Diagram**: Included (talentscan_architecture.png)

---

## 📱 Android App Features
- Select and upload PDF resume
- Get feedback (score, missing skills, suggestions)
- Save results to Firebase Firestore
- Recruiter Dashboard to view uploaded resumes

## 🌐 Spring Boot Backend
- `/api/upload` – Accepts resume file (PDF)
  - Parses text (mocked)
  - Returns NLP feedback (score, skills, recommendation)
  - Stores metadata + content in Firestore

## 🔥 Firebase Firestore
- Stores: filename, resume_text, score, missing_skills, recommendation, timestamp

## 📊 Recruiter Dashboard (Mobile)
- RecyclerView listing all submitted resumes
- Shows score and file name
- Pulls data from Firestore, ordered by timestamp

---

## 🚀 Setup Instructions

### Android
1. Add `google-services.json` in `app/` folder
2. Add to `build.gradle (project)`:
   ```groovy
   classpath 'com.google.gms:google-services:4.3.15'
   ```
3. Add to `build.gradle (app)`:
   ```groovy
   apply plugin: 'com.google.gms.google-services'
   implementation 'com.google.firebase:firebase-firestore:24.7.0'
   implementation 'com.squareup.okhttp3:okhttp:4.10.0'
   implementation 'org.json:json:20220320'
   ```
4. Connect Firebase in Android Studio

### Backend
1. Place your Firebase admin key in the root as `firebase-service-account.json`
2. Add dependencies in `pom.xml`:
   ```xml
   <dependency>
       <groupId>com.google.firebase</groupId>
       <artifactId>firebase-admin</artifactId>
       <version>9.1.1</version>
   </dependency>
   ```
3. Run the app: `mvn spring-boot:run`

---

## 📂 Deliverables
- Android project (Java)
- Spring Boot backend project
- Firebase integration (both app + backend)
- Recruiter dashboard
- Architecture diagram
- Documentation (this file)

