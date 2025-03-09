# Feynkscape

Feynkscape is an [Inkscape](https://inkscape.org) `.svg` document that contains some elements that will be helpful to draw Feynman diagrams. It is not an extension, it just contains paths that can be cloned and copied in order to create by hand the diagrams. Basic knowledge of Inkscape is needed. You can learn more about it in this wiki ([https://inkscape-manuals.readthedocs.io/en/latest/](https://inkscape-manuals.readthedocs.io/en/latest/)).

This was inspired by these two posts:

- [https://graphicdesign.stackexchange.com/questions/107442/inkscape-feynman-diagrams](https://graphicdesign.stackexchange.com/questions/107442/inkscape-feynman-diagrams)
- [https://alpha.inkscape.org/vectors/www.inkscapeforum.com/viewtopic5d9c.html](https://alpha.inkscape.org/vectors/www.inkscapeforum.com/viewtopic5d9c.html)

With Feynkscape you can draw diagrams like these:

![Penguin diagram.](/imgs/penguin.png)

![Scotogenic model.](/imgs/scotogenic.png)

![Some random thing.](/imgs/something.png)

---

## License

This project is licensed under the GNU General Public License (GPL) v3.0 for the `feynkscape.svg` file. The documentation and images of `imgs/` are licensed under Creative Commons Attribution 4.0 International (CC BY 4.0). Diagrams created with this document are in the public domain under Creative Commons Zero (CC0).

For more details, please refer to the [LICENSE](./LICENSE) file.

## Installation

> [!IMPORTANT]  
> Feynkscape requires Inkscape version 1.4.

1. Download the `feynkscape.svg` file via GitHub's download buttons and put it inside your preferred folder.
2. Open it and draw your diagrams (check the [Usage](#usage) section).

### Using custom fonts

You can use any custom font by installing them system wide and Inkscape will recognize it. However, if for some reason you do not want to install the font, you can point Inkscape to the folder that contains the fonts you want to use by givint it the path.

Assume that your fonts are stored in `/path/to/my/fonts/`. First, open Inkscape preferences by clicking on `Edit > Preferences`:

![How to open Inkscape preferences.](/imgs/edit_preferences.png)

Next, click on the `System` tab and scroll down to the `Custom Font directories` item. Write one path per line. In this case, we write `/path/to/my/fonts/`:

![Custom fonts item inside preferences.](/imgs/custom_fonts.png)

Finally, **restart Inkscape** in order to apply the changes.
> In the image above, the other fields are deleted for the screenshot. In your case you will have information, do not touch it.

## Usage

> [!WARNING]  
> Sometimes something weird happens and even if you are following the steps the result does not look the same. It is very uncommon, it has only happened to me a couple of times. In such cases, delete the object you are creating and do it again. It has only occurred when applying a pattern to a line. Redoing the line takes 30 seconds. If I ever manage to reproduce that behaviour, I will try to explain how to avoid it.

The document has dimensions of a portrait A4. It contains a rectangular grid with minor lines separated every 3 px to help moving the diagrams and the lines. You can completely remove the grid or not use the Snapping tool (the one that has a magnet symbol) if you wish.

When you open the document you will see several elements on the top left corner:

![These are the basic elements to use for almost all Feynman Diagrams](/imgs/elements.png)

All of these elements (unless stated otherwise) have a **stroke width of 3 px**. You can change it if you wish, but one should maintain the consistence among every object of the diagram.

> [!WARNING]  
> If you scale an object with the Selector Tool, the stroke width will increase or decrease according to the scale change. Rembember to change it back to 3 px! You can click on `Object > Fill and stroke > Stroke style` to change it.

There are several elements of our interest when drawing a Feynman diagram:

- **Vertexes:** a vertex represents a point of interaction.
- **Lines:** a line represents a real or virtual particle "traveling" on the diagram.
- **Blobs:** a blob encapsulates any complex process made of several subdiagrams.
- **Labels:** a text label describes the names of the incoming and outgoing particles taking part in the diagram or maybe the internal momenta of a loop and so on.

Depending on the type of particle, the line will have a certain style. In addition, these can also be part of a loop. Let us describe how to draw each element.

**You can use the blank space below the elements, inside the document, to draw your diagram.** Go to the [Exporting your diagram](#exporting-your-diagram) subsection in order to export individual diagrams as `.pdf`, `.svg`, `.png` and so on.

### Lines

Basic lines can be drawn with the Pen Tool (press `B`) to draw Bezier curves and straigth lines.

#### Scalar lines

Scalars are represented by dashed lines. To draw a scalar line use the Pen Tool and:

1. Click once on the document to start drawing the line. A red line that follows your cursor will appear now.
![First click on the document and then move the mouse.](/imgs/scalar_line1.png)

2. Double click it again at the tail of the line to finish drawing it. Having the grid with the Snapping tool on will help.
![Double click it to close the line.](/imgs/scalar_line2.png)

3. The line has a different stroke width and a different style. Use the Selector Tool (press `S`) and select the dashed straight line that appears at the top of the document (highlighted with a red rectangle). Copy it with `Edit > Copy` or press `Ctrl + C`.
![Double click it to close the line.](/imgs/scalar_line3.png)

4. Select again our line and paste the style with `Edit > Paste > Style` or by pressing `Ctrl + Shift + V`. Our line will have the desired style now.
![We have our fermion line.](/imgs/scalar_line4.png)

5. In order to move the line around, select the Node Tool (press `N`) and select our line. Now click on one of the nodes and move it wherever you want. This way of moving things does not change the stroke width. You can also use the Selector Tool to move and rotate elements. Just be careful because you will need to change the stroke width back to 3 px after doing so.
![Freely move it to your wish.](/imgs/scalar_line5.png)

### Fermionic lines

Fermions are represented by solid lines that contain an arrow in the middle. To draw a fermion line, follow the steps 1 and 2 from the [scalar line](#scalar-lines) and then:

1. Adjust the final position of the line with the Node Tool.
2. In order to add the arrow, we need to add a third node in the middle. That is where the arrow will be placed. Select both nodes (you can click drag the mouse, for example).
![Selected nodes are marked with a different colour.](/imgs/fermion_line1.png)

3. With the Node Tool selected, click on the button that says "Insert new nodes into selected segments".
![Insert a node.](/imgs/fermion_line2.png)

4. Now our line will have three nodes. Beware, because we can no longer move the position of the line with the nodes. Now one should use the Selector Tool (press `S`) and fix the stroke width later if we desire to make small position/rotation adjustments.
![There is a new node in the middle now.](/imgs/fermion_line3.png)

5. Like with the scalar line, go to the top of the document, select a fermion line with an arrow and copy it.
![Select one of the fermion lines](/imgs/fermion_line4.png)

6. Select our line and paste the style with `Ctrl + Shift + V`. Now you have a nice looking fermion line.
![Your fermion line is ready.](/imgs/fermion_line5.png)

7. If the arrow is in the other direction. Do not worry. You can rotate 180º the whole line by using the Selector Tool and pressing twice the rotate 90º button
![Rotate the object with these two buttons.](/imgs/fermion_line6.png)

or you can also copy and paste the other fermion line style of the top of the document.

If you prefer not to use these method. I provide a triangle that can be used as an arrow marker. Copy it and place it within your needs. However it will be a bit more harder to put it exactly in the middle of the line.

#### Vector boson and gluonic lines

Vector mediators like photons and W and Z bosons are represented with a wiggly line. Whereas gluons are represented with a coiled line. Applying this pattern to the line requires an extra step. As always, first we draw our line following the steps 1 and 2 from the [scalar line](#scalar-lines) and then:

1. **Check that the line has no markers.** When we create a straight line or a Bezier curve with the Pen Tool, it can carry the style of the last object we have copied. See for example the line we have created:
![The line has an arrow marker for every middle node.](/imgs/gluon_line1.png)
Even though there are only two nodes and it looks fine, if we go to `Object > Fill and Stroke > Stroke style`, we see that the marker in the middle (highlighted with a red rectangle in the previous image) has a triangle in it. If we added more nodes, these would be filled with arrow markers. Before continuing, click on the arrow marker to expand it and select the solid line which means no marker.
![Select no marker.](/imgs/gluon_line2.png)

2. Move the line to the position you desire and fix the stroke width if it is not of 3 px. An easy way to do this is to copy the straight solid line of the top of the document with `Ctrl + C` and then paste the style with `Ctrl + Shift + V` on our solid line. This is what was described in steps 3 and 4 of [scalar lines](#scalar-lines).
![Copy the style of the first line.](/imgs/gluon_line3.png)

3. Next, we will apply our path effect (wiggly or coiled) to our line. Select the line we have drawn and click on `Path > Path Effects`. A new tab should open on the right side of Inkscape. Click on the arrow (highlited with a red rectangle in the image) to open a new menu with different path effects.
![Path effects tab is opened.](/imgs/gluon_line4.png)

4. With the new menu opened, select the `Pattern Along Path` option. A new menu will appear.
![Select pattern along path.](/imgs/gluon_line5.png)

5. Within the Pattern Along Path menu, click on the `Pattern Copies` option and select `Repeated, stretched`. This will copy our pattern as many times as needed to fill our line and stretch it when needed.
![Select a repeated, stretched pattern.](/imgs/gluon_line6.png)
If we did everything right, our straight line should still look the same. If something weird has happened, probably you have an arrow marker on your line. Please check step 1.
6. Now the fun starts. Select the pattern you want to copy. I provide several patterns. Two for vector bosons (wiggly) and two for gluons (coiled):
![Select the desired pattern.](/imgs/gluon_line7.png)
The right one of vector bosons is a bit sharper, whereas the left one is smoother. In the case of gluons, the difference between the patterns is that one has the coils on above the line and the other one has them below the line. Select the pattern you prefer and copy it with `Ctrl + C` to your clipboard.

> [!IMPORTANT]
> What about the patterns that appear below the red rectangle of the vector bosons? Each column provides the same pattern as the one on the first row above them. The difference is the starting point. Think of that as a $\sin(x)$. The first one starts at $x = 0$, the next one at $x = \pi / 2$, the next one at $x = \pi$ and the last one at $x = 3\pi /2$. This difference in the phase is useful if your vector boson line has a certain angle and it looks weird when joined by the vertex to other lines.

7. Go to the `Path effects` tab and click on the Paste path icon highlighted with a red rectangle.
![Click on Paste path.](/imgs/gluon_line8.png)

This will paste the previously copied path and apply it to our line. For the vector boson case, it will look like this:
![Vector boson line](/imgs/gluon_line9.png)

In the case of the gluon, it looks like this:
![Gluon line](/imgs/gluon_line10.png)

Now you are ready to do whatever you like with your lines. You can still use the Node Tool (press `N`) to modify the length and angle of your line. Precise position adjustments should be done later with the Selector Tool (press `S`).

Moving the line with the Node Tool looks like this:

![Modify your gluon line.](/imgs/gluon_line11.gif)

The number of coils is automatically changed. Note that for very short gluon/vector boson lines you can have undesired results. In that case, it is adviced to make a longer gluon/vector boson line and then resize it with the Selector Tool.

### Loops

Loops are very common when computing higher order terms of physical processes. Scalars, gluons and vector bosons are easier to draw. Fermions are a bit trickier and will be explained separately. No matter what kind of loop line you want to draw, all of them start with the same Inkscape tool: the Ellipse/Arc Tool (press `E`).

1. With the Ellipse/Arc Tool you can draw, as the name implies, ellipses/circles and arcs. Let us start drawing a ellipse. Click and drag the mouse on the document to start drawing the ellipse (if you hold `Ctrl` while doing so, you will be able to draw a circle) and release it to finish the drawing.

> [!IMPORTANT]  
> Check that there are no markers in the Stroke Style tab of the ellipse. This was explained in the [vector bosons and gluons lines](#vector-boson-and-gluonic-lines) subsection.

2. If you select now the Node Tool (press `N`) you will see that there are three markers. The squared markers allow you to change the shape of the ellipse. The circular marker is the one we are interested now.
![A drawn ellipse.](/imgs/ellipse1.png)

3. Clicking and dragging the circular marker will convert the ellipse into an arc. Note that the mouse should be inside the ellipse. If it is outside of it, instead of an arc we will have an slice.
![An arc.](/imgs/ellipse2.png)

4. This procedure can also be done with the Ellipse/Arc Tool, not only with the Node Tool. If we want to switch back to an ellipse or, for some reason, we would like to change the arc into a slice or a chord, there are four buttons in the top row that will allow us to do so. As can be seen in the following image (highlighted with the red rectangle), the last one is used to get back to the whole ellipse.
![Slice, arc, chord and ellipse buttons.](/imgs/ellipse3.png)

5. Once we have drawn the ellipse or arc as we wish, with the correct size, position and shape, we must apply a style to it. Note that ellipses/arcs should pass through each vertex involved in it. Depending on your dexterity with Inkscape, this will take more or less time. As a rule of thumb, is easier to work with circles than with ellipses and you adjust the radius so vertexes go trough it. It also helps to draw the circle first and then adjust the other elements around it. Play with Inkscape and you will find the procedure that works the best with you.

> [!TIP]
> Sometimes loops are made of different particles, e.g., a photon and a fermion. You can draw these with two arcs. Not every loop is made of the same particle or has the same shape.

#### Scalar loops

In the case of scalar loops, we do the same as steps 3 and 4 of the [scalar lines](#scalar-lines). We copy the style of the scalar line and paste it into our ellipse.

![A scalar arc.](/imgs/ellipse4.png)

#### Vector bosons and gluonic loops

In the case of vector bosons or gluonic loops, we do the same as steps 2 to 7 of the [vector boson and gluonic lines](#vector-boson-and-gluonic-lines). We add the Pattern Along Path path effect, copy the style we desire to use and paste it with the button.

![A vector boson and a gluonic arc.](/imgs/ellipse5.png)

Like before, with the Node Tool (press `N`) we can modify the shape of the arc and the path effect will change accordingly.

#### Fermionic loops

Fermionic loops are trickier because of the arrow. If you try to draw a circle and apply the fermionic line style to it, you will see that you get three arrows.

![Weird fermionic loop.](/imgs/ellipse6.png)

For a circle/ellipse, we would like to see only two arrows on opposite sides. How can we solve this? Depending on the length of the arc, there are several ways to solve it.

- **Arc with an angle $0^\circ \leq \theta < 180^\circ$**

For a simple arc with an angle smaller than $180^\circ$ you just simply draw the arc, then select the fermionic line style, copy it with `Ctrl + C` and then you paste the style onto the arc by selecting it and pressing `Ctrl + Shift + V`. This is the same procedure we followed for [scalar loops](#scalar-loops). Because the angle is not that big, the arc will only have one arrow.

![Smaller angle arc with one arrow.](/imgs/ellipse7.png)

- **Whole ellipse**

If we want to draw a whole ellipse, we need to break some of its nodes appart. The idea is to break the whole ellipse in subpaths such that there are just two middle nodes in total. That is where the arrows will be placed. It is easier done than said.

1. First of all, draw your ellipse with the shape, size and orientation you want. I have deleted all of the arrow markers and set a stroke width of 3 px. You will see that it has two squared nodes for the size and one circular node for the angle of the arc.
![Start drawing the ellipse.](/imgs/ellipse8.png)

2. Select the ellipse and click on `Path > Object to Path` or press `Ctrl + Shift + C`. The ellipse is no longer an ellipse object, but a path with four nodes.
![Start drawing the ellipse.](/imgs/ellipse9.png)

3. Assuming that the vertexes of the interaction (where the other lines will join the ellipse) are the left and right ones, the arrows will be placed on the top and bottom nodes. Select the left and right nodes with the Node Tool (press `N`).
![Left and right nodes are selected.](/imgs/ellipse10.png)

4. Click on the `Break path at selected nodes` button. It is located on the top bar of Inkscape (see the red rectangle in the image down below).
![Click on Break path at selected nodes.](/imgs/ellipse11.png)

5. Now the path is broken into two disconnected segments at the selected nodes. You can see that if you move one of those with the Node Tool (press `Edit > Undo` or `Ctrl + Z` to undo this if you moved the nodes).
![Path is now disconnected.](/imgs/ellipse12.png)

6. Select all the nodes with the Node Tool (press `N`) or select the whole ellipse with the Selector Tool (press `S`) and click on `Path > Break Apart` or press `Ctrl + Shift + K`. This has broken apart both segments of the same path into two separated paths. This can be seen on the Layers and Objects panel of the right.
![Path is broken appart into two separated paths.](/imgs/ellipse13.png)

7. Since we have two separated paths with just one node in the middle, we apply steps 5 and 6 of the [fermionic lines](#fermionic-lines) to each of the paths, i.e., copy the fermionic line with `Ctrl + C` and paste the style it into each ellipse path with `Ctrl + Shift + V`. Depending on the direction of the arrows you want, select one or another fermionic line.
8. Select both paths and group them by clicking `Object > Group` or pressing `Ctrl + G`. This allows you to move the whole ellipse as one object and not to worry about its components. Of course you can access its subcomponents and edit them individually if you wish by double clicking them or accessing through the Layers and Objects panel of the right.
![The ellipse is finished.](/imgs/ellipse14.png)

Voilà! You have your fermionic loop with arrows. Note that if you want to modify your ellipse now, you have to use the Selector Tool and transform/rotate the ellipse. After doing so, fix the stroke width back to 3 px again.

- **Arc with an angle $180^\circ \leq \theta < 270^\circ$**

There are two ways of doing this, a simple one and another one in which we break paths like with the whole ellipse. Choose the one you prefer.

1. Draw your arc and paste the style of the fermion line so you see where your arrows are falling in.
![An arc with arrows.](/imgs/ellipse15.png)

2. With the arc selected, we convert the object into a path by clicking on `Path > Object to Path` or by pressing `Ctrl + Shift + C`.
3. Select the Node Tool (press `N`) and select both nodes with the arrows. The problem is that the middle of arc does not have any node, so we are going to add one.
![Nodes with the arrows are selected.](/imgs/ellipse16.png)

4. Click on the `Insert new nodes into selected segments` button, which is in the top bar of Inkscape (see red rectangle in the image).
![Add a node in the middle.](/imgs/ellipse17.png)

This button inserts new nodes right in the middle of the selected segments. Now there are two approaches to tackle the problem. Let us see the simpler one first.
5. Select the nodes with the arrows that are not in the middle and delete them by clicking on the `Delete selected nodes` button, which is in the same top bar of Inkscape.
![Delete selected nodes.](/imgs/ellipse18.png)

6. And that is it. You have your fermionic arc. If you want to modify the angle of it, you have to start again. We no longer have the arc object, but a path now. You can still rotate or transform it with the Selector Tool. Remember to set the stroke width back to 3 px afterwards.
![There you go.](/imgs/ellipse19.png)

Instead of steps 5 and 6, one can also do the other approach, which is what we did with the **whole ellipse**. You select with the Node Tool the middle node that you have just added on step 4. Then, you click on the `Break path at selected nodes` button and break apart both paths with `Path > Break Apart` or by pressing `Ctrl + Shift + K`. You will end up with something like this:

![Alternative method for this fermionic arc.](/imgs/ellipse20.png)

Now, you select the fragment of the left, for example, and go to the `Fill and Stroke > Stroke style` panel. Click on the middle marker button and set it to none like in this image:

![Remove middle markers of the first fragment.](/imgs/ellipse21.png)

Select the fragment of the right and remove the middle marker again. Moreover, click on the start markers button and select the arrow. Since the first node of this fragment falls right in between the arc, putting an arrow here will put it in the middle of the arc.

![The fermionic arc is complete](/imgs/ellipse23.png)

Of course, if you prefer not to use these two methods, you can always put the arrow by hand. I provide one on the top of the document for you to clone it.

- **Arc with an angle $270^\circ \leq \theta < 360^\circ$**

This case is very similar to the previous one, but even more simpler, since now there is a node with an arrow exactly on the middle of the arc.

1. Draw your arc and convert the object to a path (click on `Path > Object to Path` or press `Ctrl + Shift + C`) as described in steps 1 and 2 of the previous case.
![A big arc with three arrows.](/imgs/ellipse24.png)

2. Select the nodes that have the extra arrows and press the `Delete selected nodes` button.
![Delete those extra arrows.](/imgs/ellipse25.png)

3. Your fermionic arc is now complete. Again, if you want to modify the angle of it, you have to start again. We no longer have the arc object, but a path now. You can still rotate or transform it with the Selector Tool. Remember to set the stroke width back to 3 px afterwards.
![There you go again.](/imgs/ellipse26.png)

With the other method we can do the same. In this case we select the middle arrow node and click on `Break path at selected nodes`, then we click on `Path > Break Apart` or we press `Ctrl + Shift + K` so get two separated paths. We delete the midle markers on both of them and keep the startin (or ending) marker in one of the others.

![Alternative method for doing the fermionic arc.](/imgs/ellipse27.png)

And this is it! We have finished with loops. Phew! Do not worry, once you grasp and memorize this, it will be quite fast to do.

### Vertexes

Once we have drawn the lines of our diagram, we need to add the vertexes, which are given by this small dot:

![The vertex is the dot.](/imgs/vertexes1.png)

To put the vertex in position is as simple as selecting it, and creating a copy of it with `Ctrl + C` and `Ctrl + V` to copy and paste or with `Ctrl + D` to duplicate it. The duplicated object is on top of the original one. Move it with the Selector Tool (press `S`).

Take for example, this simple diagram of a fermion and a photon. Once the lines are correctly placed,

![Simple diagram with only lines.](/imgs/vertexes2.png)

we can position manually the vertex. Sometimes is easier to deactivate the Snapping tool (the top-right corner button with a magnet symbol) and zoom a bit the canvas for a more precise control. Note that you may want to move the lines a bit later so they are perpendicular to the edge of the vertex. The finalized diagram woud look like this:
![Finalized diagram.](/imgs/vertexes3.png)

If you do not like the dots for the vertex and prefer to use only lines, you are free to do so. But **PLEASE**, do join the vertexes correctly! Avoid making these kind of things

![No, please no.](/imgs/vertexes4.png)

and **spend thirty seconds fixing them**. Once they are fixed, group all the lines with `Ctrl + G` if you want to better move them around.

![This looks way better.](/imgs/vertexes5.png)

I did nothing special, but I had the Snapping tool activated (top-right corner) to make it faster and easier.

![Activate the Snapping tool to make things easier.](/imgs/vertexes6.png)

These are my default settings for the Snapping tool, I have not touched anything:

![Default Snapping tool settings.](/imgs/vertexes7.png)

If the Snapping mode gets finicky and you cannot make precise adjustments, zooming in (`Ctrl + Scrolling wheel` for example) always helps. If not, you can check or uncheck certain boxes of the menu and see if that helps. You can also deactivate the Snapping tool. It is up to you to choose your workflow.

### Blobs

Blobs can be placed very easily, like vertexes. They are the filled colored circle of the elements.

![A blob.](/imgs/blob1.png)

Once the blob is selected, duplicate it with `Ctrl + D` and move it to your diagram with the Selector Tool (press `S`). An example diagram looks like this:

![Diagram with a blob.](/imgs/blob2.png)

### Labels

Labels are elements that we add on the diagram to give additional information, like the name of the particles, the direction and names of the momenta and so on.

You can add text in Inkscape with the Text Tool (press `T`). Once you select the tool, click on the document and start typing. Once you have finished typing, you can click on the Selector Tool (press `S`) and move the text around.

If you open the Text and Font panel (click on `Text > Text and Font` or press `Ctrl + Shift + T`), you can modify some properties like the size, the style, the font, among others. There is not much to say here, personalize it to your needs.

I recommend using the [STIX fonts](https://www.stixfonts.org/), which can be downloaded on [https://github.com/stipub/stixfonts](https://github.com/stipub/stixfonts). They are suited for scientific needs and publication. They are based on [The Unicode Standard](https://en.wikipedia.org/wiki/Unicode) and provide a lot of glyphs. Regarding the font size and style. I have found that a font size of 20 -- 26 approximately for the regular style looks good. It depends on the size of the final image.

In addition to text, you can add arrows to indicate the direction of the momenta inside loops. I provide a simple arrow from which you can copy the style and paste it in your diagram. Please, feel free to modify the Stroke style to your needs.

![An arrow.](/imgs/labels1.png)

Not everyone chooses to draw an arrow with the momenta, sometimes it clutters too much the diagram. Here you have a simple example of two tadpole diagrams. One with the momentum arrow, and one without it.

![Two tadpole diagrams.](/imgs/labels2.png)

Regarding the input of greek letters for the name of particles, you can choose a font that supports Unicode glyphs like the STIX fonts and directly paste the symbol (γ for photon, Ξ for the baryon and so on) or you can enter LaTeX formulas using an extension like [TexText](https://github.com/textext/textext). I prefer to enter the symbol directly because it is easier to change the font later. But for more complex diagrams, I would probably use the LaTeX extension if I needed mathematical expressions or things like `\vec{}`, `\overline{}` and so on. Inkscape directly provides a Unicode chart to input symbol. To open it, click on `Text > Unicode Characters...`.

### Extra

- **Majorana lines**

In case you want to draw a majorana neutrino interaction or any other interaction that requires a cross, I provide a straight solid line with a cross marker in the middle. You can use it in the same way as the fermionic lines, since it is basically the same but with a different marker for the middle nodes. Check the [fermion lines](#fermionic-lines) and the [fermion loops](#fermionic-loops) subsections in case of doubt.

![Majorana line.](/imgs/extra1.png)

- **Independent markers**

If you also prefer to place the middle markers by hand instead of with the methods explained before, you can duplicate them and move them as you prefer.

![Markers.](/imgs/extra2.png)

If you want to use custom markers, please check the [Custom markers](#custom-markers) section.

- **Extra length for gluonic lines**

If you think your gluonic lines are too close to the vertex, you can extend them a bit with this small line:

![Extra small line.](/imgs/extra4.png)

Duplicate it and move it next to your gluonic lines.

![Move the line closer](/imgs/extra5.png)

Zooming in a bit and using the Snapping tool helps aligning them perfectly. Once that is done, group them by clicking on `Object > Group` or by pressing `Ctrl + G` so they can be moved together.

![Group them.](/imgs/extra6.png)

Sometimes you can see a very thin line between the gluonic line and the extra segment. With the Selector Tool (press `S`) select the extra small segment and move it into the gluonic line by 0.2 px (more or less), so it falls inside the line. Now the segment will overlap the gluonic line a bit and you will not see this ugly line. In this case I had to move it horizontally to the left, that is why I only changed the X value of the segment.
![Move 0.2 px to the inside of the gluonic line the segment.](/imgs/extra7.png)
You can compare on the next image the result. The bottom diagram has those small segments and the coils of the gluonic line are not that close to the blob.

![Final result.](/imgs/extra8.png)

This is a very small subtlety, but hey, it is there if you want to use it. Feel free to make the line longer or shorter according to your needs.

### Moving elements around

Once you have a complex element of your diagram done, like a subdiagram, a blog with text, a gluonic line with an extension or anything you think you will not need to modify but you will need to move around, it is a good idea to group the elements.

This is very easy to do. First you select every element with the Selector Tool (press `S`) or the Node Tool (press `N`). I recommend the Selector Tool. Recall that you can drag with the mouse to select several elements or you can hold `Shift` while clicking on each one of them individually. Once you have all the desired objects selected, group them by clicking on `Object > Group` or by pressing `Ctrl + G`. Now when you select them you will see that they are one entity.

If you select the group and change a property, like the fill color, it will affect all the elements of the group. If you only want to modify a single element. You can double click the group and the click the element once to access to it.

Let me explain this with images.

Click on `Object > Layers and Objects` or press `Ctrl + Shift + L` to open the Layers and Objects panel on the right. Here you can see every element of the diagram. It is convenient to name the elements if you have tons of them.

![Layers and Objects.](/imgs/move_elements1.png)

When I click on my group object once, it is selected also on the panel. Note that `Layer 1` is also selected. This means that each single click with select the whole element/group relative to the Layer 1 page.

![Group is selected.](/imgs/move_elements2.png)

Deselect the group by clicking on a blanck space outside of it. Now double click it. Even though there is nothing selected, you can notice on the panel that now `Layer 1` is not selected, but `g59` is. This means that the group g59 will be the root of our selection, i.e., each single click we make will only select elements inside the group and relative to it.

![Layer 1 is no longer the root of the selection.](/imgs/move_elements3.png)

This is why a single click in one of the blobs selects it now.

![The blob is selected with a single click.](/imgs/move_elements4.png)

To return back to normal, you can double click the empty page and the root will change again to the Layer 1 page.

![Everything is back to normal.](/imgs/move_elements5.png)

You can also select the elements by clicking directly on them on the `Layers and Objects` panel. However, if you do not name your elements and have a lot of copies of them, it will be a bit harder to know which `blob`, for example, is each one on the diagram.

### Exporting your diagram

Once your diagram is made, we want to save it in a different format. For example a `.pdf` file that will be included in a LaTeX document for the paper or some slides, a `.png` if you prefer an image, and so on.

Firs of all, click on `File > Export` or press `Ctrl + Shift + E` to open the Export panel. You will see on the top of the panel that there are several options: `Document`, `Page`, `Selection` and `Custom`. This is what will be exported.

![Export panel.](/imgs/export1.png)

In our case we do not want to export the whole document, only the diagram. The simplest way to solve this is by selecting the diagram we are interested into with the Selector Tool (press `S`) and then clicking on `Selection`. You will see on the small preview at the bottom of the panel that now only the diagram will be exported.

![Export only the selection.](/imgs/export2.png)

Next, click on the folder icon to select the path where the file will be saved and then click on the arrow of the right to change the export format.

![Select the output folder and the format.](/imgs/export3.png)

There are several export formats. Use `Inkscape SVG` if you want to store a separated Inkscape document of just the diagram. This is useful if later one you want to modify the diagram and change colors, widths and so on. Use `PDF` if you want a high quality vector format that can be included in a LaTeX document for a journal, a presentation, a poster, and so on. Rembember that you can open PDF files with Inkscape (if the `.svg` file is not available) and make complex layouts too! Otherwise, choose `PNG` for an image format that allows the use of transparency. If you want other format, go ahead.

![Export formats.](/imgs/export4.png)

Click on the wheel to change the export settings and click on `Export` to save it.

![Export settings.](/imgs/export5.png)

In the case of PDF, you can choose to embed the fonts into the document or to convert every text to paths. In the later case, everyone will be able to open the document, but you will lose the ability to modify the text font, since now it is a path. If you keep the original `.svg` in your computer, there is no problem then.

If you want to export the diagram as a `.png`, you can change the DPI of the image to increase or decrease its resolution. For a example, with a DPI of 96.00, the image has a size in px of 280 x 60.

![Smaller DPI.](/imgs/export6.png)

Increasing the DPI to 600.00 will make the image bigger. Not it has a size in px of 1749 x 375.

![Bigger DPI.](/imgs/export7.png)

Recall that bigger image sizes imply heaver files and that a vector file is very small if it has no grandients or fancy things.

## Advanced usage

Everything that has been described in the [Usage](#usage) section will cover the majority of diagrams. Inkscape is a very capable and powerful program to draw vector graphics. If you want to go beyond, you can. The limit is your imagination, really.

Let me describe a couple of ideas which are more advanced to implement that might be useful for your diagrams.

### Modify the style as you wish

Every path of Inkscape can be modified. You can change the color of the filling, the stroke, you can change the width, the stroke style, the marker style, how the nodes are joined together and so on.

Imagine that you want to draw a diagram with a scalar line and a fermionic arrow. It is as simple as changing the Stroke style `Dashes` to dashed and then putting a middle node with an arrow marker.

![Make a fancier line.](/imgs/style1.png)

Or maybe you feel like making fancier things and you start changing the `Cap` to `Round Cap`, then you adjust the `Dashes` to incrase the spacing a bit and choose a fancier middle `Marker` that you modify a bit.

![Fancier line.](/imgs/style2.png)

But then you decide to add a color gradient to change the `Stroke paint` to go from black to red. And you want the marker to have a different color than the strike, so you click on `Extensions > Styles > Color Markers...` and give the marker a dark green color for the stroke and fill it with a lighter green with a lower alpha level (the opacity).

![Even fancier line.](/imgs/style3.png)

As you can see, once you have an idea, you can start composing it little by little to achieve the desired final result.

### Custom markers

Imagine that you want to make a diagram with a new process that requires a different marker: the smiley scattering. First of all, we start drawing our marker with the tools that you prefer. For the sake of the example, I will use the Pen Tool (press `P`) to draw the best smiley face you will ever see.

![Amazing, isn't it?](/imgs/custom_marker1.png)

Great, we have our marker. First of all, we select all the individual paths and combine them into just one by clicking on `Path > Combine` or by pressing `Ctrl + K`. Now let us make it smaller and save the original in case we want to place it in random places on the diagram. Remember to adjust the Stroke width after scaling the path. If you do not plan to use the original marker, it is not needed to combine all the elements, just resize the selection a bit.

![Gorgeous.](/imgs/custom_marker2.png)

Now, since we want to conserve a copy, duplicate the object with `Ctrl + D` and move it to the side. Select the object and click on `Object > Objects to Marker`.

![Convert the selection to a line marker.](/imgs/custom_marker3.png)

Finally, create a path and apply your fancy new marker to it. It will appear on top of all the other markers. I have modified the `Size` property a bit to make it smaller. You can change the orientation, rotation, whatever, to suit your needs.

![There you go.](/imgs/custom_marker4.png)

Custom markers are stored in the `.svg` document. They are not shared across the whole Inkscape program.

### Parallel lines

When you draw the diagram of a composite particle, like a nucleon, you draw parallel lines representing the quarks. If you have straight lines, drawing these is straightforward. You just duplicate the line and move it up or down.

![Three parallel lines.](/imgs/parallel_lines1.png)

There is a small issue, do you see it? They are not distributed equally. You can separate the lines by hand more or less and with the help of the Snapping tool it can be good. Let me show you another method that I really like: the `Align and Distribute` panel. To open it click on `Object > Align and Distribute` or press `Ctrl + Shift + A`. Once the panel is open, select your three lines and click on the `Distribute vertically with even vertical gaps` button.

![Click on distribute vertically.](/imgs/parallel_lines2.png)

And now your lines are equally spaced vertically.

![Lines are parallel.](/imgs/parallel_lines3.png)

Play with the `Align and Distribute` panel to learn how to use each mode and get used to it. Aligning objects is also useful.

What about arcs? The easy way is to use circles, not ellipses. When you draw a ellipse, pressing `Ctrl` will help to make it a circle. If you also press `Shift`, the circle will be created from the center. After your circles are created, align the centers with the `Align and Distribute` panel if needed.

![Three concentric circles.](/imgs/parallel_lines4.png)

Next, to make them equidistant, change the radius of the circles accordingly. For example, let us sepparate it 15 px in radius, with the inner circle having a radius of 40 px. Select the Ellipse/Arc Tool (press `E`) and then click on the first circle. On the top left corner you can change the radius with the specific values. Select the units as px and write 40 on both `Rx` and `Ry`.

![Change the radius.](/imgs/parallel_lines5.png)

Do the same with the other circles. The middlemost one will have `Rx = Ry = 55 px` and the outtermost will have `Rx = Ry = 70 px`.

![Concentric circles.](/imgs/parallel_lines6.png)

If you want to convert that now to an arc, you can draw two auxiliary lines that will be deleted afterwards that will serve you as guidelines. I have drawn them in blue.

![Blue guidelines.](/imgs/parallel_lines7.png)

Next, with the Node Tool (press `N`), change the angle of the arc so it falls between the guidelines. Do this for every circle. If it is difficult to adjust, make the guideline thinner. For this I have reduced its Stroke width to just 0.1 px. The final result is

![Final arcs.](/imgs/parallel_lines8.png)

Remove the guidelines and group the objects if needed.

#### Arbitrary parallel paths

Alright, you prefer to not use straight lines or circles but an arbitrary path. Bear with me, this is a bit more elaborated. I will start drawing a random path with the Pen Tool (press `B`), but you can use whatever you prefer. If you have several paths, combine them with `Ctrl + K`.

![Random path drawn with the Pen Tool.](/imgs/parallel_lines9.png)

We will start having just two parallel lines.

1. Increase the Stroke width by your desired amount. For example, 23 px.
![Increase Stroke width.](/imgs/parallel_lines10.png)

2. Convert the Stroke into a path. To do so, click on `Path > Stroke to Path` or press `Ctrl + Alt + C`. See how now the nodes have changed.
![Convert Stroke to Path.](/imgs/parallel_lines11.png)

3. Click on Fill and Stroke and set the `Fill` to `None`. Do not worry if the path is invisible now. You see that it still exits and it is selected.
![Make the fill to none.](/imgs/parallel_lines12.png)
Click on `Stroke paint` and set it to `Flat color`. Choose black.
![Add stroke color.](/imgs/parallel_lines13.png)
Go to `Stroke style` and set the width to 3 px, for example.
![Increase the Stroke width](/imgs/parallel_lines14.png)

4. Now we need to remove the edge lines. Select those nodes with the Node Tool (press `N`). Recall that you can hold `Shift` while clicking on the nodes or doing several drags with the mouse to select them. Next, click on the `Break path at selected nodes` button.
![Break path at those nodes.](/imgs/parallel_lines15.png)

5. Click on `Path > Break Apart` or press `Ctrl + Shift + K` to separate each subpath. This is what we already did within the [fermionic loop](#fermionic-loops) subsection.
6. Select each edge element and delete it (press `Supr` key).
![Delete those edge elements.](/imgs/parallel_lines16.png)

7. Once deleted, select every path of the line and combine them back with `Ctrl + K` or by clicking on `Path > Combine`. Now you have two parallel lines. Modify or add nodes in the middle to refine the result.
![There you go.](/imgs/parallel_lines17.png)

What if we want to do the same with three parallel lines? It is as simple as having two paths.

1. Draw your path and duplicate it. Change the Stroke width of one of those by your desired amount, but do not move the paths, they must be aligned. Let me make the middle line red so you can see it and put it above the other one.
![One line is wide, the other one is not.](/imgs/parallel_lines18.png)

2. Select only the big wide black line and follow the same procedure we described for having two parallel lines. Using the `Make selected nodes auto-smooth` can help to make the curve look less sharp and nicer.
![Three parallel lines.](/imgs/parallel_lines19.png)

3. Change the red line color back to black and combine everything (press `Ctrl + K`). Or, if you prefer, group them if you want to modify them further (press `Ctrl + G`).
![There you go again.](/imgs/parallel_lines20.png)

What about four, five, six lines and so on? The procedure is the same. If you want an even number of parallel lines, duplicate as many times as you need your original curve and change each Stroke width. For four parallel lines, we would need to copies. The outer copy must be wider than the inner one. Then follow the procedure described. If you want an odd number of parallel lines, do the same but add the additional center line, as described in the process of three parallel lines.

Your patience is the limit!

![Mega blob](/imgs/parallel_lines21.png)

Yes, I have used auto-smooth nodes for this last figure on corners that looked weird. Maybe they are not perfectly parallel and is not even the best method, but it is a solution.

## Technical notes

In order to create the gluonic and vector boson patterns, you have to draw a rectangle with the Rectangle Tool (press `R`) and select it.

![Create the rectangle](/imgs/technical_notes1.png)

Then, click on `Extensions > Render > Parametric Curves...` to open the parametric curves dialog.

![Open the parametric curves extesion.](/imgs/technical_notes2.png)

For the smooth vector boson pattern, the line was created with the following parameters:

![Vector boson pattern.](/imgs/boson.png)

The sharp vector boson pattern was obtained from [this post](https://graphicdesign.stackexchange.com/questions/107442/inkscape-feynman-diagrams).

For the gluonic lines pattern, the line was created with the following parameters:

![Gluonic pattern.](/imgs/gluon.png)

If you want more nodes in the created pattern, increase the number of `Samples` when applying the parametric curve to the rectangle. Later on, you can modify the nodes by hand if you wish, as I did. Be careful on not breaking the periodicity of the pattern, or it may look weird once it is repeated on the line.
