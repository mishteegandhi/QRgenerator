<html lang="en">
  <header>
    <title>Document</title>
    <link rel="stylesheet" href="app.css" />

    <script
      src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"
      integrity="sha512-CNgIRecGo7nphbeZ04Sc13ka07paqdeTu0WR1IM4kNcpmBAUSHSQX0FslNhTDadL4O5SAGapGt4FodqL8My0mA=="
      crossorigin="anonymous"
      referrerpolicy="no-referrer"
    ></script>
  </header>
  <main>
    <div class="code">
      <form action="#" id="frm">
        <div class="form-group">
          <label for="url">Enter Website Link</label>
          <input type="url" id="url" placeholder="Enter URL" required />
        </div>

        <div class="form-group">
          <label for="size">Select Your Size</label>
          <select id="size">
            <option value="100">100x100</option>
            <option value="200">200x200</option>
            <option value="300">300x300</option>
            <option value="400">400x400</option>
          </select>
        </div>
        <div class="form-single-group">
          <label for="colorDark">Color Dark</label>
          <input type="color" id="colorDark" value="#000000" />
        </div>
        <div class="form-single-group">
          <label for="colorLight">Color Light</label>
          <input type="color" id="colorLight" value="#ffffff" />
        </div>
        <button type="submit">Generate QR Code</button>
        <a href="#" id="btn-save" download>Download</a>
      </form>
    </div>
    <div class="output">
      <div id="qrcode">
        <img src="images/qrcode.png" />
      </div>
      <div id="loading">
        <div id="spinner" />
        <p>Please Wait</p>
      </div>
    </div>

  </main>

      <div class="faq">
        <h1 id="f">FAQ</h1>

        <div class="row">
          <div class="column left" style="background-color:#0000;">
            <p />
            <h3>
              Check most frequently asked questions<br />
              and get your queries solved.
            </h3>
            <p />
          </div>

          <div class="column right" style="background-color:#0000;">
            <p />
            <h3>How does a QR Code work?</h3>
            <h5>
              When you scan a QR code, the QR reader in your phone's camera
              deciphers the code, and the resulting information triggers an
              action on your phone.
            </h5>

            <p />
            <h3>How do I generate a QR Code?</h3>
            <h5>
              To generate a QR Code, enter the url into the text box and set you
              specifications before clicking generate.
            </h5>

            <p />
            <h3>What is the size of a QR Code?</h3>
            <h5>
              A QR code must be at least 2 centimeters wide by 2 centimeters
              long to be scanned by most modern devices.
            </h5>

            <p />
            <h3>Can QR Codes be customized?</h3>
            <h5>
              A QR Code can be customized to fit any purpose and any space
              depending on the requisites of a particular campaign.
            </h5>

            <p />
            <h3>What is a static QR Code and dynamic QR Code?</h3>
            <h5>
              Static QR Codes cannot be changed once created and printed. If the
              link is broken, there is nothing you can do except reprint a new
              one. Dynamic QR Codes, on the other hand, are editable and can be
              edited in real-time.
            </h5>

            <p />
            <h3>Can QR Codes be edited?</h3>
            <h5>Yes, as long as the original QR Code is Dynamic.<br /></h5>
          </div>
        </div>
      </div> 
    
</html>
