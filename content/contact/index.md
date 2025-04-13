---
title: Contact Us
menu:
  main:
    weight: 70
type: single
---

{{% blocks/lead color="primary" %}}
Questions, Comments, Ideas?
Did you find a lost node and want to report it?

Contact Us Below!
{{% /blocks/lead %}}

{{< blocks/section color="white" >}}
<form action="https://formsubmit.co/n4jhcradio@gmail.com" method="POST">
  <div class="mb-3">
    <label for="InputEmail" class="form-label">Email address</label>
    <input name="email" type="email" class="form-control" id="InputEmail" aria-describedby="emailHelp">
    <div id="emailHelp" class="form-text">We'll never share your email with anyone else.</div>
  </div>
  <div class="mb-3">
    <label for="InputSubject" class="form-label">Subject</label>
    <input name="subject" type="string" class="form-control" id="InputSubject">
  </div>
  <div class="mb-3">
    <label for="InputBody" class="form-label">Body</label>
    <textarea name="body" type="string" class="form-control" id="InputBody" rows=10></textarea>
  </div>
  <button type="submit" class="btn btn-primary">Submit</button>
</form>
{{< /blocks/section >}}
