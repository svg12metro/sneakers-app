<template>
  <div class="women">
    <h1>Women's Sneakers</h1>
    <p>
      Discover our latest women's sneaker collection, combining elegance and performance.
    </p>
    <ul>
      <li>Sporty Sneakers</li>
      <li>Fashion Sneakers</li>
      <li>Everyday Comfort</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Women",
};
</script>

<style scoped>
.women {
  max-width: 800px;
  margin: 50px auto;
  padding: 20px;
  text-align: center;
  background-color: #fff;
  border-radius: 10px;
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
}

.women h1 {
  font-size: 2.5rem;
  margin-bottom: 20px;
  color: #333;
}

.women p {
  font-size: 1rem;
  line-height: 1.6;
  color: #555;
  margin-bottom: 15px;
}

.women ul {
  list-style: none;
  padding: 0;
}

.women li {
  font-size: 1.2rem;
  color: #333;
  margin-bottom: 10px;
}
</style>
