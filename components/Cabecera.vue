<template>
  <div class="flex">
    <div
      class="fixed flex justify-end w-full p-2 mx-auto text-xs max-w-7xl dark:text-white"
    >
      <button @click="makeDark(dark)">{{ dark ? "light" : "dark" }}</button>
    </div>
  </div>
</template>
<script>
export default {
  watch: {
    dark() {
      this.checkDark();
    },
  },
  data() {
    return {
      dark: false,
    };
  },
  mounted() {
    console.log("monado");
    this.checkDark();
  },
  methods: {
    makeDark(valor) {
      console.log("dhio", this.dark);
      this.dark = !this.dark;
      if (this.dark) {
        // Whenever the user explicitly chooses dark mode
        document.documentElement.classList.add("dark");
        localStorage.theme = "dark";
      } else {
        // Whenever the user explicitly chooses light mode
        localStorage.theme = "light";
        document.documentElement.classList.remove("dark");
      }
    },

    checkDark() {
      // On page load or when changing themes, best to add inline in `head` to avoid FOUC
      if (
        localStorage.theme === "dark" ||
        (!("theme" in localStorage) &&
          window.matchMedia("(prefers-color-scheme: dark)").matches)
      ) {
        document.documentElement.classList.add("dark");
        this.dark = true;
      } else {
        this.dark = false;
        document.documentElement.classList.remove("dark");
      }

      // Whenever the user explicitly chooses to respect the OS preference
      localStorage.removeItem("theme");
    },
  },
};
</script>
