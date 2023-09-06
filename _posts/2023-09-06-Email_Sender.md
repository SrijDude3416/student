---
title: Email Sender
layout: base
description: Use case of Javascript inputs and the 'mailto' href
permalink: /utils/emailsend
tags: [javascript]
courses: { compsci: {week: 3} }
type: hacks
---

<html>
<head>
  <title>Email Composer</title>
  <style>
    /* Add your CSS styles here */
    .email-input {
      padding: 10px;
      font-size: 16px;
    }

    .compose-button {
      padding: 10px 20px;
      font-size: 16px;
      background-color: #007bff;
      color: #fff;
      border: none;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <h1>Email Composer</h1>
  <input type="text" id="email-address" class="email-input" placeholder="Enter Gmail Address">
  <input type="text" id="subject" class="email-input" placeholder="Enter Subject">
  <input type="text" id="content" class="email-input" placeholder="Enter Content">
  <button id="compose-button" class="compose-button">Compose Email</button>

  <script>
    const composeButton = document.getElementById('compose-button');
    const emailAddressInput = document.getElementById('email-address');
    const subjectInput = document.getElementById('subject');
    const contentInput = document.getElementById('content');

    composeButton.addEventListener('click', () => {
      const emailAddress = emailAddressInput.value;
      const subjectContent = subjectInput.value;
      const bodyContent = contentInput.value;
      if (emailAddress.trim() !== '') {
        const mailtoLink = `mailto:${emailAddress}?subject=${subjectContent}&body=${bodyContent}`;
        window.location.href = mailtoLink;
      } else {
        alert('Please enter a Gmail address.');
      }
    });
  </script>
</body>
</html>
