# Location object

## Location

This object contains geolocation data.

## The Location Object

```python
{
       'text': '803 Green Lane London N07 8MA',
       'lat': 51.581551, 
       'lng': -0.099649, 
       'geojson': {
          'house': null, 
          'category': null, 
          'near': null, 
          'house_number': 803, 
          'road': 'Green Lane', 
          'unit': null, 
          'level': null, 
          'staircase': null, 
          'entrance': null, 
          'po_box': null, 
          'postcode': null, 
          'suburb': null, 
          'city_district': null, 
          'city': 'London', 
          'island': null, 
          'state_district': null, 
          'state': null, 
          'country_region': null, 
          'country': 'UK', 
          'world_region': null}
}
```

## Attributes

| name | description |
| :--- | :--- |
| text | The detected location information as found in the document |
| lat | The location's latitude |
| lng | The location's longitude |
| geojson | The geojson object gives more details about location : street number / city / country ... |

