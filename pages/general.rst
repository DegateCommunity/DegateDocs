General
==================================

You will find here general documentation about workspace elements.

Logic model
~~~~~

The logic model represents the electrical logic of the project, where the majority of your work will be on. It's directly linked to the reconstruction of the netlist, which will pass by creating a list of used gates (with a behaviour defined, in Verilog for example), finding gate instances and interconnecting all electrical objects to then be able to retrieve the full netlist and be able to export it.

.. toctree::
   :maxdepth: 2
   :caption: Contents:

   general_dir/annotation
   general_dir/subproject
   general_dir/emarker
   general_dir/gate
   general_dir/via
   general_dir/wire