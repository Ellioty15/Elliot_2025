---
layout: post
title: Personal Highlights, Retrospective Sprint 4
permalink: /retrospective/
toc: true
comments: true
---

# Project Retrospective: Sprint 4

## Project Context and Purpose
The sprint's purpose was to  implement accessiility elements with a user preferences system for the Open Coding Society, with the intent of improving how students interact with their course materials. 

The website is used by students across multiple computer science courses, including AP CSA and AP Computer Science Principles (AP CSP). Due to the diverse userbase, we created a system that would allow inclusivity and adaptation in the user experience.

---

## Team Collaboration and Roles
Working in a team required consistent coordination, shared responsibility, and clear communication. Each team member contributed to different aspects of the project, including planning, design, implementation, and testing.

My primary contributions focused on creating a backend API and creating a connection with the front end in order to save styles into a database. I I also contributed to the testing of styles and uniformity across the website.

By dividing tasks, we were able to maintain a shared understanding of the overall system while maximizing efficiency.

---

## Design History and Development Process
The project followed an intentional design progression that allowed us to move from abstract ideas to a functional working prototype.

In the backend, we looked at existing APIs and databases. Since we were more familiar with flask, we searched online in order to increase our understanding of the Spring structure.

As the project progressed, we began to create APIs and tested them. We used Postman in order to check if the APIs were receiving requests. 

Simutaneously, some of us were working on a database and establishing a connection to the frontend once the database was established. 
Due to bugs in the backend, our progress was slow, but we made sure to continue progressing. 

---

## Core Features and Technical Implementation

### Visual Preferences and Customization
The system allows students to customize text color, font family, font size, background color, and highlight color. These features help improve readability, reduce eye strain, and support different learning preferences.

By giving students control over the interface, the system removes unnecessary obstacles and allows them to focus on understanding the content rather than struggling with presentation.

---

### Preset Themes
To make customization more accessible, we implemented preset themes such as light mode, dark mode, and high-contrast mode. These themes provide quick, effective configurations for students who want immediate accessibility without manually adjusting individual settings.

---

### Translation Feature and Language Support
One of the most impactful components of the project was the translation feature. This tool was designed to help students who struggle with English better understand content on the teacher’s website.

The translation feature was especially beneficial for **AP CSP students**, many of whom relied heavily on translated explanations to understand instructions and concepts. Students who preferred learning in **Chinese** were able to engage more confidently with the material, reducing reliance on external help and increasing independence.

---

### Text-to-Speech Functionality
The text-to-speech feature allows students to listen to website content rather than only reading it. This supports auditory learners and students who benefit from hearing information presented aloud.

By offering multiple ways to consume content, the system aligns with inclusive learning principles and helps accommodate diverse learning styles.

---

### SASS Consolidation and Maintainability
From a technical standpoint, our team prioritized maintainability and scalability. We consolidated styling using SASS, organizing shared variables, mixins, and theme definitions to reduce redundancy.

This approach made the system easier to update and extend, ensuring that new themes or preference options could be added without rewriting large portions of the codebase.

---

## Impact on Students and Courses
The accessibility system had a meaningful impact on students using the teacher’s website. Students reported improved readability, reduced frustration, and greater confidence navigating course materials.

The impact was particularly noticeable in **AP CSP**, where the translation feature helped students overcome language barriers that previously limited their participation and understanding. By improving accessibility, the project supported more equitable learning experiences across courses.

---

## Reflection on Teamwork
I saw that everybody has their own strenghts, but we struggled to communicate progress between the frontend and backend. Also, the front end seemed to do more work because of how we split our project. I think that we can have one or two people working on the backend next sprint, and the rest can work on the front end.

---

## Reflection on Communication
Going forward, I plan to improve communication by documenting features more thoroughly, explaining design decisions clearly, and regularly updating collaborators on progress and challenges. I also want to communicate more frequently to Mr. Mortenson directly, since he is the owner and the product is only useful if the owner approves.

---

## Looking Ahead: The Next Chapter
I want to continue iterate on this project and improving my learning.
Issues with my system along with unfamiliarity to the device have caused me to struggle, but I am confident that going forward I will be able to be more productive with a stronger understanding of the system.

---

## Conclusion
Developing this accessibility and preferences system as part of an AP CSA team demonstrated the real-world impact that thoughtful software design can have in education. By developing user friendly feautures, I believe that user learning will be more efficient and enjoyable.