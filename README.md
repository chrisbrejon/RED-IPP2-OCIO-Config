# RED-IPP2-OCIO-Config
Based on the [RED IPP2 Output Presets](https://www.red.com/download/ipp2-output-presets) I have created a minimal OCIO config of RED IPP2 for full CG projects. This is the **RED Image Processing Pipeline** in its most minimalistic and simple form:
* Inputs (textures) are in "linear"
* Rendering and Nuke working space are also in "linear"
* View Transform is for Rec.1886 display

There is no need to go wide gamut or do anything complex to **craft beautiful images**. Enjoy!

# Image Examples
<p>
    <img ![hue_sweep_red_ipp2] width="144" height="81" src="https://github.com/user-attachments/assets/0dfa6ad7-d4db-416e-bc92-fede1a4cd9f4" >  
    <img ![photographic_scene_red_ipp2] width="144" height="81" src="https://github.com/user-attachments/assets/b6df973b-91a1-4ab2-acc7-a442dc6ba3d8" >
    <img ![light_sabers_red_ipp2] width="144" height="81" src="https://github.com/user-attachments/assets/af99c0f8-8cef-42a2-a9cc-0aa22d00fe7d" >
    <img ![lego_sailors_red_ipp2] width="144" height="81" src="https://github.com/user-attachments/assets/7caeb8ab-23cf-4206-a889-87255b1afed0" >
    <img ![louise_concert_red_ipp2] width="144" height="81" src="https://github.com/user-attachments/assets/06f2dc8a-0ad2-40b1-9785-266ec69c8f51" >
</p>

Original files (encoded in "linear-AP0") are available [here](https://www.dropbox.com/scl/fo/fhzx0bcwcjylek1oz7kjc/ACGfmi0EHeufVOQPZLvvk7w?rlkey=53cp61955hbns8x46j6cf8k55&e=1&dl=0).

# About the config
* Reference color space is XYZ which is the base of all colourimetry
* All matrixes have been generated using [colour-science](https://www.colour-science.org/apps/) with CAT02
* "linear" stands for "linear_bt.709"
* "cineonlog_rec709" can be used for a matte-painting workflow in Photoshop
* "log3g10_redwg" is the shaper space. It can be used for color timing and some log operations (such as sharpen)
* Substance_painter roles were set following [this page](https://mrlixm.github.io/blog/substance-painter-color-management/)
* An inverse of the View Transform has been provided even though it is not perfect
* One may easily add several colorspaces or displays for HDR output if needed (such as "p3_d65_pq")

# Looks
* 32 looks from the [RED Creative LUT Kit](https://www.red.com/download/red-creative-lut-kit) have been uploaded
* The use of Looks is highly recommended with RED IPP2
* To use one of the looks, you need to combine it with a View. Like this for instance:

```- !<View> {name: RED IPP2 Caustic, colorspace: RED IPP2 - Rec.709 - 2.4 Gamma, looks: RED_CAUSTIC}```

# Other available Color Management Workflows
| Name                                                                                             | Author               | Release date |              Observations                             |
|:---:                                                                                             |         :---:        |      :---:   |                 :---:                                 |
| [ARRI K1S1](https://www.arri.com/en/learn-help/learn-help-camera-system/tools/lut-generator)     | Harald Brendel       | 2011         | THE most used LUT on the planet (ARRI Alexa workflow) |
| [Filmic](https://github.com/sobotka/filmic-blender)                                              | Troy Sobotka         | 2017         | Original Blender Color Management used on [this movie](https://www.youtube.com/watch?v=uf3ALGKgpGU) |
| [ACES](https://github.com/AcademySoftwareFoundation/OpenColorIO-Config-ACES/releases)            | AMPAS                | 2021         | Color Encoding System developed by the Academy |
| [Sony Venice](https://sonycine.com/resources/luts/)                                              | Sony / Picture Shop  | 2022         | LUT files made in partnership with [Picture Shop](https://www.pictureshop.com/) |
| [ARRI Reveal](https://www.arri.com/en/learn-help/learn-help-camera-system/tools/lut-generator)   | Sean Cooper          | 2022         | The new ARRI Alexa35 workflow described [here](https://www.youtube.com/watch?v=s_RXjVeC_7s) |
| [Tony](https://github.com/h3r2tic/tony-mc-mapface)                                     | Tomasz Stachowiak    | 2023         | A cool-headed display transform |
| [AgX Blender](https://github.com/EaryChow/AgX)                                                   | Eary Chow            | 2023         | Blender Color Management used on [this video game](https://www.youtube.com/watch?v=mVjBRZqajYY) |
| [TCAMv3](https://www.filmlight.ltd.uk/support/customer-login/colourspaces/colourspaces.php)      | Daniele Siragusano   | 2024         | Baselight Color Management Workflow explained [here](https://youtu.be/DL4n6LErMbw?t=325) |
| [AgX SB2383](https://github.com/sobotka/SB2383-Configuration)                                    | Troy Sobotka         | 2024         | Minimal AgX OCIO Config using Linear BT.709 |
| [JP-2499](https://github.com/jedypod/JP2499)                                                     | JP Zambrano          | 2024         | A popular picture formation pipeline described [here](https://www.liftgammagain.com/forum/index.php?threads/2499-drt-an-alternative-picture-formation-pipeline.18639/) |
| [Open DRT](https://github.com/jedypod/open-display-transform)                                    | Jed Smith            | 2024         | State-of-the-art Color Management Workflow |
