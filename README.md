# Error-Analysis-of-CONTES---BioNLP-2019
Error Analysis of CONTES(https://github.com/ArnaudFerre/CONTES) method's performance on the Bacteria Biotope (BB) Task at BioNLP-OST 2019 (https://2019.bionlp-ost.org).


1. Extract informations from the file of prediction result(contes_500_dev.csv):

- reference ID (ex.OBT:000000), reference name(ex. [fermented, milk])
- predict ID (ex.OBT:000000), predict name(ex.[bottle])




2. Define error type by combining ontology information(path to the terms : OntoBiotope_BioNLP-OST-2019_paths.txt):

- Wrong type : the term of prediction and the term of reference aren't the same type(ex. Phenotype vs. habitat)

- Wrong class : the term of prediction and the term of reference are in the different class(ex. food vs. artificial environment)
    - Wrong3 : the distance between the predict term and reference term is 3 on the Ontobiotope ontology.
    - Wrong4 : distance is 4
    
- General : the path to the prediction term is the subpath to the reference term
    - General1 : the distance between two terms is 1
    - General2 : the distance between two terms is 2
    - General3 : the distance between two terms is 3
    - Too General : exclude the situation above, if the prediction term is the root of each type(ex. "Habitat"/"Phenotype")

- Precise : the path to the reference term is the subpath to the prediction term

- Correct : correct predicted terms


3. Visualization of the error:

- numerical propotion of each error type (pie chart)
- score distribution of each error type (& Kernel density estimation)
