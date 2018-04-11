---
layout: page
current: contact
title: Надіслати повідомлення
navigation: true
logo: 'assets/images/ghost.png'
class: page-template
subclass: 'post page'
---

<form name="contact" netlify-honeypot="bot-field" method="POST" action="thank-you" netlify>
    <p class="hidden">
    <label>Don’t fill this out if you're human: <input name="bot-field"></label>
  </p>
  <p>
    <label>Ваше Ім'я: <input type="text" name="name"></label>   
  </p>
  <p>
    <label>Ваш Email: <input type="email" name="email"></label>
  </p>
  <p>
    <label>Повідомлення: <textarea name="message"></textarea></label>
  </p>
  <div data-netlify-recaptcha></div>
  <p>
    <button type="submit">Надіслати</button>
  </p>
</form>


