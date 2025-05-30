<script setup>
import linkedinIcon from './assets/linkedin.svg'
import facebookIcon from './assets/facebook.svg'
import twitterIcon from './assets/twitter.svg'
import instagramIcon from './assets/instagram.svg'
</script>

<template>
  <div class="app">
    <header>
      <nav>
        <router-link to="/">Home</router-link>
        <router-link to="/users">Users</router-link>
        <router-link to="/login">Login</router-link>
        <router-link to="/profile">Profile</router-link>
      </nav>
    </header>

    <main>
      <router-view v-slot="{ Component }">
        <component :is="Component" />
      </router-view>
    </main>

    <footer>
      <div class="social-links">
        <a href="#" class="social-link">
          <img :src="facebookIcon" alt="Facebook" />
        </a>
        <a href="#" class="social-link">
          <img :src="twitterIcon" alt="Twitter" />
        </a>
        <a href="#" class="social-link">
          <img :src="instagramIcon" alt="Instagram" />
        </a>
        <a href="#" class="social-link">
          <img :src="linkedinIcon" alt="LinkedIn" />
        </a>
      </div>
      <p>© 2024 Your Company. All rights reserved.</p>
    </footer>
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
  background-color: #ffffff;
  min-height: 100vh;
  color: #333333;
}

#app {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

main {
  flex: 1;
  padding-bottom: 40px;
  margin-top: 60px;
}

header {
  background: white;
  padding: 16px 0;
  box-shadow: 0 1px 2px rgba(0,0,0,0.1);
  width: 100%;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 100;
}

nav {
  max-width: 1152px;
  margin: 0 auto;
  display: flex;
  justify-content: flex-end;
  gap: 32px;
  padding: 0 16px;
}

nav a {
  text-decoration: none;
  color: #333333;
  font-weight: 500;
  font-size: 16px;
  line-height: 24px;
  position: relative;
}

nav a.router-link-active {
  color: #FF6464;
}

footer {
  background: white;
  padding: 32px 0;
  margin-top: auto;
}

.social-links {
  display: flex;
  justify-content: center;
  gap: 35px;
  margin-bottom: 26px;
}

.social-link img {
  width: 30px;
  height: 30px;
}

footer p {
  text-align: center;
  color: #333333;
  font-size: 14px;
  line-height: 21px;
}

nav a::after {
  content: '';
  position: absolute;
  bottom: -4px;
  left: 0;
  width: 0;
  height: 2px;
  background-color: #FF6464;
}

nav a.router-link-active::after {
  width: 100%;
}
</style>