<template>
  <div class="container mx-auto px-4 text-center md:pb-8 lg:pb-16">
    <h1 class="text-2xl mt-4 md:mt-8 lg:mt-16 mb-1 text-gray-700">Contact</h1>
    <h3 class="text-xs font-light mb-6 md:mb-12">Full-stack Web Development</h3>
    <div class="container mx-auto px-4 flex justify-center mb-6 md:mb-12">
      <img class="w-7/12 md:w-5/12 lg:w-4/12" src="~/assets/img/contact.svg" alt="functions" />
    </div>

    <div
      class="w-full md:w-1/2 mx-auto text-left font-light border border-gray-300 shadow bg-gray-200 p-4 rounded"
    >
      <form
        ref="contactForm"
        action="https://formspree.io/xjvvabkp"
        method="POST"
        @submit.prevent="handleSubmit"
      >
        <div class="mb-4">
          <label for="name" class="block">Name</label>
          <input
            type="text"
            class="w-full p-2 outline-none border boder-gray-400 rounded"
            :class="{ 'border-green-500': (name.valid === true), 'border-red-500':(name.valid === false) }"
            id="name"
            name="name"
            v-model="name.value"
            @blur="validateName"
          />
          <small v-if="name.error" class="w-full text-sm text-red-500">{{ name.error }}</small>
        </div>

        <div class="mb-4">
          <label for="email" class="block">Email</label>
          <input
            type="email"
            class="w-full p-2 outline-none border boder-gray-400 rounded"
            :class="{ 'border-green-500': (email.valid === true), 'border-red-500':(email.valid === false) }"
            id="email"
            name="reply_to"
            v-model="email.value"
            @blur="validateEmail"
          />
          <small v-if="email.error" class="w-full text-sm text-red-500">{{ email.error }}</small>
        </div>

        <div class>
          <label for="message" class="block">Message</label>
          <textarea
            class="w-full p-2 outline-none border boder-gray-400 rounded"
            :class="{ 'border-green-500': (message.valid === true), 'border-red-500':(message.valid === false) }"
            rows="4"
            id="message"
            name="message"
            v-model="message.value"
            @blur="validateMessage"
          ></textarea>
          <small v-if="message.error" class="w-full text-sm text-red-500">{{ message.error }}</small>
        </div>

        <div class="text-right my-6">
          <button
            type="submit"
            @click.prevent="handleSubmit"
            class="border border-green-400 px-3 py-2 bg-green-400 text-white rounded outline-none"
          >Send</button>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: {
        value: '',
        error: '',
        valid: null
      },
      email: {
        value: '',
        error: '',
        valid: null
      },
      message: {
        value: '',
        error: '',
        valid: null
      }
    }
  },
  methods: {
    validateName() {
      if (this.name.value) {
        this.name.error = ''
        this.name.valid = true
        return true
      } else {
        this.name.error = 'Name is required'
        this.name.valid = false
        return false
      }
    },
    validateEmail() {
      if (!this.email.value) {
        this.email.error = 'Email is required'
        this.email.valid = false
        return false
      }

      const emailRegex = /^([a-zA-Z0-9_\-\.\+]+)@((\[[0-2]{1}[0-5]{1}[0-5]{1}\.[0-2]{1}[0-5]{1}[0-5]{1}\.[0-2]{1}[0-5]{1}[0-5]{1}\.)|(([a-zA-Z0-9\-]+\.)+))([a-zA-Z]{2,4}|[0-2]{1}[0-5]{1}[0-5]{1})(\]?)$/i

      const check = emailRegex.test(this.email.value)

      if (!check) {
        this.email.error = 'Email must contain valid email address'
        this.email.valid = false
        return false
      }

      this.email.error = ''
      this.email.valid = true
      return true
    },
    validateMessage() {
      if (this.message.value) {
        this.message.error = ''
        this.message.valid = true
        return true
      } else {
        this.message.error = 'Message is required'
        this.message.valid = false
        return false
      }
    },
    validateForm() {
      this.validateName()
      this.validateEmail()
      this.validateMessage()
    },
    handleSubmit() {
      this.validateForm()
      if (this.formIsValid) {
        this.$refs.contactForm.submit()
      }
    }
  },
  computed: {
    formIsValid() {
      if (this.name.value || this.email.value || this.message.value) {
        return (
          this.validateName() && this.validateEmail() && this.validateMessage()
        )
      }

      return false
    }
  }
}
</script>

<style lang="scss" scoped>
</style>