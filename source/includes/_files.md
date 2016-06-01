# Files

You can add external files to Invoiced through the API and attach them to invoices. The [File Attachments Guide](https://invoiced.com/docs/dev/file-attachments) details the entire workflow.

## File Object

Represents an external file.

### Attributes

```shell
{
  "id": 13,
  "object": "file",
  "name": "logo-invoice.png",
  "size": 6936,
  "type": "image/png",
  "url": "https://invoiced.com/img/logo-invoice.png",
  "created_at": 1464625855
}
```

```ruby
#<Invoiced::File:0x3fdbf95e4d08 id=13> JSON: {
  "id": 13,
  "object": "file",
  "name": "logo-invoice.png",
  "size": 6936,
  "type": "image/png",
  "url": "https://invoiced.com/img/logo-invoice.png",
  "created_at": 1464625855
}
```

```php
Invoiced\File JSON: {
  "id": 13,
  "object": "file",
  "name": "logo-invoice.png",
  "size": 6936,
  "type": "image/png",
  "url": "https://invoiced.com/img/logo-invoice.png",
  "created_at": 1464625855
}
```

```python
<File id=13 at 0x3fdbf95e4d08> JSON: {
  "id": 13,
  "object": "file",
  "name": "logo-invoice.png",
  "size": 6936,
  "type": "image/png",
  "url": "https://invoiced.com/img/logo-invoice.png",
  "created_at": 1464625855
}
```

Parameter | Type | Description
--------- | ---- | -----------
**id** | *integer* | The file's unique ID
**object** | *string* | `file`
**name** | *string* | Filename
**size** | *int* | File size in bytes
**type** | *string* | MIME type
**url** | *string* | File URL
**created_at** | *timestamp* | Timestamp when created

## Create a file

```shell
curl "https://api.invoiced.com/files" \
  -u {API_KEY}: \
  -d url="https://invoiced.com/img/logo-invoice.png" \
  -d name="logo-invoice.png" \
  -d size=6936 \
  -d type="image/png"
```

```ruby
invoiced.File.create(
  :url => "https://invoiced.com/img/logo-invoice.png",
  :name => "logo-invoice.png",
  :size => 6936,
  :type => "image/png"
)
```

```php
<?php

$invoiced->File->create([
  'url' => "https://invoiced.com/img/logo-invoice.png",
  'name' => "logo-invoice.png",
  'size' => 6936,
  'type' => "image/png"
]);
```

```python
client.File.create(
  url="https://invoiced.com/img/logo-invoice.png",
  name="logo-invoice.png",
  size=6936,
  type="image/png"
)
```

> The above command returns JSON structured like this:

```shell
{
  "id": 13,
  "object": "file",
  "name": "logo-invoice.png",
  "size": 6936,
  "type": "image/png",
  "url": "https://invoiced.com/img/logo-invoice.png",
  "created_at": 1464625855
}
```

```ruby
#<Invoiced::File:0x3fdbf95e4d08 id=13> JSON: {
  "id": 13,
  "object": "file",
  "name": "logo-invoice.png",
  "size": 6936,
  "type": "image/png",
  "url": "https://invoiced.com/img/logo-invoice.png",
  "created_at": 1464625855
}
```

```php
Invoiced\File JSON: {
  "id": 13,
  "object": "file",
  "name": "logo-invoice.png",
  "size": 6936,
  "type": "image/png",
  "url": "https://invoiced.com/img/logo-invoice.png",
  "created_at": 1464625855
}
```

```python
<File id=13 at 0x3fdbf95e4d08> JSON: {
  "id": 13,
  "object": "file",
  "name": "logo-invoice.png",
  "size": 6936,
  "type": "image/png",
  "url": "https://invoiced.com/img/logo-invoice.png",
  "created_at": 1464625855
}
```

Create a new file profile with this endpoint.

### HTTP Request

`POST /files`

### Attributes

Parameter | Type | Description
--------- | ---- | -----------
**name** | *string* | Filename
**size** | *int* | File size in bytes
**type** | *string* | MIME type
**url** | *string* | File URL

## Retrieve a file

```shell
curl "https://api.invoiced.com/files/:id" \
  -u {API_KEY}:
```

```ruby
file = invoiced.File.retrieve("{FILE_ID}")
```

```php
<?php

$file = $invoiced->File->retrieve("{FILE_ID}");
```

```python
file = client.File.retrieve("{FILE_ID}")
```

> The above command returns JSON structured like this:

```shell
{
  "id": 13,
  "object": "file",
  "name": "logo-invoice.png",
  "size": 6936,
  "type": "image/png",
  "url": "https://invoiced.com/img/logo-invoice.png",
  "created_at": 1464625855
}
```

```ruby
#<Invoiced::File:0x3fdbf95e4d08 id=13> JSON: {
  "id": 13,
  "object": "file",
  "name": "logo-invoice.png",
  "size": 6936,
  "type": "image/png",
  "url": "https://invoiced.com/img/logo-invoice.png",
  "created_at": 1464625855
}
```

```php
Invoiced\File JSON: {
  "id": 13,
  "object": "file",
  "name": "logo-invoice.png",
  "size": 6936,
  "type": "image/png",
  "url": "https://invoiced.com/img/logo-invoice.png",
  "created_at": 1464625855
}
```

```python
<File id=13 at 0x3fdbf95e4d08> JSON: {
  "id": 13,
  "object": "file",
  "name": "logo-invoice.png",
  "size": 6936,
  "type": "image/png",
  "url": "https://invoiced.com/img/logo-invoice.png",
  "created_at": 1464625855
}
```

This endpoint retrieves a specific file.

### HTTP Request

`GET /files/:id`

## Delete a file

```shell
curl "https://api.invoiced.com/files/:id" \
  -u {API_KEY}: \
  -X DELETE
```

```ruby
file.delete
```

```php
<?php

$file->delete();
```

```python
file.delete()
```

> The above command returns `204 No Content`

This endpoint deletes a specific file.

### HTTP Request

`DELETE /files/:id`