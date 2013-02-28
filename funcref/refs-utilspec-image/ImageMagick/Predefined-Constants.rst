预定义的常量
=======================

The constants below are defined by this extension, and will only be available when the extension has either been compiled into PHP or dynamically loaded at runtime.

COLOR_* constants
Colortype constants. These constants are mainly used with ImagickPixel.

imagick::COLOR_BLACK (integer)
Black color
imagick::COLOR_BLUE (integer)
Blue color
imagick::COLOR_CYAN (integer)
Cyan color
imagick::COLOR_GREEN (integer)
Green color
imagick::COLOR_RED (integer)
Red color
imagick::COLOR_YELLOW (integer)
Yellow color
imagick::COLOR_MAGENTA (integer)
Magenta color
imagick::COLOR_OPACITY (integer)
Color's opacity
imagick::COLOR_ALPHA (integer)
Color's alpha
imagick::COLOR_FUZZ (integer)
Color's fuzz
DISPOSE constants
Dispose type constants

imagick::DISPOSE_UNRECOGNIZED (integer)
Unrecognized dispose type
imagick::DISPOSE_UNDEFINED (integer)
Undefined dispose type
imagick::DISPOSE_NONE (integer)
No dispose type defined
imagick::DISPOSE_BACKGROUND (integer)
Dispose background
imagick::DISPOSE_PREVIOUS (integer)
Dispose previous
Composite Operator Constants
imagick::COMPOSITE_DEFAULT (integer)
The default composite operator
imagick::COMPOSITE_UNDEFINED (integer)
Undefined composite operator
imagick::COMPOSITE_NO (integer)
No composite operator defined
imagick::COMPOSITE_ADD (integer)
The result of image + image
imagick::COMPOSITE_ATOP (integer)
The result is the same shape as image, with composite image obscuring image where the image shapes overlap
imagick::COMPOSITE_BLEND (integer)
Blends the image
imagick::COMPOSITE_BUMPMAP (integer)
The same as COMPOSITE_MULTIPLY, except the source is converted to grayscale first.
imagick::COMPOSITE_CLEAR (integer)
Makes the target image transparent
imagick::COMPOSITE_COLORBURN (integer)
Darkens the destination image to reflect the source image
imagick::COMPOSITE_COLORDODGE (integer)
Brightens the destination image to reflect the source image
imagick::COMPOSITE_COLORIZE (integer)
Colorizes the target image using the composite image
imagick::COMPOSITE_COPYBLACK (integer)
Copies black from the source to target
imagick::COMPOSITE_COPYBLUE (integer)
Copies blue from the source to target
imagick::COMPOSITE_COPY (integer)
Copies the source image on the target image
imagick::COMPOSITE_COPYCYAN (integer)
Copies cyan from the source to target
imagick::COMPOSITE_COPYGREEN (integer)
Copies green from the source to target
imagick::COMPOSITE_COPYMAGENTA (integer)
Copies magenta from the source to target
imagick::COMPOSITE_COPYOPACITY (integer)
Copies opacity from the source to target
imagick::COMPOSITE_COPYRED (integer)
Copies red from the source to target
imagick::COMPOSITE_COPYYELLOW (integer)
Copies yellow from the source to target
imagick::COMPOSITE_DARKEN (integer)
Darkens the target image
imagick::COMPOSITE_DSTATOP (integer)
The part of the destination lying inside of the source is composited over the source and replaces the destination
imagick::COMPOSITE_DST (integer)
The target is left untouched
imagick::COMPOSITE_DSTIN (integer)
The parts inside the source replace the target
imagick::COMPOSITE_DSTOUT (integer)
The parts outside the source replace the target
imagick::COMPOSITE_DSTOVER (integer)
Target replaces the source
imagick::COMPOSITE_DIFFERENCE (integer)
Subtracts the darker of the two constituent colors from the lighter
imagick::COMPOSITE_DISPLACE (integer)
Shifts target image pixels as defined by the source
imagick::COMPOSITE_DISSOLVE (integer)
Dissolves the source in to the target
imagick::COMPOSITE_EXCLUSION (integer)
Produces an effect similar to that of imagick::COMPOSITE_DIFFERENCE, but appears as lower contrast
imagick::COMPOSITE_HARDLIGHT (integer)
Multiplies or screens the colors, dependent on the source color value
imagick::COMPOSITE_HUE (integer)
Modifies the hue of the target as defined by source
imagick::COMPOSITE_IN (integer)
Composites source into the target
imagick::COMPOSITE_LIGHTEN (integer)
Lightens the target as defined by source
imagick::COMPOSITE_LUMINIZE (integer)
Luminizes the target as defined by source
imagick::COMPOSITE_MINUS (integer)
Subtracts the source from the target
imagick::COMPOSITE_MODULATE (integer)
Modulates the target brightness, saturation and hue as defined by source
imagick::COMPOSITE_MULTIPLY (integer)
Multiplies the target to the source
imagick::COMPOSITE_OUT (integer)
Composites outer parts of the source on the target
imagick::COMPOSITE_OVER (integer)
Composites source over the target
imagick::COMPOSITE_OVERLAY (integer)
Overlays the source on the target
imagick::COMPOSITE_PLUS (integer)
Adds the source to the target
imagick::COMPOSITE_REPLACE (integer)
Replaces the target with the source
imagick::COMPOSITE_SATURATE (integer)
Saturates the target as defined by the source
imagick::COMPOSITE_SCREEN (integer)
The source and destination are complemented and then multiplied and then replace the destination
imagick::COMPOSITE_SOFTLIGHT (integer)
Darkens or lightens the colors, dependent on the source
imagick::COMPOSITE_SRCATOP (integer)
The part of the source lying inside of the destination is composited onto the destination
imagick::COMPOSITE_SRC (integer)
The source is copied to the destination
imagick::COMPOSITE_SRCIN (integer)
The part of the source lying inside of the destination replaces the destination
imagick::COMPOSITE_SRCOUT (integer)
The part of the source lying outside of the destination replaces the destination
imagick::COMPOSITE_SRCOVER (integer)
The source replaces the destination
imagick::COMPOSITE_SUBTRACT (integer)
Subtract the colors in the source image from the destination image
imagick::COMPOSITE_THRESHOLD (integer)
The source is composited on the target as defined by source threshold
imagick::COMPOSITE_XOR (integer)
The part of the source that lies outside of the destination is combined with the part of the destination that lies outside of the source
MONTAGEMODE constants
imagick::MONTAGEMODE_FRAME (integer)
imagick::MONTAGEMODE_UNFRAME (integer)
imagick::MONTAGEMODE_CONCATENATE (integer)
STYLE constants
imagick::STYLE_NORMAL (integer)
imagick::STYLE_ITALIC (integer)
imagick::STYLE_OBLIQUE (integer)
imagick::STYLE_ANY (integer)
FILTER constants
imagick::FILTER_UNDEFINED (integer)
imagick::FILTER_POINT (integer)
imagick::FILTER_BOX (integer)
imagick::FILTER_TRIANGLE (integer)
imagick::FILTER_HERMITE (integer)
imagick::FILTER_HANNING (integer)
imagick::FILTER_HAMMING (integer)
imagick::FILTER_BLACKMAN (integer)
imagick::FILTER_GAUSSIAN (integer)
imagick::FILTER_QUADRATIC (integer)
imagick::FILTER_CUBIC (integer)
imagick::FILTER_CATROM (integer)
imagick::FILTER_MITCHELL (integer)
imagick::FILTER_LANCZOS (integer)
imagick::FILTER_BESSEL (integer)
imagick::FILTER_SINC (integer)
IMGTYPE constants
imagick::IMGTYPE_UNDEFINED (integer)
imagick::IMGTYPE_BILEVEL (integer)
imagick::IMGTYPE_GRAYSCALE (integer)
imagick::IMGTYPE_GRAYSCALEMATTE (integer)
imagick::IMGTYPE_PALETTE (integer)
imagick::IMGTYPE_PALETTEMATTE (integer)
imagick::IMGTYPE_TRUECOLOR (integer)
imagick::IMGTYPE_TRUECOLORMATTE (integer)
imagick::IMGTYPE_COLORSEPARATION (integer)
imagick::IMGTYPE_COLORSEPARATIONMATTE (integer)
imagick::IMGTYPE_OPTIMIZE (integer)
RESOLUTION constants
imagick::RESOLUTION_UNDEFINED (integer)
imagick::RESOLUTION_PIXELSPERINCH (integer)
imagick::RESOLUTION_PIXELSPERCENTIMETER (integer)
COMPRESSION constants
imagick::COMPRESSION_UNDEFINED (integer)
imagick::COMPRESSION_NO (integer)
imagick::COMPRESSION_BZIP (integer)
imagick::COMPRESSION_FAX (integer)
imagick::COMPRESSION_GROUP4 (integer)
imagick::COMPRESSION_JPEG (integer)
imagick::COMPRESSION_JPEG2000 (integer)
imagick::COMPRESSION_LOSSLESSJPEG (integer)
imagick::COMPRESSION_LZW (integer)
imagick::COMPRESSION_RLE (integer)
imagick::COMPRESSION_ZIP (integer)
imagick::COMPRESSION_DXT1 (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.0 or higher.
imagick::COMPRESSION_DXT3 (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.0 or higher.
imagick::COMPRESSION_DXT5 (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.0 or higher.
PAINT constants
imagick::PAINT_POINT (integer)
imagick::PAINT_REPLACE (integer)
imagick::PAINT_FLOODFILL (integer)
imagick::PAINT_FILLTOBORDER (integer)
imagick::PAINT_RESET (integer)
GRAVITY constants
imagick::GRAVITY_NORTHWEST (integer)
imagick::GRAVITY_NORTH (integer)
imagick::GRAVITY_NORTHEAST (integer)
imagick::GRAVITY_WEST (integer)
imagick::GRAVITY_CENTER (integer)
imagick::GRAVITY_EAST (integer)
imagick::GRAVITY_SOUTHWEST (integer)
imagick::GRAVITY_SOUTH (integer)
imagick::GRAVITY_SOUTHEAST (integer)
STRETCH constants
imagick::STRETCH_NORMAL (integer)
imagick::STRETCH_ULTRACONDENSED (integer)
imagick::STRETCH_CONDENSED (integer)
imagick::STRETCH_SEMICONDENSED (integer)
imagick::STRETCH_SEMIEXPANDED (integer)
imagick::STRETCH_EXPANDED (integer)
imagick::STRETCH_EXTRAEXPANDED (integer)
imagick::STRETCH_ULTRAEXPANDED (integer)
imagick::STRETCH_ANY (integer)
ALIGN constants
imagick::ALIGN_UNDEFINED (integer)
imagick::ALIGN_LEFT (integer)
imagick::ALIGN_CENTER (integer)
imagick::ALIGN_RIGHT (integer)
DECORATION constants
imagick::DECORATION_NO (integer)
imagick::DECORATION_UNDERLINE (integer)
imagick::DECORATION_OVERLINE (integer)
imagick::DECORATION_LINETROUGH (integer)
NOISE constants
imagick::NOISE_UNIFORM (integer)
imagick::NOISE_GAUSSIAN (integer)
imagick::NOISE_MULTIPLICATIVEGAUSSIAN (integer)
imagick::NOISE_IMPULSE (integer)
imagick::NOISE_LAPLACIAN (integer)
imagick::NOISE_POISSON (integer)
imagick::NOISE_RANDOM (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.6 or higher.
CHANNEL constants
imagick::CHANNEL_UNDEFINED (integer)
imagick::CHANNEL_RED (integer)
imagick::CHANNEL_GRAY (integer)
imagick::CHANNEL_CYAN (integer)
imagick::CHANNEL_GREEN (integer)
imagick::CHANNEL_MAGENTA (integer)
imagick::CHANNEL_BLUE (integer)
imagick::CHANNEL_YELLOW (integer)
imagick::CHANNEL_ALPHA (integer)
imagick::CHANNEL_OPACITY (integer)
imagick::CHANNEL_MATTE (integer)
imagick::CHANNEL_BLACK (integer)
imagick::CHANNEL_INDEX (integer)
imagick::CHANNEL_ALL (integer)
imagick::CHANNEL_DEFAULT (integer)
METRIC constants
imagick::METRIC_UNDEFINED (integer)
imagick::METRIC_MEANABSOLUTEERROR (integer)
imagick::METRIC_MEANSQUAREERROR (integer)
imagick::METRIC_PEAKABSOLUTEERROR (integer)
imagick::METRIC_PEAKSIGNALTONOISERATIO (integer)
imagick::METRIC_ROOTMEANSQUAREDERROR (integer)
PIXEL constants
imagick::PIXEL_CHAR (integer)
imagick::PIXEL_DOUBLE (integer)
imagick::PIXEL_FLOAT (integer)
imagick::PIXEL_INTEGER (integer)
imagick::PIXEL_LONG (integer)
imagick::PIXEL_QUANTUM (integer)
imagick::PIXEL_SHORT (integer)
EVALUATE constants
imagick::EVALUATE_UNDEFINED (integer)
imagick::EVALUATE_ADD (integer)
imagick::EVALUATE_AND (integer)
imagick::EVALUATE_DIVIDE (integer)
imagick::EVALUATE_LEFTSHIFT (integer)
imagick::EVALUATE_MAX (integer)
imagick::EVALUATE_MIN (integer)
imagick::EVALUATE_MULTIPLY (integer)
imagick::EVALUATE_OR (integer)
imagick::EVALUATE_RIGHTSHIFT (integer)
imagick::EVALUATE_SET (integer)
imagick::EVALUATE_SUBTRACT (integer)
imagick::EVALUATE_XOR (integer)
imagick::EVALUATE_POW (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.4 or higher.
imagick::EVALUATE_LOG (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.4 or higher.
imagick::EVALUATE_THRESHOLD (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.4 or higher.
imagick::EVALUATE_THRESHOLDBLACK (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.4 or higher.
imagick::EVALUATE_THRESHOLDWHITE (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.4 or higher.
imagick::EVALUATE_GAUSSIANNOISE (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.4 or higher.
imagick::EVALUATE_IMPULSENOISE (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.4 or higher.
imagick::EVALUATE_LAPLACIANNOISE (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.4 or higher.
imagick::EVALUATE_MULTIPLICATIVENOISE (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.4 or higher.
imagick::EVALUATE_POISSONNOISE (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.4 or higher.
imagick::EVALUATE_UNIFORMNOISE (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.4 or higher.
imagick::EVALUATE_COSINE (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.4 or higher.
imagick::EVALUATE_SINE (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.4 or higher.
imagick::EVALUATE_ADDMODULUS (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.4 or higher.
COLORSPACE constants
imagick::COLORSPACE_UNDEFINED (integer)
imagick::COLORSPACE_RGB (integer)
imagick::COLORSPACE_GRAY (integer)
imagick::COLORSPACE_TRANSPARENT (integer)
imagick::COLORSPACE_OHTA (integer)
imagick::COLORSPACE_LAB (integer)
imagick::COLORSPACE_XYZ (integer)
imagick::COLORSPACE_YCBCR (integer)
imagick::COLORSPACE_YCC (integer)
imagick::COLORSPACE_YIQ (integer)
imagick::COLORSPACE_YPBPR (integer)
imagick::COLORSPACE_YUV (integer)
imagick::COLORSPACE_CMYK (integer)
imagick::COLORSPACE_SRGB (integer)
imagick::COLORSPACE_HSB (integer)
imagick::COLORSPACE_HSL (integer)
imagick::COLORSPACE_HWB (integer)
imagick::COLORSPACE_REC601LUMA (integer)
imagick::COLORSPACE_REC709LUMA (integer)
imagick::COLORSPACE_LOG (integer)
imagick::COLORSPACE_CMY (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.2 or higher.
VIRTUALPIXELMETHOD constants
imagick::VIRTUALPIXELMETHOD_UNDEFINED (integer)
imagick::VIRTUALPIXELMETHOD_BACKGROUND (integer)
imagick::VIRTUALPIXELMETHOD_CONSTANT (integer)
imagick::VIRTUALPIXELMETHOD_EDGE (integer)
imagick::VIRTUALPIXELMETHOD_MIRROR (integer)
imagick::VIRTUALPIXELMETHOD_TILE (integer)
imagick::VIRTUALPIXELMETHOD_TRANSPARENT (integer)
imagick::VIRTUALPIXELMETHOD_MASK (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.2 or higher.
imagick::VIRTUALPIXELMETHOD_BLACK (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.2 or higher.
imagick::VIRTUALPIXELMETHOD_GRAY (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.2 or higher.
imagick::VIRTUALPIXELMETHOD_WHITE (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.2 or higher.
imagick::VIRTUALPIXELMETHOD_HORIZONTALTILE (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.3 or higher.
imagick::VIRTUALPIXELMETHOD_VERTICALTILE (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.3 or higher.
PREVIEW constants
imagick::PREVIEW_UNDEFINED (integer)
imagick::PREVIEW_ROTATE (integer)
imagick::PREVIEW_SHEAR (integer)
imagick::PREVIEW_ROLL (integer)
imagick::PREVIEW_HUE (integer)
imagick::PREVIEW_SATURATION (integer)
imagick::PREVIEW_BRIGHTNESS (integer)
imagick::PREVIEW_GAMMA (integer)
imagick::PREVIEW_SPIFF (integer)
imagick::PREVIEW_DULL (integer)
imagick::PREVIEW_GRAYSCALE (integer)
imagick::PREVIEW_QUANTIZE (integer)
imagick::PREVIEW_DESPECKLE (integer)
imagick::PREVIEW_REDUCENOISE (integer)
imagick::PREVIEW_ADDNOISE (integer)
imagick::PREVIEW_SHARPEN (integer)
imagick::PREVIEW_BLUR (integer)
imagick::PREVIEW_THRESHOLD (integer)
imagick::PREVIEW_EDGEDETECT (integer)
imagick::PREVIEW_SPREAD (integer)
imagick::PREVIEW_SOLARIZE (integer)
imagick::PREVIEW_SHADE (integer)
imagick::PREVIEW_RAISE (integer)
imagick::PREVIEW_SEGMENT (integer)
imagick::PREVIEW_SWIRL (integer)
imagick::PREVIEW_IMPLODE (integer)
imagick::PREVIEW_WAVE (integer)
imagick::PREVIEW_OILPAINT (integer)
imagick::PREVIEW_CHARCOALDRAWING (integer)
imagick::PREVIEW_JPEG (integer)
RENDERINGINTENT constants
imagick::RENDERINGINTENT_UNDEFINED (integer)
imagick::RENDERINGINTENT_SATURATION (integer)
imagick::RENDERINGINTENT_PERCEPTUAL (integer)
imagick::RENDERINGINTENT_ABSOLUTE (integer)
imagick::RENDERINGINTENT_RELATIVE (integer)
INTERLACE constants
imagick::INTERLACE_UNDEFINED (integer)
imagick::INTERLACE_NO (integer)
imagick::INTERLACE_LINE (integer)
imagick::INTERLACE_PLANE (integer)
imagick::INTERLACE_PARTITION (integer)
imagick::INTERLACE_GIF (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.4 or higher.
imagick::INTERLACE_JPEG (integer)
imagick::INTERLACE_PNG (integer)
FILLRULE constants
imagick::FILLRULE_UNDEFINED (integer)
imagick::FILLRULE_EVENODD (integer)
imagick::FILLRULE_NONZERO (integer)
PATHUNITS constants
imagick::PATHUNITS_UNDEFINED (integer)
imagick::PATHUNITS_USERSPACE (integer)
imagick::PATHUNITS_USERSPACEONUSE (integer)
imagick::PATHUNITS_OBJECTBOUNDINGBOX (integer)
LINECAP constants
imagick::LINECAP_UNDEFINED (integer)
imagick::LINECAP_BUTT (integer)
imagick::LINECAP_ROUND (integer)
imagick::LINECAP_SQUARE (integer)
LINEJOIN constants
imagick::LINEJOIN_UNDEFINED (integer)
imagick::LINEJOIN_MITER (integer)
imagick::LINEJOIN_ROUND (integer)
imagick::LINEJOIN_BEVEL (integer)
RESOURCETYPE constants
imagick::RESOURCETYPE_UNDEFINED (integer)
imagick::RESOURCETYPE_AREA (integer)
imagick::RESOURCETYPE_DISK (integer)
imagick::RESOURCETYPE_FILE (integer)
imagick::RESOURCETYPE_MAP (integer)
imagick::RESOURCETYPE_MEMORY (integer)
LAYERMETHOD constants
imagick::LAYERMETHOD_UNDEFINED (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.2.9 or higher.
imagick::LAYERMETHOD_COALESCE (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.2.9 or higher.
imagick::LAYERMETHOD_COMPAREANY (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.2.9 or higher.
imagick::LAYERMETHOD_COMPARECLEAR (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.2.9 or higher.
imagick::LAYERMETHOD_COMPAREOVERLAY (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.2.9 or higher.
imagick::LAYERMETHOD_DISPOSE (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.2.9 or higher.
imagick::LAYERMETHOD_OPTIMIZE (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.2.9 or higher.
imagick::LAYERMETHOD_OPTIMIZEPLUS (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.2.9 or higher.
imagick::LAYERMETHOD_OPTIMIZEIMAGE (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.0 or higher.
imagick::LAYERMETHOD_OPTIMIZETRANS (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.0 or higher.
imagick::LAYERMETHOD_REMOVEDUPS (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.0 or higher.
imagick::LAYERMETHOD_REMOVEZERO (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.0 or higher.
imagick::LAYERMETHOD_COMPOSITE (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.0 or higher.
imagick::LAYERMETHOD_MERGE (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.7 or higher.
imagick::LAYERMETHOD_FLATTEN (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.7 or higher.
imagick::LAYERMETHOD_MOSAIC (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.7 or higher.
ORIENTATION constants
imagick::ORIENTATION_UNDEFINED (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.0 or higher.
imagick::ORIENTATION_TOPLEFT (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.0 or higher.
imagick::ORIENTATION_TOPRIGHT (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.0 or higher.
imagick::ORIENTATION_BOTTOMRIGHT (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.0 or higher.
imagick::ORIENTATION_BOTTOMLEFT (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.0 or higher.
imagick::ORIENTATION_LEFTTOP (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.0 or higher.
imagick::ORIENTATION_RIGHTTOP (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.0 or higher.
imagick::ORIENTATION_RIGHTBOTTOM (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.0 or higher.
imagick::ORIENTATION_LEFTBOTTOM (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.0 or higher.
DISTORTION constants
imagick::DISTORTION_UNDEFINED (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.6 or higher.
imagick::DISTORTION_AFFINE (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.6 or higher.
imagick::DISTORTION_AFFINEPROJECTION (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.6 or higher.
imagick::DISTORTION_ARC (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.6 or higher.
imagick::DISTORTION_BILINEAR (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.6 or higher.
imagick::DISTORTION_PERSPECTIVE (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.6 or higher.
imagick::DISTORTION_PERSPECTIVEPROJECTION (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.6 or higher.
imagick::DISTORTION_SCALEROTATETRANSLATE (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.6 or higher.
imagick::DISTORTION_POLYNOMIAL (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.6 or higher.
imagick::DISTORTION_POLAR (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.6 or higher.
imagick::DISTORTION_DEPOLAR (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.6 or higher.
imagick::DISTORTION_BARREL (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.6 or higher.
imagick::DISTORTION_BARRELINVERSE (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.6 or higher.
imagick::DISTORTION_SHEPARDS (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.6 or higher.
imagick::DISTORTION_SENTINEL (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.6 or higher.
ALPHACHANNEL constants
imagick::ALPHACHANNEL_ACTIVATE (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.8 or higher.
imagick::ALPHACHANNEL_DEACTIVATE (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.8 or higher.
imagick::ALPHACHANNEL_RESET (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.8 or higher.
imagick::ALPHACHANNEL_SET (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.8 or higher.
imagick::ALPHACHANNEL_UNDEFINED (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.6 or higher.
imagick::ALPHACHANNEL_COPY (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.6 or higher.
imagick::ALPHACHANNEL_EXTRACT (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.6 or higher.
imagick::ALPHACHANNEL_OPAQUE (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.6 or higher.
imagick::ALPHACHANNEL_SHAPE (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.6 or higher.
imagick::ALPHACHANNEL_TRANSPARENT (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.6 or higher.
SPARSECOLORMETHOD constants
imagick::SPARSECOLORMETHOD_UNDEFINED (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.6 or higher.
imagick::SPARSECOLORMETHOD_BARYCENTRIC (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.6 or higher.
imagick::SPARSECOLORMETHOD_BILINEAR (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.6 or higher.
imagick::SPARSECOLORMETHOD_POLYNOMIAL (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.6 or higher.
imagick::SPARSECOLORMETHOD_SPEPARDS (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.6 or higher.
imagick::SPARSECOLORMETHOD_VORONOI (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.6 or higher.
FUNCTION constants
imagick::FUNCTION_UNDEFINED (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.9 or higher.
imagick::FUNCTION_POLYNOMIAL (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.9 or higher.
imagick::FUNCTION_SINUSOID (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.9 or higher.
INTERPOLATE constants
imagick::INTERPOLATE_UNDEFINED (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.2 or higher.
imagick::INTERPOLATE_AVERAGE (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.2 or higher.
imagick::INTERPOLATE_BICUBIC (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.2 or higher.
imagick::INTERPOLATE_BILINEAR (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.2 or higher.
imagick::INTERPOLATE_FILTER (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.2 or higher.
imagick::INTERPOLATE_INTEGER (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.2 or higher.
imagick::INTERPOLATE_MESH (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.2 or higher.
imagick::INTERPOLATE_NEARESTNEIGHBOR (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.2 or higher.
imagick::INTERPOLATE_SPLINE (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.3.4 or higher.
DITHERMETHOD constants
imagick::DITHERMETHOD_UNDEFINED (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.6 or higher.
imagick::DITHERMETHOD_NO (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.6 or higher.
imagick::DITHERMETHOD_RIEMERSMA (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.6 or higher.
imagick::DITHERMETHOD_FLOYDSTEINBERG (integer)
This constant is available if Imagick has been compiled against ImageMagick version 6.4.6 or higher.
