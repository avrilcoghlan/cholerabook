Uploading reads or assembled genomes
====================================

Checking if your fastq files of reads are suitable for Vibriowatch
------------------------------------------------------------------

If you have fastq files of reads for your isolate, you can upload the fastq files to Vibriowatch to make an assembly.

The maximum file size that Vibriowatch can accept for a zipped fastq file (that is, zipped with file names ending in .gz) is 500 Mbyte.

Usually you will have a pair of zipped fastq files for an isolate, with the forward and reverse reads respectively, called something like sample1_R1.fastq.gz and sample1_R2.fastq.gz.

If you have these files on a computer running Linux, you can find their sizes in Megabytes by typing in the terminal window:

.. code-block:: console

   $ du -h *fastq.gz
   
You will see something like this in your terminal window:

.. code-block:: console

   $ 160M    sample1_R1.fastq.gz
   $ 176M    sample1_R2.fastq.gz

If the zipped fastq files are each `<`500 Mbyte in size, then they are fine for Vibriowatch to accept.

If your zipped fastq files of reads are `>`500 Mbyte in size, you could either (i) sample a smaller set of the reads in the files to give to Vibriowatch to make an assembly (the easier option), or (ii) alternatively you can make an assembly outside Vibriowatch using an assembly software (a more difficult option).

Uploading reads to Vibriowatch, to make an assembly 
---------------------------------------------------



Creating recipes
----------------

To retrieve a list of random ingredients,
you can use the ``Vibriowatch.get_random_ingredients()`` function:

.. autofunction:: Vibriowatch.get_random_ingredients

The ``kind`` parameter should be either ``"meat"``, ``"fish"``,
or ``"veggies"``. Otherwise, :py:func:`Vibriowatch.get_random_ingredients`
will raise an exception.

.. autoexception:: Vibriowatch.InvalidKindError

For example:

>>> import Vibriowatch
>>> Vibriowatch.get_random_ingredients()
['shells', 'gorgonzola', 'parsley']

