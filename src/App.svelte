<script>
  import Navbar from "./lib/navbar.svelte";
  import HomeMobile from "./lib/home-mobile.svelte";
  import DriveWithUsMobile from "./lib/drive-with-us-mobile.svelte";
  import SellACarMobile from "./lib/sell-a-car-mobile.svelte";

  import BookDistance from "./lib/booking-mobile-distance.svelte";
  import CheckoutMobile from "./lib/checkout-mobile.svelte";
  import Promo from "./lib/promo-code.svelte";
  import CheckoutPromo from "./lib/promo-entered.svelte";
  import Booked from "./lib/booking-confirmed.svelte";

  import Router from "svelte-spa-router";

  let routes = {
    "/home": HomeMobile,
    "/drive": DriveWithUsMobile,
    "/sell": SellACarMobile,
    "/bookdistance": BookDistance,
    "/checkout": CheckoutMobile,
    "/promo": Promo,
    "/promoentered": CheckoutPromo,
    "/booked": Booked,
  };
</script>

<main>
  <Navbar />
  <Router {routes} />
</main>
