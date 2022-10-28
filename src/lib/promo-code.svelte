<script>
  function promoEntered() {
    window.location.href = "#/promoentered";
  }
  function previousPage() {
    window.location.href = "#/bookdistance";
  }
  function cancelCheckout() {
    window.location.href = "#/home";
  }
</script>

<main>
  <div class="apply-promo">
    <p>APPLY PROMO CODE</p>
    <!-- svelte-ignore a11y-click-events-have-key-events -->
    <img on:click={cancelCheckout} src="/public/cancel-icon.svg" alt="" />
  </div>
  <!-- svelte-ignore a11y-click-events-have-key-events -->
  <svg
    on:click={previousPage}
    xmlns="http://www.w3.org/2000/svg"
    fill="none"
    viewBox="0 0 24 24"
    stroke-width="1.5"
    stroke="currentColor"
    class="back"
  >
    <path
      stroke-linecap="round"
      stroke-linejoin="round"
      d="M10.5 19.5L3 12m0 0l7.5-7.5M3 12h18"
    />
  </svg>
  <div class="promo-input">
    <p>PROMO CODE</p>
    <input type="text" />
  </div>
  <button on:click={promoEntered}>APPLY</button>
</main>

<style>
  .apply-promo {
    display: flex;
    justify-content: space-between;
  }

  .back {
    width: 30px;
  }
  .promo-input {
    background-color: black;
  }
</style>
