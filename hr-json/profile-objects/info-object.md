---
description: Hrflow.ai profile info JSON object.
---

# Info JSON

Profile's personal information.

## The Info Object

```python
{
      "full_name": "Harry Potter",
      "first_name": "Harry",
      "last_name": "Potter",
      "email": "harry.potter@gmail.com",
      "phone": "0658100491",
      "birthdate": "1990-08-09T00:00:00+0000",
      "location": {
            "text": "I place Robert Desnos 75010 Paris",
            "lat": 48.878300000000003,
            "lng": 2.3679100000000002,
            "gmaps": null,
            {'fields': {
                                "category": null,
                                "city": "Paris",
                                "city_district": "8e Arrondissement",
                                "country": "FRA",
                                "country_region": null,
                                "entrance": null,
                                "house": null,
                                "house_number": "18",
                                "island": null,
                                "level": null,
                                "near": null,
                                "po_box": null,
                                "postcode": "75008",
                                "road": "Rue Daru",
                                "staircase": null,
                                "state": "Ile-de-France",
                                "state_district": "Paris",
                                "suburb": "8e Arrondissement",
                                "text": "18 Rue Daru, 75008 Paris, France",
                                "unit": null,
                                "world_region": null
                            }
      },
      "urls": [
            {
            "type": "from_resume",
            "url": []
            },
            {
            "type": "linkedin",
            "url": null
            },
            {
            "type": "twitter",
            "url": null
            },
            {
            "type": "facebook",
            "url": null
            },
            {
            "type": "github",
            "url": null
            }
      ],
      "picture": "picture public url",
      "gender": "male",
      "summary": "Comptabilité gérance"
}
```

## Attributes

| name | description |
| :--- | :--- |
| full\_name | Profile's full name |
| first\_name | Profile's first name |
| last\_name | Profile's last name |
| email | Profile's email |
| phone | Profile's phone |
| birthdate | Profile's birthdate |
| location | The Profile's location as [location](../trait-objects/location-object.md) object |
| urls | Profile's url |
| picture | Profile's picture as public URL if it exists |
| gender | Profile's gender \(male, female, None\) \[Tasks\] |
| summary | Profile's summary |

