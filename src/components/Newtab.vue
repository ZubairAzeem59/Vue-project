<template>
    <div>
      <!-- Your page content goes here -->
    </div>
  </template>
  
  <script>
  export default {
    mounted() {
      document.addEventListener("visibilitychange", this.handleVisibilityChange);
    },
    beforeUnmount() {
      document.removeEventListener("visibilitychange", this.handleVisibilityChange);
    },
    methods: {
      handleVisibilityChange() {
        if (!document.hidden) {
          this.showNotification();
        }
      },
      showNotification() {
        // Add your notification logic here
        alert("You change the tab.");
      },
    },
  };
  </script>
  