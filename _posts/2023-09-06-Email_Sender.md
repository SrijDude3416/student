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
    body {
      font-family: Arial, sans-serif;
      background-color: #f7f7f7;
      margin: 0;
      padding: 0;
    }
    h1 {
      background-color: #9A4CE6;
      color: #fff;
      padding: 20px;
      text-align: center;
    }
    .email-form {
      max-width: 400px;
      margin: 20px auto;
      padding: 30px; /* Increased left padding here */
      background-color: #fff;
      box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
    }
    .email-input {
      width: 100%;
      padding: 10px;
      font-size: 16px;
      margin-bottom: 10px;
      margin-left: 15px;
      border: 1px solid #ccc;
      resize: vertical;
      border-radius: 4px;
    }
    .compose-button {
      width: 100%;
      padding: 10px;
      font-size: 16px;
      background-color: #9A4CE6;
      color: #fff;
      border: none;
      border-radius: 4px;
      cursor: pointer;
    } 
    .compose-button:hover {
      background-color: #5F3574;
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
