<template>
  <div class="navbar">
    <div class="logo"><img src="../assets/logo.png" alt=""></div>

    <form action="#">
      <input type="search" class="search-data" placeholder="Search" />
      <button type="submit" class="fas fa-search"></button>
    </form>
  </div>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style scoped>
.navbar {
  position: fixed;
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: grey;
  padding: 6px 12px 6px 12px;
  color: #fff;
}
.navbar img{
height: 40px;
}

.navbar form {
  display: flex;
  height: 34px;
  background: white;
  border-radius: 4px;
  border: 1px solid rgba(155, 155, 155, 0.2);
}

.navbar form .search-data {
  height: 100%;
  width: 180px;
  padding: 0 10px;
  color: #fff;
  font-weight: 500;
  background: none;
  border: none;
  font-size: 17px;
  outline: none;
  color:grey;
}
.fa-hippo{
  color: orangered;
}
.navbar form button {
  background: #ff3d00;
  border: none;
  cursor: pointer;
  font-size: 17px;
  color: #fff;
  border-radius: 2px;
  padding: 0 12px;
}
.navbar form button:hover {
  background: #e63600;
}
@media only screen and (max-width: 500px) {
  .navbar form {
    display: none;
  }
}
</style>
