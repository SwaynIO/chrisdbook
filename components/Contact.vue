<template>
  <div class="fields">
    <ValidationObserver v-slot="{ handleSubmit }">
      <form class="contact_form" @submit.prevent="handleSubmit(onSubmit)">
        <div class="first">
          <ul>
            <ValidationProvider
              name="name"
              rules="required"
              v-slot="{ errors }"
            >
              <li>
                <input
                  v-model="formData.name"
                  type="text"
                  placeholder="Name"
                  autocomplete="off"
                />
                <span class="inpur-error">{{ errors[0] }}</span>
              </li>
            </ValidationProvider>

            <ValidationProvider
              name="email"
              rules="required|email"
              v-slot="{ errors }"
            >
              <li>
                <input
                  type="text"
                  rules="required|email"
                  v-model="formData.email"
                  placeholder="Email"
                />
                <span class="inpur-error">{{ errors[0] }}</span>
              </li>
            </ValidationProvider>
            <ValidationProvider
              name="message"
              rules="required"
              v-slot="{ errors }"
            >
              <li>
                <textarea
                  v-model="formData.message"
                  placeholder="Message"
                ></textarea>
                <span class="inpur-error">{{ errors[0] }}</span>
              </li>
            </ValidationProvider>
          </ul>
        </div>
        <div class="tokyo_tm_button">
          <button type="submit" class="ib-button">
            Send Message
          </button>
        </div>
      </form>
    </ValidationObserver>
  </div>
</template>

<script>
import { ValidationObserver } from "vee-validate";
import { ValidationProvider } from "vee-validate/dist/vee-validate.full.esm";
export default {
  components: {
    ValidationObserver,
    ValidationProvider,
  },
  data() {
    return {
      formData: {
        name: "",
        email: "",
        message: "",
      },
    };
  },
  methods: {
    onSubmit() {
      console.log(this.formData);
    },
  },
};
</script>

<style lang="scss">
.inpur-error {
  color: red;
  font-size: 14px;
  padding-top: 5px;
}
</style>
