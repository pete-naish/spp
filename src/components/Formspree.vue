<template>
  <form
    class="formspree"
    action="https://formspree.io/simplypurepilates@yahoo.co.uk"
    method="POST"
  >
    <input required type="text" name="name" placeholder="Name">
    <input required type="email" name="_replyto" placeholder="Email">
    <input required type="text" name="_replyto" placeholder="Mobile">
    <input type="text" name="_gotcha" style="display:none">
    <textarea required name="message" placeholder="Message"></textarea>
    <button type="submit">Send message</button>
  </form>
</template>

<script>

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.formspree {
  max-width: 450px;
  margin: 0 auto 65px;
  padding: 0 40px;
  input,
  textarea,
  button {
    border: 0;
    box-sizing: border-box;
    color: #404040;
    display: block;
    font-family: 'Nunito', sans-serif;
    font-size: 32px;
    margin: 0 0 30px;
    padding: 8px 20px;
    resize: none;
    width: 100%;
    &:focus {
      outline: none;
    }
  }
  button {
    background-color: #fff;
    color: #e75d64;
    transition: all .2s ease-out;
    &:hover {
      background-color: #e75d64;
      color: #fff;
      cursor: pointer;
      transition-duration: .1s;
    }
  }
  textarea {
    min-height: 250px;
  }
}
</style>
