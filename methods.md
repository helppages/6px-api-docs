# METHODS

## ROTATE

| Options      | Type    | Required | Description                                                        |
|--------------|---------|----------|--------------------------------------------------------------------|
| `degrees`    | Number  | True     | -                                                                  |
| `background` | String  | False    | The background color to fill.  Any hex or `transparent` works.     |

**Example:**

```json
{
  "method": "rotate",
  "options": {
    "degrees": 90
  }
}
```

> The image rotates around the center point.

## RESIZE

| Options | Type    | Required   | Description                                                          |
|---------|---------|------------|----------------------------------------------------------------------|
| `height`  | Number  | False    | -                                                                    |
| `width`   | Number  | False    | -                                                                    |

**Example 1:**

```json
{
  "method": "resize",
  "options": {
    "height": 200,
    "width" : 200
  }
}
```

**Example 2:**

```json
{
  "method": "resize",
  "options": {
    "width": 400
  }
}
```

> **Height and/or width are required parameters. Automatic proprotions provided if either parameter is omitted.**

## CROP

| Options   | Type    | Required | Description                                                                    |
|-----------|---------|----------|--------------------------------------------------------------------------------|
| `height`  | Number  | False    | -                                                                              |
| `width`   | Number  | False    | -                                                                              |
| `x`       | Number  | False    | -                                                                              |
| `y`       | Number  | False    | -                                                                              |
| `face`    | Boolean | False    | Crops to dominant face. Omit `x` and `y` coordinates when using this option.   |
| `padding` | Number  | False    | Sets specified padding when using `face` parameter.                            |

**Example 1:**

```json
{
  "method": "crop",
  "options": {
    "height": 200,
    "width": 200,
    "x": 150,
    "y" 300
  }
}
```

**Example 2:**

```json
{
  "method": "crop",
  "options": {
    "height": 100,
    "face": true
  }
}
```

**Example 3:**

```json
{
  "method": "crop",
  "options": {
    "height": 100,
    "width": 100,
    "face": true,
    "padding" 20
  }
}
```

## FILTER

| Options        | Type    | Required | Description                                                          											|
|----------------|---------|----------|-----------------------------------------------------------------------------------------------------------------|
| `sepia`        | Number  | False    | Expects a number between `0` to `100`.  The higher the number, the more sepia that is applied.   											|
| `invert`       | Number  | False    | Expects `true` or `false`. For best results, omit `invert` alltogether if you do not want the filter.  			|
| `brightness`   | Number  | False    | Default value is `0`. If you want to white-wash the image, pass `100` as the value.  Blaken the image by passing `-100` |
| `contrast`     | Number  | False    | Default value is `0`. If you want to double the contrast, pass `100` as the value.|
| `exposure`     | Number | False | Adjust the exposure amount in the image.  `-100` to `100` are accepted values.  Defaults to `0`. |
| `noise`        | Number | False | Add noise to an image.  Defaults to `0` (no noise).  Maxes out at `100` (a whole lot of noise). |
| `saturation`   | Number | False | Range of `-100` to `100` (defaults at `0`).|
| `vibrance`     | Number | False | Boosts colors if passed a value above `0`.  Will make colors more dull if passed in a value below `0`. |
| `hue`          | Number | False | Range of `0` to `100`|
| `gamma`        | Number | False | Range of `0` to `100` |
| `colorize`     | String | False | Recolor an image with the passed in hex value.  Make the image blue, just pass in `#0000FF`. |
| `channels`     | Object | False | Pass in an object with at least one channel that you want to modify. `red`, `blue`, and `green` are your options and their default values are `0`.  To cancel a channel out, pass `-100` as the value.
| `sharpen`      | Number  | False    | Default value is `100`. If you want to double the sharpness, send the value `200`.|
| `stackBlur`    | Number  | False    | Pass in the  blue radius. `0` - `100` are accepted values. |

Undocumented: `curves`

**Example 1:**

```json
{
  "method": "filter",
  "options": {
    "sepia": 70
  }
}
```

**Example 2:**

```json
{
  "method": "filter",
  "options": {
    "brightness": 150,
    "stackBlur": 30
  }
}
```

**Example 3:**

```json
{
  "method": "filter",
  "options": {
    "sepia": true,
    "sharpness": 175,
    "blur": true
  }
}
```

## LAYER

| Options        | Type    | Required | Description                                                          										   |
|----------------|---------|----------|-----------------------------------------------------------------------------------------------------------------|
| `x`            | Number  | False    | The `x` position for the layered image.  																	   |
| `y`            | Number  | False    | The `y` position for the layered image.  																	   |
| `opacity`      | Number  | False    | Default value is `1`. Can be omitted if opaque is desired effect.                 			       		   |
| `ref`          | String  | False    | Image that you would like to layer on top. This is a reference from the `input` array.                  		|


**Example 1:**

```json
{
  "method": "layer",
  "options": {
    "x": 0,
    "y": 0,
    "opacity": 0.6,
    "ref": "img1"
  }
}
```

**Example 2:**

```json
{
  "method": "layer",
  "options": {
    "opacity": 0.6,
    "ref": "img2"
  }
}
```

> The `x` and `y` values can be omitted if you want to play your layered image at the top left corner (0,0)

## ANALYZE

| Options        | Required | Description                                                          									            	                                   |
|----------------|----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `exif`         | False    | Returns the EXIF data associated with an image.  																	                                               |
| `color`        | False    | Analyzing the color returns the `pallete` or `dominant` colors in the image. This is specified via the `context` parameter. The default context is palette. |  																	   |
| `nudity`       | False    | This is an experimental analysis feature. It's accuracy is approximately 60%.      																		 |

**Example 1:**

```json
{
  "method": "analyze",
  "options": {
    "type": "exif"
  }
}
```

**Example 2:**

```json
{
  "method": "analyze",
  "options": {
    "type": "color",
    "context": "palette"
  }
}
```
**Example 3:**

```json
{
  "method": "analyze",
  "options": {
    "type": "nudity"
  }
}
```
