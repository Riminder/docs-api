# Attachment object

This object represents the attached document, it can be a resume or a cover.

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

| name | description |
| :--- | :--- |
| alt | The file hash id, the value is calculated based on the file's binary |
| updated_at | Time at which the object was last updated |
| created_at | Time at which the object was created |
| extension | The attachment's extension |
| file_name | The attachment's file name |
| file_size | The attachment's file size |
| original_file_name | The attachment's original file name |
| public_url | The attachment's url, it is useful when you want to retrieve original files |
| type | The attachment's type, its value can be one from this set (resume/cover/other) |

