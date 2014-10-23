# Beyond Markers and Info Windows

### Lesson 0 - Getting Set Up

- Obtain an API key by following instructions at [developers.google.com](https://developers.google.com/maps/documentation/javascript/tutorial#api_key)
- Use your API key (by replacing API_KEY) to load Google Maps JavaScript API in [lesson-0.html](./lesson-0.html).

```
    <script type="text/javascript"
            src="https://maps.googleapis.com/maps/api/js?key= **API_KEY** "></script>
```

- Uncomment the JavaScript code snippet inside [lesson-0.html](./lesson-0.html) to add a map. It's near the end of the file, before the ending `</body>` tag.
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

---

### Lesson 1 - Adding Marker and Info Window

- Use the results of the previous lesson as a starting point. Or, you can jump to [lesson-1.html](./lesson-1.html).
- To add a marker, create a `google.maps.Marker` in the `initialize` function. Some code was added (but commented out) to add a marker. Notice how it uses the `map` object that was created in the previous exercise.

```
    var dlsu = new google.maps.LatLng(14.5649213, 120.993946699);
    // To add the marker to the map, use the 'map' property
    var marker = new google.maps.Marker({
        position: dlsu,
        map: map,
        title: 'Animo La Salle!',
        icon: '...png'
    });
```

- To add an info window, create a `google.maps.InfoWindow` object, and use the `open` method when marker is clicked.

```
    // To add an infowindow, use the 'open' method when marker is clicked
    var contentString = document.getElementById('infowindow-content');
    var infowindow = new google.maps.InfoWindow({
      content: contentString
    });
    google.maps.event.addListener(marker, 'click', function() {
      infowindow.open(map, marker);
    });
```

- Load the HTML file again, and you should see somthing like this:

![Screenshot of Map with Marker and Infowindow](lesson-1.png)

---

### Lesson 2 - Store locator

- In this exercise, you'll load data (from a CSV file) and display the markers on the map.
- This uses code from [storelocator.googlecode.com](http://storelocator.googlecode.com).
- To get started, refer to [storelocator/examples/panel.html](storelocator/examples/panel.html).
- For more information about the store locator, refer to [storelocator/index.html](storelocator/index.html).
