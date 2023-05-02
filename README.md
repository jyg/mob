# mob 
(develop branch, version 0.3)
### PureData multitouch widgets + fast exporting of pd patches to mobile platform app (MobMuPlat)
  <p align="center"> <img src="https://raw.githubusercontent.com/jyg/mob/master/doc/mob-scratch-demo.png" alt="mob scratch demo" ></p>

### Abstract
**mob** achieves two goals : 

* an **helper** for quickly creating **MobMuPlat "apps"**;
* a collection of special **multitouch gui-widgets**.

## 1) Another way to create MobMuPlat apps

MobMuPlat (see http://danieliglesia.com/mobmuplat/) is an app that let you run pd patches on iOS / Android mobile devices.
In order to create GUIs, you can use the MobMuPlat native mode **or** use a special java app (**MobMuPlat Editor**) for designing your interface files (*.mmp).

The [mob] helper is aimed to replace the javascript MobMuPlat Editor for creating on-the-fly MobMuPlat apps from within puredata.
It lets you build those .mmp files directly from the patch you want to use on mobile platform, in one click, without the need of using MobMuPlat Editor. What you get should be what you see !

**Why not use simply mobmuplat native mode ?**

Native mode is a special feature of MobMuPlat app that enables the direct rendering of your pd patches with all native guis (vsl, hsl, tgl, etc..), but doesn't let you access to MobMuPlat enhanced gui features (grid, xy slider, xy multitouch, lcd panel, etc..), nor use of multiple pages. 

**With [mob] you can access to most of those features**, in a faster way than with the MobMuPlat Java Editor. Furthermore, if you think your widgets are displayed too small or too big on your target mobile device, **you can easily adjust the scale factor** (hard zooming).

[mob] converts native pd-guis (hsv, vsl, hradio, vradio, toggle, bang, cnv, array) and text comments into mmp.widgets in the .mmp file.
It comes with enhanced guis (vfader, hfader, button, xy_slider, jog, menu, xy_multitouch, knob, lcd) that are also converted to mmp.widgets.

[mob] includes a RJDJ-based preset saving mechanism (work in progress).

**Requirements :**
- pd >= 0.52 on development platform
- **iemguts** & **iemlib** external lib
- (optional) for multitouch support : https://github.com/jyg/multitouch + hidio

Note that current version of pd on MobMuPlat-Android is 0.51-3.

**Installation**

Download from https://github.com/jyg/mob/releases/tag/mob-0.3 , uncompress and copy **mob** folder into the externals directory of your desktop puredata installation (pd >= 0.52).

**Usage**

Have first a look at patches in **tutorial** and **example** folders. 

Edit the patch you want to export to MobMuPlat with pd >= 0.52. **Add the [mob] object on it**. Check the background color, the layout size, the number of pages, etc.. You can adjust the scale factor with the "zoom" slider.

All the native pd GUIs will be exported. They must interact with the patch only with their rcv and snd channel names. Don't use wired connections with any guis.

Save your patch. Click on red button, [**mob**] adds some stuff in the current patch and creates a new graphical interface file, with the same name of the patch but with the *.mmp extension. Copy both *.pd and *.mmp files to your mobile device (MobMuPlat directory). 

That's all !

See the "examples" folder for more infos.

## 2) A collection of special multitouch gui-widgets
The gui-widgets include faders, xy slider, knob, jog, menu, lcd widgets. It requires pd 0.51 + iemguts + iemlib external libs. You can use it as an extension library for your existing desktop pd-patches.

