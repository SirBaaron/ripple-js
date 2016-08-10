# ripple-js
**A small Javascript library for ripple effects**

<br><br>

####View a demo [here](http://sirbaaron.github.io/ripple-js/demo/)

<br><br><br>

### Setup
**With npm:**<p>1. At the root of your index, type `npm install ripple-js` into the command line.<br>2. Add the tag `<script src="node_modules/ripple-js/ripple.min.js"></script>` to your index file.

 
**Then simply add the class ripple to elements**

<br><br><br>
### Properties

To customize the ripple effect you can set the following tags on your ripple elements:
* **ripple-color**<br>Customize the background of the ripple <p>°Corresponds to the css `background` property. You can set it to a color, a gradient or even a picture.<br>°_Examples:_ `ripple-background="#FF8C00"`, `ripple-background="radial-gradient(red, yellow, green)"`, `ripple-background="url('some-image.jpg')"`<br>°_Default Value:_ `white`
* **ripple-opacity**<br>Set the opacity of the ripple <p>°Corresponds to the css `opacity` property. Set it to a numerical value between 0 and 1, where 0 means full transparency and 1 no transparency<br>°_Example:_ `ripple-opacity="0.7"`<br>°_Default value:_ `0.6`
* **ripple-shadow**<br>Add a shadow to the ripple <p>°Corresponds to the css `box-shadow` property.<br>°_Example:_ `ripple-shadow="box-shadow: 0px 0px 25px 2px rgba(112,112,112,0.63)"`<br>°_Default value:_ `none`
* **ripple-press-expand-time**<br>Change the time the ripple needs to fully expand while the element is being pressed. <p>°The unit of measurement is seconds.<br>°_Example:_ `ripple-press-expand-time="10"`<br>°_Default value:_ `3`
* **ripple-release-expand-time**<br>Set the time the ripple needs to ripple away when the user releases the mouse / touch. <p>°The unit of measurement is seconds.<br>°_Example:_ `ripple-release-expand-time="1.5"`<br>°_Default value:_ `0.4`
* **ripple-leave-collapse-time**<br>Configure the time the ripple collapses in itselft when the user moves the touch / mousepress away from the element. <p>°The unit of measurement is seconds.<br>°_Example:_ `ripple-leave-collapse-time=".8"`<br>°_Default Value:_ `0.4`
* **ripple-cancel-on-move**<br>If applied, the ripple cancels on the slightest touch movement. <br>°Normally the ripple gets canceled when the touch is being moved out of the container. With this attribute, the touch gets canceled on a touchmove or mousemove. This is especially great for when the container can be scrolled around by the user.

* **onrippleclick**<br>You can specify JavaScript that executes when the ripple gets released in this attribute. It works like _onclick_ and is a short alternative to listening for a ripple-button-click event.

<br><br><br>
###Methods

* **registerRipples()**<br>Call this method to register ripple elements afterwards <p>°If you add ripple elements after the document has loaded, you then need to call this function. The function gets called auomatically on initial load.<br>°_Example:_ 
```
document.body.innerHTML += '<div class="ripple">Added Afterwards</div>';
ripple.registerRipples();
```
* **ripple(element)**<br>With this function you can trigger a ripple programatically.<p>°The only argument it takes is the element you want to start the ripple at. This element needs to have been registered before!<br>°The ripple starts at the center of the element. This function is useful when you want to click an element based on key presses.<br>°_Example:_ `ripple.ripple(document.getElementById("someEl"));`

<br><br><br>
###Events

* **ripple-button-click**<br>This event gets fired when a ripple is released<p>The only parameter is `target`, which is the element that got clicked


<br><br><br>
Tip: To unregister an element, simply remove the `ripple` class.
