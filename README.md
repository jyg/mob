# mob
### Custom PureData widgets + fast exporting of pd patches to mobile platform app (MobMuPlat)
  <p align="center"> <img src="https://raw.githubusercontent.com/jyg/mob/master/data/mob-scratch-demo.png" alt="mob scratch demo" width=600 height=300></p>

**MobMuPlat** (see http://danieliglesia.com/mobmuplat/) is an app that lets you run pd patches on iOS / Android mobile devices.
In order to create GUIs, it comes with a java app (**MobMuPlat Editor**) that you have to use for designing your interface files (*.mmp).

Alternatively, **[mob]** lets you build those .mmp files directly from the patch you want to use on mobile platform, in one click, without the need of using MobMuPlat Editor. What you get should be what you see !

**Why not use simply mobmuplat native mode ?**

Native mode is a special feature of MobMuPlat app that enables the direct rendering of your pd patches with all native guis (vsl, hsl, tgl, etc..), but doesn't let you access to MobMuPlat enhanced gui features (grid, xy slider, xy multitouch, lcd panel, etc..), nor use of multiple pages. 

**With [mob] you can access to most of those features**, in a faster way than with the MobMuPlat Java Editor. Furthermore, if you think your widgets are displayed too small or too big on your target mobile device, you can easily adjust the scale factor (hard zooming).

[mob] maps native pd-guis (hsv, vsl, hradio, vradio, toggle, bang, cnv, array) and text comments into mmp.widgets in the .mmp file.
It comes with enhanced guis (vfader, hfader, button, xy_slider, jog, menu, xy_nultitouch, knob) that are also converted to mmp.widgets.

[mob] includes a RJDJ-based preset saving mechanism.

**Requirements :**
- pd >= 0.50 on development platform
- mrpeach/binfile external
- iemguts + iemlib external libs
- (optional) for multitouch support : https://github.com/jyg/multitouch + hidio

Note that current version of pd on MobMuPlat is 0.48-0. **Don'use in your patch : [savestate], [pdcontrol], [slop~] ; beware of [declare]'s different behaviour ; [value] has no second inlet, if you need it, use [mob/value] instead.**

## Instructions

**Installation**

Copy this folder (named 'mob') into the externals directory of your desktop puredata installation (pd >= 0.50).

Copy the content of subfolder named 'MobMuPlat_target_folder' into the MobMuPlat directory on your mobile device.

**Usage**

Have first a look at **mob-help.pd**

Edit the patch you want to export to MobMuPlat with pd >= 0.50. **Add the [mob] object on it**. Check the background color, the layout size, the number of pages, etc.. You can adjust the scale factor with the "zoom" slider.

All the native pd GUIs will be exported. They must interact with the patch only with their rcv and snd channel names (wired connections not tested).

Save your patch. Click on red button, [mob] creates dynamically the needed wrappers in the patch. The default name for the generated graphical interface file is the name of the patch but with the *.mmp extension. Copy both *.pd and *.mmp files to your mobile device (MobMuPlat directory). 

That's all !

See the "examples" folder for more infos.
