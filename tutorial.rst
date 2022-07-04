Tutorial
--------

Examples of how to read in a CDF file using Python
==================================================

`SpacePy <https://spacepy.github.io/>`_ provides a module called *pycdf* that facilitates reading in a CDF file. Once SpacePy module and `CDF library <https://spdf.gsfc.nasa.gov/>`_ have been installed properly, one can use

.. code:: python

   from spacepy import pycdf

   cdf = pycdf.CDF('solo_L2_swa-pas-vdf_20220403_V02.cdf')
   print(cdf)
   cdf.close()

This will show you the parameters and their dimensions as shown in Table 5.1.

Then, to read in the parameters, e.g., **epoch**

.. code:: python 

   time = cdf['Epoch'][...]
   print(time)

this gives a list of timestamps

.. code:: python 

   [datetime.datetime(2022, 4, 3, 0, 0, 2, 398445)
   datetime.datetime(2022, 4, 3, 0, 0, 6, 398452)
   datetime.datetime(2022, 4, 3, 0, 0, 10, 398459) ...
   datetime.datetime(2022, 4, 3, 23, 49, 58, 549214)
   datetime.datetime(2022, 4, 3, 23, 50, 2, 549221)
   datetime.datetime(2022, 4, 3, 23, 50, 6, 549228)]
