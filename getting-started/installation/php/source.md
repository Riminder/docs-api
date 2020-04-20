# Source

| List of methods |  |
| :--- | :--- |
| list all sources | Method used for finding list of sources by the given condition |
| get a source | Retrieve source's information for a given source\_id |

## List

This method takes name, page, limit, sort\_by and order\_by as method arguments

```php
$client->source->list('python', 1, 1, 'date', 'asc');
```

## Get

This method takes source\_id

```php
$client->source->get('source_id');
```

