<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" type="text/css" href="three.css">
</head>
<body>
<input type="text" id="productInput" placeholder="Enter a product">
<button id="submitBtn">Submit</button>

<div id="productContainer"></div>

<div id="productDetailsContainer">
  <h2 id="productTitle"></h2>
  <p id="productDescription"></p>
  <img id="productImage" src="" >
  <p id="productPrice"></p>
</div>
<script src="three.js"></script>
</body>
</html>


#productDetailsContainer {
    margin-top: 20px;
    display: none; /* Initially hide the details container */
  }
  
  #productTitle {
    font-size: 20px;
  }
  
  #productDescription {
    margin-bottom: 10px;
  }
  
  #productImage {
    max-width: 200px;
  }
  
  #productPrice {
    font-weight: bold;
  }
  
  
  
  
  
  
  
  
  
  // Get references to the HTML elements
const productInput = document.getElementById('productInput');
const submitBtn = document.getElementById('submitBtn');
const productContainer = document.getElementById('productContainer');
const productDetailsContainer = document.getElementById('productDetailsContainer');
const productTitle = document.getElementById('productTitle');
const productDescription = document.getElementById('productDescription');
const productImage = document.getElementById('productImage');
const productPrice = document.getElementById('productPrice');

// Add event listener to the submit button
submitBtn.addEventListener('click', function() {
  // Retrieve the value from the input textbox
  const product = productInput.value;

  // Clear the input textbox
  productInput.value = '';

  if (product !== '') {
    // Create a new product container
    const productContainerElement = document.createElement('div');
    productContainerElement.classList.add('product');

    // Create a new element to display the product name
    const productElement = document.createElement('p');
    productElement.textContent = product;

    // Create a new element to display the product description
    const descriptionElement = document.createElement('p');
    descriptionElement.textContent = getProductDescription(product);

    // Create a new image element
    const imageElement = document.createElement('img');
    imageElement.src = getProductImage(product);
    imageElement.alt = 'Product Image';

    // Create a new element to display the product price
    const priceElement = document.createElement('p');
    priceElement.textContent = getProductPrice(product);

    // Append the elements to the product container
    productContainerElement.appendChild(productElement);
    productContainerElement.appendChild(descriptionElement);
    productContainerElement.appendChild(imageElement);
    productContainerElement.appendChild(priceElement);

    // Append the product container to the main container
    productContainer.appendChild(productContainerElement);
  }

  // Show the product details container
  productDetailsContainer.style.display = 'block';
});

// Function to get the description based on the product
function getProductDescription(product) {
  // Add conditions to return the appropriate description based on the product
  if (product.toLowerCase() === 'monitor') 
  {
    return 'High-resolution display for excellent visual experience';
  } else if (product.toLowerCase() === 'keyboard') {
    return 'Mechanical keyboard with customizable RGB lighting';
  }
  else if (product.toLowerCase() === 'mouse') {
    return 'Very sensitive';
  }
  // Add more conditions for other products as needed

  // Return a default description if the product is not found
  return 'No description available';
}

// Function to get the image path based on the product
function getProductImage(product) {
  // Add conditions to return the appropriate image path based on the product
  if (product.toLowerCase() === 'monitor') {
    return 'https://tse2.mm.bing.net/th?id=OIP.YhqtA9y7ql1Yl5MNkZwtVgHaE7&pid=Api&P=0';
  } else if (product.toLowerCase() === 'keyboard') {
    return 'https://tse1.mm.bing.net/th?id=OIP.l_ZjFUn6SOwbW3XmI6oLJQHaE7&pid=Api&P=0';
  }
  else if (product.toLowerCase() === 'mouse') {
    return 'https://tse3.mm.bing.net/th?id=OIP.vnBEawlr7-ycFG3GQPGQzAHaEv&pid=Api&P=0';
  }
  // Add more conditions for other products as needed

  // Return a default image path if the product is not found
  return 'path/to/default-image.jpg';
}

// Function to get the price based on the product
function getProductPrice(product) {
  // Add conditions to return the appropriate price based on the product
  if (product.toLowerCase() === 'monitor') {
    return '$199.99';
  } else if (product.toLowerCase() === 'keyboard') {
    return '$111.99';
  }
  else if (product.toLowerCase() === 'mouse') {
    return '$79.99';
  }
  
  // Add more conditions for other products as needed

  // Return a default price if the product is not found
  return 'Price not available';
}
