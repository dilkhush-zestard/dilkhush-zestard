To redirect customers back to the current collection page when they click the "Continue Shopping"

document.addEventListener('DOMContentLoaded', function() {
    var continueShoppingLink = document.getElementById('my-link');
    var referringURL = document.referrer;
    
    if (referringURL.includes(window.location.hostname) && referringURL.includes('/collections/')) {
      // Extract the collection URL from the referring URL
      var match = referringURL.match(/\/collections\/([^/]+)/);
      if (match) {
        var collectionURL = match[0];
        continueShoppingLink.setAttribute('href', collectionURL);
      }
    } else {
      // If the referring URL is not a collection page within your domain, set it to the homepage or another default URL.
      continueShoppingLink.setAttribute('href', '/');
    }
  });
