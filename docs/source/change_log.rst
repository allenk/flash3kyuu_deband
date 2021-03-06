Change log
----------

2.0.0
*****

* Support Vapoursynth natively

* New parameter: preset

* C++ API support

* Dropped YUY2 support, please process in YV16 instead

* Dropped f3kdb_dither, please use ``f3kdb(preset="depth", ...)`` for bitdepth conversion

* Dropped several deprecated parameter values

1.5.1 (2012-04-07)
******************

* Supports setting StdDev (sigma) for the Gaussian random number generator

1.5.0 (2012-03-12)
******************

* (There isn't any new feature in this version, only some parameters are
  modified to reduce user confusion)

* ditherY/ditherC are renamed to grainY/grainC

* dynamic_dither_noise is renamed to dynamic_grain

* precision_mode is renamed to dither_algo, mode 4 and 5 are removed

* random_algo_dither is renamed to random_algo_grain

* enable_fast_skip_plane is removed, this optimization will be enabled
  implicitly whenever possible (Filter result won't be changed by this
  optimization)

1.4.2 (2011-11-10)
******************

* Fixed crash on some non-mod16 videos

1.4.1 (2011-11-05)
******************

* Fixed broken YUY2 support (still slow)

* Improved default value handling of bitdepth-related parameters

* precision_mode 4 / 5 are now deprecated and may be removed in future versions,
  you can use output_mode 1 / 2 to achieve the same result
 
1.4.0 (2011-10-30)
******************

* 9 ~ 16 bit-depth input/output

  * Related parameters: input_mode/input_depth/output_mode/output_depth

* New random number generator, reference position and dither noise can be generated in uniform or gaussian distribution

  * Related parameters: random_algo_ref / random_algo_dither

* diff_seed is replaced with dynamic_dither_noise, when enabled, noise pattern will be different for each frame

* Another new parameter: enable_fast_skip_plane

* Short filter alias: f3kdb

* Now the ICC-compiled DLL should be runnable on pre-SSE2 systems (untested)

* Several bug fixes

1.3.0 (2011-09-07)
******************

* Added x64 version

* Added a downsample filter: f3kdb_dither

* Internal precision is increased to 16bit

* New parameter: keep_tv_range, please see readme.txt for details

* Default sample_mode is changed to 2 as it is better in most cases

* Fixed: Floyd-Steinberg dithering may produce incorrect result for full-range videos

* Fixed: Broken YUY2 debanding

* Minor optimizations
  
1.2.0 (2011-08-01)
******************

* Added support for YUY2 (not optimized yet)

* Added support for all planar YUV format in AviSynth 2.6

* The filter is now compatible with both AviSynth 2.5 and 2.6

* 16bit output (precision_mode = 4/5)

  * Note: The internal processing precision is still 14bit, this will be improved in future versions
 
1.1.0 (2011-06-18)
******************

* Fixed a bug that high threshold values would produce incorrect result in
  high precision modes.

* Threshold values was scaled based on other parameter in previous versions,
  it is unscaled now to increase flexibility. Using same value has weaker
  effect in new version. Effect of default parameter set is also changed.

* SSE optimization for high precision mode.

* Rejects some invalid parameter combination instead of silently skips them

1.0.2 (2011-06-06)
******************

* High precision mode

  * (currently non-optimized, SSE routine will be added later)

* Frame edges are properly processed now

* Fix crash in some cases (unaligned frames are handled correctly)

* Other bug fixes

1.0.1 (2011-05-27)
******************

* Multi-threaded processing

* Skip planes which threshold is 0

1.0.0 (2011-05-21)
******************

* Lots of bug fix

* SSE optimization, massive speed up

0.9.1 (2011-05-05)
******************

* Fix: Incorrect results when blur_first=true

0.9 (2011-05-04)
******************

* Initial release
