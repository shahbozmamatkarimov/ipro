<template>
  <main>
    <section class="bg-gray-50 dark:bg-gray-900">
      <div
        class="flex flex-col items-center justify-center px-6 py-8 mx-auto md:h-screen lg:py-0"
      >
        <a
          href="#"
          class="flex items-center mb-6 text-2xl font-semibold text-gray-900 dark:text-white"
        >
          <img
            class="w-28 h-12 object-cover"
            src="https://www.henkel.com/resource/image/856716/1x1/1000/1000/854e29c0488e730d5214df4637878014/A14CC1F49988F23711FAACAEE2B23D39/ipro-logo.webp"
            alt="logo"
          />
        </a>
        <div
          class="w-full bg-white rounded-lg shadow dark:border md:mt-0 sm:max-w-md xl:p-0 dark:bg-gray-800 dark:border-gray-700"
        >
          <div class="p-6 space-y-4 md:space-y-6 sm:p-8">
            <h1
              class="text-xl font-bold leading-tight tracking-tight text-gray-900 md:text-2xl dark:text-white"
            >
              Register to your account
            </h1>
            <form
              @submit.prevent="register"
              class="space-y-4 md:space-y-6"
              action="#"
            >
              <div>
                <input
                  type="text"
                  name="name"
                  id="name"
                  class="bg-gray-50 border border-gray-300 text-gray-900 sm:text-sm rounded-lg focus:ring-blue-600 focus:border-blue-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                  placeholder="John"
                  required=""
                />
              </div>
              <div>
                <input
                  type="text"
                  name="surname"
                  id="surname"
                  class="bg-gray-50 border border-gray-300 text-gray-900 sm:text-sm rounded-lg focus:ring-blue-600 focus:border-blue-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                  placeholder="Doe"
                  required=""
                />
              </div>
              <div>
                <input
                  type="email"
                  name="email"
                  id="email"
                  class="bg-gray-50 border border-gray-300 text-gray-900 sm:text-sm rounded-lg focus:ring-blue-600 focus:border-blue-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                  placeholder="name@company.com"
                  required=""
                />
              </div>
              <div>
                <input
                  type="password"
                  name="password"
                  id="password"
                  placeholder="••••••••"
                  class="bg-gray-50 border border-gray-300 text-gray-900 sm:text-sm rounded-lg focus:ring-blue-600 focus:border-blue-600 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
                  required=""
                />
              </div>
              <button
                type="submit"
                class="w-full text-white bg-blue-600 hover:bg-blue-700 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800"
              >
                Register
              </button>
              <p class="text-sm font-light text-gray-500 dark:text-gray-400">
                Don’t have an account yet?
                <a
                  href="#"
                  class="font-medium text-blue-600 hover:underline dark:text-blue-500"
                  >Log in</a
                >
              </p>
            </form>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<script setup>
const router = useRouter();
const register = () => {
  localStorage.setItem("register", true);
  router.push("/login");
};

onBeforeMount(() => {
  if (localStorage.getItem("tel") != 'true') {
    router.push("/check_phone");
  } else if (localStorage.getItem("otp") != 'true') {
    router.push("/otp_verification");
  }
});
</script>

<style lang="scss" scoped></style>
