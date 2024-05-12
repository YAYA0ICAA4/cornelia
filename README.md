<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Mother's Day!</title>
   <style>
     @import url('https://fonts.googleapis.com/css?family=Source+Sans+Pro:400,600,700,900');

* {
  margin:0;
  padding:0;
  outline: none;
}

body {
  font-family: "Source Sans Pro";
}

.overlay {
  width: 100vw; 
  height: 100vh;
  position: fixed;
  background-color: white;
  z-index: 3;
  transition: all 0.3s ease-out;
}

.overlay.hidden {
  visibility: hidden;
  opacity: 0;
}

.giftMessage {
  width: 410px;
  height: 358.75px;
  position: absolute;
  top: 50%;
  left: 50%;
  z-index: 5;
  margin-top: -179.375px;
  margin-left: -205px;
  visibility: visible;
  opacity: 1;
  transition: all 0.3s ease-out;
}

.giftMessage.hidden {
  visibility: hidden;
  opacity: 0;
  margin-top: -160px;
}

.giftMessage img {
  width: 410px;
  height: 358.75px;
  position: absolute;
  opacity: 0.1;
}

.giftMessage p {
  color: white;
  -webkit-text-fill-color: transparent;
  -webkit-background-clip: text;
  background-image: url("https://images.unsplash.com/photo-1524005552021-ae918bff36ae?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=2134&q=80");
  background-position: 30% 60%;
  background-repeat: no-repeat;
  font-size: 24px;
  font-weight: 700;
  width: 330px;
  padding: 0px 40px;
  text-align: center;
  position: absolute;
  top: 90px;
}

.header {
  width: 100vw;
  height: 100vh;
  background-image: url("https://images.unsplash.com/photo-1524005552021-ae918bff36ae?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=2134&q=80");
  background-position: 50% 60%;
  background-size: cover;
  background-repeat: no-repeat;
  display: grid;
  justify-content: center;
  align-items: center;
}

.headerContainer {
  line-height: 1;
}

.headerContainer h1 {
  color: white;
  font-size: 100px;
  font-weight: 900;
}

.headerContainer h2 {
  color: rgba(255, 255, 255, 0.5);
  font-size: 36px;
  text-align: right;
  text-transform: uppercase;
}

.notification {
  width: 500px;
  height: 75px;
  background-color: white;
  display: flex;
  border-radius: 10px;
  position: fixed;
  right: 50%;
  bottom: 0;
  margin-right: -250px;
  transform: translateY(-30px);
  visibility: visible;
  transition: all 0.3s ease-out;
}

.notification.hidden {
  visibility: hidden;
  opacity: 0;
  transform: translateY(-10px);
}

.notification.animate {
  width: 75px;
  height: 75px;
  margin-right: -37.5px;
}

.notification.expand {
  width: 100%;
  height: 100%;
  border-radius: 0px;
    top: 0;
  bottom: 0;
  right: 0;
  left: 0;
  margin: 0;
}

.giftIcon {
  width: 25px;
  height: 21.88px;
  padding: 0;
  display: block;
  margin-top: 27px;
  margin-left: 30px;
  z-index: 4;
}

.giftIcon.animate {
  margin-left: 25px;
}

#giftIconTop, #giftIconBottom {
  width: 25px;
  margin: 0;
  position: absolute;
}

#giftIconTop {
  height: 12.5px;
  top: 27px;
  transition: all 0.3s ease-out;
}

#giftIconTop.open {
  transform: rotate(6deg) translateY(-3px);
}

#giftIconBottom {
  height: 7.81px;
  bottom: 26px;
}

.notification p {
  color: #F3647A;
  font-size: 24px;
  font-weight: 600;
  margin-top: 22px;
  margin-left: 15px;
  transition: visibility 0.3s ease-out, opacity 0.3s ease-out;
}

.notification p.hidden {
  visibility: hidden;
  opacity: 0;
}

.notification a {
  font-size: 24px;
  font-weight: 700;
  color: #F3647A;
  cursor: pointer;
  background-color: rgba(243, 100, 122, 0.2);
  padding: 10px 22px 9px 22px;
  border-radius: 10px;
  position: absolute;
  right: 30px;
  top: 13px;
  transition: visibility 0.3s ease-out, opacity 0.3s ease-out;
}

.notification a.hidden {
  visibility: hidden;
  opacity: 0;
}
   </style>
</head>
<body>
   <div class="giftMessage hidden">
  <img src="https://svgshare.com/i/CzJ.svg" id="heartIcon">
  <p>“To the world you are a mother, but to your family you’re the world.”</p>
</div>
<div class="header">
  <div class="headerContainer">
    <h2>To world's best mom</h2>
    <h1>Happy Mother's Day</h1>
  </div>
  <div class="notification hidden">
    <div class="giftIcon">
      <img src="https://svgshare.com/i/D0X.svg" id="giftIconTop">
      <img src="https://svgshare.com/i/Czz.svg" id="giftIconBottom">
    </div>
    <p>Oh, you got a new gift!</p>
    <a id="openBtn">Open</a>
  </div>
  <div class="overlay hidden"></div>
</div>
    <script >
    var overlay = document.querySelector(".overlay");
var notification = document.querySelector(".notification");
var openButton = document.querySelector("#openBtn");
var notificationText = document.querySelector(".notification p");
var notificationButton = document.querySelector(".notification a");
var giftIcon = document.querySelector(".giftIcon");
var giftIconTop = document.querySelector("#giftIconTop");
var giftMessage = document.querySelector(".giftMessage");

setTimeout(() => {
  notification.classList.remove("hidden");
}, 3500);

openBtn.addEventListener("click", async function() {
  // When button is clicked
  notificationText.classList.add("hidden");
  notificationButton.classList.add("hidden");
  await delay(100);
  notification.classList.add("animate");
  giftIcon.classList.add("animate");
  
  await delay(500);
 
  giftIconTop.classList.add("open");
    
  await delay(100);
  
  overlay.classList.remove("hidden");
  
  await delay(200);
  
  giftMessage.classList.remove("hidden");
});

function delay(ms) {
  return new Promise(resolve => setTimeout(resolve, ms));
}
    </script>
</body>
</html>
