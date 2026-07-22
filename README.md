ComfyUI Render Pass Setup - N-Panel Edition  (Blender 5.1+, fallbacks for 4.x)
==============================================================================
SEJ Productions - portable per-project setup script.
Drop into any project: Scripting tab > Open > Run Script.
Safe to re-run; it rebuilds its own panel, layers and nodes cleanly.

HOW TO USE
  1. Run this script once (Scripting tab > Run Script).
  2. In the 3D Viewport press N to open the sidebar.
  3. Find the "ComfyUI Passes" tab.
  4. Tick the passes you want, pick an output folder, click
     "Build / Rebuild Passes", then render (F12 still, Ctrl+F12 anim).

WHAT THE PANEL OFFERS
  - Checkboxes: Clay / Depth / Outline / Alpha (pick any combination)
  - Output directory (folder picker; default //render_passes/ next to
    the .blend)
  - Outline thickness slider
  - Auto-MP4 toggle (converts PNG sequences after Ctrl+F12 renders)
  - "Open Output Folder" button

THE PASSES (unchanged from the original script)
  Clay_Pass    - flat grey material override           (8-bit RGB PNG)
  Depth_Pass   - Depth > Invert > Normalize > Curves   (16-bit BW PNG)
  Outline_Pass - white Freestyle lines on black        (8-bit RGB PNG)
  Alpha        - white subject matte on black, taken from the clay
                 layer's alpha (no extra render time; if Alpha is ticked
                 without Clay, the clay layer still renders silently to
                 supply the matte)

THINGS TO KNOW
  - Switches the engine to EEVEE if on Workbench (Freestyle needs it).
  - Disables every other view layer so only your ticked passes render.
  - REPLACES the scene's compositor node tree when you click Build.
  - Panel + MP4 handler last one Blender session; re-run this script
    after restarting Blender. Your tick/folder choices are saved in
    the .blend and come back automatically.
  - Depth uses Normalize (re-scales per frame). If depth videos "pulse"
    during big distance changes, ask Claude for the fixed-range variant.

    You have both options to either drag script into blender script 
    Or Install via addons in the preferences 
