# HiDimVisualization
Clustering Chemical Compounds using LargeVis

Background

The data set is this thing called ugi*.  Smiles is a format that
describes the connections of a compound and looks like CCCNC(=O) which
means there is a Carbon C bound to another C to another C and to an
Nitrogen and back to a C but that last C is also double-bond connected
to an oxygen.  Essentially these are a complete descriptor for a
chemical structure and I've shown a few in sampleCompounds.jpg.

We have taken a compound structure with a few "R-groups" that are like
variables.  We have plugged all sorts of different compounds in for
each of the R-groups that are kind of like variables.  This has
generated a large "library" of compounds.

Computation Begins...

Compounds are pretty and what not, but they don't lend themselves to
machine learning or visualization.  For that, we need descriptors.  We
can take general counts like the #carbon, #oxygen, etc. but it's not
enough--we want the connectivity at least.  In some cases, we want to
have full 3D descriptors.  We have generated descriptors called
"fingerprints" and these are the increasing integers in the
*Properties.csv and a different kind in the ECFP (extended
connectivity fingerprint).  These are a concise way of writing the
list of structural features or connections that exist.  So, a
45,53,101,137... is the equivalent of saying feature1-no, feature2-no,
...feature44-no, feature45-yes, feature46-no,...feature53-yes, etc.

For generating the properties, we broke the 100000 entries into 4
(a,b,c,d) files.

Calculating distances

The standard approach for fingerprints is using the Tanimoto distance
which is defined as the intersection/union so it's a score between 0
and 1.  The Euclidian distance is occasionally used but mostly when it
has a particularly nice property in some math equations.  Both are
official distance metrics.

Distance --> Visualization

If we have the distance between entries, then we can cluster the
results and we should be able to come up with some form of
visualization using something like Largevis.  Let's start with that
code.  I have included the link (https://github.com/lferry007/LargeVis) and the paper.  The first
step will be trying with the first 100 and creating a view using this
software.  We'll then raise the number and see how far we can go.  If
you are stuck for computation and your computer is smoking, we can run
code here as well.

Peter Henstock

Senior Data Scientist, Pfizer

Lecturer, Harvard University Extension School

03/02/2018
