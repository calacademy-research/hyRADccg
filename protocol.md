# hyRADccg wetlab protocol  

* This markdown document can be printed for use at the bench with no formatting worries (such as lines spanning pages).
* The reagent-calc.md doc that is also in this repository details how we calculated the amounts of probes, blocking oligos, binding beads, and input library used in this protocol. 

Contents  
## 1. ddRAD RAD library & probe construction
### 1.1 Double Digest
### 1.2 Double Digest Zymo Clean-Up
### 1.3 Ligation
### 1.4 Ligation Bead Clean-Up  
### 1.5 Size Selection
### 1.6 RT PCR
### 1.7 PCR Clean-up Using Gel Excision
### 1.8 QC
### 1.9 Deadapterization
### 1.10 Deadapterization Bead Clean-Up
### 1.11 Probe Biotinylation  
### 1.12 Biotinylation Zymo Clean-Up  
### 1.13 QC 
## 2. Whole-genome Library Preps (for captures)
### 2.1 Covaris shearing (for modern samples only)
### 2.2 KAPA End Repair and A-tailing 
### 2.3 KAPA Ligation
### 2.4 KAPA Ligation Bead Clean-up
### 2.5 RT-PCR
### 2.6 PCR Bead Clean-up
### 2.7 QC
## 3.0 Hybridization
### 3.1 Prepare Hybridization Mix & Blockers Mix
### 3.2 Incubation
### 3.3 Prepare Wash & Binding Buffers
### 3.4 Dynabead Preparation
### 3.5 Bead Binding & Washing
### 3.6 RT-PCR
### 3.7 PCR Bead Clean-up
### 3.8 QC

## 1. ddRAD RAD library & probe construction
Use the below protocol or your favorite other method for construction of a ddRAD library.  

### 1.1 Double Digest
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


### 1.2 Double Digest Zymo Clean-Up
* using DNA Clean & Concentrator™-5 columns (Zymo Research)  
    * https://www.zymoresearch.com/dna/dna-clean-up/pcr-dna-clean-up-concentration/dna-clean-concentrator-5
  
Zymo Protocol:  
  
1. Transfer digested sample to 1.5 ml non-stick tube
* add 5X DNA Binding Buffer (50 µL * 5 = 250 µL DNA Binding Buffer)
* pipette mix 5X and transfer sample to Zymo Clean & Concentrator column
* spin at 4000 x g for 3 min
* spin at 10,000 x g for 30 sec
* discard flow-through
* add 200 µL Wash Buffer
* spin at 10,000 x g for 1 min
* add 200 µL Wash Buffer
* spin at 10,000 x g for 1 min 30 sec
* transfer column to new tube
* add 35 µL 10 mM Tris-HCl, pH 8 (pre-heated to 65°C)  
* incubate at room temp 3 min
* spin at 10,000 x g for 1 min
  * Quantify cleaned products using Qubit dsDNA High Sensitivity kit
  
### 1.3 Ligation
In a PCR tube, prepare a 30 µl aliquot of digested DNA at concentration 4 ng/µl using sterile H20

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

### 1.4 Ligation Bead Clean-Up
Perform standard 1.6X AmPure bead clean-up using the following protocol:  
  
1. bring AmPure beads to room temperature
* mix beads well
* add 64 µL of beads to ligation rxn
* pipette mix 10X
* incubate at room temp for 10 min
* place rxn on magnetic plate for 2 min
* aspirate cleared solution and discard
* dispense 200 µL of 80% ethanol to sample
* wait 10 sec
* aspirate out the ethanol and discard
* repeat ethanol wash for a total of two washes
* ensure all ethanol is removed from sample
* place sample (on magnetic rack) in the fume hood to dry for 8 min
* check that all ethanol has evaporated from the sample
* remove sample from magnetic plate
* resuspend beads in 30 µl of 10 mM Tris-HCl, pH 8
* pipette mix 10X
* place sample on magnetic plate for 2 min
* aspirate eluted DNA and transfer to 0.5 ml non-stick tube
  
### 1.5 Size Selection

Perform a tight 325 bp target size selection using Blue Pippin 2% gel with marker V1

Proceed immediately to RT-PCR


### 1.6 RT PCR
* using HiFi Real-Time PCR Library Amplification Kit (Kapa Biosystems)  
    * https://www.kapabiosystems.com/product-applications/products/next-generation-sequencing-2/library-amplification/
    
* pipette measure exactly how much product was collected from the Pippin
* divide this number in half and set up **two** PCR reactions per sample using the following recipe:

KAPA real time PCR reaction mix:

Reagent	| x1
---- | ----
size selected Pippin product* |	20 µL
H2O |	3 µL
KAPA HiFi HotStart Real-time PCR Master Mix (2X) |	25 µL
25 uM PCR1 primer |	1 µL
25 uM PCR2 indexed primer |	1 µL
TOTAL |	50 µL

RT-PCR Reaction Conditions:

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
* Once the amplification graph shows RFU plateau, wait until step (5) to pause or cancel the run at 72°C and remove samples
* Clean PCR product using gel excision with the Zymoclean Gel DNA Recovery kit

### 1.7 PCR Clean-up Using Gel Excision
* with Zymoclean DNA Recovery kit
    * https://www.zymoresearch.com/dna/dna-clean-up/gel-dna-recovery/zymoclean-gel-dna-recovery-kit
  
Excison Protocol:  
  
1. Run PCR product out on a 1% low melt agarose gel along with a 100 bp ladder
* Excise the PCR band using a sterile razor and place the gel slice in a 1.5 ml non-stick tube
* add 3 volumes of Buffer ADB to the tube
* incubate the tube at 50°C for 10 min to dissolve the gel slice
* transfer the melted gel sample to a Zymoclean DNA Recovery column
* spin at 10,000 x g for 30 sec
* discard the flow-through
* add 200 µL Wash Buffer
* spin at 10,000 x g for 30 sec
* add 200 µL Wash Buffer
* spin at 13,000 x g for 1 min 30 sec
* transfer column to new tube
* add 30 µL 10 mM Tris-HCl, pH 8 (pre-heated to 65°C)
* incubate at room temp 3 min
* spin at 10,000 x g for 1 min
 
### 1.8 QC
* Quantify products using Qubit dsDNA High Sensitivity kit
* Make a 1:20 dilution of RAD library in sterile H20
* Run 1 µL of this diluted product on Bioanalyzer using the High Sensitivity DNA kit
* Set aside at least 5 µL of RAD library and store at -20°C **(excess product that is set aside at this step may be used to generate more probes via PCR if needed in the future)**

### 1.9 Deadapterization

* Calculate out how many ngs of product you have
* Prepare as many deadapterization rxns that your product will allow for using the below recipe:

Reagent	| x1  
----- | -----  
H20 | var µL
10X NEB Cutsmart buffer | 5 µL 
MluCI (10000 U/ml)	|  3.30 µL
SphI (20000 U/ml)| 1.70 µL  
DNA | up to 1 µg 
TOTAL |	50 µL  

* Pipette mix 5X
* Quick spin

* Place in thermal cycler and run the following program:

Step |	Temperature (°C) |	Time
---- | ---- | ----
1	| 37	| 3 hours
2	| 65	| 20 min
3	| 8	| hold

### 1.10 Deadapterization Bead Clean-Up
Perform standard 1.5X AmPure bead clean-up using the following protocol:  
  
1. bring AmPure beads to room temperature
* mix beads well
* add 75 µL of beads to ligation rxn
* pipette mix 10X
* incubate at room temp for 10 min
* place rxn on magnetic plate for 2 min
* aspirate cleared solution and discard
* dispense 200 µL of 80% ethanol to sample
* wait 10 sec
* aspirate out the ethanol and discard
* repeat ethanol wash for a total of two washes
* ensure all ethanol is removed from sample
* place sample (on magnetic rack) in the fume hood to dry for 8 min
* check that all ethanol has evaporated from the sample
* remove sample from magnetic plate
* resuspend beads in 30 µl of 10 mM Tris-HCl, pH 8
* pipette mix 10X
* place sample on magnetic plate for 2 min
* aspirate eluted DNA and transfer to 0.5 ml non-stick tube
  
  

* Quantify products using Qubit dsDNA High Sensitivity kit
* Run 1 µL of this product on Bioanalyzer using the High Sensitivity DNA kit

### 1.11 Probe Biotinylation  
* using BioNick™ DNA Labeling System (Thermo Fisher Scientific)  
    * https://www.thermofisher.com/order/catalog/product/18247015
  
Labeling Recipe:

Reagent	| x1  
----- | -----  
10X dNTP Mix | 5 µL  
DNA | up to 1 µg  
H2O	|  var µL
10X Enzyme Mix | 5 µL  
TOTAL |	50 µL  

1. mix well  
* quick spin  
* ensure heated lid is 10°C over incubation temperature  
* incubate at 16°C for 1.5 hours 
* add 5 µL Stop Buffer  
* clean reactions using Zymo Clean & Concentrator protocol below

### 1.12 Biotinylation Zymo Clean-Up  
* using DNA Clean & Concentrator™-5 columns (Zymo Research)  
    * https://www.zymoresearch.com/dna/dna-clean-up/pcr-dna-clean-up-concentration/dna-clean-concentrator-5
  
Zymo Protocol:  
   
1. Transfer digested sample to 1.5 ml non-stick tube
2. add 5X DNA Binding Buffer (50 µL * 5 = 250 µL DNA Binding Buffer)
* spin at 4000 x g for 3 min
* spin at 10,000 x g for 30 sec
* discard flow-through
* add 200 µL Wash Buffer
* spin at 10,000 x g for 1 min
* add 200 µL Wash Buffer
* spin at 10,000 x g for 1 min 30 sec
* transfer column to new tube
* add 25 µL kit Resuspension Buffer (10 mM Tris-HCl, pH 8) (pre-heated to 65°C)  
* incubate at room temp 2 min.
* spin at 10,000 x g for 1 min
* keep cleaned product on ice
  * probes can be stored at -20°C in TE buffer for at least one year

### 1.13 QC 
* Quantify probe products using Qubit dsDNA High Sensitivity kit
* Run 1 µL of this product on Bioanalyzer using the High Sensitivity DNA kit

#### Calculating probe amount

X µL of probes at Qubit concentration (ng/µL) = Z ng probes

Add as many probes as you can given the amount of probes that you have, the number of hybridizations you want to do, and the amount of library that you have. We added ~ 100 ng of probes to each hybridization.  

## 2. Whole-genome Library Preps (for captures)
Use the below protocol or your favorite other method that yields whole-genome libraries with indexed Illumina adapters.  

* using KAPA Hyper Prep kit
	* https://www.kapabiosystems.com/product-applications/products/next-generation-sequencing-2/dna-library-preparation/kapa-hyper-prep-kits/
	
### 2.1 Covaris shearing (for modern samples only)
* For each sample, prepare a 130 µl aliquot of DNA at concentration 7.7 ng/µl in 10 mM Tris-HCl, pH 8
* Transfer sample to a Covaris microTUBE (AFA Fiber Snap-Cap)
* Use the following shear settings:


Setting	| value  
----- | ----- 
Peak Incident Power | 50
Duty Factor | 20%
Cycles per Burst | 200
Treatment Time | 200 sec
Temperature | 20°C

These settings produce sheared product in the range of 100 - 400 bps
* Run 20 ul of sheared product on a standard 1.5% agarose gel along with a 100 bp ladder to confirm size of sheared product

### 2.2 KAPA End Repair and A-tailing 
(refer to the detailed Technical Data Sheet supplied with the KAPA Hyper Prep kit)

* In a standard PCR strip tube, assemble the following per sample:

Reagent	| x1  
----- | -----   
Sheared DNA | 50 µl
End Repair and A-tail buffer | 7 µL 
End Repair and A-tail enzyme mix	|  3 µL 
TOTAL |	60 µL  

* Pipette mix 5X
* Quick spin
* Place in thermal cycler and run the following program:

Step |	Temp (°C) |	Time
---- | ---- | ----
(1)	| 20	| 30 min
(2)	| 65 |	30 min
(3)	| 8	| hold

### 2.3 KAPA Ligation
* To each End Repaired and A-tailed reaction, add the following:

Reagent	| x1  
----- | -----  
End Repaired & A-tailed product | 60 µL  
H20 | 5 µL  
Ligation Buffer | 30 µL
15 uM TruSeq indexed adapter* | 5 µL 
DNA Ligase	|  10 µL 
TOTAL |	110 µL  

* Pipette mix 5X
* Quick spin
* For modern samples, incubate the reaction at 20°C for 15 min
* For ancient samples, incubate the reactions at 20°C for 4 hours

### 2.4 KAPA Ligation Bead Clean-up
Perform standard 1.6X AmPure bead clean-up using the following protocol:  
  
1. bring AmPure beads to room temperature
* mix beads well
* add 64 µL of beads to ligation rxn
* pipette mix 10X
* incubate at room temp for 10 min
* place rxn on magnetic plate for 2 min
* aspirate cleared solution and discard
* dispense 200 µL of 80% ethanol to sample
* wait 10 sec
* aspirate out the ethanol and discard
* repeat ethanol wash for a total of two washes
* ensure all ethanol is removed from sample
* place sample (on magnetic rack) in the fume hood to dry for 8 min
* check that all ethanol has evaporated from the sample
* remove sample from magnetic plate
* resuspend beads in 30 µl of 10 mM Tris-HCl, pH 8
* pipette mix 10X
* place sample on magnetic plate for 2 min
* aspirate eluted DNA and transfer to 0.5 ml non-stick tube
  
  

### 2.5 RT-PCR
* using HiFi Real-Time PCR Library Amplification Kit (Kapa Biosystems)  
    * https://www.kapabiosystems.com/product-applications/products/next-generation-sequencing-2/library-amplification/

KAPA real time PCR reaction mix  
* Divide library product in half to allow for two PCR rxns per sample*

Reagent	| x1
---- | ----
KAPA Hyper DNA library product* |	20 µL
KAPA HiFi HotStart Real-time PCR Master Mix (2X) |	25 µL
KAPA Illumina Library Amplification Primer Mix (10X) |	5 µL
TOTAL |	50 µL

#### RT-PCR Reaction Conditions

Step |	Temp (°C) |	Time
---- | ---- | ----
(1)	| 98	| 45sec
(2)	| 98 |	15sec
(3)	| 60	| 30sec
(4)	| 72 |	30sec
plate read||
(5) |	72 |	10sec
(6)	| Go to (2) 44X	 
(7) |	72 |	1min

* Run the PCR as many cycles as it takes for amplification to reach between 3500 - 4000 RFU. This should take only ~ 5 cycles.
* Once the desired amplification level is met, wait until step (5) to pause or cancel the run at 70°C and remove samples
* Combine the sample replicates together and proceed to bead clean-up

### 2.6 PCR Bead Clean-up
Perform standard 1.0X AmPure bead clean-up using the following protocol:  
  
1. bring AmPure beads to room temperature
* mix beads well
* add an equal amount of beads to PCR rxn
* pipette mix 10X
* incubate at room temp for 10 min
* place rxn on magnetic plate for 2 min
* aspirate cleared solution and discard
* dispense 200 µL of 80% ethanol to sample
* wait 10 sec
* aspirate out the ethanol and discard
* repeat ethanol wash for a total of two washes
* ensure all ethanol is removed from sample
* place sample on magnetic rack in the fume hood to dry for 8 min
* remove sample from magnetic plate
* check that all ethanol has evaporated from tubes
* resuspend beads in 40 µl of 10 mM Tris-HCl (pH 8)
* pipette mix 10X
* place sample on magnetic plate for 2 min
* aspirate eluted DNA and transfer to 0.5 ml non-stick tube
  
### 2.7 QC
* Quantify products using Qubit dsDNA High Sensitivity kit
* Make a 1:5 dilution of each library in sterile H20
* Run 1 µl of diluted products on Bioanalyzer using the High Sensitivity DNA kit
   
For single sample captures:
  
* use between 100 - 150 ng of each library for hybridization
  
For pooled sample captures, do the following:
  
* Make an 18 ul working aliquot of each sample at 8.2 ng/ul in 10 mM Tris-HCl, pH 8
* Pool each of the 18 ul aliquots together
* Pipette mix 10X
* Use a speed vac to dry down the pooled sample to ~ 7-10 ul volume
* Use this pooled, concentrated sample for hybridization
  
## 3.0 Hybridization

#### Reagents needed
* 20X SSC
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
* 10 mM Tris-HCl, pH 8
* 1 mM EDTA  
* 10 mM Tris-HCl, 0.1 mM EDTA, pH 8.0
* Dynabeads® MyOne™ Streptavidin C1 beads (Thermo Fisher Scientific)
  * https://www.thermofisher.com/order/catalog/product/65001

#### Other Notes
* Before starting make sure ** bench top incubator ** (w/ rotator inside) is set to 55°C
* Also be sure one ** tube incubator ** is set to 55°C and the other is set to 95°C
* Perform captures in ** 1.5 ml screw-cap tubes with o-ring ** 

### 3.1 Prepare Hybridization Mix & Blockers Mix

#### Hybridization Mix Recipe
* This includes comparison with the final concentration of the reagents in the original hyRAD protocol and in the MyBaits protocol.  

Reagent |	x1 | Final conc in 121 µL	| original hyRAD protocol final concentration |	MyBaits protocol final concentration
---- | ---- | ---- | ---- | ----
20X SSC | 54 µL |	8.93X |	8.60X |	9.47X
50X Denhardt’s Solution |	21 µL |	8.68X |	2.87X |	9.21X
0.5M EDTA, pH 8.0 |	3 µL |	0.0124 M |	0.0072 M |	0.0132 M
10% Sodium Dodecyl Sulfate (SDS) |	3 µL |	0.248% |	0.143% |	0.263%
probes (~ 100 ng)  |	~ 40 µL | | |
TOTAL |	~ 121 µL | | |

* briefly vortex and centrifuge mix
* Note: white precipitate will form in Hyb Mix prior to addition of probes. Heat mix @ 65°C for 2 min for precipitate to dissolve. Bring back to room temp before adding probes.

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

### 3.2 Incubation
* Use tube incubators for incubations

Reaction Profile

Step |	Temperature (°C) |	Time
---- | ---- | ----
1	| 95	| 5 min
2	| 55	| 5 min
3	| 55	| hold

* As summarized above in the reaction profile:
  * incubate Blocker Mix + library at 95°C for 5 min
  * incubate Blocker Mix + library at 55°C for 5 min
  * incubate Hybridization Mix at 55°C for 5 min
  * after completion of 5 minutes, leaving tubes in the incubators, quickly add each Hybridization Mix into each Blocker Mix + library
    * ensure cap is  screwed tightly on hybridization tube
* quickly transfer tube to tube rotator in pre-heated incubator 
* Snap tube into place and turn on rotator 
* Close glass door, cover with foil, and tape door shut
  * hybridize (incubate at 55°C) for 65-72 hours

##### 1.5-2 hours before end of hybridization: turn on one tube incubator to 65°C and one to 80°C & prepare Wash Buffer

### 3.3 Prepare Wash & Binding Buffers

###### Wash Buffer Recipe:

Reagent |	x33
---- | ----
10% Sodium Dodecyl Sulfate (SDS) |	400 µL
H2O	| 39.6 mL
0.1X SSC, 0.1% SDS (= MyBaits Wash Buffer #2)|	10 mL
TOTAL	| 50 mL
* vortex thoroughly to mix
* heat Wash Buffer to 65°C (hybridization temperature) for at least 45 min before use

###### 2X Binding Buffer Recipe:  
2 M NaCl  
10 mM Tris-HCl, pH 7.5  
1 mM EDTA  
0.5% Tween
* it is efficient to make 45-50 mL of the Binding Buffer

* bring Dynabeads to room temp and bring aliquot of AmPure beads to room temp

### 3.4 Dynabead Preparation

To wash Dynabeads:  

1. for each capture reaction, aliquot 50 µL Dynabeads MyOne Streptavidin C1 beads to a 1.5 ml non-stick tube
* place on magnetic plate for 2 min until suspension clears
* aspirate out supernatant and discard
* add 200 µL 1X Binding Buffer to each tube
* remove samples from magnetic plate, vortex for 3 seconds, and pulse spin
* place on magnetic plate for 2 min until suspension clears
* aspirate out supernatant and discard
* perform ** two **  additional washes with 200 µL 1X Binding Buffer to give a total of ** three ** washes
* finally, resuspend each washed bead aliquot in 70 µL 2X Binding Buffer - DO NOT pipette mix. Add buffer, gentle vortex and pulse spin  
  

### 3.5 Bead Binding & Washing

#### Binding of Beads to Probes
1. heat bead aliquot to 65°C for at least 10 min (use tube incubator)
* transfer capture reaction to heated bead aliquot, invert tube to mix
* incubate beads + captures at room temp for 30 min on nutator

#### Bead Washing
1. quick spin
2. place beads + captures on magnetic particle concentrator for 2 min
* remove supernatant
* add 500 µL Wash Buffer (heated to 65°C) to the beads (180 µL if using small tubes), vortex for 3 seconds, and briefly centrifuge
* incubate at 55°C for 10 min, in incubator on rotator
* place on magnetic stand for 1-2 min until suspension clears
* remove supernatant
* perform two additional washes with 500 µL Wash Buffer (180 µL if using small tubes) for a total of three washes (perform four total washes if using small tubes)
* following the last wash and pelleting on the magnetic particle concentrator, remove as much liquid as possible without touching the bead pellet
* resuspend in 30 µL 10 mM Tris-HCl, 0.05% TWEEN, pH 8 (pre-heated to 80°C)
* gentle vortex and incubate for 10 min at 80°C, quick spin before magnetizing

### 3.6 RT-PCR
* using HiFi Real-Time PCR Library Amplification Kit (Kapa Biosystems)  
    * https://www.kapabiosystems.com/product-applications/products/next-generation-sequencing-2/library-amplification/

KAPA real time PCR reaction mix  

Reagent	| x1
---- | ----
final, cleaned, bead-bound libraries |	15 µL
H2O |	5 µL
KAPA HiFi HotStart Real-time PCR Master Mix (2X) |	25 µL
KAPA Illumina Primer Mix (10X) |	5 µL
TOTAL |	50 µL

RT-PCR Reaction Conditions:

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
* purify with AMPure beads

  
### 3.7 PCR Bead Clean-up

Perform standard 1.0X AmPure bead clean-up using the following protocol:  
  
1. bring AmPure beads to room temperature
* mix beads well
* add an equal volume of beads to PCR rxn
* pipette mix 10X
* incubate at room temp for 10 min
* place rxn on magnetic plate for 2 min
* aspirate cleared solution and discard
* dispense 200 µL of 80% ethanol to sample
* wait 10 sec
* aspirate out the ethanol and discard
* repeat ethanol wash for a total of two washes
* ensure all ethanol is removed from sample
* place sample (on magnetic rack) in the fume hood to dry for 8 min
* check that all ethanol has evaporated from the sample
* remove sample from magnetic plate
* resuspend beads in 30 µl of 10 mM Tris-HCl, pH 8
* pipette mix 10X
* place sample on magnetic plate for 2 min
* aspirate eluted DNA and transfer to 0.5 ml non-stick tube
  
### 3.8 QC
* Quantify products using Qubit dsDNA High Sensitivity kit
* Make a 1:5 dilution of each library in sterile H20
* Run 1 µl of diluted products on Bioanalyzer using the High Sensitivity DNA kit 




### References
Peterson BK, Weber JN, Kay EH, Fisher HS, Hoekstra HE (2012) Double digest RADseq: an inexpensive method for de novo SNP discovery and genotyping in model and non-model species. PLoS ONE, 7, e37135.
