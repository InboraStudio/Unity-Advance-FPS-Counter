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

``` bash
// place this line right at the beginning of your .cs file!
``` 
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
AFPSCounter draws all its data using Labels, which are the uGUI Texts placed within the automatically generated Canvas
with Screen Space - Overlay mode.
Thus, in order to see the counters, you do not need to perform any additional actions in most cases.
IMPORTANT:
If you will place AFPSCounter somewhere inside the existing Canvas, auto-generated one will inherit options from the
parent. This is useful when you wish to use plugin in some special environment, such as a World Canvas in the VR project.
Please refer to the Troubleshooting section below if you do not see the counters after performing initial setup.
