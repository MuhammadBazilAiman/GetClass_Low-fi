<script>
  let isDistance = false;
  let isHourly = false;
  let isFlatRate = false;

  function toggleDistance() {
    isDistance = !isDistance;
    isHourly = false;
    isFlatRate = false;
  }

  function toggleHourly() {
    isHourly = !isHourly;
    isDistance = false;
    isFlatRate = false;
  }

  function toggleFlatRate() {
    isFlatRate = !isFlatRate;
    isDistance = false;
    isHourly = false;
  }

  function bookNow() {
    window.location.href = "#/bookdistance";
  }
</script>

<main>
  <div class="first-section">
    <p class="trusted">MALAYSIA'S MOST TRUSTED</p>
    <p class="premium">PREMIUM CHAUFFEUR SERVICE</p>
    <div class="smaller-box">
      <!-- svelte-ignore a11y-click-events-have-key-events -->
      <div on:click={toggleDistance}><p>DISTANCE</p></div>
      <!-- svelte-ignore a11y-click-events-have-key-events -->
      <div on:click={toggleHourly}><p>HOURLY</p></div>
      <!-- svelte-ignore a11y-click-events-have-key-events -->
      <div on:click={toggleFlatRate}><p>FLAT RATE</p></div>
    </div>

    {#if isDistance}
      <div class="smaller-box-details">
        <div>
          <p>PICKUP LOCATION</p>
          <input
            class="location-input"
            type="text"
            placeholder="Enter a location"
          />
        </div>
        <div>
          <p>DROP-OFF LOCATION</p>
          <input
            class="location-input"
            type="text"
            placeholder="Enter a location"
          />
        </div>
        <div>
          <p>PICKUP DAY AND TIME</p>
          <input class="date-input" type="date" />
        </div>
        <div>
          <p>TRANSFER TYPE</p>
          <select name="transfer-type" id="transfer-type">
            <option value="one-way">One Way</option>
            <option value="return">Return</option>
            <option value="return-new-ride">Return (new ride)</option>
          </select>
        </div>
      </div>
    {/if}

    {#if isHourly}
      <div class="smaller-box-details hourly">
        <div>
          <p>PICKUP LOCATION</p>
          <input
            class="location-input"
            type="text"
            placeholder="Enter a location"
          />
        </div>
        <div>
          <p>DROP-OFF LOCATION</p>
          <input
            class="location-input"
            type="text"
            placeholder="Enter a location"
          />
        </div>
        <div>
          <p>DATE OF JOURNEY</p>
          <input class="date-input" type="date" />
        </div>
        <div>
          <p>DURATION (IN HOURS)</p>
          <select name="transfer-type" id="transfer-type">
            <option value="4-hours">4 hour(s)</option>
            <option value="5-hours">5 hour(s)</option>
            <option value="6-hours">6 hour(s)</option>
            <option value="7-hours">7 hour(s)</option>
            <option value="8-hours">8 hour(s)</option>
            <option value="9-hours">9 hour(s)</option>
            <option value="10-hours">10 hour(s)</option>
            <option value="11-hours">11 hour(s)</option>
            <option value="12-hours">12 hour(s)</option>
          </select>
        </div>
      </div>
    {/if}

    {#if isFlatRate}
      <div class="smaller-box-details hourly">
        <div>
          <p>ROUTE</p>
          <input
            class="location-input"
            type="text"
            placeholder="Enter a location"
          />
        </div>
        <div>
          <p>DATE OF JOURNEY</p>
          <input class="date-input" type="date" />
        </div>
        <div>
          <p>TRANSFER TYPE</p>
          <select name="transfer-type" id="transfer-type">
            <option value="one-way">One Way</option>
            <option value="return">Return</option>
            <option value="return-new-ride">Return (new ride)</option>
          </select>
        </div>
      </div>
    {/if}

    <button on:click={bookNow} class="book">Book Now</button>
    <img class="whatsapp-svg" src="/public/whatsapp-icon.svg" alt="" />
  </div>

  <div class="services">
    <p class="checkout">CHECK OUT OUR SERVICES</p>
    <div class="first-service">
      <div class="service-img">Image here</div>
      <p>AIRPORT TRANSFER</p>
      <p>
        Premium service perfect for business and pleasure. Transfers to and from
      </p>
      <p>Kuala Lumpur International Airport (KLIA1&2)</p>
      <p>Sultan Abdul Aziz Shah Airport (Subang)</p>
      <button>LEARN MORE</button>
    </div>
    <div class="second-service">
      <div class="service-img">Image here</div>
      <p>CORPORATE & PREMIUM TRAVEL</p>
      <p>We provide premium cars with experienced drivers.</p>
      <p>
        Pre-book your service from one (1) hour to two (2) months in advance
      </p>
      <p>Reach your destination safely, in comfort and on time</p>
      <button>LEARN MORE</button>
    </div>
    <div class="third-service">
      <div class="service-img">Image here</div>
      <p>PRIVATE EVENT SERVICE</p>
      <p>
        Hire us whether it is a short shopping trip or a long-distance journey
      </p>
      <p>Ride up to 8 cars at once</p>
      <p>
        Get you there in comfort plus we will handle the entire event
        efficiently
      </p>
      <button>LEARN MORE</button>
    </div>
  </div>

  <div class="footer">
    <p>Contact GetClass - Malaysia's #1 Toyota Vellfire Chauffeur Service</p>
    <p>GC GetClass</p>
    <p>Redefining chauffer experience</p>
    <p>Address</p>
    <p>UG 5, The Scott Garden, Old Klang Road, 58200, Kuala Lumpur, Malaysia</p>
    <p>Phones</p>
    <p>Bookings: (018) 972 2688</p>
    <p>Office: (03) 7890 1149</p>
    <p>Working hours</p>
    <p>Monday - Sunday: 0400 - 0100</p>
    <p class="copyright">Copyright 2017-2021 GetClass Sdn Bhd (985148-U)</p>
  </div>
</main>

<style>
  .trusted {
    font-size: 20px;
  }

  .premium {
    font-size: 30px;
    padding-bottom: 10px;
  }

  .first-section {
    padding: 10px;
    display: flex;
    flex-direction: column;
    align-items: center;
    background-image: url(https://images.unsplash.com/photo-1511312817910-ffa2ca5d954e?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=735&q=80);
    position: relative;
  }

  .first-section > p {
    font-weight: 100;
    margin: 5px;
    width: 100%;
  }

  .smaller-box {
    display: flex;
    background-color: lightgray;
    width: 100%;
    color: black;
    font-size: 12px;
  }

  .smaller-box > * {
    border: 1px solid gray;
    text-align: center;
    color: #213547;
    width: 100%;
  }

  .smaller-box > *:hover {
    color: green;
    cursor: pointer;
    border-bottom: 3px solid green;
  }

  .smaller-box-details {
    color: black;
    font-weight: bold;
    display: flex;
    flex-direction: column;
    width: 100%;
    font-size: 15px;
    background-color: white;
  }

  .smaller-box-details > * {
    border-bottom: 1px solid black;
    padding: 0 10px;
  }

  .location-input {
    background-color: transparent;
    border: none;
    outline: none;
    color: black;
    margin-bottom: 10px;
  }

  .date-input {
    padding: 3px 10px;
    margin-bottom: 10px;
    border: none;
    outline: none;
  }

  #transfer-type {
    margin-bottom: 10px;
    padding: 2px;
    background-color: transparent;
    color: black;
    border: none;
    outline: none;
  }

  .book {
    width: 100%;
    background-color: rgb(3, 187, 3);
    border: none;
    cursor: pointer;
    padding: 15px;
    margin: 10px;
    font-size: large;
    font-weight: bold;
    border-radius: 10px;
  }

  .book:hover {
    background-color: rgb(40, 156, 4);
  }

  .whatsapp-svg {
    position: absolute;
    right: 3%;
    bottom: 0;
    cursor: pointer;
  }

  .checkout {
    text-align: center;
  }

  .first-service,
  .second-service,
  .third-service {
    border: 1px solid black;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .service-img {
    text-align: center;
    border: 1px solid black;
    width: 100%;
    height: 200px;
  }

  .footer {
    border: 1px solid black;
    padding: 3%;
  }

  .copyright {
    font-size: small;
    text-align: center;
  }
</style>
