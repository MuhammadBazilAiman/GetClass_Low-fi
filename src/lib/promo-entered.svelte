<script>
  function cancelCheckout() {
    window.location.href = "#/home";
  }

  function previousPage() {
    window.location.href = "#/bookdistance";
  }

  function bookingConfirmed() {
    window.location.href = "#/booked";
  }
</script>

<main>
  <div class="top-bar">
    <p>BOOKING</p>
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <img on:click={cancelCheckout} src="/public/cancel-icon.svg" alt="" />
  </div>
  <div class="back-checkout">
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <svg
      on:click={previousPage}
      xmlns="http://www.w3.org/2000/svg"
      fill="none"
      viewBox="0 0 24 24"
      stroke-width="1.5"
      stroke="currentColor"
      class="w-6"
    >
      <path
        stroke-linecap="round"
        stroke-linejoin="round"
        d="M10.5 19.5L3 12m0 0l7.5-7.5M3 12h18"
      />
    </svg>
    <p>CHECK OUT</p>
  </div>
  <div class="location">Location map here</div>
  <div>
    <h4>FROM</h4>
    <h4>KLIA 2</h4>
    <h4>TO</h4>
    <h4>JW Marriot, Jalan Bukit Bintang, 50100 Kuala Lumpur</h4>
    <h4>DATE & TIME</h4>
    <h4>27 Aug 2023 2:00PM</h4>
    <h4>VEHICLE</h4>
    <h4>Toyota Vellfire</h4>
    <h4>CONTACT & BILLING INFO</h4>
    <h4>Jamie Tan</h4>
    <h4>No.1 Green, Johor, Malaysia</h4>
    <h4>jamietan@gmail.com</h4>
    <h4>PAYMENT METHOD</h4>
    <h4>Stripe</h4>
  </div>
  <div class="bottom-nav">
    <div class="price">
      <p>JOURNEY PRICE</p>
      <p>RM258.00</p>
    </div>
    <div class="promo-entered">
      <p>PROMO CODE</p>
      <p>-RM25.80</p>
    </div>
    <button on:click={bookingConfirmed}>BOOK NOW</button>
  </div>
  <div>
    <p>SAVE10</p>
    <p>-RM25.80</p>
    <button>REMOVE</button>
  </div>
</main>

<style>
  .top-bar {
    display: flex;
    justify-content: space-between;
  }

  .back-checkout {
    display: flex;
    gap: 20px;
  }

  .w-6 {
    width: 40px;
  }

  .location {
    background-color: black;
    text-align: center;
    height: 100px;
  }
  .price {
    display: flex;
    justify-content: space-between;
  }
  .bottom-nav {
    padding: 20px;
    background-color: black;
    text-align: center;
  }
</style>
