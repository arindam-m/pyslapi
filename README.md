# pyslapi
Python bindings for the official Sketchup API and an importer for blender based on them


# OSX Build info
INSTALL DEV TOOLS
1) Install Python3 from Python website (python.org)
2) Install Cython from shell:
   pip3 install Cython --install-option="--no-cython-compile"
   (replace by pip if needed)

3) Download Sketchup SDK https://extensions.sketchup.com/sketchup-sdk

BUILD
4) Copy LayOutAPI.framework and SketchUpAPI.framework from SDK directory to pyslapi
5) Build OSX/Windows version
   python3 setup.py build_ext --inplace
6) Run the two last lines of setup script manually
	install_name_tool -change @rpath/SketchUpAPI.framework/Versions/Current/SketchUpAPI @loader_path/SketchUpAPI.framework/Versions/Current/SketchUpAPI sketchup.cpython-37m-darwin.so
	install_name_tool -change @rpath/SketchUpAPI.framework/Versions/A/SketchUpAPI @loader_path/SketchUpAPI.framework/Versions/A/SketchUpAPI sketchup.cpython-37m-darwin.so

INSTALL
6) Copy the following files from pyslapi to SketchUp_Importer
  LayOutAPI.framework
  SketchUpAPI.framework
  sketchup.cpython-37m-darwin

7) Look the addon in Blender and enable it

