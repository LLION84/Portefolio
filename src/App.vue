<template>
  <header>
    <a href="">
      <img
        src="../image/MonLogo.png"
        alt="Logo du portfolio"
        class="profile-img"
      />
    </a>
  </header>
</template>

<script setup></script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@700&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@400;500&display=swap");

h1,
h2,
h3,
h4,
h5,
h6 {
  font-family: "Poppins", sans-serif;
  font-weight: 700;
  color: #12110f;
}
body {
  background-color: #feecd4f2;
}
header {
  padding: 20px;
  text-align: center;
}
.profile-img {
  width: 100px;
  height: auto;
  border: 5px solid #4d3c2f;
  border-radius: 15px;
  padding: 2px;
  box-shadow: 0 4px 8px #322922;
  transition: all 0.3s ease;
}
.profile-img:hover {
  box-shadow: 0 6px 16px #28211d;
  transform: scale(1.05);
}
</style>
