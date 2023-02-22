Uploading reads or assembled genomes
====================================

If you have fastq files of reads for an isolate, you can upload them to Vibriowatch to make an assembly for your isolate.

Alternatively, if you already have an assembly for your isolate, you can upload the assembly to Vibriowatch.

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

The sizes of the files in Mbyte are given in the left column.

If the zipped fastq files are each :math:`<` 500 Mbyte in size, then they are fine for Vibriowatch to accept.

If your zipped fastq files of reads are :math:`>` 500 Mbyte in size, you could either (i) sample a smaller set of the reads in the files to give to Vibriowatch to make an assembly (the easier option), or (ii) alternatively you can make an assembly outside Vibriowatch using an assembly software (a more difficult option).

Uploading reads to Vibriowatch, to make an assembly 
---------------------------------------------------

To upload files to Vibriowatch, they need to have file-names ending in '_R1.fastq.gz' and '_R2.fastq.gz'.

If your files do not have file-names ending in '_R1.fastq.gz' and '_R2.fastq.gz', you will need to rename them using the Linux 'mv' command. For example, you can rename a file 'S1_R1_001.fastq.gz' to be called 'S1_R1.fastq.gz' by typing:

.. code-block:: console

   $ mv S1_R1_001.fastq.gz S1_R1.fastq.gz

Once your files have names ending in '_R1.fastq.gz' and '_R2.fastq.gz', you can upload them to Vibriowatch by going to the `Pathogenwatch`_ website.

.. _Pathogenwatch: https://pathogen.watch/

On the Pathogenwatch website, click on 'Upload' at the top right of the website:

.. image:: Picture1.png
  :width: 650
  
You will need to now sign into the Pathogenwatch website. To upload data to the Pathogenwatch website, it's necessary
to make an account first, for example, using your email address as your login. 

This will bring you to a webpage saying 'What would you like to upload?', and you need to click on 'FASTQ':

.. image:: Picture2.png
  :width: 500

You then need to click on the '+' button at the bottom right of the screen to upload your zipped fastq files:

.. image:: Picture3.png
  :width: 500
  
Then select all the zipped fastq files that you want to upload, for example, if you want to upload fastq files for 9 isolates:

.. image:: Picture4.png
  :width: 200
  
The Pathogenwatch website will then tell you that it is uploading your data, and when it has finished uploading it all, it will tell you that it is making assemblies for your isolates. The assembly process takes quite a while (e.g. roughly one hour for 10 isolates), and while it is running the website will give you a piechart showing its progress, for example:

.. image:: Picture5.png
  :width: 650
  
As soon as some of the genomes have been assembled, the piechart will show which species they have been recognised to be, and also will show how many analyses have been carried out on the assemblies (see to the left of the piechart), for example:

.. image:: Picture6.png
  :width: 650
  
We call the *Vibrio cholerae* component of Pathogenwatch 'Vibriowatch'. Vibriowatch carries out eight different analyses for each assembly:

# 1. Species identification.
# 2. AMR gene analysis.
# 3. cgMLST.
# 4. Core gene summary.
# 5. Inctyper (to find plasmids).
# 6. MLST.
# 7. Assembly statistics.
# 8. Virulence gene identification using the 'Vista' software.

We will explain all of these analyses later in the tutorial.

When Pathogenwatch has finished the analyses on all the isolates that it has assembled genomes for, the piechart will look something like this:

.. image:: Picture7.png
  :width: 650
  
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

