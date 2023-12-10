# Unity-Advance-FPS-Counter
This is a advanced unity express counter that work with every unity supported version that shows system type Ram V Ram device name. and tons of things including professor Fps count In this you can even see how much your display size and what is your display frame rate. What is your display and your device name? What number of course processor have. How much v ram your graphic card haven't. What is your graphic card name? What is your graphic card? API version and everything you can see on your screen and just some clicks and it's 100 percent free.



# Installation and setup
IMPORTANT:
   To avoid different compatibility issues and errors, always remove previous version from project Assets before updating.
   As you import plugin, you have such options for adding Advanced FPS Counter to your scenes:
- Drag Inbora Studio/AdvancedFPSCounter/Prefabs/Advanced FPS Counter prefab to the Scene Hierarchy.

  Hint:

- You also may find prefabs from the Examples/Prefabs folder useful for the VR or World Space setup.

- Add from the Scene Hierarchy context menu (or Game Object menu):

------------------------------------------------------------------------

- Add AFPSCounter component to any existing Game Object using Add Component button or just drag dropping it from
  Project Browser:


  "Add Component" button > Code Stage > Advanced FPS Counter

- Add to scene from code using AFPSCounter.AddToScene() API

Hint:
- You need to add namespace CodeStage.AdvancedFPSCounter to usings in order to work with plugin from code.
  Here is a simple example:

``` cpp
// place this line right at the beginning of your .cs file!
using CodeStage.AdvancedFPSCounter;

// ...
private void Start()
{
  // instantiates AFPSCounter in scene if it not exists
  // with disabled keepAlive option
  AFPSCounter.AddToScene(false);

  // changes spacing between counters
  AFPSCounter.Instance.CountersSpacing = 1;
}
```

AFPSCounter draws all its data using Labels, which are the uGUI Texts placed within the automatically generated Canvas
with Screen Space - Overlay mode.
Thus, in order to see the counters, you do not need to perform any additional actions in most cases.


IMPORTANT:
If you will place AFPSCounter somewhere inside the existing Canvas, auto-generated one will inherit options from the
parent. This is useful when you wish to use plugin in some special environment, such as a World Canvas in the VR project.


Please refer to the Troubleshooting section below if you do not see the counters after performing initial setup.


------------------------------------------------------------------------


## Plugin features in-dept


Operation Mode: controls how AFPSCounters runs.
  - Disabled mode is used to remove all counters and stop all internal
    processes except the global hotkey / gesture listener.
  
  - Normal mode should be used in most cases: counters are visible and
    operate as intended.
  
  - Background mode allows reading all enabled counters data using
    Scripting API without uGUI output thus avoiding any additional

resources usage. Useful for performance / hardware stats, for hidden
performance monitoring and quality settings suggestion, etc.

 - Hot Key: customizable global hotkey to show / hide plugin using
   Disabled / Normal Operation Mode switch. Does not affect Background
   Operation Mode.
   
 - Circle Gesture: complements Hot Key and does same job.
   Touch screen / touchpad or hold left mouse button and make ~2
   circles in any direction to switch Operation Mode.

 - Keep Alive: allows keeping Advanced FPS Counter’s Game Object on new
   scene load (using DontDestroyOnLoad).

------------------------------------------------------------------------

IMPORTANT:
The topmost root Game Object will be kept alive if AFPSCounter is
placed on the nested Game Object.
  - Force FPS: allows trying your game at specified frame rate, may help to
    debug your game behavior / physics on slow devices; specified frame
    rate is not guaranteed though (and may not work at all).

------------------------------------------------------------------------

# Look & Feel settings


- Auto Scale: controls Canvas’s CanvasScaler uiScaleMode.
    When disabled, uses ConstantPixelSize with specified Scale Factor.  
    When enabled, uses ScaleWithScreen.

- Labels Font: font used to render counters in Labels (uGUI Texts).
    Monospace font with Bold style support usually looks great.

- Font Size: controls size of the used Font.

- Line Spacing: controls space between lines in single Label using uGUI Text
    LineSpacing.

- Counters Spacing: empty lines count between different counters in same
    Label.

- Padding Offset: offset for the Labels placement. Relative to the Anchor
    position set at the per-counter settings and automatically changes sign
    for the right and bottom Labels.

- Pixel Perfect: controls own Canvas PixelPerfect property in overlay
    modes.

- Background: colored background effect with customizable Color and
    Padding. Costs only 1 Draw Call. Fair deal for better visibility.

- Shadow & Outline: text rendering effects with customizable Color and
    Distance. These are resources-heavy (especially outline) so use with
    caution on mobile devices.

------------------------------------------------------------------------


# Advanced settings

- Sorting Order: controls Canvas’s sortingOrder property.
   With higher value Canvas gets closer to the user while sorting with
   other canvases.
