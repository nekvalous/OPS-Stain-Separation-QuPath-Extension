--------------------
OPS STAIN SEPARATION
--------------------
QuPath extension




1. VERSION AND AUTHOR

Version: 1.9.1
Name: © Nektarios Valous
Website: https://nekvalous.github.io



2. INSTALLATION

Requirement: QuPath 0.7.0

1. Download qupath-extension-ops-stain-separation.jar.
2. Close QuPath and remove older or duplicate OPS QuPath extension JARs
   from your QuPath user directory's extensions folder.
3. Open QuPath and drag the new JAR onto its main window.
4. Accept installation. Select a user directory if prompted.
5. Restart QuPath.
6. Open Extensions > OPS Stain Separation > Separate Stains...




3. HOW TO USE THE EXTENSION


3.1 Open an image and choose the processing area

Open a color brightfield image or whole slide in QuPath. Images must have 8-bit
color channels. Keep the source image open until processing finishes.

Under Process, choose:

- Whole image: process the current image plane.
- Selected annotations: process only the area annotations you select in
  QuPath's Annotations panel. Select one or more annotations on the current
  image plane. Point and line annotations cannot be used as processing areas.


3.2 Select the stains

Check exactly one combination:

- H + E
- Blue + Brown
- Blue + Red
- Blue + Green
- Blue + Brown + Red

A combination must be selected before processing can continue.


3.3 Choose the mode

Automated (Macenko)

This is the default mode. Select the stain combination and leave the
automated settings at their defaults for a first run. Settings remain
expanded in the form.

Manual

1. Choose Manual and select the stain combination.
2. Click the first Pick button, such as Pick H or Pick Blue.
3. Click one representative pixel of that stain in the source image.
   The cursor becomes a crosshair and advances to the next stain.
4. Click one pixel for each remaining stain in the displayed order.

Use one click per stain: two clicks for a pair or three for Blue + Brown + Red.
When processing selected annotations, pick the pixels inside any of those
areas. You do not need to repeat the picks for each annotation.

Choose distinct stained pixels and avoid pure black, white background, and
strongly mixed colors. No sampling annotation is created. Press Escape to
stop picking. To replace a sample, click its Pick button and choose again.
Pick the stains again after changing the selected areas, image plane,
processing resolution, or stain combination.


3.4 Set the processing and appearance options

- Downsample: choose 1 for native resolution. Larger values produce smaller
  output images and reduce processing time and memory or disk use.
- CPU threads: leave Automatic selected, or choose a maximum thread count.
  Choose 1 to use a single thread. Automatic uses up to eight threads,
  depending on QuPath settings, available processors, memory, and image size.
- Challenging case: check this when the image is difficult to separate.
  It is available below the automated settings or the manual picking controls.
- Stain pseudocolor: check this to display stain colors on a white background.
  Leave it unchecked for grayscale output.
- Enhance output: optionally check this to make faint stains more visible.
  It is unchecked by default and applies to displayed and saved images.

The appearance options are available in both modes, including Challenging
case. For large slides, start with a smaller selected area or a larger
Downsample value. Widely separated annotations can produce a large output
image. Increase Downsample or process smaller groups if needed.


3.5 Run the separation

Choose an Output option, then click Separate:

Open in QuPath

This is the default. The stain images appear over the original image in
the main viewer. No output folder is required and no images are saved
automatically.


Save images and open

Choose an existing, writable folder. Each run creates a new subfolder with
two or three pyramidal OME-TIFF images, one per stain. These images also
open in QuPath. No JSON or other sidecar file is produced.

The form stays open after processing so that you can adjust the settings
and run again. Cancel stops an active run and removes incomplete saved
output. Close closes the form when no run is active.


3.6 View and save results

For Open in QuPath, use the OPS results panel:

- Stain checkboxes: toggle each stain overlay on or off.
- Opacity: adjust the visibility of the overlays over the original image.
- Original only: switch all stain overlays off.
- Run list: return to an earlier completed result.
- Save images...: save every stain in the selected run as a separate
  pyramidal OME-TIFF without repeating the separation.
- Remove: discard the selected result from memory.

Pan, zoom, and rotate the image as usual. Annotation overlays cover only
the processed areas. Gaps and holes show the original image underneath.
Overlays are temporarily hidden while you pick stain pixels.

Saved images retain the selected grayscale or pseudocolor appearance,
optional enhancement, and processing resolution. Overlay visibility,
opacity, and viewer zoom do not change the saved images. Excluded areas
are black in grayscale files or white in pseudocolor files.

Closing the separation form leaves completed results available. Save them
before closing or replacing the source image, closing its viewer, or
exiting QuPath. Unsaved results are released when any of these occurs.

About and Citations is available from the extension menu and the form.




4. CITATIONS

Please cite both OPS papers when using this extension:

1. Valous, N. A., et al. (2025).
   Computational workflows for natural and biomedical image processing
   based on hypercomplex algebras.
   Patterns, 6(11), 101388.
   https://doi.org/10.1016/j.patter.2025.101388
   https://www.cell.com/patterns/fulltext/S2666-3899(25)00236-3

2. Valous, N. A., et al. (2026).
   Protocol for natural and biomedical image processing in the hypercomplex
   domain using the 2D orthogonal planes split.
   STAR Protocols, 7(2), 104548.
   https://doi.org/10.1016/j.xpro.2026.104548
   https://www.cell.com/star-protocols/fulltext/S2666-1667(26)00201-7

Additional references:

3. Macenko, M., et al. (2009).
   A method for normalizing histology slides for quantitative analysis.
   IEEE International Symposium on Biomedical Imaging: From Nano to Macro,
   1107–1110.
   https://doi.org/10.1109/ISBI.2009.5193250

5. Bankhead, P., et al. (2017).
   QuPath: Open source software for digital pathology image analysis.
   Scientific Reports, 7, 16878.
   https://doi.org/10.1038/s41598-017-17204-5