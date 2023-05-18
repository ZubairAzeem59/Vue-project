<template>
  <div :class="['sidebar', { expanded: isExpanded }]">
    <!-- <i @click="toggleSidebar" :class="arrow" class="fa-solid fa-bars"></i> -->

    <div class="logo-container">
      <div class="imgText search-icon">
        <i @click="toggleSidebar" class="fa-solid fa-magnifying-glass"></i>
        <span v-if="isExpanded">
          <form action="#">
            <input
              type="search"
              class="search-data"
              placeholder="Search"
            /></form
        ></span>
      </div>
      <div class="imgText">
        <i @click="toggleSidebar" :class="arrow" class="fa-solid fa-bars"></i>
        <span v-if="isExpanded"></span>
      </div>
      <div class="imgText">
        <i @click="toggleSidebar" class="fa-brands fa-whatsapp"></i>
        <span v-if="isExpanded">Whatsapp</span>
      </div>
      <div class="imgText">
        <i @click="toggleSidebar" class="fa-brands fa-twitter"></i>
        <span v-if="isExpanded">Twitter</span>
      </div>
      <div class="imgText">
        <i @click="toggleSidebar" class="fa-brands fa-instagram"></i>
        <span v-if="isExpanded">Instagram</span>
      </div>
      <div class="imgText">
        <i @click="toggleSidebar" class="fa-brands fa-github"></i>
        <span v-if="isExpanded">Github</span>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Sidebar",
  data() {
    return {
      isExpanded: false,
    };
  },
  methods: {
    toggleSidebar() {
      this.isExpanded = !this.isExpanded;
    },
  },
};
</script>
<style scoped>
.sidebar {
  border-top-right-radius: 16px;
  margin-top: 58px;
  border-top: 1px solid white;
  display: flex;
  flex-direction: column;
  align-items: left;
   /* Initial width of the sidebar */
  background-color: #9b9da0;
  padding: 10px;
  color: white;
  transition: width 0.3s;
  height: 100vh;
  
}
.imgText {
  margin: 0 12px;
  display: flex;
  align-items: center;
}
.search-icon {
  display: none;
}
.fa-solid:hover {
  color: orangered;
}
.fa-whatsapp:hover {
  color: orangered;
}
.fa-twitter:hover {
  color: orangered;
}
.fa-instagram:hover {
  color: orangered;
}
.fa-github:hover {
  color: orangered;
}
.expanded {
  width: 200px; /* Expanded width of the sidebar */
}

.logo-container {
  display: flex;
  flex-direction: column;
}

button {
  display: block;
  width: 100%;
  padding: 5px;
  margin-top: 10px;
  justify-content: center;
}
.fa-bars {
  font-size: 28px;
  margin: 8px 0 20px 0;
  cursor: pointer;
  color: orangered;
}
.fa-brands {
  font-size: 28px;
  margin: 16px 0 20px 0;
  cursor: pointer;
}
span {
  margin-left: 12px;
}
form {
  display: flex;
  height: 34px;
  background: #171c24;
  border-radius: 4px;
  border: 1px solid rgba(155, 155, 155, 0.2);
}

form .search-data {
  height: 100%;
  width: 180px;
  padding: 0 10px;
  color: #fff;
  font-weight: 500;
  background: none;
  border: none;
  font-size: 17px;
  outline: none;
}
form button {
  background: #ff3d00;
  border: none;
  cursor: pointer;
  font-size: 17px;
  color: #fff;
  border-radius: 2px;
  padding: 0 12px;
}
form button:hover {
  background: #e63600;
}

@media only screen and (max-width: 550px) {
  .sidebar{
    
  }
  .search-icon {
    display: block;
  }
  .fa-solid {
    font-size: 28px;
    margin: 20px 0 20px 0;
  }
}
</style>
