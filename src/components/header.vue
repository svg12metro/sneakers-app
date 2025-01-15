<template>
    <header>
        <div class="logo">
        <img src="@/assets/logo.svg" alt="Logo" />
        </div>
        <nav class="nav-links">
            <a href="#collections">Collections</a>
            <a href="#men">Men</a>
            <a href="#women">Women</a>
            <a href="#about">About</a>
            <a href="#contact">Contact</a>
        </nav>
        
        <div class="icons">
            <img src="@/assets/icon-cart.svg" alt="Cart" id="cart-icon" @click='opencart'/>
            <img src="@/assets/image-avatar.png" alt="Profile" class="profile-img" />
        </div>
    </header>
    <main class="main">
        <div class="product-images">
             <img src="@/assets/4.webp" alt="Product Image" />
            <div class="thumbnail-container">
            <img
                v-for="(image, index) in images"
                :key="index"
                :src="image.thumbnail"
                :alt="'Thumbnail ' + (index + 1)"
                @click="openPopup(image.full)"
                />
            </div>
        </div>

            <div class="product-details">
                <h1>AsicsGEL-NYC</h1>
                <h1>Sneakers</h1>
                <p>Inspired by traditional and modern performance running styles, the GEL-NYC from asics features a midsole with a combination of lightweight foam and GEL technology inserts for optimal comfort.
                   - Breathable mesh

                    - Lace-up closure

                    - GEL technology 
                </p>
                <div class="price-section">
                    <span class="price">$125.00</span>
                    <span class="discount">50%</span>
                </div>
                <span class="original-price">$250.00</span>
                <div class="cart-actions">
                    <div class="quantity">
                        <button @click='minus1'>-</button>
                        <span>{{quantity}}</span>
                        <button @click='add1'>+</button>
                    </div>
                    <button class="add-to-cart" @click='addtocart'>Add to cart</button>
                </div>
                 <!-- Popup Modal -->
                <div v-if="isPopupVisible" class="popup-overlay" @click="closePopup">
                    <div class="popup-content" @click.stop>
                        <img :src="currentImage" alt="Popup Image" />
                        <button class="close-button" @click="closePopup">Close</button>
                    </div>
                </div>
                    <div @click="closecart" class='cart-overlay'>
                        <div v-if="popupcart" class="cart-popup">
                        <div class="cart-header">
                            <h4>Cart</h4>
                        </div>
                        <div v-if="!pressed" class="cart-body-not-pressed">
                            <p>Your cart is empty.</p>
                        </div>
                        <div v-else class="cart-body">
                            <div class="cart-item">
                            <img src="@/assets/1.webp" alt="Product Thumbnail" />
                            <div class="cart-item-details">
                                <p>Fall Limited Edition Sneakers</p>
                                <p>
                                $125.00 × {{ quantity }} <span class="cart-item-total">${{ finalprice }}</span>
                                </p>
                            </div>
                            <img
                                src="@/assets/icon-delete.svg"
                                alt="Delete Icon"
                                class="delete-icon"
                                @click="clearCart"
                            />
                            </div>
                            <div class="cart-footer">
                            <button class="checkout-button">Checkout</button>
                            </div>
                        </div>
                        </div>

                    </div>
                
            </div>
    </main>
</template>

<script>
    import { ref } from 'vue';
    export default {
        name: "Header",
        setup() {
            const quantity=ref(1);
            function add1()
            {
            quantity.value++;
            }
            function minus1(){
                if(Number(quantity.value)>1)
                quantity.value--;
            }
            const images = ref([
            {
                thumbnail: require('@/assets/1.webp'),
                full: require('@/assets/1.webp'),
            },
            {
                thumbnail: require('@/assets/2.webp'),
                full: require('@/assets/2.webp'),
            },
            {
                thumbnail: require('@/assets/3.webp'),
                full: require('@/assets/3.webp'),
            },
            {
                thumbnail: require('@/assets/5.webp'),
                full: require('@/assets/5.webp'),
            },
            ]);

            const isPopupVisible = ref(false);
            const currentImage = ref('');
     
            const openPopup = (image) => {
            currentImage.value = image;
            isPopupVisible.value = true;
            };

            const closePopup = () => {
            isPopupVisible.value = false;
            currentImage.value = '';
            };
            const popupcart=ref(false);
            function opencart(){
               popupcart.value=true;
            };
            function closecart(){
               popupcart.value=false;
            };
            
            const price=ref(125);
            const finalprice=ref(125*quantity.value);
            const pressed=ref(false);
            function addtocart(){
                 finalprice.value=price.value*quantity.value;
                 pressed.value=true;

                
            }
            const clearCart = () => {
                quantity.value = 1;
                finalprice.value = price.value;
                pressed.value = false;
            };
            
            return{
                quantity,
                images,
                isPopupVisible,
                currentImage,
                openPopup,
                closePopup,
                add1,
                minus1,
                opencart,
                popupcart,
                closecart,
                addtocart,
                price,
                pressed,
                finalprice,
                clearCart
                
            };
        }
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
          .cart-popup {
            position: absolute;
            top: 70px; /* Adjust to align with the cart icon */
            right: 20px; /* Adjust as needed */
            width: 360px;
            background-color: white;
            border-radius: 10px;
            box-shadow: 0px 4px 15px rgba(0, 0, 0, 0.2);
            z-index: 1000;
            overflow: hidden;
            animation: fadeIn 0.3s ease-in-out;
            font-family: Arial, sans-serif;
            }

            .cart-popup::before {
            content: '';
            position: absolute;
            top: -10px;
            right: 30px; /* Adjust for alignment */
            width: 0;
            height: 0;
            border-left: 10px solid transparent;
            border-right: 10px solid transparent;
            border-bottom: 10px solid white;
            }

            .cart-header {
            padding: 15px;
            font-weight: bold;
            border-bottom: 1px solid #ddd;
            text-align: left;
            font-size: 1.2rem;
            }

            .cart-body-not-pressed {
            padding: 20px;
            text-align: center;
            color: #717171;
            }

            .cart-body-not-pressed p {
            margin: 0;
            font-size: 1rem;
            }

            .cart-body {
            padding: 15px;
            }

            .cart-item {
            display: flex;
            align-items: center;
            gap: 15px;
            margin-bottom: 20px;
            }

            .cart-item img {
            width: 50px;
            height: 50px;
            border-radius: 5px;
            object-fit: cover;
            }

            .cart-item-details {
            flex: 1;
            }

            .cart-item-details p {
            margin: 0;
            font-size: 14px;
            color: #717171;
            }

            .cart-item-total {
            font-weight: bold;
            color: black;
            }

            .delete-icon {
                cursor: pointer;
                width: 20px !important;
                height: 20px !important;
            }

            .cart-footer {
            text-align: center;
            }

            .checkout-button {
            background-color: #ff7d1a;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
            font-size: 1rem;
            transition: background-color 0.3s;
            }

            .checkout-button:hover {
            background-color: #ff5500;
            }

    
        .popup-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 1000;
        }
       
        .popup-content {
            background-color: white;
            padding: 20px;
            border-radius: 10px;
            position: relative;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 20px;
        }

        .popup-content img {
            max-width: 100%;
            max-height: 80vh;
            border-radius: 10px;
        }

        .close-button {
            background-color: #000;
            color: #fff;
            border: none;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
        }

        .close-button:hover {
          background-color: orange;
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
            color: #696767;
            font-size: 1rem;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: orange;
            cursor:pointer;
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
            width: 40px !important; /* Force width */
            height: 40px !important; /* Force height */
            border-radius: 50%;
            object-fit: cover;
            cursor: pointer;
            margin-left:20px;
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
            justify-content: center; /* Center the thumbnails */
            margin-right:160px;
            margin-top: 10px;
            gap: 40px; /* Adjust gap between thumbnails */
            height: auto; /* Remove fixed height */
        }

        .thumbnail-container img {
            width: 70px; /* Slightly smaller size for thumbnails */
            height: 70px; /* Keep the height consistent with the width */
            object-fit: cover; /* Ensure images maintain aspect ratio without distortion */
            border-radius: 10px;
            cursor: pointer;
            border: 2px solid transparent;
            transition: border 0.3s, transform 0.2s;
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
            color: #717171;
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
            background-color: rgb(43, 43, 42);
            color: #fff;
            padding: 5px 10px;
            border-radius: 5px;
            font-size: 1rem;
        }

        .original-price {
            text-decoration: line-through;
            color: #2d2c2c;
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
            background-color: rgb(30, 30, 29);
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
