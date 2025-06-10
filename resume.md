---
layout: base
title: Resume
description: Elliot Yang's Resume and Experience
permalink: /resume
hide: false
---

<div class="bg-gradient-to-br from-blue-50 to-white min-h-screen flex flex-col items-center justify-center p-8 space-y-12">

  <!-- Name + Role -->
  <div class="text-center space-y-1">
    <h1 class="text-3xl font-bold text-gray-800">Elliot Yang</h1>
    <p class="text-lg text-gray-600">High School Junior • Dashboard Developer • Intern @ Code Ninjas</p>
  </div>

  <!-- Contact Blocks -->
  <div class="w-full max-w-3xl grid grid-cols-1 md:grid-cols-3 gap-6">

    <!-- Email Card -->
    <div class="bg-white rounded-2xl border border-red-200 p-6 shadow-lg hover:shadow-xl transition text-center space-y-3">
      <img src="https://img.icons8.com/color/48/gmail.png" alt="Gmail" class="mx-auto w-10 h-10" />
      <p class="text-sm text-gray-500 font-medium">Email</p>
      <a href="mailto:elliotyschool@gmail.com" class="text-base font-semibold text-red-600 hover:underline">elliotyschool@gmail.com</a>
    </div>

    <!-- LinkedIn Card -->
    <div class="bg-white rounded-2xl border border-red-200 p-6 shadow-lg hover:shadow-xl transition text-center space-y-3">
      <img src="https://img.icons8.com/color/48/linkedin.png" alt="LinkedIn" class="mx-auto w-10 h-10" />
      <p class="text-sm text-gray-500 font-medium">LinkedIn</p>
      <a href="https://www.linkedin.com/in/elliot-yang-841686368" target="_blank" class="text-base font-semibold text-red-600 hover:underline">View Profile</a>
    </div>

    <!-- vCard Download -->
    <div class="bg-white rounded-2xl border border-red-200 p-6 shadow-lg hover:shadow-xl transition text-center space-y-3">
      <img src="https://img.icons8.com/fluency/48/download.png" alt="Download" class="mx-auto w-10 h-10" />
      <p class="text-sm text-gray-500 font-medium">vCard</p>
      <button onclick="downloadVCard()" class="text-base font-semibold text-red-600 hover:underline">Download Contact Card</button>
    </div>

  </div>

  <!-- Experience Section -->
  <div class="w-full max-w-4xl mt-16 space-y-8">
    <h2 class="text-2xl font-bold text-gray-800 text-center">Experience & Leadership</h2>

    <ul class="list-disc list-inside space-y-4 text-gray-700">
      <li><strong>President | Christians in Action</strong> – Leading faith-based initiatives, coordinating events, and mentoring fellow members.</li>
      <li><strong>VP | Jumpstart to Strings</strong> – Help manage curriculum and logistics for student cello instruction.</li>
      <li><strong>VP | Korean Student Association</strong> – Organize cultural events and foster community among Korean students.</li>
      <li><strong>Leader | Hanbit Church High School Praise Team</strong> (June 2024–Present) – Lead worship, schedule rehearsals, and guide a 14-member music team.</li>
      <li><strong>Volunteer | Torrey Pines Junior Guard</strong> (Summer 2023) – Assisted lifeguards in leading safety training and CPR instruction for 20–30 children.</li>
      <li><strong>Volunteer | Hanbit Korean School</strong> (Fall 2023–Present) – Support Korean language education through classroom assistance and cultural activities.</li>
      <li><strong>Instructor | Jumpstart</strong> (Fall 2023–Present) – Teach beginner cello students with a focus on fundamentals and musical growth.</li>
      <li><strong>Mission Volunteer | Ensenada Mission Trip</strong> (Summer 2024) – Renovated mission buildings and engaged in community outreach and evangelism.</li>
      <li><strong>Team Member | SCORE Competition</strong> – Coded a motion detection mechanism using Arduino IDE and presented to tech judges.</li>
      <li><strong>Member | Cyber CEO</strong> (Fall 2023–Present) – Taught cybersecurity basics to 60 students with engaging presentations and games.</li>
      <li><strong>Member | Fortissimo Challenge</strong> – Performed in benefit concert raising donations for Rady’s Children Hospital.</li>
      <li><strong>Cellist | Haussman Chamber Music Program</strong> (Spring 2024) – Performed in a trio setting with violin and piano.</li>
      <li><strong>Varsity Golfer | Del Norte High School</strong> (Spring 2023, Spring 2024) – Competed in matches and contributed to team spirit and performance.</li>
      <li><strong>Student | Summer Springboard: Biotechnology</strong> (Summer 2024)</li>
      <li><strong>Cellist | Pit Orchestra</strong> (Nov 2024–Feb 2025)</li>
      <li><strong>Cellist | San Diego Youth Symphony</strong> (Fall 2021–Summer 2023)</li>
      <li><strong>Volunteer | Vacation Bible School</strong> (Summer 2020–Present)</li>
      <li><strong>Member | Christians in Action</strong> (Aug 2024–Present)</li>
      <li><strong>Editor | MOZZ</strong> (March 2024–Present)</li>
      <li><strong>Intern | Code Ninjas</strong> – Code Sensei teaching young students to code through games and projects.</li>
      <li><strong>Mentee | NetSerpent LLC</strong> – Participating in mentorship related to tech and cybersecurity.</li>
    </ul>

    <h2 class="text-2xl font-bold text-gray-800 text-center mt-12">Awards</h2>
    <ul class="list-disc list-inside space-y-2 text-gray-700">
      <li>Scholar Athlete – Varsity Golf</li>
    </ul>
  </div>
</div>

<script>
function downloadVCard() {
  const vCardData = `BEGIN:VCARD
VERSION:3.0
FN:Elliot Yang
EMAIL:elliotyschool@gmail.com
TEL:+18583109480
URL:https://ellioty15.github.io/Elliot_2025/resume
NOTE:High school junior | Dashboard Developer | Intern at Code Ninjas
END:VCARD`;
  const blob = new Blob([vCardData], { type: 'text/vcard' });
  const url = window.URL.createObjectURL(blob);
  const a = document.createElement('a');
  a.href = url;
  a.download = 'elliot_yang_contact.vcf';
  document.body.appendChild(a);
  a.click();
  document.body.removeChild(a);
  window.URL.revokeObjectURL(url);
}
</script>
