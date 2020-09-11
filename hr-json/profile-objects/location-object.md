# Education object

## Education

This is a complete object that contains **Parsing** results, it details
 detected entities by our algorithm such dates and locations as they have 
 been in the document, it helps data scientist to go further in their studies.
 
## The Education Object

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
| content\_uid | The document's content_uid |
| key | Unique identifier for the object |
| file name | The original uploaded file name |
| file size | The original uploaded file size |
| persons | A list of all parsed full names |
| emails | A list of all parsed emails |
| phones | A list of all parsed phones |
| location | Location as detected in the document, it contains the original text|
| images | All detected images  |
| picture | A link for profile's picture |
| urls |  |
| gender | The Profile's gender |
| driving licence | The Profile's parsed driving licence if exits  |
| summary | The Profile's parsed summary |
| text | The Profile's parsed text |
| text language | The profile's document original language  |
| experiences | A list of Object experience |
| experiences\_duration | Experience's duration |
| educations | A list of Object education |
| eductions\_duration | Education's duration |
| skills | The profile's parsed skills |
| languages | The profile's parsed languages |
| interests | The profile's parsed interests |

