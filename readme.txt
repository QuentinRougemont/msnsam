This version is the October 2007 version of the ms code with the added ability to include the number of samples (nsam) as a tbs argument. Please see Hudson's website for details on ms as well as installation instructions, but please email me for questions or bug reports, as bugs are likely mine and NOT part of the original code.

The primary motivation for this is to allow efficient simulation of datasets with unequal sampling across loci. Running this version of ms using sample size as a tbs argument appears to be much faster than running an independent ms run for each of many loci.

Please cite the following two papers if using this code (and I’d love an email just to know it’s being used!):

Hudson, R. (2002) Generating samples under a Wright-Fisher neutral model of genetic variation. Bioinformatics, 18, 337–338

Ross-Ibarra J, Wright SI, Foxe JP, Kawabe A, DeRose-Wilson L, et al. 2008. Patterns of Polymorphism and Demographic History in Natural Populations of Arabidopsis lyrata . PLoS ONE 3(6): e2411

Documentation

Uncompress the download, then run the installer script using "./clms" from within the msnsam directory (requires you have gcc installed). This should create three new files: msnsam, samplestats, and mean_std. The latter two are useful for calculating summary statitics and mean and sd from ms-style output (an example use of samplestats can be found here). For details on these two programs, please read the ms manual.

msnsam works exactly like the tbs feature of the normal ms program (as documented in the ms manual). An example tbsfile, example_tbs, is included in the msnsam directory. An example run using this file would be:

"./msnsam tbs 3 -t tbs -r tbs tbs -eN 0.25 0.05 < example_tbs"

which simulates a reduction in population size to 0.05*N which occured N generations in the past for 3 loci.

The example_tbs file reads:

10 5 3.9 1000
12 5.2 4.1 1200
16 4.6 5.6 1250

which, with the above command line, would simulate 3 loci of sample size 10, 12, and 16 (first column). The second column is the value of θ for each locus, the third column is the value of ρ, and the fourth column is the length of each locus in bp. 

