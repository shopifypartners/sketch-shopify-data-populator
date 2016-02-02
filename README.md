![Sketch Data Populator](sketch-shopify-data-populator.png)

## Credits

_Sketch Data Populator_ was conceived by [precious design studio](http://precious-forever.com/) and developed the plugin in collaboration with [Lukas Ondrej](https://github.com/lukasondrej) to improve our design process for working with data.

For full project details visit [Sketch Data Populator](https://github.com/preciousforever/sketch-data-populator)

## Why Use Data Populator with our Ecommerce Data

Precious Design Studio believe that designers should work with _meaningful_ and _realistic_ data as early as possible in the design process for the following reasons:

1. **Content informs design decisions** (and helps you convey your purpose)
2. **Data are relentless** (so UI components must be designed for robustness)
3. **It's fun** (seeing your design evolve with meaningful data is motivating and rewarding)

_Sketch Data Populator_ not only makes you more productive, it changes the way you design user interfaces.

The ecommerce data presets will let you quickly pick a set of product category images and product info to get you started as quickly as possible on your Shopify project.

## Installation
1. Download the ZIP file (or clone repository)
2. Move the file ```Sketch Shopify Data Populator.sketchplugin``` into your Sketch Plugins folder. In Sketch 3, choose **Plugins › Reveal Plugins Folder…** to open it.

## How to use …

The **Sketch Shopify Data Populator** plugin creates a grid from a selected element (Layer Group or Artboard) and replaces text and image {placeholders} with data from a JSON source:

![Sketch Data Populator](sketch-data-populator.gif)

### Here's how it works:

1. Create a Layer Group that contains at least one Text Layer. In these Text Layers, use placeholders for you data fields in curly brackets – such as ```{firstname}``` or ```{lastname}```. Within a Text Layer, you can do arbitrary string concatenation such as ```{lastname}, {firstname}```. The plugin's "Populate with …" command will replace all these placeholders with respective data.

2. In the same Layer Group, create a Shape Layer (this is your image placeholder). Give the Shape Layer a placeholder name in curly brackets – such as ```{image}```. The plugin's "Populate with …" command will replace this placeholder with respective image data (PNG, JPG).

3. Create another Shape Layer as your icon placeholder. Give it a placeholder name in double curly brackets, something like ```{{icon}}```. Set any of its properties like size, fill color or shadow as desired – all properties will apply to the final icon once populated. The plugin's "Populate with …" command will replace this placeholder with respective icon vector data (SVG).

### Available Commands:

#### Populate with Preset
will display a dialog that allows you to select one of your Presets as well as configure Data and Layout options:

![Populate with Preset](populate-with-preset-dialog.png)

**Data options**  
* _Randomize data order_: instead of going through the JSON top down row by row, it will pick a random data set.  
* _Trim overflowing text_: a Text Layer that has been set with a fixed width will trim overflowing text.  
* _Insert ellipsis after trimmed text_: will insert a "…" after the trimmed text.  
* _Default substitute_ (see below)  


#### Populate again (⌘⇧X)
re-populates all selections with the last used Preset/JSON and options configuration. Great for "shuffling" through different data sets.

#### Place image
will prompt you for picking an image on your computer and then use it as the background for the selected shape.

#### Reveal Presets
will point you into the plugin's location for its Presets. Presets are simply JSON files and folders with image assets that live inside the plugin bundle. In there, you can use any desired folder structure. To find the "Preset" folder inside the plugin bundle, right click _Sketch Data Populator.sketchplugin_ and select _Show Package Contents_.

---

Check out the **Shopify Demo.sketch** file to get an idea.

---

### Data format & assets

The data need to be stored in JSON files that can be loaded by the plugin from either the Presets Folder (Populate with Preset) or from any folder on your computer (Populate with JSON). The data in JSON need to be in an array like in this example of apparel products:

```json
[
    {
	    	"id": 1,
	    	"name": "Ayres Chambray",
        "description": "Comfortable and practical, our chambray button down is perfect for travel or days spent on the go. The Ayres Chambray has a rich, washed out indigo color suitable to throw on for any event. Made with sustainable soft chambray featuring two chest pockets with sturdy and scratch resistant corozo buttons.",
        "price": "$99.99",
        "image": "assets/apparel_001.jpeg",
        "thumbnail_001": "assets/apparel_001.jpeg",
        "thumbnail_002": "assets/apparel_001_thumb.jpeg"
    },
    {
	    	"id": 2,
	    	"name": "Duckworth Woolfill",
        "description": "Inspired by the timeless, functional style of your grandfather's work coat, the Foraker features brass buttons and 4 patch pockets. Crafted in Bristol, Tennessee, our 10oz organic duck canvas is light enough for an early summer morning, but rugged enough to handle your days work.",
        "price": "$219.99",
        "image": "assets/apparel_002.jpeg",
        "thumbnail_001": "assets/apparel_002.jpeg",
        "thumbnail_002": "assets/apparel_002_thumb.jpeg",
        "thumbnail_003": "assets/apparel_002_thumb2.jpeg"
    }
]
```

Note that in the example the image file (JPG) are referenced from a folder called _assets_. This means all your image and icon data should be placed inside a folder that sits on the same level as your JSON file. The images/icons folders as well as your images and icons can be named anything you like, you just need to reference them relative to your JSON file.

You can also use a full URL to reference your images if that is your preference.

<sup>The “apparel” images are from http://unitedbyblue.com, The "products" images are from apple.com.</sup>
