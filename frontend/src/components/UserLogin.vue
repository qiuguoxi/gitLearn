<template>
  <div class="login-container">
    <h2>用户登录</h2>
    <form @submit.prevent="handleLogin">
      <div>
        <label for="username">用户名:</label>
        <input type="text" v-model="username" required />
      </div>
      <div>
        <label for="password">密码:</label>
        <input type="password" v-model="password" required />
      </div>
      <button type="submit">登录</button>
    </form>
    <p v-if="errorMessage" class="error">{{ errorMessage }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      username: '',
      password: '',
      errorMessage: ''
    };
  },
  methods: {
    handleLogin() {
      // 这里可以添加登录逻辑，例如调用 API
      if (this.username === 'admin' && this.password === 'password') {
        alert('登录成功！');
      } else {
        this.errorMessage = '用户名或密码错误';
      }
    }
  }
};
</script>

<style scoped>
.login-container {
  max-width: 300px;
  margin: auto;
}
.error {
  color: red;
}
</style>
