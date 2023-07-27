# Zenestra
The Zenestra is a modular keyboard case which allows you to easily add, replace and design your own parts.

> **Warning**
> The Zenestra project is currently in pre-alpha status. Prototypes for the case are in production, and PCBs for the project are still in development. These files are being made available for open source development purposes, so that tooling can be developed. If you are a customer, please hold off until the official project reveal before developing or ordering things based off of these files.

## Warranty and license
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

This work is licensed under the Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License. To view a copy of this license, visit http://creativecommons.org/licenses/by-nc-sa/4.0/.

These files are available for non-commercial use only. You explicitly have permission to make objects with these files for yourself, friends, family and coworkers. If you'd like to sell objects made from these files, please [get in touch](mailto:support@splitkb.com).

## Files
The Zenestra project has the following files available:

### Kicad template project
You can place the `zenestra-template` folder into your own Kicad installation's template folder. Please see the [Kicad template documentation](https://docs.kicad.org/6.0/en/kicad/kicad.html#template-locations) on where these files can be placed.

> **Note**
> The template requires Kicad version 7.0.0 or higher.

If you then Choose **File** > **New Project** > **New Project from Template**, you'll be able to select the newly added template to get a head start when creating PCBs for your new case.

### Design files
The following projections are available in the `projections` folder which you can import into Kicad, Inkscape, LibreCAD and many other tools to design case parts with:

- `pcb-edge-cuts.dxf`: An outline of the PCB. You can import this into your PCB design program to use as edge cuts. It's simply a 150x100mm rectangle with rounded corners.
- `pcb-mounting-holes.dxf`: The mounting holes to use for the PCB. You can import this into your PCB design program in a layer such as User.Drawings or Eco1, to put mounting holes at the locations marked by the circles.
- `pcb-keepout.dxf`: An outline of areas where the PCB and tripod thread can touch the PCB. You can import this into your PCB design program to use as B.Courtyard, so you can avoid placing components at these spots on the bottom of your board.
- `top-shallow.dxf`: An outline of the PCB with mounting holes you can use as a template for top layers that cover only the PCB, but not the rims of the enclosure.
- `top-wide.dxf`: An outline of the case with mounting holes you can use as a template for top layers that cover both the PCB and the portion of the case up to the chamfered edges.
- `top-full.dxf`: An outline of the full case, handy to use when designing a foam cutout for a carry case and such.
- `inside.dxf`: An outline of the inner profile you can use to design an inlay for the case, such as a sound dampening mat. It has an offset of 0.5mm all around the wall to account for the inside fillet, and there's a cutout for the tripod mounting hole.
- `bottom.dxf`: A projection of the bottom showing the case outline, mounting holes and bolt recesses, SKUF rubber feet recesses and the tripod mounting hole.
- `emblem.dxf`: A projection of the case's emblem.

Do mind that all the files do not include kerf. If using it with a laser cutting service, inquire for the kerf setting to use. If kerf is required, you may need to modify your files, or ask your supplier to modify them for you.

## Dimension Guide
Here's some guidance on important dimensions:

- The bare **case** is 153.2mm wide, 103.2mm tall and 5.7mm deep, excluding bumpons and any installed parts.
    - With bumpons, the depth is 7.2mm.
    - The top of the PCB sits flush with the top of the case, barring allowable tolerances.
    - Any bolts used may protrude from the top and/or bottom of the case.
    - Switches, keycaps, optional case parts and other installed components will change the height of the final assembled keyboard.
- The **PCB** should be 150mm wide by 100mm tall, and 1.6mm thick.
- The **corner** fillets of the PCB should have a radius of 3.50mm.
- There’s **2.2mm of clearance below the PCB**, which is enough for Kailh Hotswap Sockets (usually the tallest component on the bottom of the board).
    - It’s likely not enough for a LiPo battery or some bulkier components. You can choose to add cutouts to facilitate this, if you have enough space left besides your layout.
- There are **ten mounting holes** distributed along the edges of the case.
    - Mounting holes are always positioned 3.5mm away from an edge.
    - Given that the very top left would be coordinate X0 Y0, and that the very bottom right would be coordinate X150 Y100, the mounting holes are positioned at:
        - **Top left**: X3.50 Y3.50
        - **Top second left**: X51.167 Y3.50
        - **Top second right**: X98.833 Y3.50
        - **Top right**: X146.50 Y3.50
        - **Center left**: X3.50 Y50.00
        - **Center right**: X146.50 Y50
        - **Bottom left**: X3.50 Y96.50
        - **Bottom second left**: X51.167 Y96.50
        - **Bottom second right**: X98.833 Y96.50
        - **Bottom right**: X146.50 Y96.50
    - The mounting hole recesses on the bottom of the case are 0.7mm deep.
- The **SKUF feet** recesses are 0.5mm deep. The feet then protrude 1.5mm from the bottom of the case, including the recess.
- The **tripod mounting hole** is at the absolute center of the board (at X75 Y50). A diameter of 6.25mm should be kept clear above this area, as the tripod’s threading can move through the bottom of the case.

## PCB Design Considerations
These are helpful tips to keep in mind when designing your own PCB for the Zenestra case:

- **Connector placement**: Connectors (USB, TRRS) should be as near to the PCB as possible to allow for cables to reach the connectors properly. The case wall is 1.8mm thick, and there’s a tolerance of 0.1mm between the PCB and the case all around its perimeter, so connectors will need to clear a distance of between 1.8 to 2.0mm to the edge of the case.
- **Keeping clear**: There are various features of the case you need to take into account when placing components:
    - **Mounting holes**: The top and bottom of the PCB should be kept clear in a quarter or half-circle of 3.6mm around the centerpoint of each mounting hole, extending straight toward the edge of the case. The PCB rests on these mounting holes, and bolts will go through these holes.
    - **Tripod mounting hole**: The tripod mounting hole is at the absolute center of the board (at X75 Y50). A diameter of 6.25mm should be kept clear above this area, as the tripod’s threading can move through the bottom of the case.
- **Mounting holes are optional**: You do not have to use all mounting holes. You can, for example, choose to use only the corner mounting holes for a cleaner look. I’d recommend to use at least two opposing holes, and using at least four mounting holes is preferable.
- **Mounting holes are fully threaded**: You can insert bolts from the bottom of the case, too. If you use bolts with low heads (low profile bolts go down to 1.65mm tall heads), you can fit them while still having enough clearance from the SKUF rubber bumpons. You can then tighten the assembly with nuts or threaded inserts in a top component.
- **Symmetry**: The case is functionally fully symmetrical. There’s an accent at the front of the case, which you can rotate around to become the back of the case.
- **ESD protection**: Let one mounting point on the case have a conductive ring around it and connect it to GND. All mounting points can be conductive, but you should only connect one of them to GND as to prevent ground loops. Leave the other mounting points unconnected. You can pick the pad closest to the controller to wire to GND if it’s easier.
