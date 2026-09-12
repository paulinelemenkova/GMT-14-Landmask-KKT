# GMT Landmask KKT — Land/Water Mask Grid Script

A GMT (Generic Mapping Tools) shell script demonstrating construction of a land/water mask grid from GSHHG shoreline data. Using grdlandmask, land nodes are flagged and ocean nodes set to NaN, producing a binary mask that isolates marine areas; the mask is then rendered over a relief basemap. The example covers the Kuril-Kamchatka Trench area. The script has been used in the author's marine-geophysical and cartographic mapping workflows.

## What the script does

- extracts a regional relief subset (grdcut)
- generates a colour palette for the ocean (makecpt)
- builds a land/water mask at a chosen resolution with land = 1 and water = NaN (grdlandmask -N1/NaN)
- renders the mask with illumination (grdimage)
- overlays shoreline contours (grdcontour), grid, scale bar and directional rose (psbasemap)
- adds the GMT logo (logo)
- exports to raster (psconvert) at high resolution

## Data sources

Shorelines from GSHHG via GMT; relief from ETOPO1 (1 arc-minute).

## Requirements

- GMT 6.x (Generic Mapping Tools): https://www.generic-mapping-tools.org
- A POSIX shell (bash/sh)
- The GSHHG shoreline dataset and an ETOPO1 relief grid available locally

## Usage

Adjust the -R region and -I mask resolution at the top of the script, then run:

    bash GMT-14-Landmask-JM-KKT.sh

The script writes a PostScript file and converts it to a raster image (JPG/PNG) via psconvert.

## Author and citation

Polina Lemenkova
ORCID: https://orcid.org/0000-0002-5759-1089

This script supports figures in the author's marine-geophysical and cartographic papers; please cite the specific article a given figure appears in. The full publication list is available via the ORCID record above.

## License

See the LICENSE file in this repository.
