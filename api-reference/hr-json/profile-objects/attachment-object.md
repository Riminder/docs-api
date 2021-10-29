---
description: Hrflow.ai attachment JSON object.
---

# Attachment JSON

This object represents an attachment (resume or cover).

## The Attachment Object

```python
{
      'alt': 'alt_resume',
      'updated_at': '2020-09-11T10:26:29+0000',
      'created_at': '2020-09-11T10:26:29+0000',
      'extension': '.pdf',
      'file_name': 'resume',
      'file_size': 528305,
      'original_file_name': 'resume',
      'public_url': 'https://riminder-documents-eu-2019-12.s3-eu-west-1.amazonaws.com/resume.pdf',
      'type': 'resume'
}
```

## Attributes

| name                 | description                                                                    |
| -------------------- | ------------------------------------------------------------------------------ |
| alt                  | The file hash id, the value is calculated based on the file's binary           |
| updated\_at          | Time at which the object was last updated                                      |
| created\_at          | Time at which the object was created                                           |
| extension            | The attachment's extension                                                     |
| file\_name           | The attachment's name                                                          |
| file\_size           | The attachment's size                                                          |
| original\_file\_name | The attachment's original name                                                 |
| public\_url          | The attachment's url, One of \["resume", "cover", "other"]                     |
| type                 | The attachment's type, its value can be one from this set (resume/cover/other) |
