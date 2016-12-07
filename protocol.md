# hyRADccg protocol  

* This markdown document can be printed for use at the bench with no formatting worries (such as lines spanning pages).
* The reagent-calc.md doc that is also in this repository details how we calculated the amounts of probes, blocking oligos, binding beads, and input library used in this protocol.

## Wetlab protocol  

### ddRAD library construction (for use in making probes)
Use the below protocol or your favorite other method for construction of a ddRAD library.  

### Double Digest
* Quantify extracted DNA using Qubit dsDNA High Sensitivity kit

* Prepare a 40 µl aliquot of DNA at concentration 12.5 ng/µl

* To this aliquot, add the following reagents:

Reagent	| x1  
----- | -----  
H20 | 2 µL  
10X NEB Cutsmart buffer | 5 µL 
MluCI (10000 U/ml)	|  2 µL
SphI (20000 U/ml)| 1 µL  
TOTAL |	50 µL  

* Pipette mix 5X

* Using a thermal cycler, incubate the reaction at 37°C for 3 hours
* Clean digested product using a Zymo DNA Clean & Concentrator™-5 column

#### Zymo DNA clean and concentrate  
* using DNA Clean & Concentrator™-5 columns (Zymo Research)  
    * https://www.zymoresearch.com/dna/dna-clean-up/pcr-dna-clean-up-concentration/dna-clean-concentrator-5
  
Protocol  
  
1. add 5X DNA Binding Buffer  
* 50 µL * 5 = 250 µL DNA Binding Buffer
* spin at 4000 x g for 3 min
* spin at 10,000 x g for 30 sec
* add 200 µL Wash Buffer
* spin at 10,000 x g for 1 min
* add 200 µL Wash Buffer
* spin at 10,000 x g for 1 min 30 sec
* transfer column to new tube
* add 30 µL 10 mM Tris-HCl (pH 8) (pre-heated to 65°C)  
* incubate at room temp 2 min
* spin at 10,000 x g for 1 min

* Quantify products using Qubit dsDNA High Sensitivity kit

### Ligation
In a PCR tube, prepare a 30 ul aliquot of digested DNA at concentration 4 ng/ul using sterile H20

To this aliquot, add the following reagents:

Reagent	| x1  
----- | -----   
10X NEB T4 DNA Ligase buffer | 4 µL 
10 uM PI adapter	|  2 µL
10 uM P2 adapter | 2 µL  
T4 Ligase | 2 µL
TOTAL |	40 µL  

* Pipette mix 5X
* Place rxn in thermal cycler and run the following program:

Step |	Temperature (°C) |	Time
---- | ---- | ----
1	| 37	| 30 min
2	| 65	| 10 min
3	| 65	| 1.5 min, decrease -2°C every cycle for 23 cycles
4	| 20	| hold

Perform standard 1.6X AmPure bead clean-up using the following protocol:
1. bring AmPure beads to room temperature
* mix beads well
* add 64 µL of beads to ligation rxn
* pipette mix 10X
* incubate at room temp for 10 min
* place rxn on magnetic plate for 2 min
* aspirate cleared solution from rxn and discard
* dispense 200 µL of 80% ethanol to sample
* wait 10 sec
* aspirate out the ethanol and discard
* repeat ethanol wash for a total of two washes
* ensure all ethanol is removed from sample
* place sample on magnetic rack in the fume hood to dry for 8 min
* remove sample from magnetic plate
* resuspend beads in 30 ul of 10 mM Tris-HCl (pH 8)
* pipette mix 10X
* place sample on magnetic plate for 2 min
* aspirate eluted DNA and transfer to 0.5 ml non-stick tube

Perform tight 325 bp target size selection using Blue Pippin 2% gel with marker V1

Proceed immediately to RT-PCR

Proceed immediately to RT-PCR

### KAPA HiFi polymerase amplification
* using HiFi Real-Time PCR Library Amplification Kit (Kapa Biosystems)  
    * https://www.kapabiosystems.com/product-applications/products/next-generation-sequencing-2/library-amplification/

KAPA real time PCR reaction mix  

Reagent	| x1
---- | ----
size selected Pippin product |	20 µL
H2O |	3 µL
KAPA HiFi HotStart Real-time PCR Master Mix (2X) |	25 µL
25 uM PCR1 primer |	1 µL
25 uM PCR2 indexed primer |	1 µL
TOTAL |	50 µL

### RT-PCR Reaction Conditions

Step |	Temp (°C) |	Time
---- | ---- | ----
(1)	| 98	| 45sec
(2)	| 98 |	15sec
(3)	| 65	| 30sec
(4)	| 72 |	30sec
plate read||
(5) |	72 |	10sec
(6)	| Go to (2)

* Run the PCR as many cycles as it takes for amplification to max out (plateau)
* Once the amplification graph shows RFU plateau, wait until step (5) to pause or cancel the run at 70°C and remove samples

### Whole-genome library construction (for captures)
Use the below protocol or your favorite other method that yields whole-genome libraries with indexed Illumina adapters.  

### Biotin Nick Labeling  
* using BioNick™ DNA Labeling System (Thermo Fisher Scientific)  
    * https://www.thermofisher.com/order/catalog/product/18247015
  
Labeling Recipe  

Reagent	| x1  
----- | -----  
10X dNTP Mix | 5 µL  
DNA | up to 1 µg  
H2O	|  
10X Enzyme Mix | 5 µL  
TOTAL |	50 µL  

1. mix well  
* centrifuge briefly (15,000 x g for 5 sec)  
* ensure heated lid is 10°C over incubation temperature  
* incubate at 16°C for 1.5 hours 
* add 10 µL Stop Buffer  
* clean reactions using Zymo Clean & Concentrator protocol below

#### Zymo DNA clean and concentrate  
* using DNA Clean & Concentrator™-5 columns (Zymo Research)  
    * https://www.zymoresearch.com/dna/dna-clean-up/pcr-dna-clean-up-concentration/dna-clean-concentrator-5
  
Protocol  
  
1. add 5X DNA Binding Buffer  
* 50 µL * 5 = 250 µL DNA Binding Buffer
* spin at 4000 x g for 3 min (800 µL column capacity)
* spin at 10,000 x g for 30 sec
* add 200 µL Wash Buffer
* spin at 10,000 x g for 1 min
* add 200 µL Wash Buffer
* spin at 10,000 x g for 1 min 30 sec
* transfer column to new tube
* add 55 µL kit Resuspension Buffer (10 mM Tris-HCl + 0.1% TWEEN, pH 8.5) (pre-heated to 65°C)  
    * Could also elute with preheated 1X TE 10:1 buffer (10 mM Tris-HCl (pH 7.5), 1 mM EDTA)
    * or 1X TE 10:0.1 buffer (10 mM Tris-HCl (pH 7.5), 0.1 mM EDTA)
* incubate at room temp 2 min.
* spin at 10,000 x g for 1 min
* final eluted volume is ~53 µL
* keep cleaned product on ice
  * probes can be stored at -20°C in TE buffer for at least one year

#### Measure probe solution to get concentration with Qubit

X µL of probes at Qubit concentration (ng/µL) = Z ng probes

Add as many probes as you can given the amount of probes that you have, the number of hybridizations you want to do, and the amount of library that you have. We added 5-10 ng of probes to each hybridization.  

### Hybridization

#### Reagents needed
* 20X SSPE
* 50X Denhardt’s Solution
* 0.5M EDTA, pH 8.0
* 10% Sodium Dodecyl Sulfate (SDS)
* TS-p5 and TS-p7 xGen® blocking oligos (Integrated DNA Technologies)
  * https://www.idtdna.com/pages/products/nextgen/target-capture/xgen-blocking-oligos
* Chicken Hybloc™ DNA (Applied Genetics)
  * supplied at 500 µg quantities at 1mg/ml in T.E
  * http://www.appliedgenetics.com/products/hybloc-competitor-dna/
* 10% Sodium Dodecyl Sulfate (SDS)
* H2O (molecular biology grade)
* 0.1X SSC, 0.1% SDS
* 1 M NaCl  
* 10 mM Tris-HCl, pH 7.5  
* 1 mM EDTA  
* 10 mM Tris-HCl, 0.1 mM EDTA, pH 8.0
* Dynabeads® MyOne™ Streptavidin C1 beads (Thermo Fisher Scientific)
  * https://www.thermofisher.com/order/catalog/product/65001

#### Notes
* Ensure that the combination of tubes and thermal cycler allows no more than 15% volume evaporation over the hybridization period at hybridization temperature.  
* hybridize in 1.5 ml screw-cap tube with o-ring 

#### Hybridization Mix Recipe  
* This includes comparison with the final concentration of the reagents in the original hyRAD protocol and in the MyBaits protocol.  

Reagent |	x1 | Final conc in 121 µL	| original hyRAD protocol final concentration |	MyBaits protocol final concentration
---- | ---- | ---- | ---- | ----
20X SSPE | 54 µL |	8.93X |	8.60X |	9.47X
50X Denhardt’s Solution |	21 µL |	8.68X |	2.87X |	9.21X
0.5M EDTA, pH 8.0 |	3 µL |	0.0124 M |	0.0072 M |	0.0132 M
10% Sodium Dodecyl Sulfate (SDS) |	3 µL |	0.248% |	0.143% |	0.263%
probes (107 ng) at 2.68 ng/µL |	40 µL | | |
TOTAL |	121 µL | | |

* briefly vortex and centrifuge mix
* aliquot 20 µL Hybridization Mix to individual tubes (separate from blocker and library tubes)

#### xGen Blocking Oligos
* Depending on the library being hybridized, you will need to use the 6nt or 8nt p7 blocker from xGen. The Illumina LT adapters from the 1-12 set have a 6nt variable index area and the 13-24 set have a 8nt variable index area.

TS-p5 and TS-p7 (6nt Index) compatibility
* TruSeq LT Adapters 1–12
* NEB Adapters 1–12
* Bioo Adapters 1–6, 7–12, 13–24
* Any single-index adapter with a 6-nucleotide index

TS-p5 and TS-p7 (8nt Index) compatibility
* TruSeq LT Adapters 13–27
* NEB Adapters 13–27
* Bioo Adapters 96-index
* Any single-index adapter with an 8-nucleotide index

Dilution of xGen Blockers  
* IDT recommends resuspending blocking oligos in 10 mM Tris-HCl, 0.1 mM EDTA, pH 8.0.
* IDT also recommends resuspending blocking oligos to a final concentration of 1 nmole/µL and that we use 1 nmole of the oligos in each capture reaction.
* We are only adding 0.1 nmole blocker / library, though.

#### Blockers Mix Recipe - Individual Captures
To make pipetting easier, let's make a 1:20 dilution of an aliquot of our stock blocking oligos.
* take 1 µL of each oligo and add it to 19 µL 10 mM Tris-HCl, 0.1 mM EDTA, pH 8.0.
* This gives a final concentration of 0.05 nmole/µL.

Reagent	| x1
---- | ----
Chicken Hybloc (0.5 µg/µL) |	2 µL
xGen Universal Blocking Oligo -TS-p5 (0.05 nmole/µL) |	2 µL
xGen Universal Blocking Oligo -TS-p7 (0.05 nmole/µL) |	2 µL
TOTAL	| 6 µL

#### Blockers Mix Recipe - Pooled Captures
To make pipetting easier, let's make a 1:10 dilution of an aliquot of our stock blocking oligos.
* take 1 µL of each oligo and add it to 9 µL 10 mM Tris-HCl, 0.1 mM EDTA, pH 8.0.
* This gives a final concentration of 0.5 nmole/µL.

###### Pooling 7 samples
* We tried pooling up to 7 samples for a single capture reaction.  
* xGen Blockers: 0.1 nmole / sample * 7 samples = 0.7 nmole xGen blockers  

Blockers Mix Recipe - 7 Samples Pooled Capture  

Reagent |	x1
---- | ----
Chicken Hybloc (1 µg/µL) |	5 µL
xGen Universal Blocking Oligo -TS-p5 (0.5 nmole/µL)	| 1.4 µL
xGen Universal Blocking Oligo -TS-p7 (0.5 nmole/µL)	| 1.4 µL
TOTAL	| 7.8 µL

* aliquot 6 µL Blockers Mix to each tube
* add library to Blockers Mix aliquot, mix by pipetting up and down

###### Amount of capture libraries to add
* Want 7-10 µL of total volume of libraries.
* May need to evaporate excess liquid to concentrate the libraries.

#### Incubation
* Use heated thermal cycler lid for incubations (stay at 105°C or at least 10°C hotter than each step temperature).

Reaction Profile

Step |	Temperature (°C) |	Time
---- | ---- | ----
1	| 95	| 5 min
2	| 65	| 5 min
3	| 65	| hold

* As summarized above in the reaction profile:
  * incubate Blocker Mix + library in thermal cycler at 95°C for 5 min
    * Could also perform incubation in an oven with rotator, which may improve results
  * then let drop to 65°C for 5 min
  * pause program (thermal cycler holding at 65°C)
  * incubate Hybridization Mix at 65°C for 5 min (add tubes, close lid, resume program)
  * after completion of 5 minutes, leave all tubes in thermal cycler, and add each Hybridization Mix into each Blocker Mix + library, mix by pipetting up and down 5 times
    * use multichannel pipette for above step
    * can throw away tubes that held Hybridization Mix
  * hybridize (incubate at 65°C) for 24-40 hours

##### 1.5-2 hours before end of hybridization: prepare Wash and Binding Buffers
###### Prepare Wash Buffer
Wash Buffer Recipe

Reagent |	x33
---- | ----
10% Sodium Dodecyl Sulfate (SDS) |	400 µL
H2O	| 39.6 mL
0.1X SSC, 0.1% SDS |	10 mL
TOTAL	| 50 mL
* vortex thoroughly to mix
* heat Wash Buffer to 65°C (hybridization temperature) for at least 45 min before use

###### Binding Buffer Recipe  
1 M NaCl  
10 mM Tris-HCl, pH 7.5  
1 mM EDTA  
* it is efficient to make 45-50 mL of the Binding Buffer

###### Bead Preparation
* can prepare up to 160 µL of beads together in a 1.7 mL tube and multiply the wash and resuspension volumes accordingly
* for each capture reaction, aliquot 50 µL Dynabeads MyOne Streptavidin C1 beads to a low-bind tube
* place on magnetic particle collector (MPC) for 1-2 min until suspension clears
* with tubes on MPC, remove supernatant and discard
* add 200 µL Binding Buffer to each tube
* remove from MPC, vortex for 3 seconds, and briefly centrifuge
* place on MPC for 1-2 min until suspension clears
* with tubes on MPC, remove supernatant and discard
* perform two additional washes with 200 µL Binding Buffer to give a total of three washes
* finally, resuspend each washed bead aliquot in 70 µL Binding Buffer

#### Binding of Beads to Probes
1. heat bead aliquot to 65°C for at least 2 min (use heated lid in thermal cycler, at least 10°C above block temperature)
* transfer capture reaction to heated bead aliquot, pipette to mix
* incubate beads + captures at 65°C for 30 min, agitate every 5 min to keep beads in suspension (flick tube)

#### Bead Washing
1. place beads + captures on magnetic particle concentrator for 2 min
* remove supernatant
* add 500 µL Wash Buffer (heated to 65°C) to the beads (180 µL if using small tubes), vortex for 3 seconds, and briefly centrifuge
* incubate at 65°C for 10 min, agitate every 2-3 min to keep beads in suspension (flick tube and then briefly centrifuge)
* place on magnetic particle concentrator for 1-2 min until suspension clears
* remove supernatant
* perform two additional washes with 500 µL Wash Buffer (180 µL if using small tubes) for a total of three washes (perform four total washes if using small tubes)
* following the last wash and pelleting on the magnetic particle concentrator, remove as much liquid as possible without touching the bead pellet
* resuspend in 30 µL 10 mM Tris-HCl, 0.05% TWEEN (pH 8-8.5), pipette up and down to resuspend

### KAPA HiFi polymersae amplification
* using HiFi Real-Time PCR Library Amplification Kit (Kapa Biosystems)  
    * https://www.kapabiosystems.com/product-applications/products/next-generation-sequencing-2/library-amplification/

KAPA real time PCR reaction mix  

Reagent	| x1
---- | ----
final, cleaned, bead-bound libraries |	15 µL
H2O |	5 µL
KAPA HiFi HotStart Real-time PCR Master Mix (2X) |	25 µL
Library Amplification Primer Mix (10X) |	5 µL
TOTAL |	50 µL

###### rtPCR Reaction Conditions

Step |	Temp (°C) |	Time
---- | ---- | ----
(1)	| 98	| 45sec
(2)	| 98 |	15sec
(3)	| 60	| 30sec
(4)	| 72 |	30sec
plate read||
(5) |	72 |	10sec
(6)	| Go to (2) 44X |	 
(7) |	72 |	1min

* use as few cycles as possible to obtain sufficient molarity for sequencing
* pellet the beads in magnetic particle concentrator
* remove the supernatant
* purify it with Zymo Clean & Concentrator or AMPure beads (at 1.2X beads: DNA solution)

###### Zymo DNA clean and concentrate
* using DNA Clean & Concentrator™-5 columns (Zymo Research)  
    * https://www.zymoresearch.com/dna/dna-clean-up/pcr-dna-clean-up-concentration/dna-clean-concentrator-5
  
Protocol  
  
1. add 6X DNA Binding Buffer
* 50 µL * 6 = 300 µL DNA Binding Buffer
* spin at 4000 x g for 3 min
  * may need to perform multiple times as columns have a 800 µL capacity
* spin at 10,000 x g for 30 sec
* add 200 µL Wash Buffer
* spin at 10,000 x g for 1 min
* add 200 µL Wash Buffer
* spin at 10,000 x g for 1 min 30 sec
* transfer column to new tube
* add 25 µL kit Resuspension Buffer (10 mM Tris-HCl + 0.1% TWEEN, pH 8.5) (pre-heated to 65°C)
* incubate at room temp 2 min
* spin at 10,000 x g for 1 min
* final eluted volume is ~23 µL
* keep cleaned product on ice


### References
Peterson BK, Weber JN, Kay EH, Fisher HS, Hoekstra HE (2012) Double digest RADseq: an inexpensive method for de novo SNP discovery and genotyping in model and non-model species. PLoS ONE, 7, e37135.
