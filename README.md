Student Learning System – README

This project is a PHP-based Student Learning System that allows students to access lessons, exercises, downloads, quizzes, and other resources after logging into the platform. It features simple routing logic, session-based authentication, and modular page rendering.

📌 Features
🔐 User Authentication

Students must log in before accessing the system.

Session-based access control.

Automatic redirection for unauthorized users.

🧭 Dynamic Page Routing

The system uses a parameter ?q= to load different content pages:

lesson – View available lessons

exercises – Practice exercises

download – Download materials

about – About the system

playvideo – Watch lesson videos

viewpdf – Open PDF resources

question – Quiz questions

quizresult – Quiz results

Default: Home page

🧱 Modular Template System

All content pages load inside a global template:

theme/templates.php

🗂 Clean Folder Structure
/include
/theme
/home.php
/lesson.php
/exercises.php
...

🚀 How It Works
1. Session Check

If $_SESSION['StudentID'] is not found, the system redirects the user to login.php.

2. Routing Logic

The page is determined using:

?q=lesson
?q=exercises
?q=playvideo


Only defined routes are allowed for security.

3. Template Rendering

The selected content is injected into a global template.

📁 Core Routing Code
$content = 'home.php';
$view = (isset($_GET['q']) && $_GET['q'] != '') ? $_GET['q'] : '';

switch ($view) {
    case 'lesson':
        $title = "Lesson";
        $content = 'lesson.php';
        break;
    case 'exercises':
        $title = "Exercises";
        $content = 'exercises.php';
        break;
    case 'download':
        $title = "Download";
        $content = 'download.php';
        break;
    case 'about':
        $title = "About Us";
        $content = 'about.php';
        break;
    case 'playvideo':
        $title = "Play Video";
        $content = 'playvideo.php';
        break;
    case 'viewpdf':
        $title = "View PDF";
        $content = 'viewpdf.php';
        break;
    case 'question':
        $title = "Question";
        $content = 'question.php';
        break;
    case 'quizresult':
        $title = "Result";
        $content = 'quizresult.php';
        break;
    default:
        $title = "Home";
        $content = 'home.php';
}

🔧 Installation

Clone or download the project.

Place it in your local server directory:

XAMPP → htdocs/

WAMP → www/

Import the database (if provided).

Configure database settings in:

include/initialize.php


Run the project in your browser:

http://localhost/yourproject/

🤝 Contributing

Feel free to submit improvements such as:

Improved UI/UX

Better routing

Security enhancements

OOP architecture

📜 License

This project is for educational purposes and can be freely modified.
