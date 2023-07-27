<template>
  <header>
    <nav
      class="bg-white/50 shadow fixed top-0 left-0 right-0 z-50 backdrop-blur-md w-full px-5 lg:px-20 py-2.5 dark:bg-gray-800"
    >
      <div
        class="container overflow-hidden flex flex-wrap justify-between w-full items-center mx-auto"
      >
        <img
          class="w-28 h-12 object-cover"
          src="https://www.henkel.com/resource/image/856716/1x1/1000/1000/854e29c0488e730d5214df4637878014/A14CC1F49988F23711FAACAEE2B23D39/ipro-logo.webp"
          alt="logo"
        />
        <div class="flex items-center lg:order-2">
          <router-link
            to="/login"
            class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 dark:bg-blue-600 dark:hover:bg-blue-700 focus:outline-none dark:focus:ring-blue-800"
            >{{ $t("navbar.login") }}</router-link
          >
          
        <form class="mr-2">
          <select v-model="$i18n.locale" id="countries" class="bg-gray-50 ml-1 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500">
            <option class="bg-black" value="uz">{{ $t("uz") }}</option>
            <option class="bg-black" value="ru">{{ $t("ru") }}</option>
            <option class="bg-black" value="en">{{ $t("en") }}</option>
          </select>
        </form>

          <button
            @click="store.menu = !store.menu"
            type="button"
            class="inline-flex items-center p-2 mx-1 text-sm text-gray-500 rounded-lg lg:hidden hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-gray-200 dark:text-gray-400 dark:hover:bg-gray-700 dark:focus:ring-gray-600"
          >
            <svg
              class="w-6 h-6"
              fill="currentColor"
              viewBox="0 0 20 20"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                fill-rule="evenodd"
                d="M3 5a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 10a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 15a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1z"
                clip-rule="evenodd"
              ></path>
            </svg>
            <svg
              class="hidden w-6 h-6"
              fill="currentColor"
              viewBox="0 0 20 20"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                fill-rule="evenodd"
                d="M4.293 4.293a1 1 0 011.414 0L10 8.586l4.293-4.293a1 1 0 111.414 1.414L11.414 10l4.293 4.293a1 1 0 01-1.414 1.414L10 11.414l-4.293 4.293a1 1 0 01-1.414-1.414L8.586 10 4.293 5.707a1 1 0 010-1.414z"
                clip-rule="evenodd"
              ></path>
            </svg>
          </button>
        </div>
        <div
          :class="{ hidden: !store.menu }"
          class="justify-between items-center w-full lg:flex lg:w-auto lg:order-1"
          id="mobile-menu-2"
        >
          <ul
            class="flex flex-col mt-4 font-medium lg:flex-row lg:space-x-8 lg:mt-0"
          >
            <li>
              <p
                :class="{
                  'lg:text-blue-700  bg-blue-700 lg:bg-transparent':
                    store.page == 0,
                }"
                @click="
                  scrollFunc(0);
                  store.menu = false;
                "
                class="block cursor-pointer py-2 pr-4 pl-3 rounded lg:p-0"
                aria-current="page"
              >
              {{ $t("navbar.home") }}
              </p>
            </li>
            <li>
              <p
                :class="{
                  'lg:text-blue-700  bg-blue-700 lg:bg-transparent':
                    store.page == 1,
                }"
                @click="
                  scrollFunc(1);
                  store.menu = false;
                "
                class="block cursor-pointer py-2 pr-4 pl-3 text-gray-700 border-b border-gray-100 hover:bg-gray-50 lg:hover:bg-transparent lg:border-0 lg:hover:text-blue-700 lg:p-0 dark:text-gray-400 lg:dark:hover:text-white dark:hover:bg-gray-700 dark:hover:text-white lg:dark:hover:bg-transparent dark:border-gray-700"
              >
              {{ $t("navbar.social") }}
              </p>
            </li>
            <li>
              <p
                :class="{
                  'lg:text-blue-700  bg-blue-700 lg:bg-transparent':
                    store.page == 2,
                }"
                @click="
                  scrollFunc(2);
                  store.menu = false;
                "
                class="block cursor-pointer py-2 pr-4 pl-3 text-gray-700 border-b border-gray-100 hover:bg-gray-50 lg:hover:bg-transparent lg:border-0 lg:hover:text-blue-700 lg:p-0 dark:text-gray-400 lg:dark:hover:text-white dark:hover:bg-gray-700 dark:hover:text-white lg:dark:hover:bg-transparent dark:border-gray-700"
              >
              {{ $t("navbar.projects") }}
              </p>
            </li>
            <li>
              <p
                :class="{
                  'lg:text-blue-700  bg-blue-700 lg:bg-transparent':
                    store.page == 3,
                }"
                @click="
                  scrollFunc(3);
                  store.menu = false;
                "
                class="block cursor-pointer py-2 pr-4 pl-3 text-gray-700 border-b border-gray-100 hover:bg-gray-50 lg:hover:bg-transparent lg:border-0 lg:hover:text-blue-700 lg:p-0 dark:text-gray-400 lg:dark:hover:text-white dark:hover:bg-gray-700 dark:hover:text-white lg:dark:hover:bg-transparent dark:border-gray-700"
              >
              {{ $t("navbar.staff") }}
              </p>
            </li>
            <li>
              <p
                :class="{
                  'lg:text-blue-700  bg-blue-700 lg:bg-transparent':
                    store.page == 4,
                }"
                @click="
                  scrollFunc(4);
                  store.menu = false;
                "
                class="block cursor-pointer py-2 pr-4 pl-3 text-gray-700 border-b border-gray-100 hover:bg-gray-50 lg:hover:bg-transparent lg:border-0 lg:hover:text-blue-700 lg:p-0 dark:text-gray-400 lg:dark:hover:text-white dark:hover:bg-gray-700 dark:hover:text-white lg:dark:hover:bg-transparent dark:border-gray-700"
              >
              {{ $t("navbar.price") }}
              </p>
            </li>
          </ul>
        </div>
      </div>
    </nav>
    <main
      class="container mx-auto px-5 lg:px-20 pt-10"
      @mouseover="store.menu = false"
    >
      <section
        class="flex justify-between items-center min-h-screen w-full bg-white dark:bg-gray-900"
      >
        <div class="grid py-8 lg:py-16 lg:grid-cols-12">
          <div class="lg:col-span-7">
            <h1
              class="max-w-2xl mb-4 sm:text-3xl text-2xl font-extrabold leading-none md:text-5xl xl:text-6xl dark:text-white"
            >
            {{ $t("homepage.title") }}
            </h1>
            <p
              class="max-w-2xl mb-6 font-light text-gray-500 lg:mb-8 sm:text-md text-sm md:text-lg lg:text-xl dark:text-gray-400"
            >
            {{ $t("homepage.description") }}
            </p>
            <a
              href="#"
              class="inline-flex items-center justify-center sm:px-5 px-3 sm:py-3 py-2 mr-3 md:text-base text-sm font-medium text-center text-white rounded-lg bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:ring-blue-300 dark:focus:ring-blue-900"
            >
            {{ $t("homepage.hire") }}
              <svg
                class="w-5 h-5 ml-2 -mr-1"
                fill="currentColor"
                viewBox="0 0 20 20"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  fill-rule="evenodd"
                  d="M10.293 3.293a1 1 0 011.414 0l6 6a1 1 0 010 1.414l-6 6a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-4.293-4.293a1 1 0 010-1.414z"
                  clip-rule="evenodd"
                ></path>
              </svg>
            </a>
            <a
              href="#"
              class="inline-flex items-center justify-center sm:px-5 px-3 sm:py-3 py-2 sm:text-base text-sm font-medium text-center text-gray-900 border border-gray-300 rounded-lg hover:bg-gray-100 focus:ring-4 focus:ring-gray-100 dark:text-white dark:border-gray-700 dark:hover:bg-gray-700 dark:focus:ring-gray-800"
            >
            {{ $t("homepage.show") }}
            </a>
          </div>
          <div class="lg:col-span-5 flex rounded overflow-hidden">
            <img
              class="rounded h-full w-full lg:py-0 py-10"
              src="https://i.ytimg.com/vi/NuSMSEiBi8o/maxresdefault.jpg"
              alt=""
            />
          </div>
        </div>
      </section>

      <section class="carouselSection flex items-center min-h-[25vh]">
        <div
          id="default-carousel"
          class="relative w-full"
          data-carousel="slide"
        >
          <!-- Carousel wrapper -->
          <div
            class="flex items-center justify-center relative sm:h-20 h-10 overflow-hidden rounded-lg"
          >
            <!-- Item 1 -->
            <div class="hidden duration-700 ease-in-out" data-carousel-item>
              <div class="flex items-center justify-around sm:h-16 h-10">
                <img
                  class="h-full object-cover"
                  src="https://play-lh.googleusercontent.com/82VgpoTkbg5jhJh2ADEm73INfVl-fa_5zo6wrG25Vqa8cUEcMWINUUN7vv9rwrfv-A"
                  alt="TTP"
                />
                <img
                  class="h-full object-cover"
                  src="https://menufyproduction.imgix.net/637019254819256058+115703.png?auto=compress,format&h=1080&w=1920&fit=max"
                  alt="China House"
                />
                <h1 class="whitespace-nowrap text-2xl italic">Awiner ogit</h1>
                <img
                  class="md:block hidden h-full object-cover"
                  src="https://sultantravels.com.au/wp-content/uploads/2019/04/Sultan-Travel-Logo-01.png"
                  alt="Sultan Travel"
                />
              </div>
            </div>

            <!-- Item 2 -->
            <div class="hidden duration-700 ease-in-out" data-carousel-item>
              <div class="flex items-center justify-around sm:h-16 h-10">
                <img
                  class="h-full object-cover"
                  src="https://quadro-dev.s3.sa-east-1.amazonaws.com/quadro/logo.png"
                  alt="Quadro"
                />
                <img
                  class="h-full object-cover"
                  src="https://svarkoy.ru/wp-content/uploads/2019/01/svarochnye-apparaty-wester-01.jpg"
                  alt="Wester"
                />
                <img
                  class="md:block hidden h-full object-cover"
                  src="https://jakho.rs/wp-content/uploads/2018/01/circle.png"
                  alt="QA building"
                />
                <img
                  class="h-full object-cover"
                  src="https://1000logos.net/wp-content/uploads/2016/11/google-logo.jpg"
                  alt="Google"
                />
              </div>
            </div>

            <!-- Item 3 -->
            <div class="hidden duration-700 ease-in-out" data-carousel-item>
              <div class="flex items-center justify-around sm:h-16 h-10">
                <img
                  class="h-full object-cover"
                  src="https://logos-world.net/wp-content/uploads/2020/09/Microsoft-Logo.png"
                  alt="Microsoft"
                />
                <img
                  class="h-full object-cover"
                  src="https://quadro-dev.s3.sa-east-1.amazonaws.com/quadro/logo.png"
                  alt="Quadro"
                />
                <img
                  class="md:block hidden h-full object-cover"
                  src="https://jakho.rs/wp-content/uploads/2018/01/circle.png"
                  alt="QA building"
                />
                <img
                  class="h-full object-cover"
                  src="https://1000logos.net/wp-content/uploads/2016/11/google-logo.jpg"
                  alt="Google"
                />
              </div>
            </div>

            <!-- Item 4 -->
            <div class="hidden duration-700 ease-in-out" data-carousel-item>
              <div class="flex items-center justify-around sm:h-16 h-10">
                <img
                  class="h-full object-cover"
                  src="https://play-lh.googleusercontent.com/82VgpoTkbg5jhJh2ADEm73INfVl-fa_5zo6wrG25Vqa8cUEcMWINUUN7vv9rwrfv-A"
                  alt="TTP"
                />
                <img
                  class="h-full object-cover"
                  src="https://menufyproduction.imgix.net/637019254819256058+115703.png?auto=compress,format&h=1080&w=1920&fit=max"
                  alt="China House"
                />
                <h1 class="md:block hidden whitespace-nowrap text-2xl italic">
                  Awiner ogit
                </h1>
                <img
                  class="h-full object-cover"
                  src="https://jakho.rs/wp-content/uploads/2018/01/circle.png"
                  alt="QA building"
                />
              </div>
            </div>

            <!-- Item 5 -->
            <div class="hidden duration-700 ease-in-out" data-carousel-item>
              <div class="flex items-center justify-around sm:h-16 h-10">
                <img
                  class="h-full object-cover"
                  src="https://sultantravels.com.au/wp-content/uploads/2019/04/Sultan-Travel-Logo-01.png"
                  alt="Sultan Travel"
                />
                <img
                  class="h-full object-cover"
                  src="https://quadro-dev.s3.sa-east-1.amazonaws.com/quadro/logo.png"
                  alt="Quadro"
                />
                <img
                  class="h-full object-cover"
                  src="https://svarkoy.ru/wp-content/uploads/2019/01/svarochnye-apparaty-wester-01.jpg"
                  alt="Wester"
                />
              </div>
            </div>
          </div>
          <!-- Slider indicators -->
        </div>
      </section>

      <section
        class="flex justify-center items-center min-h-screen bg-white dark:bg-gray-900"
      >
        <div class="container mx-auto">
          <h1
            class="text-2xl font-semibold text-gray-800 dark:text-white lg:text-4xl"
          >
          {{ $t("projects.projects") }}
          </h1>

          <div class="lg:-mx-12 lg:flex">
            <div class="lg:mx-12">
              <div
                class="lg:block flex items-center overflow-hidden overflow-x-auto w-full gap-5 mt-4 lg:pb-0 pb-5 lg:space-y-4 lg:mt-8"
              >
                <p
                  class="block whitespace-nowrap text-blue-500 hover:underline dark:text-blue-400"
                >
                {{ $t("projects.web_design") }}
                </p>
                <p
                  class="block whitespace-nowrap text-gray-500 hover:underline dark:text-gray-300"
                >
                {{ $t("projects.app_design") }}
                </p>
                <p
                  class="block whitespace-nowrap text-gray-500 hover:underline dark:text-gray-300"
                >
                {{ $t("projects.brending") }}
                </p>
                <p
                  class="block whitespace-nowrap text-gray-500 hover:underline dark:text-gray-300"
                >
                {{ $t("projects.animation") }}
                </p>
              </div>
            </div>

            <div class="mt-8 flex-1 lg:mx-12 lg:mt-0">
              <!-- component -->
              <div class="lg:bg-gray-100 rounded-lg -my-10">
                <div
                  class="flex flex-row overflow-hidden overflow-x-auto lg:px-10 py-10 justify-between md:gap-x-10 xl-grid-cols-4 gap-y-10 gap-x-6"
                >
                  <div
                    class="mx-auto w-full min-w-[14rem] shadow-lg rounded-lg max-w-md hover:shadow-2xl transition duration-300"
                  >
                    <img
                      src="https://images.unsplash.com/photo-1627751476653-e954179b174a"
                      alt=""
                      class="rounded-t-lg w-full"
                    />
                    <div class="p-6">
                      <h1
                        class="lg:text-xl text-md hover:text-indigo-600 transition duration-200 font-bold text-gray-900"
                      >
                        This is any title.
                      </h1>
                      <p
                        class="text-gray-700 lg:text-md text-sm my-2 hover-text-900"
                      >
                        Lorem ipsum dolor sit amet consectetur adipisicing elit.
                        Praesentium quis.
                      </p>
                    </div>
                  </div>
                  <div
                    class="mx-auto w-full min-w-[14rem] shadow-lg rounded-lg max-w-md hover:shadow-2xl transition duration-300"
                  >
                    <img
                      src="https://images.unsplash.com/photo-1572431447238-425af66a273b"
                      alt=""
                      class="rounded-t-lg w-full"
                    />
                    <div class="p-6">
                      <h1
                        class="lg:text-xl text-md hover:text-indigo-600 transition duration-200 font-bold text-gray-900"
                      >
                        This is any title.
                      </h1>
                      <p
                        class="text-gray-700 lg:text-md text-sm my-2 hover-text-900"
                      >
                        Lorem ipsum dolor sit amet consectetur adipisicing elit.
                        Praesentium quis.
                      </p>
                    </div>
                  </div>
                  <div
                    class="mx-auto w-full min-w-[14rem] shadow-lg rounded-lg max-w-md hover:shadow-2xl transition duration-300"
                  >
                    <img
                      src="https://images.unsplash.com/photo-1540202404-1b927e27fa8b"
                      alt=""
                      class="rounded-t-lg w-full"
                    />
                    <div class="p-6">
                      <h1
                        class="lg:text-xl text-md hover:text-indigo-600 transition duration-200 font-bold text-gray-900"
                      >
                        This is any title.
                      </h1>
                      <p
                        class="text-gray-700 lg:text-md text-sm my-2 hover-text-900"
                      >
                        Lorem ipsum dolor sit amet consectetur adipisicing elit.
                        Praesentium quis.
                      </p>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <section
        class="flex justify-center items-center min-h-screen overflow-hidden bg-white dark:bg-gray-900"
      >
        <div class="container mx-auto">
          <h1
            class="text-2xl mt-16 font-semibold capitalize text-gray-800 dark:text-white lg:text-4xl"
          >
            {{ $t("staff.title") }}
          </h1>

          <p class="my-6 max-w-2xl text-gray-500 dark:text-gray-300">
            {{ $t("staff.description") }}
          </p>

          <div class="flex overflow-hidden overflow-x-auto mt-8 gap-8 xl:mt-16">
            <div
              class="group flex md:min-w-[14rem] min-w-[12rem] transform cursor-pointer flex-col items-center rounded-xl p-8 transition-colors duration-300 hover:bg-blue-600"
            >
              <img
                class="md:min-h-32 md:max-h-32 md:min-w-[8rem] md:max-w-[8rem] min-h-20 max-h-20 min-w-[5rem] max-w-[5rem] rounded-full object-cover ring-4 ring-gray-300"
                src="https://images.unsplash.com/photo-1535713875002-d1d0cf377fde?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=880&q=80"
                alt=""
              />

              <h1
                class="mt-4 md:text-2xl text-lg font-semibold capitalize text-gray-700 group-hover:text-white dark:text-white"
              >
                arthur melo
              </h1>

              <p
                class="mt-2 md:text-md text-xs capitalize text-gray-500 group-hover:text-gray-300 dark:text-gray-300"
              >
                design director
              </p>

              <div class="-mx-2 mt-3 flex">
                <a
                  href="#"
                  class="mx-2 text-gray-600 hover:text-gray-500 group-hover:text-white dark:text-gray-300 dark:hover:text-gray-300"
                  aria-label="Reddit"
                >
                  <i class="bx bxl-telegram text-xl"></i>
                </a>

                <a
                  href="#"
                  class="mx-2 text-gray-600 hover:text-gray-500 group-hover:text-white dark:text-gray-300 dark:hover:text-gray-300"
                  aria-label="Facebook"
                >
                  <svg
                    class="h-6 w-6 fill-current"
                    viewBox="0 0 24 24"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      d="M2.00195 12.002C2.00312 16.9214 5.58036 21.1101 10.439 21.881V14.892H7.90195V12.002H10.442V9.80204C10.3284 8.75958 10.6845 7.72064 11.4136 6.96698C12.1427 6.21332 13.1693 5.82306 14.215 5.90204C14.9655 5.91417 15.7141 5.98101 16.455 6.10205V8.56104H15.191C14.7558 8.50405 14.3183 8.64777 14.0017 8.95171C13.6851 9.25566 13.5237 9.68693 13.563 10.124V12.002H16.334L15.891 14.893H13.563V21.881C18.8174 21.0506 22.502 16.2518 21.9475 10.9611C21.3929 5.67041 16.7932 1.73997 11.4808 2.01722C6.16831 2.29447 2.0028 6.68235 2.00195 12.002Z"
                    ></path>
                  </svg>
                </a>

                <a
                  href="#"
                  class="mx-2 text-gray-600 hover:text-gray-500 group-hover:text-white dark:text-gray-300 dark:hover:text-gray-300"
                  aria-label="Github"
                >
                  <svg
                    class="h-6 w-6 fill-current"
                    viewBox="0 0 24 24"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      d="M12.026 2C7.13295 1.99937 2.96183 5.54799 2.17842 10.3779C1.395 15.2079 4.23061 19.893 8.87302 21.439C9.37302 21.529 9.55202 21.222 9.55202 20.958C9.55202 20.721 9.54402 20.093 9.54102 19.258C6.76602 19.858 6.18002 17.92 6.18002 17.92C5.99733 17.317 5.60459 16.7993 5.07302 16.461C4.17302 15.842 5.14202 15.856 5.14202 15.856C5.78269 15.9438 6.34657 16.3235 6.66902 16.884C6.94195 17.3803 7.40177 17.747 7.94632 17.9026C8.49087 18.0583 9.07503 17.99 9.56902 17.713C9.61544 17.207 9.84055 16.7341 10.204 16.379C7.99002 16.128 5.66202 15.272 5.66202 11.449C5.64973 10.4602 6.01691 9.5043 6.68802 8.778C6.38437 7.91731 6.42013 6.97325 6.78802 6.138C6.78802 6.138 7.62502 5.869 9.53002 7.159C11.1639 6.71101 12.8882 6.71101 14.522 7.159C16.428 5.868 17.264 6.138 17.264 6.138C17.6336 6.97286 17.6694 7.91757 17.364 8.778C18.0376 9.50423 18.4045 10.4626 18.388 11.453C18.388 15.286 16.058 16.128 13.836 16.375C14.3153 16.8651 14.5612 17.5373 14.511 18.221C14.511 19.555 14.499 20.631 14.499 20.958C14.499 21.225 14.677 21.535 15.186 21.437C19.8265 19.8884 22.6591 15.203 21.874 10.3743C21.089 5.54565 16.9181 1.99888 12.026 2Z"
                    ></path>
                  </svg>
                </a>
              </div>
            </div>

            <div
              class="group flex min-w-[14rem] transform cursor-pointer flex-col items-center rounded-xl p-8 transition-colors duration-300 hover:bg-blue-600"
            >
              <img
                class="md:min-h-32 md:max-h-32 md:min-w-[8rem] md:max-w-[8rem] min-h-20 max-h-20 min-w-[5rem] max-w-[5rem] rounded-full object-cover ring-4 ring-gray-300"
                src="https://images.unsplash.com/photo-1570295999919-56ceb5ecca61?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=880&q=80"
                alt=""
              />

              <h1
                class="mt-4 md:text-2xl text-lg font-semibold capitalize text-gray-700 group-hover:text-white dark:text-white"
              >
                John Doe
              </h1>

              <p
                class="mt-2 md:text-md text-xs capitalize text-gray-500 group-hover:text-gray-300 dark:text-gray-300"
              >
                Full stack developer
              </p>

              <div class="-mx-2 mt-3 flex">
                <a
                  href="#"
                  class="mx-2 text-gray-600 hover:text-gray-500 group-hover:text-white dark:text-gray-300 dark:hover:text-gray-300"
                  aria-label="Reddit"
                >
                  <i class="bx bxl-telegram text-xl"></i>
                </a>

                <a
                  href="#"
                  class="mx-2 text-gray-600 hover:text-gray-500 group-hover:text-white dark:text-gray-300 dark:hover:text-gray-300"
                  aria-label="Facebook"
                >
                  <svg
                    class="h-6 w-6 fill-current"
                    viewBox="0 0 24 24"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      d="M2.00195 12.002C2.00312 16.9214 5.58036 21.1101 10.439 21.881V14.892H7.90195V12.002H10.442V9.80204C10.3284 8.75958 10.6845 7.72064 11.4136 6.96698C12.1427 6.21332 13.1693 5.82306 14.215 5.90204C14.9655 5.91417 15.7141 5.98101 16.455 6.10205V8.56104H15.191C14.7558 8.50405 14.3183 8.64777 14.0017 8.95171C13.6851 9.25566 13.5237 9.68693 13.563 10.124V12.002H16.334L15.891 14.893H13.563V21.881C18.8174 21.0506 22.502 16.2518 21.9475 10.9611C21.3929 5.67041 16.7932 1.73997 11.4808 2.01722C6.16831 2.29447 2.0028 6.68235 2.00195 12.002Z"
                    ></path>
                  </svg>
                </a>

                <a
                  href="#"
                  class="mx-2 text-gray-600 hover:text-gray-500 group-hover:text-white dark:text-gray-300 dark:hover:text-gray-300"
                  aria-label="Github"
                >
                  <svg
                    class="h-6 w-6 fill-current"
                    viewBox="0 0 24 24"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      d="M12.026 2C7.13295 1.99937 2.96183 5.54799 2.17842 10.3779C1.395 15.2079 4.23061 19.893 8.87302 21.439C9.37302 21.529 9.55202 21.222 9.55202 20.958C9.55202 20.721 9.54402 20.093 9.54102 19.258C6.76602 19.858 6.18002 17.92 6.18002 17.92C5.99733 17.317 5.60459 16.7993 5.07302 16.461C4.17302 15.842 5.14202 15.856 5.14202 15.856C5.78269 15.9438 6.34657 16.3235 6.66902 16.884C6.94195 17.3803 7.40177 17.747 7.94632 17.9026C8.49087 18.0583 9.07503 17.99 9.56902 17.713C9.61544 17.207 9.84055 16.7341 10.204 16.379C7.99002 16.128 5.66202 15.272 5.66202 11.449C5.64973 10.4602 6.01691 9.5043 6.68802 8.778C6.38437 7.91731 6.42013 6.97325 6.78802 6.138C6.78802 6.138 7.62502 5.869 9.53002 7.159C11.1639 6.71101 12.8882 6.71101 14.522 7.159C16.428 5.868 17.264 6.138 17.264 6.138C17.6336 6.97286 17.6694 7.91757 17.364 8.778C18.0376 9.50423 18.4045 10.4626 18.388 11.453C18.388 15.286 16.058 16.128 13.836 16.375C14.3153 16.8651 14.5612 17.5373 14.511 18.221C14.511 19.555 14.499 20.631 14.499 20.958C14.499 21.225 14.677 21.535 15.186 21.437C19.8265 19.8884 22.6591 15.203 21.874 10.3743C21.089 5.54565 16.9181 1.99888 12.026 2Z"
                    ></path>
                  </svg>
                </a>
              </div>
            </div>

            <div
              class="group flex min-w-[14rem] transform cursor-pointer flex-col items-center rounded-xl p-8 transition-colors duration-300 hover:bg-blue-600"
            >
              <img
                class="md:min-h-32 md:max-h-32 md:min-w-[8rem] md:max-w-[8rem] min-h-20 max-h-20 min-w-[5rem] max-w-[5rem] rounded-full object-cover ring-4 ring-gray-300"
                src="https://images.unsplash.com/photo-1608174386344-80898cec6beb?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=687&q=80"
                alt=""
              />

              <h1
                class="mt-4 md:text-2xl text-lg font-semibold capitalize text-gray-700 group-hover:text-white dark:text-white"
              >
                Junior REIS
              </h1>

              <p
                class="mt-2 md:text-md text-xs capitalize text-gray-500 group-hover:text-gray-300 dark:text-gray-300"
              >
                Products Managers
              </p>

              <div class="-mx-2 mt-3 flex">
                <a
                  href="#"
                  class="mx-2 text-gray-600 hover:text-gray-500 group-hover:text-white dark:text-gray-300 dark:hover:text-gray-300"
                  aria-label="Reddit"
                >
                  <i class="bx bxl-telegram text-xl"></i>
                </a>

                <a
                  href="#"
                  class="mx-2 text-gray-600 hover:text-gray-500 group-hover:text-white dark:text-gray-300 dark:hover:text-gray-300"
                  aria-label="Facebook"
                >
                  <svg
                    class="h-6 w-6 fill-current"
                    viewBox="0 0 24 24"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      d="M2.00195 12.002C2.00312 16.9214 5.58036 21.1101 10.439 21.881V14.892H7.90195V12.002H10.442V9.80204C10.3284 8.75958 10.6845 7.72064 11.4136 6.96698C12.1427 6.21332 13.1693 5.82306 14.215 5.90204C14.9655 5.91417 15.7141 5.98101 16.455 6.10205V8.56104H15.191C14.7558 8.50405 14.3183 8.64777 14.0017 8.95171C13.6851 9.25566 13.5237 9.68693 13.563 10.124V12.002H16.334L15.891 14.893H13.563V21.881C18.8174 21.0506 22.502 16.2518 21.9475 10.9611C21.3929 5.67041 16.7932 1.73997 11.4808 2.01722C6.16831 2.29447 2.0028 6.68235 2.00195 12.002Z"
                    ></path>
                  </svg>
                </a>

                <a
                  href="#"
                  class="mx-2 text-gray-600 hover:text-gray-500 group-hover:text-white dark:text-gray-300 dark:hover:text-gray-300"
                  aria-label="Github"
                >
                  <svg
                    class="h-6 w-6 fill-current"
                    viewBox="0 0 24 24"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      d="M12.026 2C7.13295 1.99937 2.96183 5.54799 2.17842 10.3779C1.395 15.2079 4.23061 19.893 8.87302 21.439C9.37302 21.529 9.55202 21.222 9.55202 20.958C9.55202 20.721 9.54402 20.093 9.54102 19.258C6.76602 19.858 6.18002 17.92 6.18002 17.92C5.99733 17.317 5.60459 16.7993 5.07302 16.461C4.17302 15.842 5.14202 15.856 5.14202 15.856C5.78269 15.9438 6.34657 16.3235 6.66902 16.884C6.94195 17.3803 7.40177 17.747 7.94632 17.9026C8.49087 18.0583 9.07503 17.99 9.56902 17.713C9.61544 17.207 9.84055 16.7341 10.204 16.379C7.99002 16.128 5.66202 15.272 5.66202 11.449C5.64973 10.4602 6.01691 9.5043 6.68802 8.778C6.38437 7.91731 6.42013 6.97325 6.78802 6.138C6.78802 6.138 7.62502 5.869 9.53002 7.159C11.1639 6.71101 12.8882 6.71101 14.522 7.159C16.428 5.868 17.264 6.138 17.264 6.138C17.6336 6.97286 17.6694 7.91757 17.364 8.778C18.0376 9.50423 18.4045 10.4626 18.388 11.453C18.388 15.286 16.058 16.128 13.836 16.375C14.3153 16.8651 14.5612 17.5373 14.511 18.221C14.511 19.555 14.499 20.631 14.499 20.958C14.499 21.225 14.677 21.535 15.186 21.437C19.8265 19.8884 22.6591 15.203 21.874 10.3743C21.089 5.54565 16.9181 1.99888 12.026 2Z"
                    ></path>
                  </svg>
                </a>
              </div>
            </div>

            <div
              class="group flex min-w-[14rem] transform cursor-pointer flex-col items-center rounded-xl p-8 transition-colors duration-300 hover:bg-blue-600"
            >
              <img
                class="md:min-h-32 md:max-h-32 md:min-w-[8rem] md:max-w-[8rem] min-h-20 max-h-20 min-w-[5rem] max-w-[5rem] rounded-full object-cover ring-4 ring-gray-300"
                src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=687&q=80"
                alt=""
              />

              <h1
                class="mt-4 md:text-2xl text-lg font-semibold capitalize text-gray-700 group-hover:text-white dark:text-white"
              >
                Joseph Gonzalez
              </h1>

              <p
                class="mt-2 md:text-md text-xs capitalize text-gray-500 group-hover:text-gray-300 dark:text-gray-300"
              >
                Software engineer
              </p>

              <div class="-mx-2 mt-3 flex">
                <a
                  href="#"
                  class="mx-2 text-gray-600 hover:text-gray-500 group-hover:text-white dark:text-gray-300 dark:hover:text-gray-300"
                  aria-label="Reddit"
                >
                  <i class="bx bxl-telegram text-xl"></i>
                </a>

                <a
                  href="#"
                  class="mx-2 text-gray-600 hover:text-gray-500 group-hover:text-white dark:text-gray-300 dark:hover:text-gray-300"
                  aria-label="Facebook"
                >
                  <svg
                    class="h-6 w-6 fill-current"
                    viewBox="0 0 24 24"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      d="M2.00195 12.002C2.00312 16.9214 5.58036 21.1101 10.439 21.881V14.892H7.90195V12.002H10.442V9.80204C10.3284 8.75958 10.6845 7.72064 11.4136 6.96698C12.1427 6.21332 13.1693 5.82306 14.215 5.90204C14.9655 5.91417 15.7141 5.98101 16.455 6.10205V8.56104H15.191C14.7558 8.50405 14.3183 8.64777 14.0017 8.95171C13.6851 9.25566 13.5237 9.68693 13.563 10.124V12.002H16.334L15.891 14.893H13.563V21.881C18.8174 21.0506 22.502 16.2518 21.9475 10.9611C21.3929 5.67041 16.7932 1.73997 11.4808 2.01722C6.16831 2.29447 2.0028 6.68235 2.00195 12.002Z"
                    ></path>
                  </svg>
                </a>

                <a
                  href="#"
                  class="mx-2 text-gray-600 hover:text-gray-500 group-hover:text-white dark:text-gray-300 dark:hover:text-gray-300"
                  aria-label="Github"
                >
                  <svg
                    class="h-6 w-6 fill-current"
                    viewBox="0 0 24 24"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      d="M12.026 2C7.13295 1.99937 2.96183 5.54799 2.17842 10.3779C1.395 15.2079 4.23061 19.893 8.87302 21.439C9.37302 21.529 9.55202 21.222 9.55202 20.958C9.55202 20.721 9.54402 20.093 9.54102 19.258C6.76602 19.858 6.18002 17.92 6.18002 17.92C5.99733 17.317 5.60459 16.7993 5.07302 16.461C4.17302 15.842 5.14202 15.856 5.14202 15.856C5.78269 15.9438 6.34657 16.3235 6.66902 16.884C6.94195 17.3803 7.40177 17.747 7.94632 17.9026C8.49087 18.0583 9.07503 17.99 9.56902 17.713C9.61544 17.207 9.84055 16.7341 10.204 16.379C7.99002 16.128 5.66202 15.272 5.66202 11.449C5.64973 10.4602 6.01691 9.5043 6.68802 8.778C6.38437 7.91731 6.42013 6.97325 6.78802 6.138C6.78802 6.138 7.62502 5.869 9.53002 7.159C11.1639 6.71101 12.8882 6.71101 14.522 7.159C16.428 5.868 17.264 6.138 17.264 6.138C17.6336 6.97286 17.6694 7.91757 17.364 8.778C18.0376 9.50423 18.4045 10.4626 18.388 11.453C18.388 15.286 16.058 16.128 13.836 16.375C14.3153 16.8651 14.5612 17.5373 14.511 18.221C14.511 19.555 14.499 20.631 14.499 20.958C14.499 21.225 14.677 21.535 15.186 21.437C19.8265 19.8884 22.6591 15.203 21.874 10.3743C21.089 5.54565 16.9181 1.99888 12.026 2Z"
                    ></path>
                  </svg>
                </a>
              </div>
            </div>
            <div
              class="group flex min-w-[14rem] transform cursor-pointer flex-col items-center rounded-xl p-8 transition-colors duration-300 hover:bg-blue-600"
            >
              <img
                class="md:min-h-32 md:max-h-32 md:min-w-[8rem] md:max-w-[8rem] min-h-20 max-h-20 min-w-[5rem] max-w-[5rem] rounded-full object-cover ring-4 ring-gray-300"
                src="https://images.unsplash.com/photo-1535713875002-d1d0cf377fde?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=880&q=80"
                alt=""
              />

              <h1
                class="mt-4 md:text-2xl text-lg font-semibold capitalize text-gray-700 group-hover:text-white dark:text-white"
              >
                arthur melo
              </h1>

              <p
                class="mt-2 md:text-md text-xs capitalize text-gray-500 group-hover:text-gray-300 dark:text-gray-300"
              >
                design director
              </p>

              <div class="-mx-2 mt-3 flex">
                <a
                  href="#"
                  class="mx-2 text-gray-600 hover:text-gray-500 group-hover:text-white dark:text-gray-300 dark:hover:text-gray-300"
                  aria-label="Reddit"
                >
                  <i class="bx bxl-telegram text-xl"></i>
                </a>

                <a
                  href="#"
                  class="mx-2 text-gray-600 hover:text-gray-500 group-hover:text-white dark:text-gray-300 dark:hover:text-gray-300"
                  aria-label="Facebook"
                >
                  <svg
                    class="h-6 w-6 fill-current"
                    viewBox="0 0 24 24"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      d="M2.00195 12.002C2.00312 16.9214 5.58036 21.1101 10.439 21.881V14.892H7.90195V12.002H10.442V9.80204C10.3284 8.75958 10.6845 7.72064 11.4136 6.96698C12.1427 6.21332 13.1693 5.82306 14.215 5.90204C14.9655 5.91417 15.7141 5.98101 16.455 6.10205V8.56104H15.191C14.7558 8.50405 14.3183 8.64777 14.0017 8.95171C13.6851 9.25566 13.5237 9.68693 13.563 10.124V12.002H16.334L15.891 14.893H13.563V21.881C18.8174 21.0506 22.502 16.2518 21.9475 10.9611C21.3929 5.67041 16.7932 1.73997 11.4808 2.01722C6.16831 2.29447 2.0028 6.68235 2.00195 12.002Z"
                    ></path>
                  </svg>
                </a>

                <a
                  href="#"
                  class="mx-2 text-gray-600 hover:text-gray-500 group-hover:text-white dark:text-gray-300 dark:hover:text-gray-300"
                  aria-label="Github"
                >
                  <svg
                    class="h-6 w-6 fill-current"
                    viewBox="0 0 24 24"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      d="M12.026 2C7.13295 1.99937 2.96183 5.54799 2.17842 10.3779C1.395 15.2079 4.23061 19.893 8.87302 21.439C9.37302 21.529 9.55202 21.222 9.55202 20.958C9.55202 20.721 9.54402 20.093 9.54102 19.258C6.76602 19.858 6.18002 17.92 6.18002 17.92C5.99733 17.317 5.60459 16.7993 5.07302 16.461C4.17302 15.842 5.14202 15.856 5.14202 15.856C5.78269 15.9438 6.34657 16.3235 6.66902 16.884C6.94195 17.3803 7.40177 17.747 7.94632 17.9026C8.49087 18.0583 9.07503 17.99 9.56902 17.713C9.61544 17.207 9.84055 16.7341 10.204 16.379C7.99002 16.128 5.66202 15.272 5.66202 11.449C5.64973 10.4602 6.01691 9.5043 6.68802 8.778C6.38437 7.91731 6.42013 6.97325 6.78802 6.138C6.78802 6.138 7.62502 5.869 9.53002 7.159C11.1639 6.71101 12.8882 6.71101 14.522 7.159C16.428 5.868 17.264 6.138 17.264 6.138C17.6336 6.97286 17.6694 7.91757 17.364 8.778C18.0376 9.50423 18.4045 10.4626 18.388 11.453C18.388 15.286 16.058 16.128 13.836 16.375C14.3153 16.8651 14.5612 17.5373 14.511 18.221C14.511 19.555 14.499 20.631 14.499 20.958C14.499 21.225 14.677 21.535 15.186 21.437C19.8265 19.8884 22.6591 15.203 21.874 10.3743C21.089 5.54565 16.9181 1.99888 12.026 2Z"
                    ></path>
                  </svg>
                </a>
              </div>
            </div>

            <div
              class="group flex min-w-[14rem] transform cursor-pointer flex-col items-center rounded-xl p-8 transition-colors duration-300 hover:bg-blue-600"
            >
              <img
                class="md:min-h-32 md:max-h-32 md:min-w-[8rem] md:max-w-[8rem] min-h-20 max-h-20 min-w-[5rem] max-w-[5rem] rounded-full object-cover ring-4 ring-gray-300"
                src="https://images.unsplash.com/photo-1570295999919-56ceb5ecca61?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=880&q=80"
                alt=""
              />

              <h1
                class="mt-4 md:text-2xl text-lg font-semibold capitalize text-gray-700 group-hover:text-white dark:text-white"
              >
                John Doe
              </h1>

              <p
                class="mt-2 md:text-md text-xs capitalize text-gray-500 group-hover:text-gray-300 dark:text-gray-300"
              >
                Full stack developer
              </p>

              <div class="-mx-2 mt-3 flex">
                <a
                  href="#"
                  class="mx-2 text-gray-600 hover:text-gray-500 group-hover:text-white dark:text-gray-300 dark:hover:text-gray-300"
                  aria-label="Reddit"
                >
                  <i class="bx bxl-telegram text-xl"></i>
                </a>

                <a
                  href="#"
                  class="mx-2 text-gray-600 hover:text-gray-500 group-hover:text-white dark:text-gray-300 dark:hover:text-gray-300"
                  aria-label="Facebook"
                >
                  <svg
                    class="h-6 w-6 fill-current"
                    viewBox="0 0 24 24"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      d="M2.00195 12.002C2.00312 16.9214 5.58036 21.1101 10.439 21.881V14.892H7.90195V12.002H10.442V9.80204C10.3284 8.75958 10.6845 7.72064 11.4136 6.96698C12.1427 6.21332 13.1693 5.82306 14.215 5.90204C14.9655 5.91417 15.7141 5.98101 16.455 6.10205V8.56104H15.191C14.7558 8.50405 14.3183 8.64777 14.0017 8.95171C13.6851 9.25566 13.5237 9.68693 13.563 10.124V12.002H16.334L15.891 14.893H13.563V21.881C18.8174 21.0506 22.502 16.2518 21.9475 10.9611C21.3929 5.67041 16.7932 1.73997 11.4808 2.01722C6.16831 2.29447 2.0028 6.68235 2.00195 12.002Z"
                    ></path>
                  </svg>
                </a>

                <a
                  href="#"
                  class="mx-2 text-gray-600 hover:text-gray-500 group-hover:text-white dark:text-gray-300 dark:hover:text-gray-300"
                  aria-label="Github"
                >
                  <svg
                    class="h-6 w-6 fill-current"
                    viewBox="0 0 24 24"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      d="M12.026 2C7.13295 1.99937 2.96183 5.54799 2.17842 10.3779C1.395 15.2079 4.23061 19.893 8.87302 21.439C9.37302 21.529 9.55202 21.222 9.55202 20.958C9.55202 20.721 9.54402 20.093 9.54102 19.258C6.76602 19.858 6.18002 17.92 6.18002 17.92C5.99733 17.317 5.60459 16.7993 5.07302 16.461C4.17302 15.842 5.14202 15.856 5.14202 15.856C5.78269 15.9438 6.34657 16.3235 6.66902 16.884C6.94195 17.3803 7.40177 17.747 7.94632 17.9026C8.49087 18.0583 9.07503 17.99 9.56902 17.713C9.61544 17.207 9.84055 16.7341 10.204 16.379C7.99002 16.128 5.66202 15.272 5.66202 11.449C5.64973 10.4602 6.01691 9.5043 6.68802 8.778C6.38437 7.91731 6.42013 6.97325 6.78802 6.138C6.78802 6.138 7.62502 5.869 9.53002 7.159C11.1639 6.71101 12.8882 6.71101 14.522 7.159C16.428 5.868 17.264 6.138 17.264 6.138C17.6336 6.97286 17.6694 7.91757 17.364 8.778C18.0376 9.50423 18.4045 10.4626 18.388 11.453C18.388 15.286 16.058 16.128 13.836 16.375C14.3153 16.8651 14.5612 17.5373 14.511 18.221C14.511 19.555 14.499 20.631 14.499 20.958C14.499 21.225 14.677 21.535 15.186 21.437C19.8265 19.8884 22.6591 15.203 21.874 10.3743C21.089 5.54565 16.9181 1.99888 12.026 2Z"
                    ></path>
                  </svg>
                </a>
              </div>
            </div>

            <div
              class="group flex min-w-[14rem] transform cursor-pointer flex-col items-center rounded-xl p-8 transition-colors duration-300 hover:bg-blue-600"
            >
              <img
                class="md:min-h-32 md:max-h-32 md:min-w-[8rem] md:max-w-[8rem] min-h-20 max-h-20 min-w-[5rem] max-w-[5rem] rounded-full object-cover ring-4 ring-gray-300"
                src="https://images.unsplash.com/photo-1608174386344-80898cec6beb?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=687&q=80"
                alt=""
              />

              <h1
                class="mt-4 md:text-2xl text-lg font-semibold capitalize text-gray-700 group-hover:text-white dark:text-white"
              >
                Junior REIS
              </h1>

              <p
                class="mt-2 md:text-md text-xs capitalize text-gray-500 group-hover:text-gray-300 dark:text-gray-300"
              >
                Products Managers
              </p>

              <div class="-mx-2 mt-3 flex">
                <a
                  href="#"
                  class="mx-2 text-gray-600 hover:text-gray-500 group-hover:text-white dark:text-gray-300 dark:hover:text-gray-300"
                  aria-label="Reddit"
                >
                  <i class="bx bxl-telegram text-xl"></i>
                </a>

                <a
                  href="#"
                  class="mx-2 text-gray-600 hover:text-gray-500 group-hover:text-white dark:text-gray-300 dark:hover:text-gray-300"
                  aria-label="Facebook"
                >
                  <svg
                    class="h-6 w-6 fill-current"
                    viewBox="0 0 24 24"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      d="M2.00195 12.002C2.00312 16.9214 5.58036 21.1101 10.439 21.881V14.892H7.90195V12.002H10.442V9.80204C10.3284 8.75958 10.6845 7.72064 11.4136 6.96698C12.1427 6.21332 13.1693 5.82306 14.215 5.90204C14.9655 5.91417 15.7141 5.98101 16.455 6.10205V8.56104H15.191C14.7558 8.50405 14.3183 8.64777 14.0017 8.95171C13.6851 9.25566 13.5237 9.68693 13.563 10.124V12.002H16.334L15.891 14.893H13.563V21.881C18.8174 21.0506 22.502 16.2518 21.9475 10.9611C21.3929 5.67041 16.7932 1.73997 11.4808 2.01722C6.16831 2.29447 2.0028 6.68235 2.00195 12.002Z"
                    ></path>
                  </svg>
                </a>

                <a
                  href="#"
                  class="mx-2 text-gray-600 hover:text-gray-500 group-hover:text-white dark:text-gray-300 dark:hover:text-gray-300"
                  aria-label="Github"
                >
                  <svg
                    class="h-6 w-6 fill-current"
                    viewBox="0 0 24 24"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      d="M12.026 2C7.13295 1.99937 2.96183 5.54799 2.17842 10.3779C1.395 15.2079 4.23061 19.893 8.87302 21.439C9.37302 21.529 9.55202 21.222 9.55202 20.958C9.55202 20.721 9.54402 20.093 9.54102 19.258C6.76602 19.858 6.18002 17.92 6.18002 17.92C5.99733 17.317 5.60459 16.7993 5.07302 16.461C4.17302 15.842 5.14202 15.856 5.14202 15.856C5.78269 15.9438 6.34657 16.3235 6.66902 16.884C6.94195 17.3803 7.40177 17.747 7.94632 17.9026C8.49087 18.0583 9.07503 17.99 9.56902 17.713C9.61544 17.207 9.84055 16.7341 10.204 16.379C7.99002 16.128 5.66202 15.272 5.66202 11.449C5.64973 10.4602 6.01691 9.5043 6.68802 8.778C6.38437 7.91731 6.42013 6.97325 6.78802 6.138C6.78802 6.138 7.62502 5.869 9.53002 7.159C11.1639 6.71101 12.8882 6.71101 14.522 7.159C16.428 5.868 17.264 6.138 17.264 6.138C17.6336 6.97286 17.6694 7.91757 17.364 8.778C18.0376 9.50423 18.4045 10.4626 18.388 11.453C18.388 15.286 16.058 16.128 13.836 16.375C14.3153 16.8651 14.5612 17.5373 14.511 18.221C14.511 19.555 14.499 20.631 14.499 20.958C14.499 21.225 14.677 21.535 15.186 21.437C19.8265 19.8884 22.6591 15.203 21.874 10.3743C21.089 5.54565 16.9181 1.99888 12.026 2Z"
                    ></path>
                  </svg>
                </a>
              </div>
            </div>

            <div
              class="group flex min-w-[14rem] transform cursor-pointer flex-col items-center rounded-xl p-8 transition-colors duration-300 hover:bg-blue-600"
            >
              <img
                class="md:min-h-32 md:max-h-32 md:min-w-[8rem] md:max-w-[8rem] min-h-20 max-h-20 min-w-[5rem] max-w-[5rem] rounded-full object-cover ring-4 ring-gray-300"
                src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=687&q=80"
                alt=""
              />

              <h1
                class="mt-4 md:text-2xl text-lg font-semibold capitalize text-gray-700 group-hover:text-white dark:text-white"
              >
                Joseph Gonzalez
              </h1>

              <p
                class="mt-2 md:text-md text-xs capitalize text-gray-500 group-hover:text-gray-300 dark:text-gray-300"
              >
                Software engineer
              </p>

              <div class="-mx-2 mt-3 flex">
                <a
                  href="#"
                  class="mx-2 text-gray-600 hover:text-gray-500 group-hover:text-white dark:text-gray-300 dark:hover:text-gray-300"
                  aria-label="Reddit"
                >
                  <i class="bx bxl-telegram text-xl"></i>
                </a>

                <a
                  href="#"
                  class="mx-2 text-gray-600 hover:text-gray-500 group-hover:text-white dark:text-gray-300 dark:hover:text-gray-300"
                  aria-label="Facebook"
                >
                  <svg
                    class="h-6 w-6 fill-current"
                    viewBox="0 0 24 24"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      d="M2.00195 12.002C2.00312 16.9214 5.58036 21.1101 10.439 21.881V14.892H7.90195V12.002H10.442V9.80204C10.3284 8.75958 10.6845 7.72064 11.4136 6.96698C12.1427 6.21332 13.1693 5.82306 14.215 5.90204C14.9655 5.91417 15.7141 5.98101 16.455 6.10205V8.56104H15.191C14.7558 8.50405 14.3183 8.64777 14.0017 8.95171C13.6851 9.25566 13.5237 9.68693 13.563 10.124V12.002H16.334L15.891 14.893H13.563V21.881C18.8174 21.0506 22.502 16.2518 21.9475 10.9611C21.3929 5.67041 16.7932 1.73997 11.4808 2.01722C6.16831 2.29447 2.0028 6.68235 2.00195 12.002Z"
                    ></path>
                  </svg>
                </a>

                <a
                  href="#"
                  class="mx-2 text-gray-600 hover:text-gray-500 group-hover:text-white dark:text-gray-300 dark:hover:text-gray-300"
                  aria-label="Github"
                >
                  <svg
                    class="h-6 w-6 fill-current"
                    viewBox="0 0 24 24"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      d="M12.026 2C7.13295 1.99937 2.96183 5.54799 2.17842 10.3779C1.395 15.2079 4.23061 19.893 8.87302 21.439C9.37302 21.529 9.55202 21.222 9.55202 20.958C9.55202 20.721 9.54402 20.093 9.54102 19.258C6.76602 19.858 6.18002 17.92 6.18002 17.92C5.99733 17.317 5.60459 16.7993 5.07302 16.461C4.17302 15.842 5.14202 15.856 5.14202 15.856C5.78269 15.9438 6.34657 16.3235 6.66902 16.884C6.94195 17.3803 7.40177 17.747 7.94632 17.9026C8.49087 18.0583 9.07503 17.99 9.56902 17.713C9.61544 17.207 9.84055 16.7341 10.204 16.379C7.99002 16.128 5.66202 15.272 5.66202 11.449C5.64973 10.4602 6.01691 9.5043 6.68802 8.778C6.38437 7.91731 6.42013 6.97325 6.78802 6.138C6.78802 6.138 7.62502 5.869 9.53002 7.159C11.1639 6.71101 12.8882 6.71101 14.522 7.159C16.428 5.868 17.264 6.138 17.264 6.138C17.6336 6.97286 17.6694 7.91757 17.364 8.778C18.0376 9.50423 18.4045 10.4626 18.388 11.453C18.388 15.286 16.058 16.128 13.836 16.375C14.3153 16.8651 14.5612 17.5373 14.511 18.221C14.511 19.555 14.499 20.631 14.499 20.958C14.499 21.225 14.677 21.535 15.186 21.437C19.8265 19.8884 22.6591 15.203 21.874 10.3743C21.089 5.54565 16.9181 1.99888 12.026 2Z"
                    ></path>
                  </svg>
                </a>
              </div>
            </div>
          </div>
        </div>
      </section>

      <section class="min-h-[125vh] flex items-center justify-center">
        <!-- component -->
        <div
          class="antialiased w-full h-full bg-white text-gray-400 font-inter py-10"
        >
          <div class="container mx-auto">
            <div>
              <div id="title" class="mb-5 mt-24">
                <h1 class="font-bold text-4xl text-gray-800">{{ $t("pricing.title") }}</h1>
                <p class="text-gray-500 text-xl">
                  {{ $t("pricing.description") }}
                </p>
              </div>
              <div
                class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 justify-evenly gap-10 pt-10"
              >
                <div
                  id="plan"
                  class="rounded-lg border-2 text-center overflow-hidden w-full transform hover:shadow-2xl hover:scale-105 transition duration-200 ease-in"
                >
                  <div id="title" class="w-full py-5 border-b border-gray-800">
                    <h2 class="font-bold text-3xl text-white">Startup</h2>
                    <h3 class="font-normal text-indigo-500 text-xl mt-2">
                      $9<sup>,99</sup>/{{ $t("pricing.month") }}
                    </h3>
                  </div>
                  <div id="content" class="">
                    <div id="icon" class="my-5">
                      <svg
                        xmlns="http://www.w3.org/2000/svg"
                        class="h-12 w-12 mx-auto fill-stroke text-indigo-600"
                        fill="none"
                        viewBox="0 0 24 24"
                        stroke="currentColor"
                      >
                        <path
                          stroke-linecap="round"
                          stroke-linejoin="round"
                          stroke-width="1"
                          d="M9.75 17L9 20l-1 1h8l-1-1-.75-3M3 13h18M5 17h14a2 2 0 002-2V5a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"
                        />
                      </svg>
                      <p class="text-gray-500 text-sm pt-2">
                        {{ $t("pricing.title1") }}
                      </p>
                    </div>
                    <div
                      id="contain"
                      class="leading-8 mb-10 text-lg font-light"
                    >
                      <ul>
                        <li>10 <span>{{ $t("pricing.hour") }}</span></li>
                        <li>128MB <span>{{ $t("pricing.storage") }}</span></li>
                        <li>2048MB <span>{{ $t("pricing.bandwith") }}</span></li>
                        <li>{{ $t("pricing.subdomen") }}</li>
                      </ul>
                      <div id="choose" class="w-full mt-10 px-6">
                        <a
                          href="#"
                          class="w-full block bg-gray-900 font-medium text-xl py-4 rounded-xl hover:shadow-lg transition duration-200 ease-in-out hover:bg-indigo-600 hover:text-white"
                          >{{ $t("pricing.choose") }}</a
                        >
                      </div>
                    </div>
                  </div>
                </div>
                <div
                  id="plan"
                  class="rounded-lg border-2 text-center overflow-hidden w-full transform hover:shadow-2xl hover:scale-105 transition duration-200 ease-in"
                >
                  <div id="title" class="w-full py-5 border-b border-gray-800">
                    <h2 class="font-bold text-3xl text-white">Corporate</h2>
                    <h3 class="font-normal text-indigo-500 text-xl mt-2">
                      $12<sup>,99</sup>/{{ $t("pricing.month") }}
                    </h3>
                  </div>
                  <div id="content" class="">
                    <div id="icon" class="my-5">
                      <svg
                        xmlns="http://www.w3.org/2000/svg"
                        class="h-12 w-12 mx-auto fill-stroke text-indigo-600"
                        fill="none"
                        viewBox="0 0 24 24"
                        stroke="currentColor"
                      >
                        <path
                          stroke-linecap="round"
                          stroke-linejoin="round"
                          stroke-width="1"
                          d="M5 3v4M3 5h4M6 17v4m-2-2h4m5-16l2.286 6.857L21 12l-5.714 2.143L13 21l-2.286-6.857L5 12l5.714-2.143L13 3z"
                        />
                      </svg>
                      <p class="text-gray-500 text-sm pt-2">
                        {{ $t("pricing.title2") }}
                      </p>
                    </div>
                    <div
                      id="contain"
                      class="leading-8 mb-10 text-lg font-light"
                    >
                      <ul>
                        <li>10 <span>{{ $t("pricing.hour") }}</span></li>
                        <li>1024MB <span>{{ $t("pricing.storage") }}</span></li>
                        <li>4GB <span>{{ $t("pricing.bandwith") }}</span></li>
                        <li>{{ $t("pricing.domen") }}</li>
                      </ul>
                      <div id="choose" class="w-full mt-10 px-6">
                        <a
                          href="#"
                          class="w-full block bg-gray-900 font-medium text-xl py-4 rounded-xl hover:shadow-lg transition duration-200 ease-in-out hover:bg-indigo-600 hover:text-white"
                          >{{ $t("pricing.choose") }}</a
                        >
                      </div>
                    </div>
                  </div>
                </div>
                <div
                  id="plan"
                  class="rounded-lg border-2 text-center overflow-hidden w-full transform hover:shadow-2xl hover:scale-105 transition duration-200 ease-in"
                >
                  <div id="title" class="w-full py-5 border-b border-gray-800">
                    <h2 class="font-bold text-3xl text-white">Enterprise</h2>
                    <h3 class="font-normal text-indigo-500 text-xl mt-2">
                      $19<sup>,99</sup>/{{ $t("pricing.month") }}
                    </h3>
                  </div>
                  <div id="content" class="">
                    <div id="icon" class="my-5">
                      <svg
                        xmlns="http://www.w3.org/2000/svg"
                        class="h-12 w-12 mx-auto fill-stroke text-indigo-600"
                        fill="none"
                        viewBox="0 0 24 24"
                        stroke="currentColor"
                      >
                        <path
                          stroke-linecap="round"
                          stroke-linejoin="round"
                          stroke-width="1"
                          d="M19 21V5a2 2 0 00-2-2H7a2 2 0 00-2 2v16m14 0h2m-2 0h-5m-9 0H3m2 0h5M9 7h1m-1 4h1m4-4h1m-1 4h1m-5 10v-5a1 1 0 011-1h2a1 1 0 011 1v5m-4 0h4"
                        />
                      </svg>
                      <p class="text-gray-500 text-sm pt-2">
                        {{ $t("pricing.title3") }}
                      </p>
                    </div>
                    <div
                      id="contain"
                      class="leading-8 mb-10 text-lg font-light"
                    >
                      <ul>
                        <li>10 <span>{{ $t("pricing.hour") }}</span></li>
                        <li>10GB <span>{{ $t("pricing.storage") }}</span></li>
                        <li>100GB <span>{{ $t("pricing.bandwith") }}</span></li>
                        <li>{{ $t("pricing.domen") }}</li>
                      </ul>
                      <div id="choose" class="w-full mt-10 px-6">
                        <a
                          href="#"
                          class="w-full block bg-gray-900 font-medium text-xl py-4 rounded-xl hover:shadow-lg transition duration-200 ease-in-out hover:bg-indigo-600 hover:text-white"
                          >{{ $t("pricing.choose") }}</a
                        >
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <section
        class="bg-white flex justify-center items-center dark:bg-gray-900"
      >
        <div class="container mx-auto">
          <div>
            <div
              id="controls-carousel"
              class="relative w-full"
              data-carousel="static"
            >
              <div class="mt-6 md:flex md:items-center md:justify-between">
                <div>
                  <h1
                    class="text-3xl font-semibold capitalize text-gray-800 dark:text-white lg:text-4xl"
                  >
                    What our clients are saying
                  </h1>

                  <div class="mx-auto mt-6 flex">
                    <span
                      class="inline-block h-1 w-40 rounded-full bg-blue-500"
                    ></span>
                    <span
                      class="mx-1 inline-block h-1 w-3 rounded-full bg-blue-500"
                    ></span>
                    <span
                      class="inline-block h-1 w-1 rounded-full bg-blue-500"
                    ></span>
                  </div>
                </div>

                <div class="mt-8 flex justify-between md:mt-0">
                  <!-- Slider controls -->
                  <button
                    type="button"
                    class="flex items-center justify-center h-full px-4 cursor-pointer group focus:outline-none"
                    data-carousel-prev
                  >
                    <span
                      class="inline-flex items-center border-2 border-blue-600 justify-center w-10 h-10 rounded-full bg-white/30 dark:bg-gray-800/30 group-hover:bg-white/50 dark:group-hover:bg-gray-800/60 group-focus:ring-4 group-focus:ring-white dark:group-focus:ring-gray-800/70 group-focus:outline-none"
                    >
                      <svg
                        class="w-4 h-4 text-blue-600 dark:text-gray-800"
                        aria-hidden="true"
                        xmlns="http://www.w3.org/2000/svg"
                        fill="none"
                        viewBox="0 0 6 10"
                      >
                        <path
                          stroke="currentColor"
                          stroke-linecap="round"
                          stroke-linejoin="round"
                          stroke-width="2"
                          d="M5 1 1 5l4 4"
                        />
                      </svg>
                    </span>
                  </button>
                  <button
                    type="button"
                    class="flex items-center justify-center h-full px-4 cursor-pointer group focus:outline-none"
                    data-carousel-next
                  >
                    <span
                      class="inline-flex items-center border-2 border-blue-600 justify-center w-10 h-10 rounded-full bg-white/30 dark:bg-gray-800/30 group-hover:bg-white/50 dark:group-hover:bg-gray-800/60 group-focus:ring-4 group-focus:ring-white dark:group-focus:ring-gray-800/70 group-focus:outline-none"
                    >
                      <svg
                        class="w-4 h-4 text-blue-600 dark:text-gray-800"
                        aria-hidden="true"
                        xmlns="http://www.w3.org/2000/svg"
                        fill="none"
                        viewBox="0 0 6 10"
                      >
                        <path
                          stroke="currentColor"
                          stroke-linecap="round"
                          stroke-linejoin="round"
                          stroke-width="2"
                          d="m1 9 4-4-4-4"
                        />
                      </svg>
                      <span class="sr-only">Next</span>
                    </span>
                  </button>
                </div>
              </div>
              <!-- Carousel wrapper -->
              <div
                class="relative min-h-[30rem] my-10 rounded-lg overflow-hidden"
              >
                <!-- Item 1 -->
                <div class="hidden duration-700 ease-in-out" data-carousel-item>
                  <div class="flex gap-5 justify-center items-center">
                    <div class="rounded-lg border p-8 dark:border-gray-700">
                      <p class="leading-loose text-gray-500 dark:text-gray-400">
                        “Lorem ipsum dolor sit amet, consectetur adipisicing
                        elit. Tempore quibusdam ducimus libero ad tempora
                        doloribus expedita laborum saepe voluptas perferendis
                        delectus assumenda rerum, culpa aperiam dolorum,
                        obcaecati corrupti aspernatur a.”.
                      </p>

                      <div class="-mx-2 mt-8 flex items-center">
                        <img
                          class="mx-2 h-14 w-14 shrink-0 rounded-full object-cover ring-4 ring-gray-300 dark:ring-gray-700"
                          src="https://images.unsplash.com/photo-1570295999919-56ceb5ecca61?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=880&q=80"
                          alt=""
                        />

                        <div class="mx-2">
                          <h1
                            class="font-semibold text-gray-800 dark:text-white"
                          >
                            Robert
                          </h1>
                          <span class="text-sm text-gray-500 dark:text-gray-400"
                            >CTO, Robert Consultency</span
                          >
                        </div>
                      </div>
                    </div>
                    <div
                      class="md:block hidden rounded-lg border p-8 dark:border-gray-700"
                    >
                      <p class="leading-loose text-gray-500 dark:text-gray-400">
                        “Lorem ipsum dolor sit amet, consectetur adipisicing
                        elit. Tempore quibusdam ducimus libero ad tempora
                        doloribus expedita laborum saepe voluptas perferendis
                        delectus assumenda rerum, culpa aperiam dolorum,
                        obcaecati corrupti aspernatur a.”.
                      </p>

                      <div class="-mx-2 mt-8 flex items-center">
                        <img
                          class="mx-2 h-14 w-14 shrink-0 rounded-full object-cover ring-4 ring-gray-300 dark:ring-gray-700"
                          src="https://images.unsplash.com/photo-1488508872907-592763824245?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80"
                          alt=""
                        />

                        <div class="mx-2">
                          <h1
                            class="font-semibold text-gray-800 dark:text-white"
                          >
                            Ema Watson
                          </h1>
                          <span class="text-sm text-gray-500 dark:text-gray-400"
                            >Marketing Manager at Stech</span
                          >
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
                <!-- Item 2 -->
                <div
                  class="hidden duration-700 ease-in-out"
                  data-carousel-item="active"
                >
                  <div class="flex gap-5 justify-center items-center">
                    <div class="md:block hidden rounded-lg border p-8">
                      <p class="leading-loose text-gray-500">
                        “Lorem ipsum dolor sit amet, consectetur adipisicing
                        elit. Tempore quibusdam ducimus libero ad tempora
                        doloribus expedita laborum saepe voluptas perferendis
                        delectus assumenda rerum, culpa aperiam dolorum,
                        obcaecati corrupti aspernatur a.”.
                      </p>

                      <div class="-mx-2 mt-8 flex items-center">
                        <img
                          class="mx-2 h-14 w-14 shrink-0 rounded-full object-cover ring-4 ring-blue-200"
                          src="https://images.unsplash.com/photo-1531590878845-12627191e687?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=764&q=80"
                          alt=""
                        />

                        <div class="mx-2">
                          <h1 class="font-semibold text-gray-900">Jeny Doe</h1>
                          <span class="text-sm text-gray-600"
                            >CEO, Jeny Consultency</span
                          >
                        </div>
                      </div>
                    </div>
                    <div class="rounded-lg border p-8 dark:border-gray-700">
                      <p class="leading-loose text-gray-500 dark:text-gray-400">
                        “Lorem ipsum dolor sit amet, consectetur adipisicing
                        elit. Tempore quibusdam ducimus libero ad tempora
                        doloribus expedita laborum saepe voluptas perferendis
                        delectus assumenda rerum, culpa aperiam dolorum,
                        obcaecati corrupti aspernatur a.”.
                      </p>

                      <div class="-mx-2 mt-8 flex items-center">
                        <img
                          class="mx-2 h-14 w-14 shrink-0 rounded-full object-cover ring-4 ring-gray-300 dark:ring-gray-700"
                          src="https://images.unsplash.com/photo-1488508872907-592763824245?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80"
                          alt=""
                        />

                        <div class="mx-2">
                          <h1
                            class="font-semibold text-gray-800 dark:text-white"
                          >
                            Ema Watson
                          </h1>
                          <span class="text-sm text-gray-500 dark:text-gray-400"
                            >Marketing Manager at Stech</span
                          >
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
                <!-- Item 3 -->
                <div class="hidden duration-700 ease-in-out" data-carousel-item>
                  <div class="flex gap-5 justify-center items-center">
                    <div class="rounded-lg border p-8 dark:border-gray-700">
                      <p class="leading-loose text-gray-500 dark:text-gray-400">
                        “Lorem ipsum dolor sit amet, consectetur adipisicing
                        elit. Tempore quibusdam ducimus libero ad tempora
                        doloribus expedita laborum saepe voluptas perferendis
                        delectus assumenda rerum, culpa aperiam dolorum,
                        obcaecati corrupti aspernatur a.”.
                      </p>

                      <div class="-mx-2 mt-8 flex items-center">
                        <img
                          class="mx-2 h-14 w-14 shrink-0 rounded-full object-cover ring-4 ring-gray-300 dark:ring-gray-700"
                          src="https://images.unsplash.com/photo-1570295999919-56ceb5ecca61?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=880&q=80"
                          alt=""
                        />

                        <div class="mx-2">
                          <h1
                            class="font-semibold text-gray-800 dark:text-white"
                          >
                            Robert
                          </h1>
                          <span class="text-sm text-gray-500 dark:text-gray-400"
                            >CTO, Robert Consultency</span
                          >
                        </div>
                      </div>
                    </div>
                    <div
                      class="md:block hidden rounded-lg border p-8 dark:border-gray-700"
                    >
                      <p class="leading-loose text-gray-500 dark:text-gray-400">
                        “Lorem ipsum dolor sit amet, consectetur adipisicing
                        elit. Tempore quibusdam ducimus libero ad tempora
                        doloribus expedita laborum saepe voluptas perferendis
                        delectus assumenda rerum, culpa aperiam dolorum,
                        obcaecati corrupti aspernatur a.”.
                      </p>

                      <div class="-mx-2 mt-8 flex items-center">
                        <img
                          class="mx-2 h-14 w-14 shrink-0 rounded-full object-cover ring-4 ring-gray-300 dark:ring-gray-700"
                          src="https://images.unsplash.com/photo-1488508872907-592763824245?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80"
                          alt=""
                        />

                        <div class="mx-2">
                          <h1
                            class="font-semibold text-gray-800 dark:text-white"
                          >
                            Ema Watson
                          </h1>
                          <span class="text-sm text-gray-500 dark:text-gray-400"
                            >Marketing Manager at Stech</span
                          >
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
                <!-- Item 4 -->
                <div class="hidden duration-700 ease-in-out" data-carousel-item>
                  <div class="flex gap-5 justify-center items-center">
                    <div
                      class="md:block hidden rounded-lg border p-8 dark:border-gray-700"
                    >
                      <p class="leading-loose text-gray-500 dark:text-gray-400">
                        “Lorem ipsum dolor sit amet, consectetur adipisicing
                        elit. Tempore quibusdam ducimus libero ad tempora
                        doloribus expedita laborum saepe voluptas perferendis
                        delectus assumenda rerum, culpa aperiam dolorum,
                        obcaecati corrupti aspernatur a.”.
                      </p>

                      <div class="-mx-2 mt-8 flex items-center">
                        <img
                          class="mx-2 h-14 w-14 shrink-0 rounded-full object-cover ring-4 ring-gray-300 dark:ring-gray-700"
                          src="https://images.unsplash.com/photo-1570295999919-56ceb5ecca61?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=880&q=80"
                          alt=""
                        />

                        <div class="mx-2">
                          <h1
                            class="font-semibold text-gray-800 dark:text-white"
                          >
                            Robert
                          </h1>
                          <span class="text-sm text-gray-500 dark:text-gray-400"
                            >CTO, Robert Consultency</span
                          >
                        </div>
                      </div>
                    </div>
                    <div class="rounded-lg border p-8 dark:border-gray-700">
                      <p class="leading-loose text-gray-500 dark:text-gray-400">
                        “Lorem ipsum dolor sit amet, consectetur adipisicing
                        elit. Tempore quibusdam ducimus libero ad tempora
                        doloribus expedita laborum saepe voluptas perferendis
                        delectus assumenda rerum, culpa aperiam dolorum,
                        obcaecati corrupti aspernatur a.”.
                      </p>

                      <div class="-mx-2 mt-8 flex items-center">
                        <img
                          class="mx-2 h-14 w-14 shrink-0 rounded-full object-cover ring-4 ring-gray-300 dark:ring-gray-700"
                          src="https://images.unsplash.com/photo-1488508872907-592763824245?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80"
                          alt=""
                        />

                        <div class="mx-2">
                          <h1
                            class="font-semibold text-gray-800 dark:text-white"
                          >
                            Ema Watson
                          </h1>
                          <span class="text-sm text-gray-500 dark:text-gray-400"
                            >Marketing Manager at Stech</span
                          >
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
                <!-- Item 5 -->
                <div class="hidden duration-700 ease-in-out" data-carousel-item>
                  <div class="flex gap-5 justify-center items-center">
                    <div class="rounded-lg border p-8 dark:border-gray-700">
                      <p class="leading-loose text-gray-500 dark:text-gray-400">
                        “Lorem ipsum dolor sit amet, consectetur adipisicing
                        elit. Tempore quibusdam ducimus libero ad tempora
                        doloribus expedita laborum saepe voluptas perferendis
                        delectus assumenda rerum, culpa aperiam dolorum,
                        obcaecati corrupti aspernatur a.”.
                      </p>

                      <div class="-mx-2 mt-8 flex items-center">
                        <img
                          class="mx-2 h-14 w-14 shrink-0 rounded-full object-cover ring-4 ring-gray-300 dark:ring-gray-700"
                          src="https://images.unsplash.com/photo-1570295999919-56ceb5ecca61?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=880&q=80"
                          alt=""
                        />

                        <div class="mx-2">
                          <h1
                            class="font-semibold text-gray-800 dark:text-white"
                          >
                            Robert
                          </h1>
                          <span class="text-sm text-gray-500 dark:text-gray-400"
                            >CTO, Robert Consultency</span
                          >
                        </div>
                      </div>
                    </div>
                    <div
                      class="md:block hidden rounded-lg border p-8 dark:border-gray-700"
                    >
                      <p class="leading-loose text-gray-500 dark:text-gray-400">
                        “Lorem ipsum dolor sit amet, consectetur adipisicing
                        elit. Tempore quibusdam ducimus libero ad tempora
                        doloribus expedita laborum saepe voluptas perferendis
                        delectus assumenda rerum, culpa aperiam dolorum,
                        obcaecati corrupti aspernatur a.”.
                      </p>

                      <div class="-mx-2 mt-8 flex items-center">
                        <img
                          class="mx-2 h-14 w-14 shrink-0 rounded-full object-cover ring-4 ring-gray-300 dark:ring-gray-700"
                          src="https://images.unsplash.com/photo-1488508872907-592763824245?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1470&q=80"
                          alt=""
                        />

                        <div class="mx-2">
                          <h1
                            class="font-semibold text-gray-800 dark:text-white"
                          >
                            Ema Watson
                          </h1>
                          <span class="text-sm text-gray-500 dark:text-gray-400"
                            >Marketing Manager at Stech</span
                          >
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <section
        class="bg-white min-h-screen flex items-center justify-center dark:bg-gray-900"
      >
        <div class="container mx-auto lg:-mt-96">
          <h1
            class="text-2xl font-semibold mb-10 text-gray-800 dark:text-white lg:text-4xl"
          >
            Frequently asked questions.
          </h1>

          <div class="grid grid-cols-1 gap-8 md:grid-cols-2 xl:grid-cols-3">
            <div>
              <div class="inline-block rounded-lg bg-blue-600 p-3 text-white">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="h-6 w-6"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke="currentColor"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M8.228 9c.549-1.165 2.03-2 3.772-2 2.21 0 4 1.343 4 3 0 1.4-1.278 2.575-3.006 2.907-.542.104-.994.54-.994 1.093m0 3h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"
                  />
                </svg>
              </div>

              <div>
                <h1 class="text-xl font-semibold text-gray-700 dark:text-white">
                  What can i expect at my first consultation?
                </h1>

                <p class="mt-2 text-sm text-gray-500 dark:text-gray-300">
                  Lorem ipsum dolor sit amet consectetur adipisicing elit.
                  Provident placeat, consequatur eveniet veritatis quos
                  dignissimos beatae dolores exercitationem laboriosam officia
                  magnam atque blanditiis illum doloremque magni ex corrupti
                  tempora quis.
                </p>
              </div>
            </div>

            <div>
              <div class="inline-block rounded-lg bg-blue-600 p-3 text-white">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="h-6 w-6"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke="currentColor"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M8.228 9c.549-1.165 2.03-2 3.772-2 2.21 0 4 1.343 4 3 0 1.4-1.278 2.575-3.006 2.907-.542.104-.994.54-.994 1.093m0 3h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"
                  />
                </svg>
              </div>

              <div>
                <h1 class="text-xl font-semibold text-gray-700 dark:text-white">
                  What are your opening house?
                </h1>

                <p class="mt-2 text-sm text-gray-500 dark:text-gray-300">
                  Lorem ipsum dolor sit amet consectetur adipisicing elit.
                  Provident placeat, consequatur eveniet veritatis quos
                  dignissimos beatae dolores exercitationem laboriosam officia
                  magnam atque blanditiis illum doloremque magni ex corrupti
                  tempora quis.
                </p>
              </div>
            </div>

            <div>
              <div class="inline-block rounded-lg bg-blue-600 p-3 text-white">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="h-6 w-6"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke="currentColor"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M8.228 9c.549-1.165 2.03-2 3.772-2 2.21 0 4 1.343 4 3 0 1.4-1.278 2.575-3.006 2.907-.542.104-.994.54-.994 1.093m0 3h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"
                  />
                </svg>
              </div>

              <div>
                <h1 class="text-xl font-semibold text-gray-700 dark:text-white">
                  Do i need a referral?
                </h1>

                <p class="mt-2 text-sm text-gray-500 dark:text-gray-300">
                  Lorem ipsum dolor sit amet consectetur adipisicing elit.
                  Provident placeat, consequatur eveniet veritatis quos
                  dignissimos beatae dolores exercitationem laboriosam officia
                  magnam atque blanditiis illum doloremque magni ex corrupti
                  tempora quis.
                </p>
              </div>
            </div>

            <div>
              <div class="inline-block rounded-lg bg-blue-600 p-3 text-white">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="h-6 w-6"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke="currentColor"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M8.228 9c.549-1.165 2.03-2 3.772-2 2.21 0 4 1.343 4 3 0 1.4-1.278 2.575-3.006 2.907-.542.104-.994.54-.994 1.093m0 3h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"
                  />
                </svg>
              </div>

              <div>
                <h1 class="text-xl font-semibold text-gray-700 dark:text-white">
                  Is the cost of the appoinment covered by private health
                  insurance?
                </h1>

                <p class="mt-2 text-sm text-gray-500 dark:text-gray-300">
                  Lorem ipsum dolor sit amet consectetur adipisicing elit.
                  Provident placeat, consequatur eveniet veritatis quos
                  dignissimos beatae dolores exercitationem laboriosam officia
                  magnam atque blanditiis illum doloremque magni ex corrupti
                  tempora quis.
                </p>
              </div>
            </div>

            <div>
              <div class="inline-block rounded-lg bg-blue-600 p-3 text-white">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="h-6 w-6"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke="currentColor"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M8.228 9c.549-1.165 2.03-2 3.772-2 2.21 0 4 1.343 4 3 0 1.4-1.278 2.575-3.006 2.907-.542.104-.994.54-.994 1.093m0 3h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"
                  />
                </svg>
              </div>

              <div>
                <h1 class="text-xl font-semibold text-gray-700 dark:text-white">
                  What is your cancellation policy?
                </h1>

                <p class="mt-2 text-sm text-gray-500 dark:text-gray-300">
                  Lorem ipsum dolor sit amet consectetur adipisicing elit.
                  Provident placeat, consequatur eveniet veritatis quos
                  dignissimos beatae dolores exercitationem laboriosam officia
                  magnam atque blanditiis illum doloremque magni ex corrupti
                  tempora quis.
                </p>
              </div>
            </div>

            <div>
              <div class="inline-block rounded-lg bg-blue-600 p-3 text-white">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="h-6 w-6"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke="currentColor"
                >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M8.228 9c.549-1.165 2.03-2 3.772-2 2.21 0 4 1.343 4 3 0 1.4-1.278 2.575-3.006 2.907-.542.104-.994.54-.994 1.093m0 3h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"
                  />
                </svg>
              </div>

              <div>
                <h1 class="text-xl font-semibold text-gray-700 dark:text-white">
                  What are the parking and public transport options?
                </h1>

                <p class="mt-2 text-sm text-gray-500 dark:text-gray-300">
                  Lorem ipsum dolor sit amet consectetur adipisicing elit.
                  Provident placeat, consequatur eveniet veritatis quos
                  dignissimos beatae dolores exercitationem laboriosam officia
                  magnam atque blanditiis illum doloremque magni ex corrupti
                  tempora quis.
                </p>
              </div>
            </div>
          </div>
        </div>
      </section>

      <section class="bg-white xl:-mt-40 dark:bg-gray-900 lg:flex">
        <div
          class="flex px-10 w-full flex-col justify-center py-8 lg:w-1/2 lg:bg-gray-100 lg:dark:bg-gray-800"
        >
          <h1
            class="text-3xl font-semibold capitalize text-gray-800 dark:text-white lg:text-5xl"
          >
            hire us.
          </h1>

          <p class="mt-4 text-gray-500 dark:text-gray-400">
            Ask us everything and we would love to hear from you
          </p>

          <div class="mt-6 md:mt-8">
            <h3 class="font-medium text-gray-600 dark:text-gray-300">
              Follow us
            </h3>

            <div class="-mx-1.5 text-2xl mt-4 flex">
              <a
                href="#"
                class="mx-1.5 transform text-gray-400 transition-colors duration-300 hover:text-blue-500 dark:hover:text-blue-400"
              >
                <i class="bx bxl-telegram"></i>
              </a>
              <a
                class="mx-1.5 transform text-gray-400 transition-colors duration-300 hover:text-blue-500 dark:hover:text-blue-400"
                href="#"
              >
                <i class="bx bxl-instagram"></i>
              </a>

              <a
                class="mx-1.5 transform text-gray-400 transition-colors duration-300 hover:text-blue-500 dark:hover:text-blue-400"
                href="#"
              >
                <i class="bx bxl-facebook"></i>
              </a>

              <a
                class="mx-1.5 transform text-gray-400 transition-colors duration-300 hover:text-blue-500 dark:hover:text-blue-400"
                href="#"
              >
                <i class="bx bxl-youtube"></i>
              </a>
            </div>
          </div>
        </div>

        <div
          class="flex w-full flex-col justify-center p-8 pt-0 lg:w-1/2 lg:px-12 xl:px-24"
        >
          <form>
            <div class="-mx-2 md:flex md:items-center">
              <div class="flex-1 px-2">
                <label
                  class="mb-2 block text-sm text-gray-600 dark:text-gray-200"
                  >Full Name</label
                >
                <input
                  type="text"
                  placeholder="John Doe"
                  class="mt-2 block w-full rounded-md border border-gray-200 bg-white px-5 py-3 text-gray-700 placeholder-gray-400 focus:border-blue-400 focus:outline-none focus:ring focus:ring-blue-400 focus:ring-opacity-40 dark:border-gray-700 dark:bg-gray-900 dark:text-gray-300 dark:placeholder-gray-600 dark:focus:border-blue-400"
                />
              </div>

              <div class="mt-4 flex-1 px-2 md:mt-0">
                <label
                  class="mb-2 block text-sm text-gray-600 dark:text-gray-200"
                  >Email address</label
                >
                <input
                  type="email"
                  placeholder="johndoe@example.com"
                  class="mt-2 block w-full rounded-md border border-gray-200 bg-white px-5 py-3 text-gray-700 placeholder-gray-400 focus:border-blue-400 focus:outline-none focus:ring focus:ring-blue-400 focus:ring-opacity-40 dark:border-gray-700 dark:bg-gray-900 dark:text-gray-300 dark:placeholder-gray-600 dark:focus:border-blue-400"
                />
              </div>
            </div>

            <div class="mt-4 w-full">
              <label class="mb-2 block text-sm text-gray-600 dark:text-gray-200"
                >Message</label
              >
              <textarea
                class="mt-2 block h-32 w-full rounded-md border border-gray-200 bg-white px-5 py-3 text-gray-700 placeholder-gray-400 focus:border-blue-400 focus:outline-none focus:ring focus:ring-blue-400 focus:ring-opacity-40 dark:border-gray-700 dark:bg-gray-900 dark:text-gray-300 dark:placeholder-gray-600 dark:focus:border-blue-400 md:h-56"
                placeholder="Message"
              ></textarea>
            </div>

            <button
              class="mt-4 w-full transform rounded-md bg-blue-500 px-6 py-3 text-sm font-medium capitalize tracking-wide text-white transition-colors duration-300 hover:bg-blue-400 focus:outline-none focus:ring focus:ring-blue-300 focus:ring-opacity-50"
            >
              Send
            </button>
          </form>
        </div>
      </section>

      <footer class="bg-white dark:bg-gray-900">
        <div class="container mx-auto py-20">
          <div
            class="grid grid-cols-1 gap-6 sm:grid-cols-2 sm:gap-y-10 lg:grid-cols-4"
          >
            <div class="sm:col-span-2">
              <h1
                class="max-w-lg text-3xl font-semibold tracking-tight text-gray-800 dark:text-white xl:text-4xl"
              >
                Subscribe our newsletter to get update.
              </h1>

              <div
                class="mx-auto mt-8 flex flex-col space-y-3 md:flex-row md:space-y-0"
              >
                <input
                  id="email"
                  type="text"
                  class="rounded-md border bg-white px-4 py-2 text-gray-700 focus:border-blue-400 focus:outline-none focus:ring focus:ring-blue-300 focus:ring-opacity-40 dark:border-gray-600 dark:bg-gray-900 dark:text-gray-300 dark:focus:border-blue-300"
                  placeholder="Email Address"
                />

                <button
                  class="w-full transform rounded-lg bg-gray-800 px-6 py-2.5 text-sm font-medium tracking-wider text-white transition-colors duration-300 hover:bg-gray-700 focus:outline-none focus:ring focus:ring-gray-300 focus:ring-opacity-80 md:mx-4 md:w-auto"
                >
                  Subscribe
                </button>
              </div>
            </div>

            <div>
              <p class="font-semibold text-gray-700">Quick Link</p>

              <div class="mt-5 flex flex-col items-start space-y-2">
                <ul class="font-medium text-gray-600">
                  <li>
                    <p
                      :class="{ 'text-blue-700': store.page == 0 }"
                      @click="
                        scrollFunc(0);
                        store.menu = false;
                      "
                      class="block cursor-pointer py-2 pr-4 pl-3 rounded lg:p-0"
                      aria-current="page"
                    >
                      Home
                    </p>
                  </li>
                  <li>
                    <p
                      :class="{ 'text-blue-700': store.page == 1 }"
                      @click="
                        scrollFunc(1);
                        store.menu = false;
                      "
                      class="block cursor-pointer py-2 pr-4 pl-3 border-b border-gray-100 hover:bg-gray-50 lg:hover:bg-transparent lg:border-0 lg:hover:text-blue-700 lg:p-0 dark:text-gray-400 lg:dark:hover:text-white dark:hover:bg-gray-700 dark:hover:text-white lg:dark:hover:bg-transparent dark:border-gray-700"
                    >
                      Social
                    </p>
                  </li>
                  <li>
                    <p
                      :class="{ 'text-blue-700': store.page == 2 }"
                      @click="
                        scrollFunc(2);
                        store.menu = false;
                      "
                      class="block cursor-pointer py-2 pr-4 pl-3 border-b border-gray-100 hover:bg-gray-50 lg:hover:bg-transparent lg:border-0 lg:hover:text-blue-700 lg:p-0 dark:text-gray-400 lg:dark:hover:text-white dark:hover:bg-gray-700 dark:hover:text-white lg:dark:hover:bg-transparent dark:border-gray-700"
                    >
                      Projects
                    </p>
                  </li>
                  <li>
                    <p
                      :class="{ 'text-blue-700': store.page == 3 }"
                      @click="
                        scrollFunc(3);
                        store.menu = false;
                      "
                      class="block cursor-pointer py-2 pr-4 pl-3 border-b border-gray-100 hover:bg-gray-50 lg:hover:bg-transparent lg:border-0 lg:hover:text-blue-700 lg:p-0 dark:text-gray-400 lg:dark:hover:text-white dark:hover:bg-gray-700 dark:hover:text-white lg:dark:hover:bg-transparent dark:border-gray-700"
                    >
                      Staff
                    </p>
                  </li>
                  <li>
                    <p
                      :class="{ 'text-blue-700': store.page == 4 }"
                      @click="
                        scrollFunc(4);
                        store.menu = false;
                      "
                      class="block cursor-pointer py-2 pr-4 pl-3 border-b border-gray-100 hover:bg-gray-50 lg:hover:bg-transparent lg:border-0 lg:hover:text-blue-700 lg:p-0 dark:text-gray-400 lg:dark:hover:text-white dark:hover:bg-gray-700 dark:hover:text-white lg:dark:hover:bg-transparent dark:border-gray-700"
                    >
                      Price
                    </p>
                  </li>
                </ul>
              </div>
            </div>

            <div>
              <p class="font-semibold text-gray-800 dark:text-white">
                Our services
              </p>

              <div class="mt-5 flex flex-col items-start space-y-2">
                <a
                  href="#"
                  class="text-gray-600 transition-colors duration-300 hover:text-blue-500 hover:underline dark:text-gray-300 dark:hover:text-blue-400"
                  >Web developers</a
                >
                <a
                  href="#"
                  class="text-gray-600 transition-colors duration-300 hover:text-blue-500 hover:underline dark:text-gray-300 dark:hover:text-blue-400"
                  >Graphic disagners</a
                >
                <a
                  href="#"
                  class="text-gray-600 transition-colors duration-300 hover:text-blue-500 hover:underline dark:text-gray-300 dark:hover:text-blue-400"
                  >App developers</a
                >
              </div>
            </div>
          </div>

          <hr class="my-6 border-gray-200 dark:border-gray-700 md:my-8" />

          <div class="flex items-center justify-between">
            <img
              class="w-28 h-12 object-cover"
              src="https://www.henkel.com/resource/image/856716/1x1/1000/1000/854e29c0488e730d5214df4637878014/A14CC1F49988F23711FAACAEE2B23D39/ipro-logo.webp"
              alt="logo"
            />

            <div class="-mx-2 flex">
              <a
                href="#"
                class="mx-2 text-gray-600 transition-colors duration-300 hover:text-blue-500 dark:text-gray-300 dark:hover:text-blue-400"
                aria-label="Reddit"
              >
                <i class="bx bxl-telegram text-xl"></i>
              </a>

              <a
                href="#"
                class="mx-2 text-gray-600 transition-colors duration-300 hover:text-blue-500 dark:text-gray-300 dark:hover:text-blue-400"
                aria-label="Facebook"
              >
                <svg
                  class="h-5 w-5 fill-current"
                  viewBox="0 0 24 24"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M2.00195 12.002C2.00312 16.9214 5.58036 21.1101 10.439 21.881V14.892H7.90195V12.002H10.442V9.80204C10.3284 8.75958 10.6845 7.72064 11.4136 6.96698C12.1427 6.21332 13.1693 5.82306 14.215 5.90204C14.9655 5.91417 15.7141 5.98101 16.455 6.10205V8.56104H15.191C14.7558 8.50405 14.3183 8.64777 14.0017 8.95171C13.6851 9.25566 13.5237 9.68693 13.563 10.124V12.002H16.334L15.891 14.893H13.563V21.881C18.8174 21.0506 22.502 16.2518 21.9475 10.9611C21.3929 5.67041 16.7932 1.73997 11.4808 2.01722C6.16831 2.29447 2.0028 6.68235 2.00195 12.002Z"
                  ></path>
                </svg>
              </a>

              <a
                href="#"
                class="mx-2 text-gray-600 transition-colors duration-300 hover:text-blue-500 dark:text-gray-300 dark:hover:text-blue-400"
                aria-label="Github"
              >
                <svg
                  class="h-5 w-5 fill-current"
                  viewBox="0 0 24 24"
                  fill="none"
                  xmlns="http://www.w3.org/2000/svg"
                >
                  <path
                    d="M12.026 2C7.13295 1.99937 2.96183 5.54799 2.17842 10.3779C1.395 15.2079 4.23061 19.893 8.87302 21.439C9.37302 21.529 9.55202 21.222 9.55202 20.958C9.55202 20.721 9.54402 20.093 9.54102 19.258C6.76602 19.858 6.18002 17.92 6.18002 17.92C5.99733 17.317 5.60459 16.7993 5.07302 16.461C4.17302 15.842 5.14202 15.856 5.14202 15.856C5.78269 15.9438 6.34657 16.3235 6.66902 16.884C6.94195 17.3803 7.40177 17.747 7.94632 17.9026C8.49087 18.0583 9.07503 17.99 9.56902 17.713C9.61544 17.207 9.84055 16.7341 10.204 16.379C7.99002 16.128 5.66202 15.272 5.66202 11.449C5.64973 10.4602 6.01691 9.5043 6.68802 8.778C6.38437 7.91731 6.42013 6.97325 6.78802 6.138C6.78802 6.138 7.62502 5.869 9.53002 7.159C11.1639 6.71101 12.8882 6.71101 14.522 7.159C16.428 5.868 17.264 6.138 17.264 6.138C17.6336 6.97286 17.6694 7.91757 17.364 8.778C18.0376 9.50423 18.4045 10.4626 18.388 11.453C18.388 15.286 16.058 16.128 13.836 16.375C14.3153 16.8651 14.5612 17.5373 14.511 18.221C14.511 19.555 14.499 20.631 14.499 20.958C14.499 21.225 14.677 21.535 15.186 21.437C19.8265 19.8884 22.6591 15.203 21.874 10.3743C21.089 5.54565 16.9181 1.99888 12.026 2Z"
                  ></path>
                </svg>
              </a>
            </div>
          </div>
        </div>
      </footer>
    </main>
  </header>
</template>

<script setup>
import { initFlowbite } from "flowbite";

const store = reactive({
  height: 0,
  page: 0,
  menu: false,
  language: 'en'
});

function scrollFunc(page) {
  store.page = page;
  if (page == 1) {
    window.scrollTo(0, store.height - store.height / 3);
  } else if (page == 2) {
    window.scrollTo(0, store.height + store.height / 3);
  } else if (page == 3) {
    window.scrollTo(0, store.height * 2 + store.height / 3);
  } else if (page == 4) {
    window.scrollTo(0, store.height * 3 + store.height / 3);
  } else {
    window.scrollTo(0, 0);
  }
}

onMounted(() => {
  initFlowbite();
  store.height = window.innerHeight;
  window.addEventListener("resize", () => {
    store.height = window.innerHeight;
  });

  window.addEventListener("scroll", () => {
    if (window.scrollY >= store.height * 3 + store.height / 3) {
      store.page = 4;
    } else if (window.scrollY >= store.height * 2 + store.height / 3) {
      store.page = 3;
    } else if (window.scrollY >= store.height + store.height / 3) {
      store.page = 2;
    } else if (window.scrollY >= store.height - store.height / 3) {
      store.page = 1;
    } else {
      store.page = 0;
    }
  });
});
</script>
