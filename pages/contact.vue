<template>
  <div>
    <h1>Contact Us</h1>
    <form @submit.prevent="submitForm">
      <div>
        <label for="name">Name:</label>
        <input v-model="form.name" type="text" id="name" />
      </div>
      <div>
        <label for="email">Email:</label>
        <input v-model="form.email" type="email" id="email" />
      </div>
      <div>
        <label for="message">Message:</label>
        <textarea v-model="form.message" id="message"></textarea>
      </div>
      <div>
        <button type="submit">Submit</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        name: '',
        email: '',
        message: '',
      },
      errors: []
    };
  },
  methods: {
    async submitForm() {
      try {
        await this.$axios.$post('/api/send', this.form); // APIエンドポイントは仮です。
      } catch (e) {
        this.errors.push(e);
      }
    }
  }
};
</script>

<style>
/* 任意のスタイル */
</style>
