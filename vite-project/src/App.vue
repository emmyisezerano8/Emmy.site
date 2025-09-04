<template>
  <div class="agasobanuyeshow">
    <header>
      <img src="https://www.google.com/imgres?q=agasobanuyeshow&imgurl=https%3A%2F%2Fyt3.googleusercontent.com%2Ffn7Z84nnl4RhFnswzU92faANJ3VMPvpOkQ8DWp3mF-a2SF-ziAXs--dGIFqZnlnY1jHxanRJiQ%3Ds900-c-k-c0x00ffffff-no-rj&imgrefurl=https%3A%2F%2Fwww.youtube.com%2F%40agasobanuyeshow-h4o&docid=79gNj8l5WB1yMM&tbnid=H9IAwfcseCaRGM&vet=12ahUKEwi72cuunKiPAxV_dUEAHahhGe8QM3oECGYQAA..i&w=900&h=900&hcb=2&itg=1&ved=2ahUKEwi72cuunKiPAxV_dUEAHahhGe8QM3oECGYQAA" alt="Agasobanuyeshow Logo" class="logo" />
      <h1>Agasobanuyeshow</h1>
    </header>
    <nav>
      <button @click="view = 'Home'">Home</button>
      <button @click="view = 'login'">Login</button>
      <button @click="view = 'signup'">Sign Up</button>
    </nav>
    <main>
      <section v-if="view === 'video'">
  <h2>Now Playing</h2>
  <div class="video-container">
    <iframe 
      width="100%" 
      height="369" 
      src="https://www.youtube.com/embed/ixcNR-FYIVc?list=RDGMEMECQexVIf8HjAQgdybEHXKw"
      title="un jour tu pleures un jour tu ris lyrics Julio Iglesias"
      frameborder="0"
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
      referrerpolicy="strict-origin-when-cross-origin"
      allowfullscreen>
    </iframe>
  </div>
</section>
  <button @click="view = 'video'">Watch Video</button>
      <section v-if="view === 'about'">
        <h2>About Us</h2>
        <p>Welcome to Agasobanuyeshow! We are dedicated to providing the best services.</p>
      </section>
      <section v-if="view === 'login'">
        <h2>Login</h2>
        <form @submit.prevent="login">
          <input v-model="loginForm.email" type="email" placeholder="Email" required />
          <input v-model="loginForm.password" type="password" placeholder="Password" required />
          <button type="submit">Login</button>
        </form>
      </section>
      <section v-if="view === 'signup'">
        <h2>Sign Up</h2>
        <form @submit.prevent="signup">
          <input v-model="signupForm.name" type="text" placeholder="Name" required />
          <input v-model="signupForm.email" type="email" placeholder="Email" required />
          <input v-model="signupForm.password" type="password" placeholder="Password" required />
          <input v-model="signupForm.comfirmPassword" type="password" placeholder="Confirm Password" required />
          <button type="submit">Sign Up</button>
        </form>
      </section>
    </main>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      view: "Home",
      loginForm: {
        email: "",
        password: ""
      },
      signupForm: {
        name: "",
        email: "",
        password: "",
        comfirmPassword: ""
      }
    };
  },
  methods: {
    login() {
      alert(`Logged in as ${this.loginForm.email}`);
    },
    signup() {
      alert(`Signed up as ${this.signupForm.name}`);
    }
  }
};
</script>

<style scoped>
.agasobanuyeshow {
  max-width: 400px;
  margin: auto;
  font-family: Arial, sans-serif;
  text-align: center;
}
.logo {
  width: 80px;
  margin-bottom: 10px;
}
nav button {
  margin: 5px;
  padding: 8px 16px;
  cursor: pointer;
}
form {
  display: flex;
  flex-direction: column;
  gap: 8px;
  margin-top: 10px;
}
input {
  padding: 6px;
  font-size: 1em;
}
button[type="submit"] {
  background: #007bff;
  color: white;
  border: none;
  padding: 8px;
  cursor: pointer;
}
</style>