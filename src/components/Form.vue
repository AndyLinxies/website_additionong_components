<template>
  <div class="first mt-20 pb-20">
    <div class="grid grid-cols-1 md:grid-cols-2">
      <div class="left">
        <p class="text-6xl font-extrabold text-white text-left pl-24">
          Learn to code by watching others
        </p>
        <p class="text-lg font-medium text-white text-left pl-24 mt-12 texte">
          See how experienced'developers solve problems in real-time. Watching
          scripted tutorials is great, but understanding how how developers
          think is invaluable
        </p>
      </div>

      <div class="right mr-10 mt-24">
        <div
          class="h-16 bg-white flex items-center justify-center text-gray-700 font-semibold shadow-xl rounded-md top_right"
        >
          <strong>Try it free 7 days</strong> then $20/mo.thereafter
        </div>
        <!-- message -->
        <div class="bg-white mt-8 rounded-md shadow-xl h-10" v-if="checked">
          <p class="text-xl font-bold">Thank you</p>
        </div>
        <!-- form -->
        <div
          class="h-90 bg-white mt-8 rounded-md shadow-xl"
          v-if="checked == false"
        >
          <form action="" class="pl-8 pr-8" @submit="checkForm">
            <input
              v-model="firstName"
              type="text"
              placeholder="First Name"
              class="input border border-gray-400 appearance-none rounded w-full px-3 py-3 pt-5 pb-2 focus focus:border-indigo-600 focus:outline-none active:outline-none active:border-indigo-600 mt-10"
              autofocus
            />
            <p
              class="text-red-500 text-sm ml-80"
              v-if="firstName == null || firstName == ''"
            >
              First Name cannot be empty
            </p>

            <input
              v-model="lastName"
              type="text"
              placeholder="Last Name"
              class="input border border-gray-400 appearance-none rounded w-full px-3 py-3 pt-5 pb-2 focus focus:border-indigo-600 focus:outline-none active:outline-none active:border-indigo-600 mt-6"
              autofocus
            />
            <p
              class="text-red-500 text-sm ml-80"
              v-if="lastName == null || lastName == ''"
            >
              Last Name cannot be empty
            </p>

            <input
              v-model="email"
              type="email"
              placeholder="Email Adress"
              class="input border border-gray-400 appearance-none rounded w-full px-3 py-3 pt-5 pb-2 focus focus:border-indigo-600 focus:outline-none active:outline-none active:border-indigo-600 mt-6"
              autofocus
            />
            <p
              class="text-red-500 text-sm ml-80"
              v-if="email == null || email == ''"
            >
              Email cannot be empty
            </p>

            <input
              v-model="password"
              type="password"
              placeholder="Password"
              class="input border border-gray-400 appearance-none rounded w-full px-3 py-3 pt-5 pb-2 focus focus:border-indigo-600 focus:outline-none active:outline-none active:border-indigo-600 mt-6"
              autofocus
            />
            <p
              class="text-red-500 text-sm ml-80"
              v-if="password == null || password == ''"
            >
              Password cannot be empty
            </p>

            <button
              type="submit"
              class="bg-green-400 pb-4 input border border-gray-400 appearance-none rounded w-full px-3 py-3 pt-5 pb-2 focus focus:border-indigo-600 focus:outline-none active:outline-none active:border-indigo-600 mt-6 text-white font-bold"
            >
              CLAIM YOUR FREE TRIAL
            </button>
            <p>
              By clicking thebutton, you are agreeing to our
              <span class="text-red-300">Terms and Services</span>
            </p>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Form",
  data() {
    return {
      firstName: null,
      lastName: null,
      email: null,
      password: null,
      checked: false,
    };
  },
  methods: {
    checkForm(e) {
      if (
        this.firstName != null &&
        this.firstName != "" &&
        this.lastName != null &&
        this.lastName != "" &&
        this.email != null &&
        this.email != "" &&
        this.password != null &&
        this.password != ""
      ) {
        return (this.checked = true);
      }

      e.preventDefault();
    },
  },
};
</script>

<style scoped>
.first {
  background-color: #ff7978;
  background-image: url("../../src/assets/imgForm/bg-intro-desktop.png");
}
.left {
  padding-top: 30%;
}
.texte {
  width: 90% !important;
}
.top_right {
  background-color: #5d54a3;
  color: whitesmoke;
}
form {
  position: relative;
}
</style>
