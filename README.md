# GeoVisualisation


## Paraview

The file `final_poster.pvsm` consist the final visualization of the earth with the trajectories of cyclones. This state can be loaded in paraview via  `Load state`. 

In the folder `paraview_data` are the vtp files that we used to visualize the points, the glyphs for the maximum radius, the colors and cone-glyph for the starting point.

`..._cyclones.vtp` files consists:
- The data for the points (the locations of the eye): `Representations: Points` in paraview
- The `Radius_max_winds`: these values are used for the coloring of the glyphs (the actual radius)
- The `Scaled Radius_max_wind`: The scaled radius values, which gave the right scale for our unit sphere. We scaled the actual radius value (radius max winds) with the radius of the earth.
The `Normals`: normals are used for the glyphs to be fitted on the earth instead of pointed through the earth.
- Also information about `Category` and `Max Speed` per cyclone location.

To visualize the cyclones with the radius, we have a separate glyph object attached to the file.
Here we changed `Glyph type` to `2D Glyph` and `Circle`, the `Orientation Array` to the `Normals` with an rotation of 90 degree to Y (second column), the `Scale Array` to the `Scaled radius_max_wind` and the `Scale Factor` to 1, and the `Color` with the `Radius_max_winds`


`...arrow.vtp` files consist:
- The `Orientation`: the vector of the first point to the second point for the starting point cone glyph.

To visualize this we also attached the glyph object to this files and changed `Glyph type` to `Cone`, the `Orientation Array` to the `Orientation` and the `Scale Factor` to 0.026.


Some extra information about the file name: `NA_nr_0_year_0_....`:
- NA = cyclones around the North Atlantic
- nr_0 = the first file from the STORM data collection, noted with 0 in the file name of the data collection STORM