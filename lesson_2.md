# Goal

How to make an item?

1. Grab an image, and resize it to png 16x16
(http://www.picresize.com/)

To convert white color to transparent color use: http://www190.lunapic.com/editor/?action=transparent

2. Put the image into the
src/main/resources/assets/[:modname]/textures/items/[:pngfilename].png

3. Make a json file into
src/main/resources/assets/[:modname]/models/item/[:jsonFilename].json

4. Make a class for the file:
src/main/java/[:modFolder]/items/Item/ItemAwesome.java

5. Add into ItemManager.createItems

6. Add into ItemManager.renderItems

