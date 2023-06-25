<template>
  <div>

    <form name="contactone" method="POST" data-netlify="true">

      <input type="hidden" name="form-name" value="contactone">

      <p>
      <label>Your Name: <input type="text" name="name" /></label>
      </p>

      <p>
        <label>Your Email: <input type="email" name="email" /></label>
      </p>

      <p>
        <label>Message: <textarea name="message"></textarea></label>
      </p>

      <p>
        <button type="submit">Send</button>
      </p>

    </form>

    <!-- <NuxtWelcome /> -->
  </div>
</template>
