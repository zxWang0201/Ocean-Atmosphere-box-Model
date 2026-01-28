# Ocean-Atmosphere-box-Model
This project implements five ocean–atmosphere box models to estimate the partitioning of noble gases and major atmospheric gases between the ocean and atmosphere under modern and Last Glacial Maximum (LGM) conditions.

The models are designed to evaluate changes in atmospheric gas ratios (e.g., dAr/N2, dKr/N2) caused by ocean volume change, temperature/salinity variations, and surface pressure changes during LGM periods.

---

## Requirements

- Python  
- Standard libraries:
  - math  

- Custom modules:
  - O2.py  
  - N2.py  
  - Ar.py  
  - Kr.py  

These modules must provide gas solubility as a function of temperature and salinity.

---

## Scientific Background
 
The gas dissolved in the sea water is related to:

- Ocean temperature and salinity  
- Ocean volume reduction due to ice-sheet growth  
- Surface pressure changes associated with sea-level lowering  

The total amount of each gas (O2, N2, Ar, Kr) is conserved between the ocean and atmosphere.  
Changes in ocean temperature, salinity, volume, and surface pressure during the LGM are used to estimate the redistribution of gases.

Main processes included:
- Gas solubility dependence on temperature and salinity  
- Ocean volume and Surface pressure change

---

## Model Framework

One box model and all Gas solubility functions are needed 

### box models

- 1box_model 
- 3box_model_uniform  
- 3box_model_AABW_non_freezing  
- 3box_model_AABW expand_uniform
- 3box_model_AABW expand_non_freezing

### Gas solubility functions

- O2  (F. H. Garcia and I. I. Gordon, “Oxygen Solubility in Seawater: Better Fitting Equations,”Limnology and 	Oceanography, Vol. 37, No. 6, 1992, pp. 1307-1312. doi:10.4319/lo.1992.37.6.1307)
- N2  (Roberta C. Hamme, Steven R. Emerson,solubility of neon, nitrogen and argon in distilled water and 	seawater,Deep Sea Research Part I: Oceanographic Research Papers,Volume 51, Issue 11,2004,Pages 	1517-1528,ISSN 0967-0637,https://doi.org/10.1016/j.dsr.2004.06.009.)
- Ar   (Roberta C. Hamme, Steven R. Emerson,solubility of neon, nitrogen and argon in distilled water and        	seawater,Deep Sea Research Part I: Oceanographic Research Papers,Volume 51, Issue 11,2004,Pages 	1517-1528,ISSN 0967-0637,https://doi.org/10.1016/j.dsr.2004.06.009.)
- Kr   (Weiss, R.F.; Kyser, T.K. Solubility of krypton in water and sea water.J. Chem. Eng. Data 1978, 23,69–72,  https://doi.org/10.1021/je60076a014.)

---

## Model Description

This project includes five model configurations:

### 1. 1box_model (`a. 1box_model.py`)

**Description**

- One global atmosphere box 
- One global ocean box   
- The entire ocean is assumed to be homogeneous 
- temperature is assumed to decrease uniformly

**Purpose**

- Provide an estimate of ocean–atmosphere gas redistribution  in LGM period

**Main characteristics**

- Single ocean temperature and salinity  
- Single ocean volume  
- Diagnostic equilibrium solution of gass solubility

**Output**

For each temperature step, the model prints:
- dAr/N2
- dKr/N2
- Remaining atmospheric N2 (mol)
- *Users can select Oxygen-related diagnostic variables to output by modifying the '#result' section

---

### 2. 3box_model_uniform (`b. 3box_model_uniform.py`)

**Description**

- One global atmosphere box 
- Three global ocean boxes  (AABW, NADW, and the residual ocean (res) )  
- temperature is assumed to decrease uniformly

**Purpose**

- Provide an estimate of ocean–atmosphere gas redistribution  in LGM period

**Main characteristics**

- Single ocean temperature and salinity  for AABW, NADW and the residual ocean
- Single ocean volume for  AABW, NADW and res.
- Diagnostic equilibrium solution of gass solubility 

**Output**

For each temperature step, the model prints:
- dAr/N2
- dKr/N2
- Remaining atmospheric N2 (mol)
- *Users can select Oxygen-related diagnostic variables to output by modifying the '#result' section

---

### 3. 3box_model_AABW non-freezing (`c. 3box_model_AABW non-freezing.py`)

**Description**

- One global atmosphere box 
- Three global ocean boxes  (AABW, NADW, res) 
- LGM ocean temperature is first set to decrease by 1.1 degrees C uniformly (same as Configuration 2)
  From there, LGM AABW temperature no longer decreases (i.e., set to -2 degree C)
- temperature is assumed to decrease uniformly in NADW and res

**Purpose**

- Provide an estimate of ocean–atmosphere gas redistribution  in LGM period

**Main characteristics**

- Single ocean temperature and salinity for AABW, NADW and the residual ocean
- Single ocean volume for AABW, NADW and the residual ocean
- Diagnostic equilibrium solution of gass solubility 

**Output**

For each temperature step, the model prints:
- dAr/N2
- dKr/N2
- Remaining atmospheric N2 (mol)
- *Users can select Oxygen-related diagnostic variables to output by modifying the '#result' section

---

### 4. 3box_model_AABW expand_uniform (`d. 3box_model_AABW expand_uniform.py`)

**Description**

- One global atmosphere box 
- Three global ocean boxes  (AABW, NADW, res) 
- an expanded LGM AABW volume in LGM period
- temperature is assumed to decrease uniformly in AABW, NADW and res

**Purpose**

- Provide an estimate of ocean–atmosphere gas redistribution  in LGM period

**Main characteristics**

- Single ocean temperature and salinity for AABW, NADW and the residual ocean
- Single ocean volume for AABW, NADW and the residual ocean
- Diagnostic equilibrium solution of gass solubility 

**Output**

For each temperature step, the model prints:
- dAr/N2
- dKr/N2
- Remaining atmospheric N2 (mol)
- *Users can select Oxygen-related diagnostic variables to output by modifying the '#result' section

---

### 5. 3box_model_AABW expand_non-freezing (`e. 3box_model_AABW expand_non-freezing.py`)

**Description**

- One global atmosphere box 
- Three global ocean boxes  (AABW, NADW, res) 
- an expanded LGM AABW volume in LGM period
- LGM AABW temperature is set to -2 degree C
- temperature is assumed to decrease uniformly in NADW and res

**Purpose**

- Provide an estimate of ocean–atmosphere gas redistribution  in LGM period

**Main characteristics**

- Single ocean temperature and salinity for AABW, NADW and the residual ocean
- Single ocean volume for AABW, NADW and the residual ocean
- Diagnostic equilibrium solution of gass solubility 

**Output**

For each temperature step, the model prints:
- dAr/N2
- dKr/N2
- Remaining atmospheric N2 (mol)
- *Users can select Oxygen-related diagnostic variables to output by modifying the '#result' section

---

## File Structure

```
Source code/
├── a. 1box_model.py 
├── b. 3box_model_uniform/
├── c. 3box_model_AABW_non_freezing/
├── d. 3box_model_AABW_expand_uniform/
├── e. 3box_model_AABW_expand_non_freezing/
├── O2.py 
├── N2.py 
├── Ar.py 
├── Kr.py 
└── README.md
```

---

## Author

Boda Li, Zixuan Wang, Yuzhen Yan

## License

For academic research use only.
