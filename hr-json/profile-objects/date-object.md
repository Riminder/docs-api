# Date object

This object contains datetime information in ISO8601 format with further 
timestamp and detected parsed date in text attribute.


## The Date Object

```python
{
      'iso8601': '2018-01-01T00:00:00', 
      'text': '2018-01-01', 
      'timestamp': 1514761200
}
```

## Attributes

| name | description |
| :--- | :--- |
| iso8601 | The datetime in iso8601 format |
| text | The parsed date as found in the document |
| timestamp | The date as timestamp. Measured in seconds since the Unix epoch |

