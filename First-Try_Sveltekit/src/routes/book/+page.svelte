<script>
    let isDistance = false;
    let isHourly = false;
    let isFlatRate = false;
  
    let isPickupDay = false;
  
    /**
	 * @type {HTMLParagraphElement}
	 */
    let dropOff;
    /**
	 * @type {HTMLParagraphElement}
	 */
    let enteredDropOff;
    /**
	 * @type {HTMLInputElement}
	 */
    let inputDropOff;
  
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
  
    function togglePickupDay() {
      isPickupDay = !isPickupDay;
    }
  
    function checkOut() {
      window.location.href = "/checkout";
    }
  
    function addDropOff() {
      const div = document.createElement("div");
      const input = document.createElement("input");
      input.classList.add("location-input");
      input.setAttribute("type", "text");
      input.setAttribute("placeholder", "Enter a location");
  
      div.appendChild(input);
      dropOff.appendChild(div);
    }
  
    function enterDropOff() {
      enteredDropOff.textContent = inputDropOff.value;
    }
  
    const onEnter = (/** @type {{ charCode: number; }} */ e) => {
      if (e.charCode === 13) {
        enterDropOff();
        inputDropOff.value = "";
      }
    };
  </script>
  
  <div class="first-section">
    <h2>1. ENTER RIDE DETAILS</h2>
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
          <p bind:this={dropOff}>DROP-OFF LOCATION</p>
          <p bind:this={enteredDropOff} />
          <div>
            <input
              on:keypress={onEnter}
              bind:this={inputDropOff}
              class="location-input"
              type="text"
              placeholder="Enter a location"
            />
            <button on:click={addDropOff}>+</button>
          </div>
        </div>
        <div>
          <p>PICKUP DAY AND TIME</p>
          <div class="pickup-time">
            <button>PICKUP NOW</button>
            <button on:click={togglePickupDay}>CHOOSE DAY/TIME</button>
          </div>
          {#if isPickupDay}
            <input class="date-input" type="date" />
            <input type="time" />
          {/if}
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
          <p bind:this={dropOff}>DROP-OFF LOCATION</p>
          <p bind:this={enteredDropOff} />
          <div>
            <input
              on:keypress={onEnter}
              bind:this={inputDropOff}
              class="location-input"
              type="text"
              placeholder="Enter a location"
            />
            <button on:click={addDropOff}>+</button>
          </div>
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
  </div>
  <div class="pick-a-vehicle">
    <h2>2. PICK A VEHICLE</h2>
    <div class="passenger-suitcase-type">
      <div>
        <p>PASSENGER</p>
        <select name="passenger" id="select">
          <option value="1">1</option>
          <option value="2">2</option>
          <option value="3">3</option>
          <option value="4">4</option>
          <option value="5">5</option>
          <option value="6">6</option>
        </select>
      </div>
      <div>
        <p>SUITCASE</p>
        <select name="suitcase" id="select">
          <option value="1">1</option>
          <option value="2">2</option>
          <option value="3">3</option>
          <option value="4">4</option>
          <option value="5">5</option>
          <option value="6">6</option>
        </select>
      </div>
      <div>
        <p>TYPE</p>
        <select name="type" id="select">
          <option value="1">1</option>
          <option value="2">2</option>
          <option value="3">3</option>
          <option value="4">4</option>
          <option value="5">5</option>
          <option value="6">6</option>
        </select>
      </div>
    </div>
    <div>
      <div class="vehicle">
        <span>6</span>
        <span>3</span>
        <p class="vehicle-img">Image here</p>
        <p>TOYOTA VELLFIRE</p>
        <p>RM 237.50</p>
        <p>
          Lorem ipsum dolor, sit amet consectetur adipisicing elit. Expedita
          tenetur illum illo earum eos quibusdam, maiores possimus facere quas
          blanditiis.
        </p>
      </div>
      <div class="vehicle">
        <span>6</span>
        <span>3</span>
        <p class="vehicle-img">Image here</p>
        <p>TOYOTA VELLFIRE</p>
        <p>RM 237.50</p>
        <p>
          Lorem ipsum dolor, sit amet consectetur adipisicing elit. Expedita
          tenetur illum illo earum eos quibusdam, maiores possimus facere quas
          blanditiis.
        </p>
      </div>
    </div>
  </div>
  <div class="extra-option">
    <h2>EXTRA OPTIONS</h2>
    <div class="options">
      <h5>CHILD BOOSTER SEAT (RENTAL)</h5>
      <h5>RM 20.50</h5>
      <p>Child Booster seat for children for ages (3yrs - 10yrs old).</p>
      <div class="quantity">
        <button>-</button>
        <p>0</p>
        <button>+</button>
      </div>
    </div>
    <div class="options">
      <h5>MULTI-PIN IN-CAR POWER PLUG (RENTAL)</h5>
      <h5>RM 10.00</h5>
      <p>
        Belkin 200W to charge your electronic device while on the move (eg.
        Laptops). US/EU/UK power head.
      </p>
      <div class="quantity">
        <button>-</button>
        <p>0</p>
        <button>+</button>
      </div>
    </div>
    <div class="options">
      <h5>MINERAL WATER</h5>
      <h5>RM 3.00</h5>
      <p>500ml bottle of mineral water</p>
      <div class="quantity">
        <button>-</button>
        <p>0</p>
        <button>+</button>
      </div>
    </div>
  </div>
  <div class="contact-info">
    <h2>3. CONTACT & BILLING INFO</h2>
    <div>
      <p>FIRST NAME</p>
      <input class="fname-input" type="text" placeholder="Enter first name" />
    </div>
    <div>
      <p>LAST NAME</p>
      <input class="lname-input" type="text" placeholder="Enter last name" />
    </div>
    <div>
      <p>EMAIL</p>
      <input class="email-input" type="text" placeholder="Enter an email" />
    </div>
    <div>
      <p>PHONE NUMBER</p>
      <input class="phone-input" type="text" placeholder="Enter a phone number" />
    </div>
  </div>
  <div class="payment">
    <h2>4. PAYMENT METHOD</h2>
    <div>
      <p>PAYMENT CHOICE</p>
      <select class="payment-option" name="payment" id="">
        <option disabled selected>Select a payment choice</option>
        <option value="stripe">Stripe</option>
        <option value="paypal">PayPal</option>
        <option value="credit-debit">Credit/Debit Card</option>
      </select>
    </div>
  </div>
  
  <div class="bottom-nav">
    <div class="bottom-icons">
      <p>img</p>
      <p>img</p>
      <p>img</p>
      <p>img</p>
    </div>
    <button on:click={checkOut}>CHECK OUT - RM 0.00</button>
  </div>
  
  <style>
    .first-section {
      padding: 10px;
      display: flex;
      flex-direction: column;
      align-items: center;
      position: relative;
    }
  
    .first-section h2 {
      align-self: flex-start;
    }
  
    .smaller-box {
      display: flex;
      background-color: lightgray;
      width: 100%;
      color: white;
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
      color: white;
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
      color: white;
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
  
    .passenger-suitcase-type {
      display: flex;
    }
  
    .passenger-suitcase-type > * {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      flex: 1 1 0px;
      margin: 10px;
      background-color: #edf4f0;
      color: darkcyan;
      font-weight: bold;
    }
  
    #select {
      color: darkcyan;
      background-color: transparent;
      border: none;
      outline: none;
    }
  
    .vehicle {
      border: 1px solid black;
      padding: 10px;
    }
  
    .vehicle > span {
      border: 1px solid black;
      background-color: black;
      height: 30px;
      width: 30px;
    }
  
    .vehicle-img {
      border: 1px solid black;
      border-radius: 50%;
      background-color: black;
      text-align: center;
      height: 100px;
      width: 100px;
    }
    .quantity {
      display: flex;
    }
    .options {
      border: 1px solid black;
    }
  
    .bottom-nav {
      display: flex;
      flex-direction: column;
      position: fixed;
      bottom: 0;
      width: 100%;
      background-color: white;
    }
    .bottom-nav button {
      background-color: gray;
      font-size: large;
      border: none;
    }
    .bottom-icons {
      display: flex;
      justify-content: space-around;
      flex: 1 1 0px;
      border: 1px solid black;
    }
    .bottom-icons > * {
      border: 1px solid black;
      border-radius: 50%;
      background-color: black;
    }
    .pickup-time {
      display: flex;
    }
  
    .pickup-time > * {
      border: 1px solid black;
    }
  
    .payment {
      margin-bottom: 100px;
    }
  
    .payment-option {
      border: none;
      outline: none;
    }
  </style>
  