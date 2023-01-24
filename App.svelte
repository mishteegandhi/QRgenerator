<script>
  let bgcolour = '#FFFFFF';
  let colour = '#000000';
  import QrCode from "svelte-qrcode";
  let a = "Get stated with QR";
  function storeInput() {
            a = document.getElementById("input").value;
            colour = document.getElementById("fc").value;
            bgcolour = document.getElementById("bg").value;
            console.log(input);

          }
</script>
<main>
  <!-- NAVBAR -->
  <header>
    <nav class="navbar">
      <div class="navbar-left">
        <ul>
          <b>
            <li><a href="#">Logo</a></li></b>
        </ul>
      </div>
      <div class="navbar-right">
        <ul>
          <b>
            <li><a href="#">Contact Us</a></li>
            <li><a href="#">About</a></li>
            <li><a href="#f">FAQ</a></li></b>
        </ul>
      </div>
    </nav>
  </header>

  <!-- QR GENERATOR -->
  <div class="container">
    <div class="row">
      <div class="column1 left1">
        <QrCode value = {a} color = {colour} background = {bgcolour}/>
        <br />

        <div class="custom-select" style="width:150px; ">
          <select>
            <option value="0">Select file type:</option>
            <option value="1">Text</option>
            <option value="2">URL</option>
          </select>
        </div>
        <br/>

        <form>
          <input type="text" id="input" size =25>
          <br/><br/>
          <button id ="button" type="submit" on:click={storeInput}>Submit</button>
        </form>

      </div>

      <div class="column2 right1">
        <h2>Generate QR Code</h2>
        <h3>QR Colour</h3>
        <input id ="fc" bind:value={colour} type="color" />
        <h3>Background Colour</h3>
        <input id ="bg" bind:value={bgcolour} type="color" />
        <br/><br/>
        <div class="custom-select" style="width:150px; ">
          <select>
            <option value="0">Select file type:</option>
            <option value="1">PNG</option>
            <option value="2">PDF</option>
            <option value="3">JPG</option>
          </select>
          <script>
            let x1, i1, j1, l1, ll2, selElmnt, a, b, c;
            /*look for any elements with the class "custom-select":*/
            x1 = document.getElementsByClassName("custom-select");
            l1 = x1.length;
            for (i1 = 0; i1 < l1; i1++) {
              selElmnt = x1[i1].getElementsByTagName("select")[0];
              ll2 = selElmnt.length;
              /*for each element, create a new DIV that will act as the selected item:*/
              a = document.createElement("DIV");
              a.setAttribute("class", "select-selected");
              a.innerHTML = selElmnt.options[selElmnt.selectedIndex].innerHTML;
              x1[i1].appendChild(a);
              /*for each element, create a new DIV that will contain the option list:*/
              b = document.createElement("DIV");
              b.setAttribute("class", "select-items select-hide");
              for (j1 = 1; j1 < ll2; j1++) {
                /*for each option in the original select element,
              create a new DIV that will act as an option item:*/
                c = document.createElement("DIV");
                c.innerHTML = selElmnt.options[j1].innerHTML;
                c.addEventListener("click", function (e) {
                  /*when an item is clicked, update the original select box,
                  and the selected item:*/
                  let y, i1, k, s, h, sl, yl;
                  s =
                    this.parentNode.parentNode.getElementsByTagName("select")[0];
                  sl = s.length;
                  h = this.parentNode.previousSibling;
                  for (i1 = 0; i1 < sl; i1++) {
                    if (s.options[i1].innerHTML == this.innerHTML) {
                      s.selectedIndex = i1;
                      h.innerHTML = this.innerHTML;
                      y =
                        this.parentNode.getElementsByClassName(
                          "same-as-selected"
                        );
                      yl = y.length;
                      for (k = 0; k < yl; k++) {
                        y[k].removeAttribute("class");
                      }
                      this.setAttribute("class", "same-as-selected");
                      break;
                    }
                  }
                  h.click();
                });
                b.appendChild(c);
              }
              x1[i1].appendChild(b);
              a.addEventListener("click", function (e) {
                /*when the select box is clicked, close any other select boxes,
                and open/close the current select box:*/
                e.stopPropagation();
                closeAllSelect(this);
                this.nextSibling.classList.toggle("select-hide");
                this.classList.toggle("select-arrow-active");
              });
            }
            function closeAllSelect(elmnt) {
              /*a function that will close all select boxes in the document,
            except the current select box:*/
              let x1,y,i1,xl,yl,arrNo = [];
              x1 = document.getElementsByClassName("select-items");
              y = document.getElementsByClassName("select-selected");
              xl = x1.length;
              yl = y.length;
              for (i1 = 0; i1 < yl; i1++) {
                if (elmnt == y[i1]) {
                  arrNo.push(i1);
                } else {
                  y[i1].classList.remove("select-arrow-active");
                }
              }
              for (i1 = 0; i1 < xl; i1++) {
                if (arrNo.indexOf(i1)) {
                  x1[i1].classList.add("select-hide");
                }
              }
            }
            /*if the user clicks anywhere outside the select box,
          then close all select boxes:*/
            document.addEventListener("click", closeAllSelect);
          </script>

        </div>
        <br /><br />
        <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
        <button class="btn"><i class="fa fa-download"></i>    Download</button>
        <a href="" download="">
        </a>
      </div>
    </div>
  </div>

  <!-- FAQ SECTION -->
  <div class="faq">
    <h1 id="f">FAQ</h1>
    <h2>Any Queries write to us..</h2>

    <div class="row">
      <div class="column left" style="background-color:#0000;">
        <p />
        <h3>
          1. Check most frequently asked questions<br />
          and get your queries solved.
        </h3>
        <p />
        <h3>
          2. If still not cleared with your query click<br /> here to contact us...
        </h3>
      </div>

      <div class="column right" style="background-color:#0000;">
        <p />
        <h3>How does a QR Code work?</h3>
        <h5>
          When you scan a QR code, the QR reader in your phone's camera
          deciphers the code, and the resulting information triggers an action
          on your phone.
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
          A QR code must be at least 2 centimeters wide by 2 centimeters long to
          be scanned by most modern devices.
        </h5>

        <p />
        <h3>Can QR Codes be customized?</h3>
        <h5>
          A QR Code can be customized to fit any purpose and any space depending
          on the requisites of a particular campaign.
        </h5>

        <p />
        <h3>What is a static QR Code and dynamic QR Code?</h3>
        <h5>
          Static QR Codes cannot be changed once created and printed. If the
          link is broken, there is nothing you can do except reprint a new one.
          Dynamic QR Codes, on the other hand, are editable and can be edited in
          real-time.
        </h5>

        <p />
        <h3>Can QR Codes be edited?</h3>
        <h5>Yes, as long as the original QR Code is Dynamic.<br /></h5>
      </div>
    </div>
  </div>
</main>
