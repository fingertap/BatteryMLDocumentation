Quick Start
===========

Installation
------------

Install dependencies.

.. code-block:: bash
    pip install batteryml --upgrade

Predicting Battery Lifespan using Early Cycle Data
--------------------------------------------------

Download public data.

.. code-block:: bash
    curl 

Preprocess the data into ``BatteryData`` format, which records the complete cycling information of a battery cell. ``BatteryData`` provides a unified and easy-to-extend interface to deal with historical battery cycling data. Checkout the :doc:`data` section for further detail, and have a look at :ref:`data`

.. code-block:: 
    python process

Now you should see the batteries organized in the folder ``data/processed/MATR``, each battery corresponding to one ``pkl`` file.
Let's check one of the batteries.

.. code-block:: python3
    import pandas as pd

You can see that the capacity of this battery soon drops.

Now let's prepare these batteries for cycle life prediction.

.. code-block:: python3
    import numpy as np

Here we used the labeler for cycle life prediction and the features proposed by Severson et al., which we already implemented in **BatteryML**. Finally, we fit a simple linear regression model on this dataset, which should reproduce the Severson's results.


Using Pipeline
--------------

In **BatteryML**, we abstracted the interfaces of data and models to allow consistent IO formats. With this feature, we further provide a way to use **BatteryML** based on config file, allowing us to avoid the boilerplate code that organizes dataset and learning process. For example, we can use the following config to obtain exactly the same results as the previous example.

.. code-block:: yaml
    - hello: world

Next Steps
----------

We have walked through a basic example using **BatteryML** for battery degradation modeling. We encourage you to first have a deeper look at the ``BatteryData`` class and then have a try on different battery modeling tasks before developing your own models upon the existing datasets and methods.
