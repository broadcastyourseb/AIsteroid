# AIsteroid

This project is aimed at automatizing the process of searching for
asteroids in image sets provided by observatories.

Let's suppose for instance that you have the following set of
observations (credit:
[Pan-STARRS](https://panstarrs.stsci.edu/)/[IASC](http://iasc.hsutx.edu/)):

![alt text](https://raw.githubusercontent.com/seap-udea/AIsteroid/master/images/example-raw.gif)

How many moving objects do you dectect in this image? 

If your answer is one, you are a good obsever.  However, if you see
between 1 and 3 objects, you seem to have a trained eye.  But if you
see 4, probably you are a machine! (to see the actual number of moving
objects see the image in [this
link](https://raw.githubusercontent.com/seap-udea/AIsteroid/master/images/example-detection.gif)).

This is precisely the purpose of **AIsteroid**. 

Searching for moving objects in a noisy images (most astronomical
images are very noisy) is a task normally intended for human
brains. With our super-power to notice small changes in visual
patterns, the task is very well suited for us. This is the way as most
of the asteroids have been discovered in the past and are being
discovered today.

With the advent of powerful computers and clever computational
algorithms such as those belonging to the broad class of **artificial
intelligence** (neural networks, decision trees, deep learning, etc.),
we can now teach machines to perform this kind of task.

In this simple package you will find a series of python scripts (and
ipython notebooks) intended to automatize the searching process, not
for replacing entirely the role of humans, but at least for ease this
process.

Quickstart
----------

If you already have the package and its dependencies (see section
Installation below) the automatized detection is performed in three
simple steps:

1. Get an image set.  They are normally provided in the form of a zip
   file containing 4 or more images in FITS format.  The package is
   provided with at least one image set (``data/sets/example.zip``).
   Sets must be installed in the ``data/sets/`` directory.

2. Provide a configuration file for the observations.  This file is in
   the format of [astrometrica](http://www.astrometrica.at).  The
   package is provided with an example file,
   ``data/sets/example.cfg``, corresponding to Pan-STARRS telescope.

3. Edit the configuration file, ``aisteroid.cfg``:

   ```
      SET="example" #Name of the zip file containing the observation set
      CFG="example" #Name of the configuration file
      TEAM="NEA" #Name of the team performing the observations
   ```

4. Run the astrometry procedure:
   
   ```
   python astometry.py
   ```
   
5. Run the detection procedure:

   ```
   python detect.py
   ```

5. Run the photometry procedure:

   ```
   python photometry.py
   ```
   
6. Create a MPC report:

   ```
   python report.py
   ```
   
If your are confident of your data you may perform the whole procedure
at once using:

```
make aisteroid
```

And voilà!  Your asteroid must be detected!

Downloading and installating
----------------------------

