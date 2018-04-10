---
layout: page
current: contact
title: Контакт
navigation: true
logo: 'assets/images/ghost.png'
class: page-template
subclass: 'post page'
---

<form name="contact" method="POST" netlify>
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


