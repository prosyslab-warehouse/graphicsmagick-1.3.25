2016-09-05  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - www/index.rst: Update for 1.3.25 release.

  - version.sh: Update library versioning for 1.3.25 release.

  - NEWS.txt: Make sure is up to date.

  - Various fixes for minor issues noticed when compiling under
    Visual Studio.

2016-08-22  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - magick/studio.h (MAGICK\_CACHE\_LINE\_SIZE): Apply patch from
    Gentoo Linux to increase MAGICK\_CACHE\_LINE\_SIZE to 128 when
    \_\_powerpc\_\_ is defined.

2016-08-21  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - NEWS.txt: Updated with latest changes.

2016-08-20  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - coders/rle.c (ReadRLEImage): Reject truncated/absurd Utah RLE
    files. Problem was reported by Agostino Sarubbo on August 19,
    2016.

2016-08-18  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - coders/tiff.c (ReadTIFFImage): Fix heap-based buffer read
    overflow.  TIFF sized attibutes were not being properly copied to
    a null-terminated string if the value was not null terminated.
    Problem was reported by Agostino Sarubbo on August 18, 2016.

2016-08-15  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - lcms/src/cmstypes.c (Type\_MLU\_Read): "Added an extra check to
    MLU bounds", change based on github mm2/Little-CMS commit
    5ca71a7bc18b6897ab21d815d15e218e204581e2 and announced to the
    oss-security list by Ibrahim M. El-Sayed on Mon, 15 Aug 2016.

2016-08-14  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - webp: Updated bundled libwebp to release 0.5.1.

  - libxml: Updated bundled libxml2 to release 2.9.4.

  - lcms: Updated bundled lcms2 to release 2.8.

  - png: Update bundled libpng to release 1.6.24.

  - coders/jpeg.c (ReadJPEGImage): Log setting resolution and
    resolution units due to JFIF marker.

  - coders/sgi.c (SGIDecode): Fix integer overflow of size type in
    Win64 build where sizeof(long) < sizeof(size\_t).

2016-08-08  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - coders, magick: Compile clean using GCC with -std=c90.

  - magick/describe.c (DescribeImage): The 'identify' and 'info'
    functionality only shows the pixel read rate if image was not read
    in 'ping' mode.  Provide seconds timing with 6 digits of precision
    since that is what is needed.

2016-08-07  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - magick/describe.c (DescribeImage): Include milliseconds
    resolution in elapsed time output.

  - magick/timer.c (ElapsedTime): Use clock\_gettime() (when
    available with default linkage) to obtain elapsed time.

2016-08-06  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - coders/yuv.c (WriteYUVImage): Fix benign clang compiler warning
    regarding "variable 'x' is incremented both in the loop header and
    in the loop body".

  - configure.ac: Fixes to use clang's OpenMP runtime library
    (-lomp) for clang 3.8 and later.  Specifically tested with clang
    3.8 on Ubuntu 16.04 'xenial'.  Problem was reported by Holger
    Hoffst??tte via private email.

  - NEWS.txt: Bring up to date with latest changes.

2016-07-23  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - magick/render.c (DrawImage): Reject abnormally absurd gradient
    size requests (many absurd requests are still allowed).  Provide
    detailed error reports when a gradient is rejected.

  - coders/svg.c: Support units for 'stroke-dashoffset'.

2016-07-09  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - magick/annotate.c (EscapeParenthesis): In private email on
    2016-07-07, Gustavo Grieco notified us of a heap overflow in
    EscapeParenthesis().  I was not able to reproduce the issue but
    changed the implementation with the suspicion that the
    implementation has a bug, and due to noticing arbitary limits and
    inefficiency.

2016-07-03  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - magick/render.c (DrawImage): Fix absolute and arbitrary gradient
    dimension sanity checks which caused gradient requests to fail.
    Resolves SourceForge issue #392 "SVG 'push defs' fails (Debian
    bugs 829063 and 828120)".

2016-06-16  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - www/security.rst: Add discussion of SVG format and SSRF
    vulnerability.

2016-06-12  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - coders/svg.c (ReadSVGImage): Assure that SVGInfo data is freed
    when XMP parsing is aborted due to an error.

2016-06-11  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - NEWS.txt: Updated NEWS with changes since last release.

  - www/security.rst: Add a page about GraphicsMagick security.

2016-06-08  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - magick/render.c (DrawPrimitive): Over-aggressive error reporting
    was causing failures when elements were "drawn" off-image.
    Resolves SourceForge issue #389 "Non-conforming drawing primitive
    definition (line)".

2016-05-31  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - magick/render.c (DrawImage): Fix problem while reading file
    "tnamkejarz.svg.2532308010849170049" provided via private email
    from Gustavo Grieco on May 31, 2016.

  - magick/utility.c (MagickGetToken): Fix problem while reading
    file "vqxwatmqmi.svg.-3669039972557308254" provided via private
    email from Gustavo Grieco on May 31, 2016.

2016-05-30  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - NEWS.txt: Update for 1.3.24 release.

  - www/Changes.rst: Mention 1.3.24 release.

  - www/index.rst: Update for 1.3.24 release.

  - version.sh: Update library ABI information in preparation for
    1.3.24 release.

  - NEWS.txt: Updated NEWS to reflect fixes and issues.

2016-05-29  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - NEWS.txt: Updated with latest news.

  - magick/blob.c (OpenBlob): Remove support for reading input from
    a shell command, or writing output to a shell command, by
    prefixing the specified filename (containing the command) with a
    '|'.  This feature provided a remote shell execution opportunity
    (CVE-2016-5118).

  - coders/mat.c (ReadMATImage): Validate that MAT frames is not
    zero.

2016-05-28  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - magick/render.c (DrawImage): Be less optimistic when estimating
    the number of points required to represent a path.  This should
    help address CVE-2016-2317 "Heap buffer overflow".  This resolves
    SourceForge issue #275 "Applying Clipping Path to high resolution
    JPG".

2016-05-25  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - magick/render.c (DrawImage): Fix problem while reading file
    "pxypjhfdxf.svg.7406476585885697806" provided via via private
    email from Gustavo Grieco on May 24, 2016.

  - coders/svg.c: Fix problem while reading file
    "pxypjhfdxf.svg.308008972284643989" provided via private email
    from Gustavo Grieco on May 24, 2016.

2016-05-23  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - coders/svg.c ("C"): Support font-size "medium".

2016-05-22  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - NEWS.txt: Updated NEWS.txt to reflect latest changes.

  - magick/render.c (DrawImage): Added DrawImage() recursion
    detection/prevention.

  - coders/svg.c (ReadSVGImage): Add basic primitive argument
    validation.

  - magick/render.c (DrawImage): Add basic primitive argument
    validation.

2016-05-21  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - coders/url.c (ReadURLImage): Reading "file://" URLs was not
    working.  Now file URLs are working.

2016-05-21  Glenn Randers-Pehrson  <glennrp@simple.dallas.tx.us>

  - coders/png.c: Respect JPEG limits (65535x65535) and user width
    and height limits from "-limit" while reading or writing JNG files.

2016-05-21  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - coders/url.c: Don't hide HTTP, FTP, and FILE URL support from
    '-list format' output.  Ignore HTTP, FTP, and FILE as a useful
    file extension for determing the file format.

2016-05-17  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - magick/render.c (ConvertPathToPolygon): Make sure that first
    edge is initialized.  Make sure that points is not null.

2016-05-15  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - magick/render.c (DrawImage): Fixed segmentation violation while
    reading file "275077586554139424.lqxdgqxtfs.svg" provided via
    private email from Gustavo Grieco on May 15, 2016.  This is due to
    another CVE-2016-2317 related issue.

2016-05-14  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - coders/svg.c ("C"): Fixed problems while reading files
    "aaphrbkwwe.svg.-1899680443073025602",
    "aaphrbkwwe.svg.-5751004588641220738",
    "aaphrbkwwe.svg.-8875730334406147537", and
    "aaphrbkwwe.svg.4495884156523242589" provided via private email
    from Gustavo Grieco on February 8, 2016.

2016-05-12  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - coders/dib.c (ReadDIBImage): Verify that DIB file data is
    sufficient to meet claims made by file header.  Validate image
    planes.  Fixes Fixes problem reported by Hanno B??ck on May 8th,
    2016 via private email entitled "malloc issue in ReadDIBImage".

2016-05-09  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - coders/msl.c (RegisterMSLImage): Ignore the file extension on
    MSL files.  The only way to read an image from a MSL file (as
    opposed to explicitly running a MSL script with 'conjure') is by
    reading using a filename specification like "msl:filename".  This
    is done for security reasons.

  - magick/render.c (DrawPrimitive): Fix Coverity issue 126378
    "Resource leak".

  - coders/mat.c (DecompressBlock): Fix Coverity issue 126379
    "Resource leak".

  - magick/render.c (DrawImage): Fix Coverity issue 126380 "Resource
    leak".

2016-05-08  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - magick/render.c (DrawPrimitive): Sanity check the image file
    path or URL before passing it to ReadImage().

  - config/delegates.mgk.in: Pare down delegates.mgk to reduce
    security exposure due to external programs not under our control.

2016-05-08  Fojtik Jaroslav  <JaFojtik@seznam.cz>

  - coders/mat.c Typo fix - matrix has nothing to do with PostScript.

2016-05-08  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - coders/mat.c (DecompressBlock): Don't hang on a corrupt deflate
    stream when reading matlab v6 file.  Fixes problem reported by
    Hanno B??ck on May 8, 2016 via private email entitled "hang of
    matlab input file".

2016-05-07  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - magick/image.c (SetImageInfo): Undocumented "TMP" magick prefix
    no longer removes the argument file after it has been read. This
    functionality is only used to support the "show" delegate which is
    used by options in the 'display' program which need to display a
    generated image in a new instance of 'display'.  The "show"
    delegate is used by writing a temporary file to be viewed, and
    which should be removed before the program quits.  Since the "TMP"
    feature was originally implemented, GraphicsMagick added a
    temporary file management subsystem which assures that temporary
    files are removed so this feature is not needed.

  - coders/tiff.c (ReadTIFFImage): Fix heap overflow with file
    "gkkxrilssm.tiff.-4678010562506843336" provided by Gustavo Grieco
    on February 8, 2006 via private email.

  - coders/viff.c (ReadVIFFImage): Fix problem with a very large
    malloc in sample file provided by Hanno B??ck on May 7, 2016 with
    subject "large malloc in ReadVIFFImage".

  - coders/mvg.c (RegisterMVGImage): Do not auto-detect MVG format
    based on file extension.  MVG files can then only be read by
    adding a "MVG:" prefix to the file name. There is already no
    auto-detection of MVG based on content.

2016-05-06  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - coders/xpm.c (ReadXPMImage): Limit the number of XPM colors and
    assure array initialization.  Fixes bad behavior with a sample
    file provided by Hanno B??ck on May 6, 2016 with subject "Invalid
    free in ReadXPMImage".

  - coders/pcx.c (ReadPCXImage): Limit the number of PCX image
    planes allowed.  Fixes an unreasonable memory allocation in a
    sample file provided by Hanno B??ck on May 5, 2016.

2016-05-04  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - config/delegates.mgk.in: Gnuplot files are inherently insecure.
    Remove delegates support for reading them.  Reported by John
    Lightsey via private email.
    Added -dSAFER to Ghostscript invokations in delegates.mgk for more
    secure execution.  Reported by David Chan via SourceForge bug
    "#386 ghostscript delegates should explicitly use -dSAFER.".

  - magick/constitute.c (ReadImages): Avoid possible infinite
    ReadImage() recursion.

2016-05-01  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - magick/render.c (DrawPolygonPrimitive): Fix divide by zero
    exception encountered while reading file "sigfpe.svg" posted by
    Gustavo Grieco on May 1, 2016 to the oss-security mailing list
    with subject "CVE request: DoS in multiple versions of
    GraphicsMagick".
    (DrawDashPolygon): Fix endless loop problem caused by negative
    stroke-dasharray arguments.  Resolves problem observed while
    reading file "circular.svg" posted by Gustavo Grieco on May 1,
    2016 to the oss-security mailing list with subject "CVE request:
    DoS in multiple versions of GraphicsMagick".

  - magick/import.c (ImportViewPixelArea): Fix assertion while
    reading TIFF file gkkxrilssm.tiff.105123337066 provided by Gustavo
    Grieco.

2016-04-30  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - coders/locale.c (ReadLOCALEImage): Make sure to close blob
    before returning.

  - coders/svg.c ("C"): Provide a hack work-around for double-quoted
    font-family argument.

  - magick/render.c (DrawImage): Make SVG path and other primitive
    parsing more robust.  Fixes SEGV when reading files provided by
    CVE-2016-2318 test cases.  Fixes CVE-2016-2318 completely.

2016-04-24  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - magick/render.c (DrawImage): Fix heap buffer overflow when
    reading aaphrbkwwe.svg.-1114777018469422437 from CVE-2016-2317
    test cases.  This resolves CVE-2016-2317 completely.

2016-04-23  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - magick/command.c (MogrifyImageCommand): Added mogrify
    -preserve-timestamp option to preserve file access and
    modification timestamps.  Contributed by Niko Rosvall via
    SourceForge patch #45 "preserve-timestamp option for mogrify
    command."

2016-04-19  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - magick/blob.c: Added ReadBlobLSBSignedShort(),
    ReadBlobMSBSignedShort(),
    ReadBlobLSBSignedLong(),ReadBlobMSBSignedLong(),
    WriteBlobLSBSignedShort(), WriteBlobLSBSignedLong(),
    WriteBlobMSBSignedLong(), WriteBlobMSBSignedShort() for doing I/O
    on signed integer types without the need for dangerous casts or
    unexpected values due to signed/unsigned conversion.

2016-04-17  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - NEWS.txt: Updated with latest changes.

  - magick/constitute.c (ReadImage): Added asserts to check that the
    I/O blob is not still open in the returned image since this causes
    problems.

  - magick/blob.c (CloneBlobInfo): Use a cloning approach which does
    not require manually keeping structure members in sync.

  - coders/msl.c (ProcessMSLScript): Need to close I/O blob before
    returning.

  - coders/psd.c (ReadPSDImage): Assure that allocated image is not
    dereferenced before checking if it is NULL.  Check some memory
    calculations for overflow.
    (ReadPSDImage): Need to close I/O blob before returning.

  - coders/dib.c (ReadDIBImage): Use DestroyBlob() rather than
    DestroyBlobInfo().

  - coders/bmp.c (ReadBMPImage): Use DestroyBlob() rather than
    DestroyBlobInfo().

  - magick/blob.c: Improve blob tracing.

2016-04-13  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - coders/bmp.c (ReadBMPImage): Fix reading 24-bit Microsoft BMP
    which claims to have a colormap.

2016-04-13 Fojtik Jaroslav  <JaFojtik@seznam.cz>

  - PerlMagick/t/input\_complex\_lsb\_double\_V4.mat Demo Matlab V4
    complex file.
  - coders/mat.c Missing break added.

2016-04-12  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - coders/xpm.c (ReadXPMImage): Fix SourceForge issue #361
    "out-of-bounds read in coders/xpm.c:150:24"

  - coders/psd.c (ReadPSDImage): Add some defensive code to assure
    that image layers are not freed twice.

2016-04-10  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - magick/log.c (InitializeLogInfo): Simplify LogInfo structure and
    its allocation in order to lessen the amount of fixed overhead.

2016-04-04  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - coders/jp2.c (WriteJP2Image): Fix SourceForge issue #378 "jp2:
    impossible to create lossless jpeg-2000".  With this fix,
    specifying 'define jp2:rate=1.0' or '-quality 100' results in a
    lossless JP2 file.

2016-04-03  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - magick/common.h: Update for GCC 5.

  - PerlMagick/MANIFEST: Update PerlMagick manifest.

  - PerlMagick/t/{read.t, write.t}: Add tests for MAT v4.

2016-04-03 Fojtik Jaroslav  <JaFojtik@seznam.cz>

  - coders/mat.c Matlab V4 attempt to read complex part of data.

2016-04-02  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - PerlMagick/t/features.pl.in: Provide a way that PerlMagick
    feature tests can test if a feature is supported.  Use it to make
    the PSD test optional.

  - coders/Makefile.am: Only build PSD module if
    ENABLE\_BROKEN\_CODERS is enabled.

  - magick/module.c (UnloadModule): Only invoke the module
    unregister function if it is defined.  The module register
    function is not defined if either the register or unregister
    functions were not found in the module which was loaded.

2016-04-02 Fojtik Jaroslav  <JaFojtik@seznam.cz>

  - coders/mat.c Matlab V4 files are also rotated.
        \* PerlMagick/t/input\_gray\_lsb\_double\_V4.mat   Demo Matlab V4 file.

2016-04-01  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - magick/magick.c (GetMagickInfo): Only declare that ExceptionInfo
    argument is not used if modules are not supported.

2016-03-28 Fojtik Jaroslav  <JaFojtik@seznam.cz>

  - coders/mat.c Attempt to read Matlab V4 files.

2016-03-27  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - magick/image.c (DestroyImage): Simply return if image is NULL
    since it is more user-friendly.

  - magick/shear.c (RotateImage): Fix Coverity issue 124519
    "Logically dead code".

  - magick/effect.c (BlurImage): Fix Coverity issue 124520
    "Dereference after null check".

  - coders/pdb.c (WritePDBImage): Fix SourceForge bug #360
    "out-of-bounds read in utilities/gm+0x80fcc71) (PDB reader)".

  - coders/meta.c (convertHTMLcodes): Fix SourceForge bug #373
    "out-of-bounds read in coders/meta.c:444:50"
    (ReadMETAImage): Fix SourceForge bug #364 "out-of-bounds write in
    coders/meta.c:1331:7".

2016-03-26  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - coders/sgi.c (ReadSGIImage): Fix SourceForge bug #366
    "out-of-bounds write in coders/sgi.c:528:4" and bug #369
    "out-of-bounds write in coders/sgi.c:535:4".

  - coders/rle.c (ReadRLEImage): Fix SourceForge bug #371
    "out-of-bounds read in coders/rle.c:633:39".

2016-03-25  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - coders/dib.c (ReadDIBImage): Fix SourceForge bug #367
    "out-of-bounds read in coders/dib.c:706:13" and bug #370
    "out-of-bounds read in coders/dib.c:716:15".

  - coders/pict.c (ReadPICTImage): Fix SourceForge bug #365
    "out-of-bounds read in magick/image.c:1305:3"

  - magick/utility.c (GetPageGeometry): Fix SourceForge bug #374
    "out-of-bounds write in magick/utility.c:4355:7"

2016-03-23  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - coders/miff.c (ReadMIFFImage): Fix SourceForge bug #376 "SIGABRT
    in magick/colorspace.c:1052".

  - magick/shear.c (RotateImage): Fix SourceForge bug #375 "SIGABRT
    in magick/image.c:1230".

  - coders/sun.c (DecodeImage): Fix SourceForge bug #368
    "out-of-bounds read in coders/sun.c:223:17" and bug #363
    "out-of-bounds read in coders/sun.c:221:16".

2016-03-20  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - coders/svg.c (GetUserSpaceCoordinateValue): Fix stack buffer
    overflow when reading file 'aaphrbkwwe.svg.-632425326915265752'
    from CVE-2016-2317 problem files.  Partial fix for SourceForge bug
    #358 "CVE-2016-2317 - SVG heap/stack buffer overflows".

  - magick/utility.c (MagickGetToken): New private function to
    replace GetToken().  The new function accepts a token buffer
    length argument.  GetToken() is modified to assume a token buffer
    length 'MaxTextExtent'.  All code using GetToken() is updated to
    use MagickGetToken().

  - coders/svg.c: Fix heap buffer overflow when reading file
    "aaphrbkwwe.svg.4495884156523242589" from CVE-2016-2317 problem
    files.  Partial fix for SourceForge bug #358 "CVE-2016-2317 - SVG
    heap/stack buffer overflows".

2016-03-19  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - coders/psd.c (ReadPSDImage): Fix SourceForge bug #341
    "out-of-bounds read in coders/psd.c:1435".
    (WriteWhiteBackground): Fix SourceForge bug #350 "SEGV in
    coders/psd.c:1685".
    (DecodeImage): Fix SourceForge bug #351 "heap-buffer-overflow in
    coders/psd.c:142".
    (ReadPSDImage): Fix SourceForge bug #342 "out-of-bounds write in
    coders/psd.c:892"

  - coders/xcf.c (load\_tile): Fix SourceForge bug #337
    "heap-buffer-overflow in coders/xcf.c:373".

  - coders/pict.c (WritePICTImage): Fix SourceForge bug #340
    "out-of-bounds write in coders/pict.c:1929".

  - coders/pdb.c (WritePDBImage): Fix SourceForge bug #348
    "heap-buffer-overflow in coders/pdb.c:949:26".

  - coders/xpm.c (ReadXPMImage): Fix SourceForge bug #334
    "heap-buffer-overflow in coders/xpm.c:150".

2016-03-09 Fojtik Jaroslav  <JaFojtik@seznam.cz>

  - coders/mat.c Fixed huge image limitation.

2016-03-06  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - coders/sun.c (WriteSUNImage): Fix SourceForge bug #343
    "out-of-bounds write in coders/sun.c:962".

  - coders/rle.c (ReadRLEImage): Fix SourceForge bug #344
    "out-of-bounds write in coders/rle.c:524".

  - coders/xpm.c (ReadXPMImage): Fix SourceForge bug #335
    "out-of-bounds read in coders/xpm.c:154 ".

2016-03-06  Glenn Randers-Pehrson  <glennrp@simple.dallas.tx.us>

  - doc/options.imdoc (-extent): Revised the example to
    clarify the interaction of -gravity with the "geometry" offsets.

2016-03-06  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - configure.ac: Add support for --enable-broken-coders which
    determines if broken or hazardous file format support should be
    enabled in the build.  Currently Adobe Photoshop (PSD) format is
    included in this category.

  - Rotate Changelog for new year.  Update documentation copyrights
    for new year.

2016-03-06  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - tiff/libtiff/tif\_config.h (HAVE\_SNPRINTF): Define HAVE\_SNPRINTF
    when using Microsoft Visual C++ 14 (Visual Studio 2015) or later.
    This is based on advice by Pablo Elpuro.

2016-02-21  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - Magick++/lib/Image.cpp (xResolution): New method to support
    setting the horizontal resolution with double precision.
    (yResolution): New method to support setting the vertical
    resolution with double precision.

  - www/Hg.rst: Document the ssh public keys for the server hosting
    the development Mercurial repository.

2016-02-16  Bob Friesenhahn  <bfriesen@simple.dallas.tx.us>

  - coders/xpm.c (ReadXPMImage): Fix SourceForge bug #333
    heap-buffer-overflow in coders/xpm.c:409.

