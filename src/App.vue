<template>
  <div class="container fade-in">
    <h1>Ubah Password</h1>
    <div class="password-container">
      <label class="label" for="password">Password Baru</label>
      <input :class="{ 'input-field': true, 'input-error': password !== '' && password !== verifyPassword }" type="password" id="password" v-model="password">
    </div>
    <div class="password-container">
      <label class="label" for="verifyPassword">Verifikasi Password</label>
      <input :class="{ 'input-field': true, 'input-error': verifyPassword !== '' && password !== verifyPassword }" type="password" id="verifyPassword" v-model="verifyPassword">
      <div v-if="password === verifyPassword">
        <p class="password-match">Passwords match!</p>
      </div>
    </div>
    <div class="search-container">
      <label class="label" for="search">Search</label>
      <input class="input-field" type="text" id="search" v-model="search">
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      password: '',
      verifyPassword: '',
      search: '',
    }
  },
}
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center; 
  width: 100%;
  margin: 50%;
  padding: 10px;
  background-color:   #f4f4f4;
  border-radius: 10px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
}

.password-container {
  margin-bottom: 20px;
}

.search-container {
  margin-top: 20px;
}

.label {
  font-weight: bold;
  margin-bottom: 5px;
}

.input-field {
  width: 100%;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.input-field:focus {
  outline: none;
  border-color: #6c63ff;
  box-shadow: 0 0 5px rgba(108, 99, 255, 0.5);
}

.input-error {
  border-color: red;
}

.password-match {
  color: green;
  font-weight: bold;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

.fade-in {
  animation: fadeIn 0.5s ease-in-out;
}

</style>
