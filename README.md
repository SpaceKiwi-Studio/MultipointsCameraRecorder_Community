# MultipointsCameraRecorder by Space Kiwi Studio

![SpaceKiwiStudio](https://cdn.discordapp.com/attachments/1018872903292436530/1018873357162254386/SpaceKiwiStudio128.png)

## Mise en place
- [A. Plugin Installation](#plugin-installation)
- [B. Find & Add Actors](#find--add-actors)
- [C. Setup Game Instance](#setup-game-instance)
- [D. Create & Setup ``BP_CameraShapeActor``](#create--setup-bp_camerashapeactor)
- [E. Setup the ``BP_CameraManager``](#setup-the-bp_cameramanager-and-set-properties)
- [F. Setup the ``BP_RecordManager``](#setup-the-bp_recordmanager-and-set-properties)
- [G. Record !](#record)
- [/!\ Need support ?](#space-kiwi-studio)

# Plugin Installation
![SpaceKiwiStudio](https://cdn.discordapp.com/attachments/1018872903292436530/1018891459061092422/StepByStepPlugin.jpg)
+ 1 In your project folder, find the ``Plugins`` folder. If the folder doesn't exist, create a new folder and name it ``Plugins``
+ 2 In the ``Plugins`` folder, you can put the plugin folder ([MultipointsCameraRecorder](https://github.com/Space-Kiwi-Studio/MultipointsCameraRecorder/releases/tag/plugin)) here 
+ 3 In Unreal Engine (``UE5.0`` minimum), go to ``Edit > Plugins``, find the plugin and activate it

# Find & Add Actors
![SpaceKiwiStudio](https://cdn.discordapp.com/attachments/1018872903292436530/1018894986458181692/FindActors.jpg)
![SpaceKiwiStudio](https://cdn.discordapp.com/attachments/1018872903292436530/1018914515737382962/SetupActorInLevel.jpg)
+ 1 Frist, Drag & Drop a ``BP_RecordManager`` in yous Level ([Tuto link](https://github.com/Space-Kiwi-Studio/MultipointsCameraRecorder/edit/main/README.md#f-setup-the-bp_recordmanager-and-set-properties))
+ 2 Now, Drag & Drop a ``BP_CameraManager`` in your Level ([Tuto link](https://github.com/Space-Kiwi-Studio/MultipointsCameraRecorder/edit/main/README.md#e-setup-the-bp_cameramanager-and-set-properties))
+ 3 And now, you can Drag & Drop many ``BP_CameraShapeActor`` in your Level ([Tuto link](https://github.com/Space-Kiwi-Studio/MultipointsCameraRecorder/edit/main/README.md#d-create-a-shapeproperties-and-setup-bp_camerashapeactor-in-level))

# Setup Game Instance
![SpaceKiwiStudio](https://cdn.discordapp.com/attachments/1018872903292436530/1019247761633316964/SetupGameInstance.jpg)
+ 1 First, in ``Edit > Project Settings`` find ``Maps & Modes`` in ``Project`` group
+ 2 After that, you can find a field named ``Game Instance`` and you need to change the Game Instance by ``GI_MPCR``

# Create & Setup ``BP_CameraShapeActor``
![SpaceKiwiStudio](https://cdn.discordapp.com/attachments/1018872903292436530/1019300970850701312/CreateShProperties.jpg)
+ 1 First, right clic and find ``Miscellaneous``
+ 2 Find ``DataAsset`` and select it
+ 3 And now, you can choose ``ShapeProperties``
![SpaceKiwiStudio](https://cdn.discordapp.com/attachments/1018872903292436530/1019273784500432987/SetShapeActorSettings.jpg)
+ 1 This is the total position point(s) count for the ``Camera``
+ 2 This is the ``Sphere/Circle`` radius property
+ 3 This is the angle clamp for the ``Sphere/Circle``
+ 4 This is the forward angle for the ``Sphere/Circle``, this property affect the ``Z`` Axis angle
+ 5 With this property, you can choose if your shape is an ``Sphere`` or ``Circle``
+ 6 This property slice the ``Sphere`` verticaly n time
+ 7 This is the min height value for the position point(s), this value is between ``[-radius, max height]``
+ 8 This is the max height value for the position point(s), this value is between ``[min height, radius]``
+ 9 You can save
![SpaceKiwiStudio](https://cdn.discordapp.com/attachments/1018872903292436530/1019275247133929552/EditShapeActor.jpg)
+ 1 Set your ``DataAsset`` here, the properties will be setup automaticaly

# Setup the ``BP_CameraManager`` and set properties
![SpaceKiwiStudio](https://cdn.discordapp.com/attachments/1018872903292436530/1019286849715449967/SetupCameraManager.jpg)
+ 1 Frist, clic on the ``+``
+ 2 When the element list is added, you can choose yout ``BP_CameraShapeActor`` in your Level
+ 3 Select your ``Camera`` you want affect the position when your lauch your record (/!\ Use your camera in your LevelSequence and remove every properties on this camera in the Sequence)
+ 4 Select your ``RecordManager`` in your Level

# Setup the ``BP_RecordManager`` and set properties
![SpaceKiwiStudio](https://cdn.discordapp.com/attachments/1018872903292436530/1019271284909158441/CreateANewShapeProperties.jpg)
+ 1 First, right clic and find ``Miscellaneous``
+ 2 Find ``DataAsset`` and select it
+ 3 And now, you can choose ``RecordProperties``
![SpaceKiwiStudio](https://cdn.discordapp.com/attachments/1018872903292436530/1019294664110657586/CreateANewRecorderProperties.jpg)
+ 1 This is the video name property
+ 2 This is the video repository property
+ 3 You can choose your video resolution here
+ 4 This property let you choose if you want the framerate of your ``LevelSequence`` or if you want override
+ 5 This is the new framerate of your video if you set the 4 property to ``True``
+ 6 This is your current ``Level`` here (The Level where your ``BP_RecorderManager`` is set)
+ 7 This is your current ``LevelSequence`` here (The LevelSequence where your ``BP_RecorderManager`` is set)
+ 8 If you set this property to ``True``, you override the ``Start`` & ``End`` frame record (This is the start and end frame of your LevelSequence)
+ 9 This is the ``Start`` frame value overrided when you set the 8 property to ``True``
+ 10 This is the ``End`` frame value overrided when you set the 8 property to ``True``
+ 11 Select your Anti-Aliasing Properties ``DataAsset`` to apply the properties to your record
+ 12 Select your ConsoleVariables Properties ``DataAsset`` to apply custom console line to your record
+ 13 This is the only Codec used now, don't modify this property
+ 14 This is the Codec Settings for your video in ``.mov`` (Proxy use less bitrate)
+ 15 This plugin use CLIEncoder plugin, this value is used by ``ffmpeg`` ([Tuto for ffmpeg](https://dev.epicgames.com/community/learning/tutorials/BbYV/unreal-engine-how-to-use-ffmpeg-with-the-command-line-encoder-in-movie-render-que))
+ 16 If you want use additional command for ``ffmpeg``, set your command line here
+ 17 If this property is ``True``, the recorder manager will open the next Level automatically
+ 18 Set your next ``Level`` here, this value is used when the 17 property is ``True``
+ 19 You can save now
![SpaceKiwiStudio](https://cdn.discordapp.com/attachments/1018872903292436530/1019290487754080317/SetupRecordManager.jpg)
+ 1 Select your ``BP_CameraManager`` in your Level
+ 2 Set your ``DataAsset`` here, the properties will be use when you launch your record

# Record
![SpaceKiwiStudio](https://cdn.discordapp.com/attachments/1018872903292436530/1019289126979248259/Record.jpg)
+ 1 Clic on this button
+ 2 & 2* After, choose ``New Editor Window (PIE)`` or if you have the button like 2*, just clic and tada! YOU RECORD!


## Space Kiwi Studio
<marteel.francois@spacekiwi.studio> support : <support@spacekiwi.studio> or https://github.com/Space-Kiwi-Studio/MultipointsCameraRecorder/discussions/categories/support
