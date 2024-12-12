<template>
  <header>
    <div class="logo">
        <img src="@/assets/logo.svg" alt="Logo" />
    </div>
    <nav class="nav-links">
        <a href="#">Collections</a>
        <a href="#">Men</a>
        <a href="#">Women</a>
        <a href="#">About</a>
        <a href="#">Contact</a>
    </nav>
    <div class="icons">
       <img src="@/assets/icon-cart.svg" alt="Cart" id="cart-icon" />
       <img src="@/assets/image-avatar.png" alt="Profile" class="profile-img" />
    </div>
</header>
<main class="main">
    <div class="product-images">
        <img src="@/assets/image-product-1.jpg" alt="Product Image" />
        <div class="thumbnail-container">
            <img src="@/assets/image-product-1-thumbnail.jpg" alt="Thumbnail 1" />
            <img src="@/assets/image-product-2-thumbnail.jpg" alt="Thumbnail 2" />
            <img src="@/assets/image-product-3-thumbnail.jpg" alt="Thumbnail 3" />
            <img src="@/assets/image-product-4-thumbnail.jpg" alt="Thumbnail 4" />
        </div>
    </div>

    <div class="product-details">
        <h1>Fall Limited Edition Sneakers</h1>
        <p>These low-profile sneakers are your perfect casual wear companion. Featuring a durable rubber outer sole, they’ll withstand everything the weather can offer.</p>
        <div class="price-section">
            <span class="price">$125.00</span>
            <span class="discount">50%</span>
            <span class="original-price">$250.00</span>
        </div>
        <div class="cart-actions">
            <div class="quantity">
                <button>-</button>
                <span>1</span>
                <button>+</button>
            </div>
            <button class="add-to-cart">Add to cart</button>
        </div>
    </div>
</main>
</template>

<script>
export default {
  name: 'Header',
  setup() {},
};
</script>

<style>

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: Arial, sans-serif;
        }

        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 30px 90px;
            background-color: #fff;
            border-bottom: 1px solid #ddd;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            text-transform: uppercase;
            color: #000;
           
        }

        .nav-links {
            display: flex;
            gap: 30px;
            margin-right: 300px;
            
        }

        .nav-links a {
            text-decoration: none;
            color: #000;
            font-size: 1rem;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: orange;
        }

        .icons {
            display: flex;
            gap: 20px;
            align-items: center;
        }

        .icons img {
            width: 24px;
            height: 24px;
            cursor: pointer;
        }

        .profile-img {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            object-fit: cover;
            cursor: pointer;
        }
        .main {
            display: flex;
            flex-direction: row;
            gap: 50px;
            margin: 50px;
        }

        .product-images {
            flex: 1;
            margin-left:100px;
        }

        .product-images img {
            width:450px;
            border-radius: 10px;
        }

        .thumbnail-container {
            display: flex;
            flex-direction: row;
            margin-top:10px;
            gap: 30px;
        }

        .thumbnail-container img {
            width: 90px;
            height: auto;
            border-radius: 10px;
            cursor: pointer;
            border: 2px solid transparent;
            transition: border 0.3s;
        }


        .thumbnail-container img:hover {
            border: 2px solid orange;
        }

        .product-details {
            flex: 1;
            display: flex;
            flex-direction: column;
            gap: 20px;
            margin-top:125px;
        }

        .product-details h1 {
            font-size: 2rem;
            color: #000;
        }

        .product-details p {
            line-height: 1.5;
            color: #666;
        }

        .price-section {
            display: flex;
            align-items: center;
            gap: 20px;
        }

        .price {
            font-size: 1.5rem;
            font-weight: bold;
            color: #000;
        }

        .discount {
            background-color: orange;
            color: #fff;
            padding: 5px 10px;
            border-radius: 5px;
            font-size: 1rem;
        }

        .original-price {
            text-decoration: line-through;
            color: #888;
        }

        .cart-actions {
            display: flex;
            align-items: center;
            gap: 20px;
        }

        .quantity {
            display: flex;
            align-items: center;
            gap: 10px;
            background-color: #f1f1f1;
            padding: 10px;
            border-radius: 5px;
        }

        .quantity button {
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
        }

        .add-to-cart {
            background-color: orange;
            color: #fff;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            font-size: 1rem;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .add-to-cart:hover {
            background-color: darkorange;
        }

        
</style>
