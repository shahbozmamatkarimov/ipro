<template>
  <main class="bg-[#203843]">
    <section>
      <div
        class="flex flex-col items-center min-h-screen justify-center px-6 py-8 mx-auto"
      >
        <div
          class="w-full bg-[#80808099] border shadow-md shadow-white backdrop-blur-sm rounded-lg md:mt-0 max-w-sm xl:p-0"
        >
          <div class="p-6 space-y-4 md:space-y-6 sm:p-8">
            <form @submit.prevent="sendPhone" class="space-y-4 md:space-y-6">
              <div>
                <label
                  for="tel"
                  class="block mb-2 text-sm font-medium text-white"
                  >Telefon raqam</label
                >
                <input
                  v-model="phone"
                  id="tel"
                  type="text"
                  class="bg-gray-50 border border-gray-300 text-black sm:text-sm rounded-lg focus:ring-blue-600 focus:border-blue-600 block w-full p-2.5"
                  autocomplete="tel"
                  placeholder="+998 (__) ___-__-__"
                  required
                />
              </div>
              <button
                type="submit"
                class="w-full text-white bg-blue-600 hover:bg-blue-700 focus:outline-none font-medium rounded-lg text-sm px-5 py-3 text-center"
              >
                Kodni jo'natish
              </button>
            </form>
          </div>
        </div>
      </div>
    </section>
  </main>
</template>

<script setup>
import { onMounted, ref } from "vue";
import { useRouter } from "vue-router";

const phone = ref("");
const router = useRouter();

// send otp --------------------
const sendPhone = () => {
  const phone_number = document.querySelector("#tel").value;
  if (phone_number.length == 19) {
      localStorage.setItem("tel", true)
        router.push("/otp_verification");
  }
};

onMounted(() => {
  // phone--------- --------------------------------
  [].forEach.call(document.querySelectorAll("input"), function (input) {
    let keyCode;
    function mask(event) {
      event.keyCode && (keyCode = event.keyCode);
      let pos = this.selectionStart;
      if (pos < 3) event.preventDefault();
      let matrix = "+998 (__) ___-__-__",
        i = 0,
        def = matrix.replace(/\D/g, ""),
        val = this.value.replace(/\D/g, ""),
        newValue = matrix.replace(/[_\d]/g, function (a) {
          return i < val.length ? val.charAt(i++) || def.charAt(i) : a;
        });
      i = newValue.indexOf("_");
      if (i != -1) {
        i < 5 && (i = 3);
        newValue = newValue.slice(0, i);
      }
      let reg = matrix
        .substr(0, this.value.length)
        .replace(/_+/g, function (a) {
          return "\\d{1," + a.length + "}";
        })
        .replace(/[+()]/g, "\\$&");
      reg = new RegExp("^" + reg + "$");
      if (
        !reg.test(this.value) ||
        this.value.length < 5 ||
        (keyCode > 47 && keyCode < 58)
      )
        this.value = newValue;
      if (event.type == "blur" && this.value.length < 5) this.value = "";
    }

    input.addEventListener("input", mask, false);
    input.addEventListener("focus", mask, false);
    input.addEventListener("blur", mask, false);
    input.addEventListener("keydown", mask, false);
    input.addEventListener("mouseup", (event) => {
      event.preventDefault();
      if (input.value.length < 4) {
        input.setSelectionRange(4, 4);
      } else {
        input.setSelectionRange(input.value.length, input.value.length);
      }
    });
  });
});
</script>

<style lang="scss" scoped>
// phone
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@100;300;400;500;700;900&display=swap");

$gray0: #f6f8ff;
$primary0: #636983;

body {
  padding: 0;
  margin: 0;
  height: 100%;
  font-family: "Roboto", sans-serif;
}
*::-webkit-scrollbar {
  width: 4px;
}

*::-webkit-scrollbar-track {
  -webkit-box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.3);
}

*::-webkit-scrollbar-thumb {
  background-color: darkgrey;
  outline: 1px solid slategrey;
}

.wrapper {
  background-color: $gray0;
  width: 100%;
  min-height: 600px;
  height: 100vh;
  p {
    margin: 0;
  }
  .containers {
    padding-top: 40px;
  }
  .buttons {
    width: 600px;
    text-align: center;
    margin: 0 auto;
  }
  .title {
    text-align: center;
    padding: 40px 0;
    font-size: 40px;
    font-weight: 300;
    color: $primary0;
  }

  .line {
    width: 50%;
    margin: 50px auto 0 auto;
    height: 1px;
    background-color: #c3d2e3;
  }
}

.container {
  width: 100%;
  padding: 10px 0;
  text-align: center;
  .card {
    max-width: 400px;
    background-color: white;
    padding: 60px 40px;
    border-radius: 10px;
    border: 1px solid #e3e3e3;
    margin: 0 auto;
  }
}

.phone-block {
  position: relative;

  .flag {
    float: left;
  }

  input[type="tel"] {
    padding: 5px;
    width: 100%;
    border: 1px solid #e3e3e3;
    outline: none;
    padding: 10px 10px 10px 100px;
    border-radius: 10px;
    box-sizing: border-box;
    background-color: #fbfcff;
    height: 40px;
    color: #777;
    transition: all 0.3s;

    &:focus {
      border: 1px solid #ccc;
      & ~ .phone {
        top: -4px;
        left: -4px;
        box-shadow: 2px 5px 10px -2px rgba(34, 60, 80, 0.2);
      }
    }
  }
  .phone {
    position: absolute;
    top: 0px;
    left: 0px;
    padding: 10px;
    height: 40px;
    width: 90px;
    box-sizing: border-box;
    background-color: #fbfcff;
    border-radius: 10px;
    border: 1px solid #e3e3e3;
    transition: all 0.3s;
    box-shadow: 0px 0px 0px -1px rgba(34, 60, 80, 0.2);

    &:hover {
      .list-code {
        visibility: visible;
        opacity: 1;
        box-shadow: 2px 5px 10px -2px rgba(34, 60, 80, 0.2);
      }
    }
  }

  .list-code {
    width: 200px;
    height: 150px;
    background-color: white;
    opacity: 0;
    transition: all 0.3s;
    padding: 5px;
    position: relative;
    left: -10px;
    top: 10px;
    padding: 10px;
    border-radius: 10px;
    box-sizing: border-box;
    visibility: hidden;

    .scroll-block {
      width: 100%;
      height: 100%;
      overflow-y: scroll;
      box-sizing: border-box;
    }

    .country-code,
    .country-name {
      font-size: 12px;
      text-align: left;
    }

    ul {
      margin: 0;
      padding: 0;
      li.line-country {
        width: calc(100% - 10px);
        padding-left: 5px;
        padding-top: 3px;
        padding-bottom: 3px;
        cursor: pointer;
        color: #777;
        display: grid;
        grid-template-columns: 27px 35px 1fr;
        border-radius: 5px;

        &:hover {
          font-weight: 600;
          background-color: $gray0;
        }
      }
    }
  }
}
</style>
