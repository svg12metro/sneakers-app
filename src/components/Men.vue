<template>
  <div class="men">
    <h1>Men's Sneakers</h1>
    <p>
      Check out our exclusive range of men's sneakers. Designed for performance, comfort, and style.
    </p>
    <ul>
      <li>Running Shoes</li>
      <li>Casual Sneakers</li>
      <li>Formal Sneakers</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Men",
};
</script>

<style scoped>
.men {
  max-width: 800px;
  margin: 50px auto;
  padding: 20px;
  text-align: center;
  background-color: #fff;
  border-radius: 10px;
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
}

.men h1 {
  font-size: 2.5rem;
  margin-bottom: 20px;
  color: #333;
}

.men p {
  font-size: 1rem;
  line-height: 1.6;
  color: #555;
  margin-bottom: 15px;
}

.men ul {
  list-style: none;
  padding: 0;
}

.men li {
  font-size: 1.2rem;
  color: #333;
  margin-bottom: 10px;
}
</style>
