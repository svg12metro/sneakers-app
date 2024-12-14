<template>
  <div class="collections">
    <h1>Our Collections</h1>
    <p>
      Explore our latest collections of sneakers, featuring modern designs, premium materials, and unmatched comfort.
    </p>
    <ul>
      <li>Fall Collection</li>
      <li>Summer Collection</li>
      <li>Limited Edition Sneakers</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Collections",
};
</script>

<style scoped>
.collections {
  max-width: 800px;
  margin: 50px auto;
  padding: 20px;
  text-align: center;
  background-color: #fff;
  border-radius: 10px;
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
}

.collections h1 {
  font-size: 2.5rem;
  margin-bottom: 20px;
  color: #333;
}

.collections p {
  font-size: 1rem;
  line-height: 1.6;
  color: #555;
  margin-bottom: 15px;
}

.collections ul {
  list-style: none;
  padding: 0;
}

.collections li {
  font-size: 1.2rem;
  color: #333;
  margin-bottom: 10px;
}
</style>
