---
layout: base
title: Resume
description: Elliot Yang's Resume and Experience
permalink: /resume
hide: false
---

<div class="bg-gradient-to-br from-blue-50 to-white min-h-screen flex flex-col items-center justify-center p-8 space-y-12">

  <!-- Profile Section -->
  <div class="w-48 h-48 md:w-56 md:h-56 rounded-full overflow-hidden shadow-xl border-4 border-red-200 transform hover:scale-105 transition duration-300">
    <img src="{{site.baseurl}}/images/me.jpg" alt="Elliot Yang" class="w-full h-full object-cover object-center" />
  </div>

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
