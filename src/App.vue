<template>
  <div>
    <component :is="currentComponent" />
  </div>
</template>

<script>
import Header from "@/components/Header";
import Collections from "@/components/Collections.vue";
import About from "@/components/About.vue";
import Contact from "@/components/Contact.vue";
import Men from "@/components/Men.vue";
import Women from "@/components/Women.vue";

export default {
  name: "App",
  components: {
    Header,
    Collections,
    About,
    Contact,
    Men,
    Women,
  },
  data() {
    return {
      hash: window.location.hash.slice(1), // Set the initial hash value
    };
  },
  computed: {
    currentComponent() {
      console.log("Hash path:", this.hash); // Debugging log
      switch (this.hash) {
        case "collections":
          return Collections;
        case "men":
          return Men;
        case "women":
          return Women;
        case "about":
          return About;
        case "contact":
          return Contact;
        default:
          return Header; // Default to Header
      }
    },
  },
  watch: {
    // Watch for changes to the hash
    hash(newValue) {
      console.log("Hash changed to:", newValue); // Debugging log
    },
  },
  mounted() {
    // Add a hash change listener
    window.addEventListener("hashchange", () => {
      this.hash = window.location.hash.slice(1); // Update the hash on change
    });
  },
};
</script>
