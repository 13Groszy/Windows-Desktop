<template>
  <div id="Contact">
    <img src="../assets/mailbox.png" @click="contact = 1" />
    <p>Contact Me</p>
    <div v-if="this.contact != 0" class="container">
      <form @submit.prevent="sendEmail">
        <div>
          <img class="exit" src="../assets/xbutton.png" @click="contact = 0" />
          <p>
            If you are happy to contact me, use the form below and I promise to
            response as soon as possible.
          </p>
        </div>
        <label>Your name</label>
        <input
          type="text"
          v-model="name"
          name="name"
          placeholder="Your Name"
          maxlength="20"
          minlength="3"
        />
        <label>Email</label>
        <input
          type="email"
          v-model="email"
          name="email"
          placeholder="Your Email"
          maxlength="50"
          minlength="3"
        />
        <label>Message</label>
        <textarea
          name="message"
          v-model="message"
          cols="30"
          rows="5"
          placeholder="Message"
          maxlength="1000"
          minlength="3"
        >
        </textarea>

        <input type="submit" value="Send" />
      </form>
    </div>
  </div>
</template>

<script>
import emailjs from "emailjs-com";
export default {
  name: "ContactUs",
  data() {
    return {
      name: "",
      email: "",
      message: "",
      contact: 0,
    };
  },
  methods: {
    sendEmail(e) {
      try {
        emailjs.sendForm(
          "service_qmp3n2l",
          "template_rffulhf",
          e.target,
          "user_kjcnyN76EcurTGKooXXyo",
          {
            name: this.name,
            email: this.email,
            message: this.meessage,
          }
        );
      } catch (error) {
        console.log({ error });
      }
      this.name = "";
      this.email = "";
      this.message = "";
    },
  },
};
</script>

<style scoped>
* {
  box-sizing: border-box;
  z-index: 3;
}
label {
  float: left;
}
input[type="text"],
[type="email"],
textarea {
  width: 100%;
  padding: 12px;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
  margin-top: 6px;
  margin-bottom: 16px;
  resize: none;
}
input[type="submit"] {
  background-color: #2bae66ff;
  color: white;
  padding: 12px 20px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}
input[type="submit"]:hover {
  background-color: #195190ff;
}
.container {
  display: block;
  margin: auto;
  text-align: center;
  border-radius: 5px;
  background-color: #a2a2a1ff;
  padding: 20px;
  width: 30%;
  bottom: 25%;
  position: absolute;
  left: 30%;
  min-width: 400px;
  border: 1px solid black;
}
img {
  height: 70px;
  width: 70px;
  bottom: 60%;
  left: 20px;
  position: relative;
}
img:hover {
  opacity: 0.8;
}
p {
  color: white;
  font-weight: bold;
  font-size: 20px;
  left: 7px;
  top: -20px;
  position: relative;
}
.container p {
  color: black;
  font-size: 12px;
  top: 0;
  width: 90%;
}
.exit {
  position: absolute;
  top: 1%;
  left: 91%;
  width: 40px;
  height: 40px;
}
</style>