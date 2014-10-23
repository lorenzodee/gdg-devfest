# Beyond Markers and Info Windows

### Lesson 0 - Getting Set Up

- Obtain an API key by following instructions at [developers.google.com](https://developers.google.com/maps/documentation/javascript/tutorial#api_key)
- Use your API key (by replacing API_KEY) to load Google Maps JavaScript API in [lesson-0.html](./lesson-0.html).

    <script type="text/javascript"
            src="https://maps.googleapis.com/maps/api/js?key= **API_KEY** "></script>

- Uncomment the JavaScript code snippet inside [lesson-0.html](./lesson-0.html) to add a map. It's near the end of the file, before the ending </body> tag.
- Load the HTML file and see if the map is loaded

Notice how the `initialize` function is called by listening to the `load` event of the window.

    <script type="text/javascript"
            src="https://maps.googleapis.com/maps/api/js?key=API_KEY"></script>
    <script type="text/javascript">
    function initialize() {
    var mapOptions = {
      center: { lat: 14.5649213, lng: 120.993946699 },
      zoom: 12
    };
    var map = new google.maps.Map(document.getElementById('map-canvas'),
        mapOptions);
    }
    google.maps.event.addDomListener(window, 'load', initialize);
    </script>

### Lesson 1 - Adding Marker and Info Window

### Lesson 2 - Store locator


