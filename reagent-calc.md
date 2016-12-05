# Calulations for reagent quantities needed  

#### Assumptions for reagent calculations  
1. want 50 probes per target fragment
* average probe fragment length (including adapters) is 393 basepairs (bp)
* 506,056 probe loci
* putting 1,000 copies of each target genome into the captures
* need at least one blocker fragment per library fragment
* genome size = 1.7 gigabasepairs (Gbp)

The calculations below assume the above values, but you can easily modify the values and redo the calculations.  

#### Calculation of mass of probes needed per hybridization
* Given 1 ng of probe solution at 393 bp average length of probe fragments (including adapters):
    * (1 ng · 6.022 · 10^23) / (393 bp · 650 · 10^9) = 2,357,408,495 DNA fragments in 1 ng
* From our MiSeq run of the RAD libraries, we have 506,056 loci.
    * So, how many DNA fragments per locus?
    * 2,357,408,495 DNA fragments / 506,056 loci = 4,658.394515 (fragments / locus) in 1 ng
* Total length of adapters attached to probes = 129 bp
* Average length of probe fragments without adapters = 393 bp - 129 bp = 264 bp
* We want at least 50,000 probes (probe fragments) per locus
    * 50,000 = 50 probes per copy of the genome * 1,000 copies of the genome
* 10.733 ng of probes with adapters attached = ((50,000 fragments/locus · 506,056 loci) · (393 bp probe fragments with adapters · 650 · 10^9)) / (6.022·10^23)
* 7.210 ng of probes without adapters attached = ((50,000 fragments/locus · 506,056 loci) · (264 bp probe fragments without adapters · 650 · 10^9)) / (6.022·10^23)

#### Calculation of mass of libraries needed per hybridization
For a modern sample sheared to average fragment size of 277 bp:  
* Given 1 ng of a library at 400 bp average length (including adapters)
    * (1 ng · 6.022 · 10^23) / (400 bp · 650 · 10^9) = 2,316,153,846 DNA fragments
    * average length of genomic DNA = (library length - TruSeq adapter length (65bp+58bp=123bp)) = 400 bp - 123 bp = 277 bp
* Genome size = 1,700,000,000 bp
* Number of double-stranded copies of genome in 1 ng amount = (277 bp average size · 2,316,153,846 DNA fragments) / 1,700,000,000 bp genome size = 377.3968326 copies of genome / 1 ng
* If we want 1000 copies of the genome per hybridization, what mass of the library do we need?
    * (1 ng · 1000 copies) / 377.3968326 copies = 2.6497 ng

For a modern sample sheared to average fragment size of 202 bp:  
* Given 1 ng of a library at 325 bp average length (including adapters)
    * (1 ng · 6.022 · 10^23) / (325 bp · 650 · 10^9) = 2,850,650,888 DNA fragments
    * average length of genomic DNA = (library length - TruSeq adapter length (65bp+58bp=123bp)) = 325 bp - 123 bp = 202 bp
* Genome size = 1,700,000,000 bp
* Number of double-stranded copies of genome in 1 ng amount = (202 bp average size · 2,850,650,888 DNA fragments) / 1,700,000,000 bp genome size = 338.7243996
* If we want 1000 copies of the genome per hybridization, what mass of the library do we need?
    * (1 ng · 1000 copies) / 338.7243996 copies = 2.9523 ng

For an historical sample with an average fragment size of 100 bp:  
* Given 1 ng of a library at 223 bp average length (including adapters)
    * (1 ng · 6.022 · 10^23) / (223 bp · 650 · 10^9) = 4,154,536,046.91 DNA fragments
    * average length of genomic DNA = (library length - TruSeq adapter length (65bp+58bp=123bp)) = 223 bp - 123 bp = 100 bp
* Genome size = 1,700,000,000 bp
* Number of double-stranded copies of genome in given ng amount = (100 bp average size · 4,154,536,046.91 DNA fragments) / 1,700,000,000 bp genome size = 244.3844
* If we want 1000 copies of the genome per hybridization, what mass of the library do we need?
    * (1 ng · 1000 copies) / 244.3844 copies = 4.092 ng

So, in general:  
* For a modern library sheared to an average fragment size around 250 bp, load 2.8 ng of the library for each hybridization.
* For a historic library with an average fragment size around 100 bp, load 4.1 ng of the library for each hybridization.

We could double or even multiply by 10 the amount of library and probes and be fine in terms of amount of blockers and beads that we're adding.  

#### Quantity of blocking oligos needed
* amount of blocking oligo supplied in the tube = 10 nmol
* manufacturer suggests resuspending to 1 nmol/µL
    * number of fragments in 1 nmol = 1 · (10^-9) · (6.022 · (10^23)) = 6.022E+14 fragments
* What if we resuspend to 0.05 nmol/µL ?
    * number of fragments in 0.05 nmol = 0.05 · (10^-9) · (6.022 · (10^23)) = 3.011E+13 fragments
* We need one blocker fragment per library fragment.
    * Overestimating, and assuming that we want 1,000 copies of the genome in the hybridization, then how many library fragments do we need of the libraries with the smallest average fragment length (historic, degraded DNA)?
        * Any libraries with larger average fragment lengths will have fewer total fragments for the same number of copies of the genome.
    * Please note that the below calculations assume a bird genome and the genome size for your project may differ, but you can use this as a model and tweak the number of copies of the genome to something that works for you and makes sense given the size of your organism's genome.
    * Bird genome size = 1.7 gigabasepairs (Gbp)
    * 1,000 copies of the genome = 1.7 terabasepairs
    * average fragment length of library = 100 bp
    * 1.7 terabasepairs / 100 bp = 17 Gbp
        * so, with our most numerous fragment library, we have 17,000,000,000 (17E+9) fragments in 1,000 copies of the genome.
* 1 µL of 0.05 nmol/µL blocking oligos gives 3.011E+13 blocking fragments
  * So, this amount of blocking oligo could block 1,000 copies of the genome how many times over?
  * 3.011E+13 blocking oligo fragments / 17E+9 genome fragments in 1,000 copies of the genome = 1771.176 times over
  * 17E+9 fragments in 1,000 copies of genome / [(10^-9) · (6.022 · (10^23))] = 0.00002823 nmole
  * In conclusion, we could add as little as 0.000028 nmole blocker per library captured for this experiment.
  * We were conservative and decided to add 0.1 nmole blocker / library
  * Your own calculations will change this number, but use this example as a model.

###### How many magnetic beads are needed?
* ds DNA binding capacity of beads is 20 µg/mg
* beads come at concentration of 10 mg/mL
    * 10 mg/mL = 10 mg / 1000 µL = 0.01 mg/µL
    * 1 µL · 0.01 mg/µL · 20 µg/mg = 0.2 µg
    * 1 µL of Dynabeads MyOne Streptavidin C1 beads will bind up to 200 ng dsDNA
* You probably only expect about 10% of the total ng amount library or pooled libraries to be of interest (bind to the probes).
* So, if you have 1,000 ng (1 µg) of library or pooled libraries in your capture reaction, you will only need enough beads to bind 100 ng of this.
* Theoretically, 1 µL of beads will be sufficient in this case.
    * We are adding plenty of excess beads by using 50 µL.
    * Keep in mind: The beads will bind fewer ng of longer DNA fragments.
