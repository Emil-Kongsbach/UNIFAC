# UNIFAC
 An implementation of the group contribution method of the Dortmund modification of UNIFAC. Calculates the activity coeficients of species in a mixture based on functional group parameters

 ```
 from unifac import Unifac_Dortmund

# Set system parameters
smiles_lst = ["CCO", "CC(=O)C","CC=CC"]     # NA
x_lst=[1/3, 1/3, 1/3]                       # NA
T=298                                       # K

mixture=Unifac_Dortmund(smiles_lst,x_lst,T)

# Returns activity coefficient of component 0 in the mixture, according to the order in which the components were passed.
print(mixture.gamma_singular(0))

# Returns activity coefficient of all components in the mixture according to the order in which componenets were passed
print(mixture.gamma_total())

# stability analysis
mixture.is_stable_local() # computes local stability (spinodal)

mixture.is_stable_global() # computes global stability (binodal)

mixture.is_stable()  # computes first local stability (cheap), and only if that is True it proceeds to calculate global stability (expensive)  

 ```

# Install
The library is installable with pip. Simply run:
>>> pip install unifac

