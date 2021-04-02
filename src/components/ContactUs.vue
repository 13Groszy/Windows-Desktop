<template>
  <div id="Contact">
    <div class="container">
      <form @submit.prevent="sendEmail">
        <div>
          <img
            class="exit"
            src="../assets/xbutton.png"
            @click="$emit('closecontactus')"
          />
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
        alert("Thank you for your email, I'll response as soon as I can");
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
box-sizing:border-box;
z-index:3;
}

label {
float:left;
}

input[type="text"],[type="email"],textarea {
width:100%;
border:1px solid #ccc;
border-radius:4px;
box-sizing:border-box;
margin-top:6px;
margin-bottom:16px;
resize:none;
padding:12px;
}

input[type="submit"] {
background-color:#2bae66ff;
color:#FFF;
border:none;
border-radius:4px;
cursor:pointer;
padding:12px 20px;
}

input[type="submit"]:hover {
background-color:#195190ff;
}

.container {
display:block;
text-align:center;
border-radius:5px;
background-color:#a2a2a1ff;
width:30%;
bottom:25%;
position:absolute;
left:30%;
min-width:400px;
box-shadow:0 3px 10px rgba(0, 0, 0, 0.8);
margin:auto;
padding:20px;
}

p {
color:#000;
font-size:12px;
top:0;
width:90%;
font-weight:700;
}

.exit {
position:absolute;
top:1%;
left:93.5%;
width:20px;
height:20px;
}
</style>