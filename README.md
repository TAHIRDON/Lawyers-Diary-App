# Lawyer's Diary App

A modern, cross-platform diary application designed specifically for lawyers and legal professionals. This application allows users to securely manage case information, track hearing dates, and set reminders, with all data synchronized in real-time across both Windows and Android devices.

---

## Features

-   **Cross-Platform Sync:** Seamlessly access and manage your diary on both a native **Windows desktop app** and a dedicated **Android app**.
-   **Real-Time Database:** Built with **Google Firebase**, all your data is synchronized instantly across all your logged-in devices.
-   **Secure User Authentication:** Each user has a private and secure account (Email/Password login) to ensure all case data remains confidential. Includes a "Forgot Password" feature.
-   **Comprehensive Case Management:** Add, edit, and delete diary entries with detailed fields:
    -   Court Name & Case Number
    -   Case Section & Parties Involved
    -   Opposition Lawyer Name
    -   Stage of Case & Proceedings Summary
    -   Payment Tracking (Done & Remaining)
    -   Next Hearing Date & Tasks/To-Do
-   **Alarm & Notification System:** Set alarms for upcoming hearing dates to receive timely native notifications on your Android device.
-   **Permanent Dark Mode:** An easy-on-the-eyes dark theme is enabled by default for a comfortable user experience.
-   **Search Functionality:** Quickly find any entry by searching for case number, party name, court, and more.

---

## Tech Stack

-   **Backend & Desktop App:**
    -   **Python:** Core application logic.
    -   **Flask:** Serves the user interface.
    -   **pywebview:** Wraps the web UI into a native Windows executable.
-   **Frontend & Mobile App:**
    -   **HTML5, Tailwind CSS, JavaScript:** For the user interface and application logic.
    -   **Apache Cordova:** Used to compile the web frontend into a native Android `.apk`.
-   **Database & Authentication:**
    -   **Google Firebase:** Handles secure user authentication and provides a real-time Firestore database for data storage and synchronization.

---

## Setup & Installation

### Windows (`.exe`)

The application can be packaged into a standalone `.exe` file using PyInstaller.

1.  **Install dependencies:** `pip install flask pywebview appdirs`
2.  **Navigate to the project directory.**
3.  **Run the build command:**
    ```bash
    pyinstaller --onefile --windowed --add-data "templates;templates" "Lawyer's Diary.py"
    ```
4.  The executable will be available in the `dist/` folder.

### Android (`.apk`)

The application is packaged for Android using Apache Cordova.

1.  **Install prerequisites:** Node.js, Cordova CLI, Java JDK, and Android Studio.
2.  **Navigate to the Cordova project directory.**
3.  **Add the Android platform:** `cordova platform add android`
4.  **Install necessary plugins:**
    ```bash
    cordova plugin add cordova-plugin-splashscreen
    cordova plugin add cordova-plugin-local-notification
    ```
5.  **Place UI code** (`index.html`, icons, etc.) into the `www/` folder.
6.  **Configure `config.xml`** with the app name, icon, and platform preferences.
7.  **Run the build command:**
    ```bash
    cordova build android
    ```
8.  The installable `.apk` will be available in the `platforms/android/app/build/outputs/apk/debug/` folder.
