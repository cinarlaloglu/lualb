# Introduction #

In 2D version of LuaLB, they visualize the scalar quantities (total density or order parameter) in the PNG image files. It means that we do need any additional software to process our simulation data. For 3D version, LauLB store the data in [HDF5](http://hdf.ncsa.uiuc.edu/HDF5/) format. This may be possible to be visualized with any software that supports HDF5 format i.e. [OpenDX](http://www.opendx.org/). We may visualize our data by using the [Visualization ToolKit (VTK)](http://www.vtk.org/) software i.e. MayaVi([1](http://mayavi.sourceforge.net/),[2](https://svn.enthought.com/enthought/wiki/MayaVi)) and [ParaView](http://www.paraview.org) by exporting HDF5 to VTK format. We will learn how to visualize our 3D data with VTK in the next section.


# Converting HDF5 to VTK #

To convert HDF5 to VTK, we need `h5tovtk` utility program included in [h5utils](http://ab-initio.mit.edu/wiki/index.php/H5utils). Please download and in install the h5utils which contains installation guide form [its page](http://ab-initio.mit.edu/wiki/index.php/H5utils)

To use h5tovtk, type:

```
$h5tovtk file.h5
```

This will automatically generate all dataset in `file.h5` to VTK with file name `file.vtk`. If you want to export only one dataset, please use this command:

```
$h5tovtk -d dataset_name file.h5
```

You can view all dataset using command:

```
$h5ls file.h5
```

Now you can use MayaVi([1](http://mayavi.sourceforge.net/),[2](https://svn.enthought.com/enthought/wiki/MayaVi)) or [ParaView](http://www.paraview.org) open the exported VTK file.