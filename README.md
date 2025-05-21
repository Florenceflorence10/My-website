# My-website
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>My Website</title>
  <link rel="stylesheet" href="css/style.css" />
</head>
<body>
  <header>
    <h1>Welcome to My Website</h1>
    <nav>
      <a href="index.html">Home</a>
      <a href="about.html">About</a>
      <a href="contact.html">Contact</a>
    </nav>
  </header>
  
  <main>
    <section class="slider">
      <img id="slider-image" src="images/slide1.jpg" alt="Slider Image" />
    </section>
  </main>

  <script src="js/script.js"></script>
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>About - My Website</title>
  <link rel="stylesheet" href="css/style.css" />
</head>
<body>
  <header>
    <h1>About Us</h1>
    <nav>
      <a href="index.html">Home</a>
      <a href="about.html">About</a>
      <a href="contact.html">Contact</a>
    </nav>
  </header>

  <main>
    <section>
      <h2>Who We Are</h2>
      <p>We are a creative team building modern, responsive websites using HTML, CSS, and JavaScript. This site demonstrates a multi-page responsive design project.</p>
    </section>
  </main>
</body>
</html>

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Contact - My Website</title>
  <link rel="stylesheet" href="css/style.css" />
  <script src="js/script.js" defer></script>
</head>
<body>
  <header>
    <h1>Contact Us</h1>
    <nav>
      <a href="index.html">Home</a>
      <a href="about.html">About</a>
      <a href="contact.html">Contact</a>
    </nav>
  </header>

  <main>
    <section>
      <form name="contactForm" onsubmit="return validateForm()">
        <label>Name:</label>
        <input type="text" name="name" />
        <label>Email:</label>
        <input type="email" name="email" />
        <input type="submit" value="Send" />
      </form>
    </section>
  </main>
</body>
</html>
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
}

header {
  background-color: #333;
  color: white;
  padding: 1em;
  text-align: center;
}

nav a {
  color: white;
  margin: 0 15px;
  text-decoration: none;
}

main {
  padding: 20px;
}

.slider img {
  width: 100%;
  height: auto;
}

/* Contact form styling */
form {
  display: flex;
  flex-direction: column;
  max-width: 400px;
  margin: 20px auto;
}

form label {
  margin-top: 10px;
}

form input[type="text"],
form input[type="email"] {
  padding: 8px;
  margin-top: 5px;
}

form input[type="submit"] {
  margin-top: 15px;
  padding: 10px;
  background-color: #333;
  color: white;
  border: none;
  cursor: pointer;
}

/* Responsive Layout */
@media (max-width: 600px) {
  header {
    font-size: 0.9em;
  }

  nav a {
    display: block;
    margin: 10px 0;
  }
}

// Image slider
const images = [
  "images/slide1.jpg",
  "images/slide2.jpg",
  "images/slide3.jpg"
];
let current = 0;

function changeImage() {
  const img = document.getElementById("slider-image");
  if (img) {
    current = (current + 1) % images.length;
    img.src = images[current];
  }
}
setInterval(changeImage, 3000);

// Form validation
function validateForm() {
  const name = document.forms["contactForm"]["name"].value;
  const email = document.forms["contactForm"]["email"].value;

  if (name === "" || email === "") {
    alert("Name and email are required.");
    return false;
  }
  return true;
}
