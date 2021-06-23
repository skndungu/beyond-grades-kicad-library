# beyond-grades-kicad-library
- This repo contains libraries used by beyond-grades in course developments, add it if you are following any tutorial 
- It asssumes the latest KiCad Version (at the time v5.1.6)
Following patterns set by KiCad's built-in libraries and [digikey-kicad-library](https://github.com/Digi-Key/digikey-kicad-library).

# Installation
1. Change to the directory you want the library folder to be in, ex: `cd kicad-libraries`
2. `git clone https://github.com/skndungu/beyond-grades-kicad-library` This creates & fills the beyond-grades-kicad-library folder.
3. Open KiCad
4. Menu `Preferences > Manage Symbol Libraries` click on the "Add existing library to table" button (looks like a folder), navigate to the `beyond-grades-kicad-library/beyond-grades-symbols` folder; select all libraries and click "Open".
5. Menu `Preferences > Manage Footprint Libraries` click on the "Add existing library to table" button (looks like a folder), navigate to the `beyond-grades-kicad-library/beyond-grades-footprints.pretty` folder; click "OK".
6. Menu `Preferences > Configure Paths`, `+` to add a new path, Name = `GCL_KICAD_3D`, Path = folder above + `/beyond-grades-kicad-library/beyond-grades-packages3d`
7. (Note: If you are just using the library & not making changes to it, the `beyond-grades-assets` directory can be deleted to save file space. It contains original design files used in creating some of the library parts.)

# Creating New Parts
- Thoroughly search KiCad's own library before adding a part to ours.
- Don't re-create or copy parts from digikey-kicad-library, assume it is already installed; [instructions here](https://forum.digikey.com/t/importing-the-digi-key-kicad-library-into-kicad-5-0-0/4075).

## Naming of Symbols, Footprints & 3d models
- Establish whether the part is an IC, Connector, Microphone, Oscillator or ...
- Next on `beyond-grades-kicad-library/beyond-grades-symbols` check the specific category as defined EX. for ICs `GCL_Integrated-Circuits`
- Select this as the library you want to add a new symbol to, also be keen on the ref designator,EX. ICs use `U` Here is a list on [ref designators](https://en.wikipedia.org/wiki/Reference_designator) or here [ref designators-by-kicad](https://klc.kicad.org/symbol/s6/s6.1/)to be sure on the designator to use 
- Add the new Symbol and name it in regards to the manufactures part number EX. BQ25125
- Other attributes to include, Footrprint(you need to asscociate with a created footprint - follow same naming procedure), Datasheet Link, Description(not very important)

---------------------------------------------------------------------------------
---------------------------------------------------------------------------------

- Parts improved from Digikey library, such as by adding 3D models, can be added.
- Refer to the [tutorial on making footprints](https://forum.kicad.info/t/tutorial-how-to-make-a-footprint-in-kicad-5-1-x-from-scratch/11092) on kicad.info
- Use maximum part dimensions for footprint CrtYd layers & 3D models
- Follow the [KiCad Library Convention (KLC)](https://kicad-pcb.org/libraries/klc/). In particular, note:
  - [Symbol](https://kicad-pcb.org/libraries/klc/#_symbol_guidelines):
    - Pin Electrical type per [KLC S4.4](https://kicad-pcb.org/libraries/klc/S4.4/), with more details described in [this forum post](https://forum.kicad.info/t/electrical-type-of-schematic-symbol-pins/9439).
  - [Footprint](https://kicad-pcb.org/libraries/klc/#_footprint_guidelines):
    - Silk layer per [KLC F5.1](https://kicad-pcb.org/libraries/klc/F5.1/)
    - Fab layer per [KLC F5.2](https://kicad-pcb.org/libraries/klc/F5.2/)
    - Paste layer: follow any Datasheet suggestions, otherwise match pads. See [KLC F6.3](https://kicad-pcb.org/libraries/klc/F6.3/) for recommended method to implement special paste requirements.
    - Courtyard per [KLC F5.3](https://kicad-pcb.org/libraries/klc/F5.3/)
  - [3D Model](https://kicad-pcb.org/libraries/klc/#_3d_model_guidelines):
    - ignore KLC M1.1: we want 3D models for all parts, and take vendor or other 3rd party models as needed
    - use [FreeCAD](https://www.freecadweb.org) + the [StepUp plugin](https://kicad-pcb.org/external-tools/stepup/) to satisfy M2.1 & M2.2

### Sources for Part models
Library | Free | Register | KiCad support | 3D
------- | ---- | -------- | ------------- | --
[SnapEDA](https://www.snapeda.com) | Y | Y | [Yes](https://www.snapeda.com/kicad/) + [plugin](https://blog.snapeda.com/2020/09/09/introducing-the-snapeda-kicad-plugin/) | Y
[Octopart](https://octopart.com) | Y | Y | Y | ?
[Ultra Librarian](https://www.ultralibrarian.com) | Y | Y | Y, good | y
[EasyEDA](https://easyeda.com) | ? | ? | ? | ?
[Component Search Engine](https://componentsearchengine.com) | Y | Y | Y | Y
[GrabCAD](https://grabcad.com/library?page=1&time=all_time&sort=most_downloaded&categories=electrical) | Y | ? | ? | only; few but high quality
[KCS KiCad](http://smisioto.no-ip.org/elettronica/kicad/kicad-en.htm) | Y | N | Y | Y
