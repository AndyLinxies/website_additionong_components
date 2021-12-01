<template>
  <div>
    <!-- card -->
    <div
      class="max-w-3xl mx-auto overflow-hidden bg-white rounded-lg shadow-md dark:bg-gray-800 big"
    >
      <div class="flex imgF">
        <img
          class="object-cover w-full h-64 flower"
          :src='image'
          alt="Article"
        />

        <div class="p-6">
          <div>
            <a
              href="#"
              class="block mt-2 text-2xl font-semibold text-gray-800 dark:text-white hover:text-gray-600 hover:underline"
            >
              <!--Title-->
              {{ title }}
            </a>
            <p class="mt-2 text-sm text-gray-600 dark:text-gray-400">
              <!--paragraphe-->
              {{ paragraphe }}
            </p>
          </div>

          <div class="mt-4 around">
            <div class="icons" v-if="show">
              <div class="flex pt-2">
                <p>S&nbsp;&nbsp;H&nbsp;&nbsp;A&nbsp;&nbsp;R&nbsp;&nbsp;E</p>
                <svg
                  class="mr-2 ml-3"
                  xmlns="http://www.w3.org/2000/svg"
                  width="20"
                  height="20"
                >
                  <path
                    fill="#FFF"
                    d="M18.896 0H1.104C.494 0 0 .494 0 1.104v17.793C0 19.506.494 20 1.104 20h9.58v-7.745H8.076V9.237h2.606V7.01c0-2.583 1.578-3.99 3.883-3.99 1.104 0 2.052.082 2.329.119v2.7h-1.598c-1.254 0-1.496.597-1.496 1.47v1.928h2.989l-.39 3.018h-2.6V20h5.098c.608 0 1.102-.494 1.102-1.104V1.104C20 .494 19.506 0 18.896 0z"
                  />
                </svg>
                <svg
                  class="mr-2"
                  xmlns="http://www.w3.org/2000/svg"
                  width="20"
                  height="17"
                >
                  <path
                    fill="#FFF"
                    d="M20 2.172a8.192 8.192 0 01-2.357.646 4.11 4.11 0 001.804-2.27 8.22 8.22 0 01-2.605.996A4.096 4.096 0 0013.847.248c-2.65 0-4.596 2.472-3.998 5.037A11.648 11.648 0 011.392 1a4.109 4.109 0 001.27 5.478 4.086 4.086 0 01-1.858-.513c-.045 1.9 1.318 3.679 3.291 4.075a4.113 4.113 0 01-1.853.07 4.106 4.106 0 003.833 2.849A8.25 8.25 0 010 14.658a11.616 11.616 0 006.29 1.843c7.618 0 11.922-6.434 11.663-12.205A8.354 8.354 0 0020 2.172z"
                  />
                </svg>
                <svg
                  class="mr-2"
                  xmlns="http://www.w3.org/2000/svg"
                  width="20"
                  height="20"
                >
                  <path
                    fill="#FFF"
                    d="M10 0C4.478 0 0 4.477 0 10c0 4.237 2.636 7.855 6.356 9.312-.088-.791-.167-2.005.035-2.868.182-.78 1.172-4.97 1.172-4.97s-.299-.6-.299-1.486c0-1.39.806-2.428 1.81-2.428.852 0 1.264.64 1.264 1.408 0 .858-.545 2.14-.828 3.33-.236.995.5 1.807 1.48 1.807 1.778 0 3.144-1.874 3.144-4.58 0-2.393-1.72-4.068-4.177-4.068-2.845 0-4.515 2.135-4.515 4.34 0 .859.331 1.781.745 2.281a.3.3 0 01.069.288l-.278 1.133c-.044.183-.145.223-.335.134-1.249-.581-2.03-2.407-2.03-3.874 0-3.154 2.292-6.052 6.608-6.052 3.469 0 6.165 2.473 6.165 5.776 0 3.447-2.173 6.22-5.19 6.22-1.013 0-1.965-.525-2.291-1.148l-.623 2.378c-.226.869-.835 1.958-1.244 2.621.937.29 1.931.446 2.962.446 5.522 0 10-4.477 10-10S15.522 0 10 0z"
                  />
                </svg>
              </div>
              <span id="triangle-code"></span>
            </div>
            <div class="bottom flex justify-between">
              <!-- Image,photo,nom et date -->
              <div class="infos flex">
                <div class="globImg">
                  <img
                    class="object-cover h-10 rounded-full"
                    src="../../src/assets/imgCard/avatar-michelle.jpg"
                    alt="Avatar"
                  />
                </div>
                <div class="name_date">
                  <p
                    class="mx-2 font-semibold text-gray-700 dark:text-gray-200"
                  >
                    <!--name-->
                    {{ name }}
                  </p>
                  <p class="mx-1 text-xs text-gray-600 dark:text-gray-300 date pl-4">
                    <!--date-->
                    {{ date }}
                  </p>
                </div>
              </div>
              <div class="shared">
                <button class="globShare" @click="set">
                  <svg
                    class="arrow"
                    xmlns="http://www.w3.org/2000/svg"
                    width="15"
                    height="13"
                  >
                    <path
                      fill="#6E8098"
                      d="M15 6.495L8.766.014V3.88H7.441C3.33 3.88 0 7.039 0 10.936v2.049l.589-.612C2.59 10.294 5.422 9.11 8.39 9.11h.375v3.867L15 6.495z"
                    />
                  </svg>
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ReproCard",
  props: {
    title: String,
    paragraphe: String,
    name: String,
    date: String,
    image: String,
  },
  data() {
    return {
      show: false,
    };
  },
  methods: {
    set() {
      this.show = !this.show;
    },
  },
};
</script>

<style scoped>
.imgF {
  height: 33vh;
}
.flower {
  height: 100%;
}

.big {
  /* height: 30.5vh; */
  margin-top: 5%;
}
.date {
  margin-left: -40% !important;
}
.globShare {
  border-radius: 50%;
  padding-top: 1%;
  width: 1.7vw;
  height: 3.2vh;
  background-color: #dadfe4;
  margin-top: 25%;
}
.spaceBottom {
  width: 100% !important;
}
.icons {
  background-color: #6d7f98;
  width: 50%;
  height: 5vh;
  border-radius: 5px;
  z-index: 2;
  position: absolute;
  right: -5px;
  top: -40px;
}
.arrow {
  padding-left: 15%;
}
.around {
  position: relative;
}

#triangle-code {
  display: inline-block;
  height: 0;
  width: 0;
  border-top: 20px solid #6d7f98;
  border-right: 10px solid transparent;
  border-left: 10 solid transparent;
  margin-left: 77%;
}
</style>
