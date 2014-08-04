# ENDPOINTS

## CREATE

#### `POST` /users/:user_id/jobs

**Example Request:**

```bash
$ curl -X POST -H "Content-Type: application/json" -d '{"output":[{"methods":[{"method": "resize","options":{"width":200,"height":200}}],"type":"image/png","ref":["main"]}],"input":{"hobbit":"http://0.tqn.com/d/scifi/1/0/n/1/1/-/HBT-008104r.jpg"}}' https://api.6px.io/v1/users/:user_id/jobs
```

**Example Response:**

```json
{
    "id": "52e1f64007438cb08073d5e8"
}
```

## GET

#### `GET` /users/:user_id/jobs/:job_id

**Example Request:**

```bash
$ curl https://api.6px.io/v1/users/52c747dc04f452f766000001/jobs/52e1f64007438cb08073d5e8
```

**Example Response:**

```json
{
  "__v": 0,
  "_id": "52e1f64007438cb08073d5e9",
  "user_id": "52c747dc04f452f766000001",
  "modified": "2014-04-16T21:21:36.544Z",
  "created": "2014-04-16T21:20:54.403Z",
  "processed": {
    "duration": {
      "start": "2014-04-16T21:20:54.474Z",
      "upload": 19842,
      "download": 8424,
      "total": 41999,
      "end": "2014-04-16T21:21:36.473Z"
    },
    "output": {
      "bus": {
        "info": {
          "bytes": 88202,
          "width": 250,
          "height": 166
        },
        "location": "http://cdn-6px.s3.amazonaws.com/52c747dc04f452f766000001/52e1f64007438cb08073d5e9/bus.png"
      }
    },
    "bytes": 88202
  },
  "output": [
    {
      "methods": [
        {
          "method": "resize",
          "options": {
            "width": 250
          }
        },
        {
          "method": "filter",
          "options": {
            "sepia": 70,
            "hue": 20
          }
        }
      ],
      "url": "6px",
      "type": "image/png",
      "tag": "Small-Sepia",
      "ref": {
        "bus": false
      }
    }
  ],
  "input": {
    "bus": "http://666a658c624a3c03a6b2-25cda059d975d2f318c03e90bcf17c40.r92.cf1.rackcdn.com/unsplash_52d5c05422a47_1.JPG"
  },
  "status": "complete",
  "data": {}
}
```

## LIST

#### `GET` /users/:user_id/jobs

**Example Request:**

```bash
$ curl https://api.6px.io/v1/users/52c747dc04f452f766000001/jobs
```

**Example Response:**

```json
[
  {
    "__v": 0,
    "_id": "52e1f64007438cb08073d5e9",
    "user_id": "52c747dc04f452f766000001",
    "modified": "2014-04-16T21:21:36.544Z",
    "created": "2014-04-16T21:20:54.403Z",
    "processed": {
      "duration": {
        "start": "2014-04-16T21:20:54.474Z",
        "upload": 19842,
        "download": 8424,
        "total": 41999,
        "end": "2014-04-16T21:21:36.473Z"
      },
      "output": {
        "bus": {
          "info": {
            "bytes": 88202,
            "width": 250,
            "height": 166
          },
          "location": "http://cdn-6px.s3.amazonaws.com/52c747dc04f452f766000001/52e1f64007438cb08073d5e9/bus.png"
        }
      },
      "bytes": 88202
    },
    "output": [
      {
        "methods": [
          {
            "method": "resize",
            "options": {
              "width": 250
            }
          },
          {
            "method": "filter",
            "options": {
              "sepia": 70,
              "hue": 20
            }
          }
        ],
        "url": "6px",
        "type": "image/png",
        "tag": "Small-Sepia",
        "ref": {
          "bus": false
        }
      }
    ],
    "input": {
      "bus": "http://666a658c624a3c03a6b2-25cda059d975d2f318c03e90bcf17c40.r92.cf1.rackcdn.com/unsplash_52d5c05422a47_1.JPG"
    },
    "status": "complete",
    "data": {}
  },
  {
    "__v": 0,
    "_id": "534ef43674b502000000edd4",
    "user_id": "5344f3842b89de102752424b",
    "modified": "2014-04-16T21:21:36.544Z",
    "created": "2014-04-16T21:20:54.403Z",
    "processed": {
      "duration": {
        "start": "2014-04-16T21:20:54.474Z",
        "upload": 19842,
        "download": 8424,
        "total": 41999,
        "end": "2014-04-16T21:21:36.473Z"
      },
      "output": {
        "farm": {
          "info": {
            "bytes": 16033211,
            "width": 4608,
            "height": 3456
          },
          "location": "http://cdn-6px.s3.amazonaws.com/52c747dc04f452f766000001/534ef43674b502000000edd4/location.png"
        },
        "forest": {
          "info": {
            "bytes": 6814070,
            "width": 2300,
            "height": 1533
          },
          "location": "http://cdn-6px.s3.amazonaws.com/52c747dc04f452f766000001/534ef43674b502000000edd4/forest.png"
        },
        "bus": {
          "info": {
            "bytes": 88202,
            "width": 250,
            "height": 166
          },
          "location": "http://cdn-6px.s3.amazonaws.com/52c747dc04f452f766000001/534ef43674b502000000edd4/bus.png"
        }
      },
      "bytes": 22935483
    },
    "output": [
      {
        "methods": [
          {
            "method": "resize",
            "options": {
              "width": 250
            }
          },
          {
            "method": "filter",
            "options": {
              "sepia": 70,
              "hue": 20
            }
          }
        ],
        "url": "6px",
        "type": "image/png",
        "tag": "Small-Sepia",
        "ref": {
          "bus": false,
          "forest": false,
          "farm": false
        }
      }
    ],
    "input": {
      "bus": "http://666a658c624a3c03a6b2-25cda059d975d2f318c03e90bcf17c40.r92.cf1.rackcdn.com/unsplash_52d5c05422a47_1.JPG",
      "forest": "http://666a658c624a3c03a6b2-25cda059d975d2f318c03e90bcf17c40.r92.cf1.rackcdn.com/unsplash_52dbe5607f0db_1.JPG",
      "farm": "http://666a658c624a3c03a6b2-25cda059d975d2f318c03e90bcf17c40.r92.cf1.rackcdn.com/unsplash_52d7cdd15b9a3_1.JPG"
    },
    "status": "complete",
    "callback": {
      "url": ""
    },
    "data": {}
  }
]
```

# INPUT JSON

## SAMPLE

```json
{
  "data": {},
  "callback": {
    "url": "http://example.com/callback"
  },
  "input": {
    "img": "http://example.com/path/to/image1.jpg"
  },
  "output": [
    {
      "methods": [
        {
          "method": "resize",
          "options": {
            "width": 200,
            "height": 200
          }
        }
      ],
      "type": "image/png",
      "tag": "Resized",
      "ref": {
        "img": false
      },
      "url": "s3://key:secret@bucket/path"
    }
  ]
}
```

### DATA `object`
An `object` that allows you to store custom data such as a database id, name or email.

**Example Store:**

```json
{
  "data": {
    "id": "1234",
    "email": "foo@example.com"
  }
}
```

You can then easily locate jobs using with a simple [search](#search):

```bash
$ curl https://api.6px.io/v1/users/:user_id/jobs?data.id=1234
```

### CALLBACK `object`
When your job is complete a `POST` will be sent to an optional callback URL. The `POST` body will contain the full JSON payload from the processed job.

### INPUT `array`
The `input` array specifies the images that are to be used when processing the job. Input should be a publicly accessable URL or a valid [data URI](https://developer.mozilla.org/en-US/docs/data_URIs).

**The following image formats are supported:**

* `JPG`
* `PNG`
* `GIF`

### OUTPUT `array`
Specifies operations that are to be run against the images in the `input` array. Multiple outputs can be achieved by providing additional objects.

**Example:**

```json
{
  "output": [
    {
      "methods": [
        {
          "method": "resize",
          "options": {
            "width": 200,
            "height": 200
          }
        }
      ],
      "type": "image/png",
      "tag": "Resized",
      "ref": {
        "main": false
      },
      "url": "s3://key:secret@bucket/path"
    },
    {
      "methods": [
        {
          "method": "filter",
          "options": {
            "colorize": { "hex": "#F00", "strength": 60 }
          }
        }
      ],
      "type": "image/png",
      "tag": "Red",
      "ref": {
        "main": false
      },
      "url": "s3://key:secret@bucket/path"
    }
  ]
}
```

#### METHODS `array`
Specifies what [methods](#methods) to run against that particular output.

**Example:**

```json
{
  "methods": [
    {
      "method": "resize",
      "options": {
        "height": 400,
        "width": 400
      }
    },
    {
      "method": "filter",
      "options": {
        "color": 0
      }
    }
  ]
}
```

#### TYPE `string`
MIME type to save the image as.

**The following MIME types are supported:**

* `image/png`
* `image/jpeg`
* `image/gif`

#### TAG `string`
A `string` that allows you to name an output so that you can reference a specific image down the road. Tags are required.

#### REF `object`
Specifies which input(s) to use. If we specify more than one ref in this block, it will duplicate whatever is in this block for each of the input indexes defined. If the value is set to false, a random filename will be generated.

**For example, if we have the following input object containing 4 inputs:**

```json
{
  "input": {
    "img1": "http://example.com/path/to/image1.jpg",
    "img2": "http://example.com/path/to/image2.jpg",
    "img3": "http://example.com/path/to/image3.jpg",
    "img4": "http://example.com/path/to/image4.jpg"
  }
}
```

**We could then specify that we want to use the 3rd input image like so:**

```json
{
  "output": [
    {
      "methods": [
        {
          "method": "crop",
          "options": {
            "face": true,
            "padding": 50
          }
        }
      ],
      "tag": "Face",
      "ref": {
        "img3": "image.png"
      }
    }
  ]
}
```

#### URL `string`
A full URL without the filename to which the output image(s) will be uploaded.

**The following output locations / connection strings are supported:**

* `s3://key:secret@bucket/path` Amazon S3
* `cf://username:api_key@container/path` Rackspace Cloud Files (US)
* `cf+uk://username:api_key@container/path` Rackspace Cloud Files (UK)
* `ftp://user:password@ftp.example.com/path` FTP
* `sftp://user:password@sftp.example.com/path` SFTP

> **FTP / SFTP**
>
> If the URL contains authentication with special characters, make sure that they are [properly escaped](http://en.wikipedia.org/wiki/Percent-encoding). We try to write from the root of your server, so use an absolute path for your URL to ensure that we can write to your server successfully.

> **Masked Connection Strings**
>
> If you're using a client side implementation or simply prefer to not expose your connection string, you can use a masked connection string. Every user document contains a `connection_string` object. This allows you to map a simple string (e.g. `prod`) to your connection string (e.g. `s3://key:secret@bucket/path`). Your masked connection strings can be specified in the dashboard.

> ** Default Hosting **
>
> If you would like to default your hosting to our Amazon S3 account, simply pass in `6px` as a masked connection string. > The output will contain an absolute URL in the form of `http://cdn-6px.s3.amazonaws.com/:user_id/:job_id/:filename`.


# OUTPUT JSON

## SAMPLE

```json
{
  "__v": 0,
  "_id": "52e1f64007438cb08073d5e9",
  "user_id": "52c747dc04f452f766000001",
  "modified": "2014-04-16T21:21:36.544Z",
  "created": "2014-04-16T21:20:54.403Z",
  "processed": {
    "duration": {
      "start": "2014-04-16T21:20:54.474Z",
      "upload": 19842,
      "download": 8424,
      "total": 41999,
      "end": "2014-04-16T21:21:36.473Z"
    },
    "output": {
      "bus": {
        "info": {
          "bytes": 88202,
          "width": 250,
          "height": 166
        },
        "location": "http://cdn-6px.s3.amazonaws.com/52c747dc04f452f766000001/52e1f64007438cb08073d5e9/bus.png"
      }
    },
    "bytes": 88202
  },
  "output": [
    {
      "methods": [
        {
          "method": "resize",
          "options": {
            "width": 250
          }
        },
        {
          "method": "filter",
          "options": {
            "sepia": 70,
            "hue": 20
          }
        }
      ],
      "url": "6px",
      "type": "image/png",
      "tag": "Small-Sepia",
      "ref": {
        "bus": false
      }
    }
  ],
  "input": {
    "bus": "http://666a658c624a3c03a6b2-25cda059d975d2f318c03e90bcf17c40.r92.cf1.rackcdn.com/unsplash_52d5c05422a47_1.JPG"
  },
  "status": "complete",
  "data": {}
}
```

The output from a job contains all of the fields that were specified in the input, along with general database values and useful metrics.

### PROCESSED `object`
Contains various information obtained while processing the image(s).

#### DURATION `object`
Benchmarks for various tasks for the job.

| Value        | Type     | Description
|--------------|----------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `start`      | Datetime | The time shown as an ISO8601 Datetime that the job started processing.          																																									     |
| `end`        | Datetime | The time shown as an ISO8601 Datetime that the job completed processing.          																																								       |
| `total`      | Number   | The total time in milliseconds taken to complete a job. The timer starts as soon as a job is received and stopps when the job is complete. If you are submitting a batch job, this will be the total time required to process all of the jobs combined.  |
| `upload`     | Number   | The total time in milliseconds taken to upload all of the outputs in your job.   																		                                                                                                |
| `download`   | Number   | The total time in milliseconds taken to download all of the images referenced in the inputs array. 																																					  |                			       																													|

#### OUTPUT `object`
Outlines various useful data for each of the outputs.

#### BYTES `number`
Size of processed data in bytes. If you are submitting a batch job, this number will be the sum of all processed bytes.

### STATUS `string`
Will be one of the following:

* `pending` Default status before job is picked up by worker
* `processing` Worker has taken on the job
* `complete` Job is complete
* `failed` Job has failed
