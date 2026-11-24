Put your pictures in this folder (JPG or PNG, ideally under 500 KB each).

To show one on a page, add this line to the page where you want it:

  {% include image.html file="your-picture.jpg" caption="What it shows" %}

Add  width="half"  for a smaller picture, for example:

  {% include image.html file="iol-sketch.png" caption="IOL sketch" width="half" %}

To add a photo of yourself to the home and About pages, name it  photo.jpg
and put it in this folder, then set   photo: photo.jpg   in _config.yml.
