# The US-RSE Gallery

## What is this?

This is a community gallery for US-RSE.

## How do I contribute?

We hope that if you take a picture at a conference, Zoom meeting, or other kind of community
event, you consider contributing here! The organization is done so that it should be fairly
easy to add new photos or other historical documents, optionally with description.
Instructions are included below.

### How does it work?

Each gallery has three components:

 - A data file in [_data/gallery](_data/gallery) for optional metadata like captions (not required), e.g., "2022.yaml"
 - A markdown page in [pages/gallery](pages/gallery) that has the same name as the data file, e.g., "2022.md"
 - A directory of images in [assets/gallery](assets/gallery) also sharing the same name, e.g., "2022."
 
While we could assume every gallery page has the same structure and find an approach to eliminate the pages, since
any particular gallery might want some special customization or layout, this is a reasonable approach to start.

#### The front page

The front page works by listing all the data files, and subsetting to those under [_data/gallery](_data/gallery).
We then select the first photo in each listing as the main image. This means that the photo could change over time,
and this is kind of neat! Other approaches that could be taken (if you want to propose and then PR to the site) are more random
selection, or hard coding an exact image in the gallery data file.

### 1. How do I add a photo?

The galleries are defined based on the data files in [_data/gallery/](_data/gallery/), and matching
photos are places in subdirectories of [assets/gallery](assets/gallery). For example, for the gallery named "2022"
we have a file [_data/gallery/2022.yaml](_data/gallery/2022.yaml) and a matching folder [assets/gallery/2022](assets/gallery/2022).
Any pictures dropped in this folder will appear automatically. Thus, to add a photo:

 1. Decide the gallery you want to add it to - drop it in the correct folder under [assets/gallery](assets/gallery)
 2. If you want a caption, edit the corresponding data file in [_data/gallery](_data/gallery) (not required)

And that's it! 

### 2. How do I create a new gallery?

A new gallery corresponds to creating a new photos directory, a data yaml file, and a new markdown page.
The easiest thing to do is copy an existing one. Here is an example:

```bash
$ cp pages/gallery/2021.md pages/gallery/2022.md
# put photos in here
$ mkdir -p assets/gallery/2022
# And captions here (optional)
$ cp _data/gallery/2022.yaml _data/gallery/2021.yaml
```

For the markdown page, the permalink and gallery include *must* correspond to the gallery folder names (e.g., 2022) otherwise it won't be
correctly linked to.

```yaml
---
layout: page
title: Gallery 2022
permalink: /2022/
---
```

And that's it!

### 3. What about other content?

We'd like to add other content here as well, but will need to think about a good design for that.
It's good to start simple!


## TODO

- search should include image captions
- add CI to test that all parts of a new gallery are added
- should we add historical documents / other media here (e.g., the showcase idea?)
- should content have tagging?
