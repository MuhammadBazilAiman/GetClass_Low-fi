<script>
  let isMenu = false;

  function toggleMenu() {
    isMenu = !isMenu;
  }
</script>

<main>
  <div class="navbar">
    <div class="nav-item">
      <!-- svelte-ignore a11y-click-events-have-key-events -->
      <img
        on:click={toggleMenu}
        class="hamburger-icon"
        src="/public/hamburger-icon.svg"
        alt=""
      />
      <p>GC Get Class</p>
    </div>
    {#if isMenu}
      <div class="nav-item2">
        <a href="#/home">SERVICES</a>
        <a href="#/drive">DRIVE WITH US</a>
        <a href="#/sell">SELL A CAR</a>
        <a href="#/home">ABOUT</a>
        <a href="#/home">CONTACT</a>
        <a href="#/bookdistance">BOOK NOW</a>
      </div>
    {:else}
      <div class="nav-item2">
        <a href="#/bookdistance">BOOK NOW</a>
      </div>
    {/if}
  </div>
</main>

<style>
  * {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
      Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  }
  .navbar {
    display: flex;
    justify-content: space-between;
    background-color: white;
    width: 100%;
    height: 100%;
  }

  .nav-item {
    padding: 0 20px;
    display: flex;
    gap: 10px;
    width: 100%;
    align-items: center;
    color: green;
  }

  .nav-item p {
    font-size: xx-large;
    text-shadow: 3px 3px 5px black;
  }

  .hamburger-icon {
    cursor: pointer;
  }

  .nav-item2 {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
  }

  .nav-item2 > * {
    color: black;
    text-decoration: none;
    font-size: 12px;
    display: flex;
    align-items: center;
    height: 100%;
    padding: 0 10px;
  }

  a:hover {
    background-color: green;
  }
</style>
