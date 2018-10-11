--------------------------------------------
Imlib 2 Essentials Library - IL2-S
--------------------------------------------

	Imlib 2 fork that aims to keep only essentials
	while adding some multi-thread friendly features.


	Notes regarding the original:
	
	* Made main Imlib2 functions thread safe.
	  Goal is to have all of them safe - requires testing.
	  Tested functions that are said to be thread safe:
	  il2s_create_cropped_scaled_image() and il2s_blend_image_onto_image().
	* Added progress callbacks with the cancel ability.
	* Image manipulation is still the same (2D arrays of 32-bit values, ARGB).
	* No global states - multi-thread requirement.
	* Dropped font processing routines - removes Freetype library dependency.
	* Dropped optional X11 suport - removes Xlib library dependency.
	* Dropped image loaders and removed plugins they depended on.
	  Imlib now cannot load image files on its own, external 
	  libraries should now be used instead.
	  Some basic image formats may be added in the future.
	* No internal image caching.
	* Only 64-bit architecture ATM., 32-bit to follow at some point
	  (original Imlib2 library supported both, of course).
	* Based on version: "imlib2-1.4.5"


	Prefix Conventions:

	* Uppercase prefix "IL2S_".
	  Used for: structures, types, enumerated types and defines.
	
	* Lowercase prefix "il2s_".
	  Used for interface functions and file names.


Build instructions
-----------------------

	* Unpack downloaded source code archive file.
	* Navigate to a subdirectory "projects/02_shared".
	* Make sure it contains "makefile" file.
	* Use command "make release" to compile and build.
	* If successful, binary file will be created in
	  the "projects/02_shared/bin/release" sub directory.
	  File name: "il2s.so".



Using the library
-----------------------
	
	Build all the source files.
	If building projects using precompiled shared library,
	include "il2s.so" durning the linking step.
	
	The only file to include for projects that use this 
	library is: "il2s_api.h". In essence, it does serve the same purpose as
	the "Imlib2.h" header found in the original.


References
------------------------

	Original Imlib2 library has been created by Carsten Haitzler
		https://www.enlightenment.org/
	
	List of all authors can be found in the attached AUTHORS file 
	in the "imlib2_references" sub directory.
	
	Original documentation can be found here: 
		https://docs.enlightenment.org/api/imlib2/html/

	Imlib2 License online version:
		https://spdx.org/licenses/Imlib2.html

