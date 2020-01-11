# mob
Generating MobMuPlat interface files (.mmp) directly from *.pd patches

MobMuPlat (see http://danieliglesia.com/mobmuplat/) is an app that lets you run pd patches on iOS / Android mobile devices.
In order to create GUIs, it comes with a java app (MobMuPlat Editor) that generates .mmp files.

[mob] lets you build those .mmp files directly from the patch you want to use on mobile platform, without the need of using MobMuPlat Editor. What you get should be what you see !

**Why not use simply mobmuplat native mode ?**

Native mode directly renders your pd patches but doesn't let you access to MobMuPlat enhanced gui features (grid, xy, xy multitouch, lcd panel, etc..), nor use of multiple pages. With [mob] you can, in a faster way than when using the MobMuPlat Java Editor.

[mob] maps native pd-guis (hsv, vsl, hradio, vradio, toggle, bang) and text comments into mmp.widgets in the .mmp file.
It comes with enhanced guis (mob/hfader, mob/button, mob/xy_slider, and, coming soon, mob/knob ...) that are also converted to mmp.widgets.

[mob] comes with a RJDJ-based preset saving mechanism.

**Requirements :**
- pd >= 0.50 on development platform
- mrpeach/binfile external
- iemguts + iemlib external libs

Note that current version of pd on MobMuPlat is 0.48-0.

## Instructions

**Installation**

Copy this folder (named 'mob') into the externals directory of your desktop puredata installation (pd >= 0.50).

Copy the content of subfolder named 'MobMuPlat_target_folder' into the MobMuPlat directory on your mobile device.

**Usage**

Edit the patch you want to export to MobMuPlat with pd >= 0.50. Add the [mob] object on it. Check the background color, the layout size, the number of pages, etc..

All the native pd GUIs will be exported. They must interact with the patch only with their rcv and snd channel names (wired connections not tested).

Save your patch. Click on red button, [mob] creates dynamically the needed wrappers in the patch. The name for the generated graphical interface file is the name of the patch but with the *.mmp extension. Copy both *.pd and *.mmp files to your mobile device (MobMuPlat directory). 

That's all !
