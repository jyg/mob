# mob
Generating MobMuPlat interface files (.mmp) directly from *.pd patches

MobMuPlat (see http://danieliglesia.com/mobmuplat/) is an app that lets you run pd patches on iOS / Android mobile devices.
In order to create GUIs, it comes with a java app (MobMuPlat Editor) that generates .mmp files.

[mob] lets you build those .mmp files directly from the patch you want to use on mobile platform, without the need of using MobMuPlat Editor. What you get should be what you see !

[mob] maps native pd-guis (hsv, vsl, hradio, vradio, toggle, bang) and text comments into mmp.widgets in the .mmp file.
It comes with enhanced guis (mob/hfader, mob/button, and - coming soon - knob / xy-slider) that are also converted to mmp.widgets.

Requirements :
- pd >= 0.50 on development platform
- mrpeach/binfile external
- iemguts + iemlib external libs

Note that current version of pd on MobMuPlat is 0.48-0.
[mob] comes with a RJDJ-based preset saving mechanism.
