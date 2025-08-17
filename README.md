<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>BetExchanger – Deposit & Withdraw Service</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
    // Dynamic confirmation popup function
    function showConfirmation(event, type, formId) {
      event.preventDefault(); // stop real form submit
      const form = document.getElementById(formId);
      const platform = form.querySelector("select[name='platform']").value;
      const amount = form.querySelector("input[name='amount']").value;
      const method = form.querySelector("select[name='method']").value;

      const popup = document.getElementById("popup");
      const popupBox = document.getElementById("popupBox");
      const msg = document.getElementById("popupMessage");

      // Set color based on type
      if(type === 'Deposit') {
        popupBox.className = "bg-blue-600 p-6 rounded-lg shadow-lg text-center max-w-sm text-white";
      } else {
        popupBox.className = "bg-green-600 p-6 rounded-lg shadow-lg text-center max-w-sm text-white";
      }

      // Dynamic message
      msg.textContent = `✅ Thank you for choosing BetExchanger! Your ${type} request has been received.
Platform: ${platform}
Amount: ${amount} USD
Payment Method: ${method}`;

      popup.classList.remove("hidden");
    }

    function closePopup() {
      document.getElementById("popup").classList.add("hidden");
    }
  </script>
</head>
<body class="bg-gray-100 text-gray-900">

  <!-- Navbar -->
  <header class="bg-blue-600 text-white shadow-md">
    <div class="container mx-auto flex justify-between items-center py-4 px-6">
      <h1 class="text-2xl font-bold">BetExchanger</h1>
      <nav>
        <a href="#deposit" class="mx-2 hover:underline">Deposit</a>
        <a href="#withdraw" class="mx-2 hover:underline">Withdraw</a>
        <a href="#support" class="mx-2 hover:underline">Support</a>
      </nav>
    </div>
  </header>

  <!-- Hero Section -->
  <section class="bg-gradient-to-r from-blue-500 to-green-500 text-white py-16">
    <div class="container mx-auto text-center px-6">
      <h2 class="text-4xl font-bold mb-4">Fast & Secure Deposit & Withdraw Service</h2>
      <p class="text-lg mb-6">For 1Xbet & Melbet Customers in Bangladesh</p>
      <div>
        <a href="#deposit" class="bg-white text-blue-600 font-semibold px-6 py-3 rounded-lg shadow hover:bg-gray-100 mx-2">Deposit Now</a>
        <a href="#withdraw" class="bg-white text-green-600 font-semibold px-6 py-3 rounded-lg shadow hover:bg-gray-100 mx-2">Withdraw Now</a>
      </div>
    </div>
  </section>

  <!-- Rates Section -->
  <section class="py-10">
    <div class="container mx-auto px-6 text-center">
      <h3 class="text-2xl font-bold mb-4">Today’s Exchange Rates</h3>
      <p class="mb-6">Easily editable in HTML</p>
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
        <div class="bg-white shadow-md p-6 rounded-lg">
          <h4 class="font-bold text-blue-600">1Xbet Deposit</h4>
          <p>1 USD = 115 BDT</p>
        </div>
        <div class="bg-white shadow-md p-6 rounded-lg">
          <h4 class="font-bold text-green-600">1Xbet Withdraw</h4>
          <p>1 USD = 110 BDT</p>
        </div>
        <div class="bg-white shadow-md p-6 rounded-lg">
          <h4 class="font-bold text-blue-600">Melbet Deposit</h4>
          <p>1 USD = 115 BDT</p>
        </div>
        <div class="bg-white shadow-md p-6 rounded-lg">
          <h4 class="font-bold text-green-600">Melbet Withdraw</h4>
          <p>1 USD = 110 BDT</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Deposit Form -->
  <section id="deposit" class="py-10 bg-gray-50">
    <div class="container mx-auto px-6">
      <h3 class="text-2xl font-bold text-center mb-6">Deposit Form</h3>
      <form id="depositForm" class="max-w-lg mx-auto bg-white p-6 rounded-lg shadow-md" 
        onsubmit="showConfirmation(event, 'Deposit', 'depositForm')">
        
        <label class="block mb-4">
          <span class="block font-semibold mb-2">Platform</span>
          <select name="platform" class="w-full border rounded p-2">
            <option>1Xbet</option>
            <option>Melbet</option>
          </select>
        </label>

        <label class="block mb-4">
          <span class="block font-semibold mb-2">Payment Method</span>
          <select name="method" class="w-full border rounded p-2">
            <option>Bkash</option>
            <option>Nagad</option>
            <option>Rocket</option>
          </select>
        </label>

        <label class="block mb-4">
          <span class="block font-semibold mb-2">Amount (USD)</span>
          <input name="amount" type="number" class="w-full border rounded p-2" placeholder="Enter amount">
        </label>

        <button type="submit" class="w-full bg-blue-600 text-white py-2 rounded-lg hover:bg-blue-700">Submit Deposit</button>
      </form>
    </div>
  </section>

  <!-- Withdraw Form -->
  <section id="withdraw" class="py-10">
    <div class="container mx-auto px-6">
      <h3 class="text-2xl font-bold text-center mb-6">Withdraw Form</h3>
      <form id="withdrawForm" class="max-w-lg mx-auto bg-white p-6 rounded-lg shadow-md" 
        onsubmit="showConfirmation(event, 'Withdraw', 'withdrawForm')">
        
        <label class="block mb-4">
          <span class="block font-semibold mb-2">Platform</span>
          <select name="platform" class="w-full border rounded p-2">
            <option>1Xbet</option>
            <option>Melbet</option>
          </select>
        </label>

        <label class="block mb-4">
          <span class="block font-semibold mb-2">Withdraw Amount (USD)</span>
          <input name="amount" type="number" class="w-full border rounded p-2" placeholder="Enter amount">
        </label>

        <label class="block mb-4">
          <span class="block font-semibold mb-2">Receive Method</span>
          <select name="method" class="w-full border rounded p-2">
            <option>Bkash</option>
            <option>Nagad</option>
            <option>Rocket</option>
          </select>
        </label>

        <button type="submit" class="w-full bg-green-600 text-white py-2 rounded-lg hover:bg-green-700">Submit Withdraw</button>
      </form>
    </div>
  </section>

  <!-- Support Section -->
  <section id="support" class="py-10 bg-gray-50">
    <div class="container mx-auto px-6 text-center">
      <h3 class="text-2xl font-bold mb-4">Need Help?</h3>
      <p class="mb-6">Contact us anytime on WhatsApp or Telegram</p>
      <div class="flex justify-center space-x-4">
        <a href="https://wa.me/your-number" class="bg-green-500 text-white px-6 py-3 rounded-lg shadow hover:bg-green-600">WhatsApp</a>
        <a href="https://t.me/your-username" class="bg-blue-500 text-white px-6 py-3 rounded-lg shadow hover:bg-blue-600">Telegram</a>
      </div>
    </div>
  </section>

  <!-- Popup (hidden by default) -->
  <div id="popup" class="hidden fixed inset-0 flex items-center justify-center bg-black bg-opacity-50">
    <div id="popupBox" class="bg-blue-600 p-6 rounded-lg shadow-lg text-center max-w-sm text-white">
      <pre id="popupMessage" class="text-lg font-semibold mb-4 whitespace-pre-wrap"></pre>
      <button onclick="closePopup()" class="bg-white text-black px-4 py-2 rounded hover:bg-gray-100">OK</button>
    </div>
  </div>

  <!-- Footer -->
  <footer class="bg-blue-600 text-white py-4 text-center">
    <p>© 2025 BetExchanger. All rights reserved.</p>
  </footer>

</body>
</html>
