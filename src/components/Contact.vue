<<template>
  <div class="contact">
    <h1>Contact Us</h1>
    <p>
      We'd love to hear from you! Whether you have questions, feedback, or inquiries, feel free to get in touch.
    </p>
    <ul>
      <li>Email: support@sneakers.com</li>
      <li>Phone: +1 234 567 890</li>
      <li>Address: 123 Sneaker St, Fashion City</li>
    </ul>
    <p>
      Follow us on social media for the latest updates and offers.
    </p>
  </div>
</template>

<script>
export default {
  name: "Contact",
};
</script>

<style scoped>
.contact {
  max-width: 800px;
  margin: 50px auto;
  padding: 20px;
  text-align: center;
  background-color: #fff;
  border-radius: 10px;
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
}

.contact h1 {
  font-size: 2.5rem;
  margin-bottom: 20px;
  color: #333;
}

.contact p {
  font-size: 1rem;
  line-height: 1.6;
  color: #555;
  margin-bottom: 15px;
}

.contact ul {
  list-style: none;
  padding: 0;
}

.contact li {
  font-size: 1.2rem;
  color: #333;
  margin-bottom: 10px;
}
</style>
