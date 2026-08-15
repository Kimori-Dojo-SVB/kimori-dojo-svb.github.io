---
title: Contact Us
---

# Get in Touch

Have questions about Aikido or Kimori Dojo? We'd love to hear from you! Whether you're interested in joining, want to observe a class, or just have questions, please reach out.

## Quickest Ways to Contact Us

**Email:** <kimoridojo@gmail.com>

**Facebook:** [@kimoridojo](https://facebook.com/kimoridojo)

We typically respond to inquiries within 24 hours.

---

## Contact Form

Please fill out the form below and we'll get back to you shortly.

<form id="my-form" name="simple-contact-form" accept-charset="utf-8" action="https://formspree.io/f/xzbwdoag" method="post">
  <fieldset id="fs-frm-inputs">
    <label for="full-name">Full Name</label>
    <input type="text" name="name" id="full-name" placeholder="First and Last" required="">
    <label for="email-address">Email Address</label>
    <input type="email" name="_replyto" id="email-address" placeholder="email@domain.tld" required="">
    <label for="message">Message</label>
    <textarea rows="5" name="message" id="message" placeholder="I'm interested in Aikido, please contact me." required=""></textarea>
    <input type="hidden" name="_subject" id="email-subject" value="Contact Form Submission">
  </fieldset>
  <input id="my-form-button" type="submit" value="Submit">
  <p id="my-form-status"></p>
</form>

<!-- Place this script at the end of the body tag -->
<script>
    var form = document.getElementById("my-form");
    
    async function handleSubmit(event) {
      event.preventDefault();
      var status = document.getElementById("my-form-status");
      var data = new FormData(event.target);
      fetch(event.target.action, {
        method: form.method,
        body: data,
        headers: {
            'Accept': 'application/json'
        }
      }).then(response => {
        if (response.ok) {
          status.innerHTML = "Thanks for your interest! We will get back to you within 24 hours.";
          form.reset()
        } else {
          response.json().then(data => {
            if (Object.hasOwn(data, 'errors')) {
              status.innerHTML = data["errors"].map(error => error["message"]).join(", ")
            } else {
              status.innerHTML = "Oops! There was a problem submitting your form"
            }
          })
        }
      }).catch(error => {
        status.innerHTML = "Oops! There was a problem submitting your form"
      });
    }
    form.addEventListener("submit", handleSubmit)
</script>

