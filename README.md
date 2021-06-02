# Overview
# SMPLIP-Score
SMPLIP-Score was develped for prediction of absolute ligand-protein binding affinities.

[![HTML Manuscript](https://img.shields.io/badge/manuscript-HTML-blue.svg)](https://jcheminf.biomedcentral.com/articles/10.1186/s13321-021-00507-1)

![image](https://user-images.githubusercontent.com/51576785/120276925-504a8c80-c2ee-11eb-89fd-6b49995b7261.png)


# Requirements:

The following necessary packages should be installed in to process, generate fingerprint, train and test your model.

1. KNIME analytics platform (> 3.5)
2. Community nodes and schrodinger nodes should be installed (For schrodinger node please follow this link: https://www.schrodinger.com/kb/1085)
3. IChem program (http://bioinfo-pharma.u-strasbg.fr/labwebsite/download.html) [License can be obtained upon request to Dr. Didier Rognan]
4. SMF program (http://vpsolovev.ru/programs/smf/)
5. python >3.0
5. Keras (2.3.1)
6. Tensorflow (2.1.0)
7. Scikit Learn (0.22)
7. Jupyter Notebook

# Procedures:

1. Process the protein PDB files using KNIME workflow (PDBbind_v2015_Preprocessing).

   => This will generate correct protein PDB files in *.mol2 file format.
   
   The interface of KNIME workflow to process the protein (PDB) file.
   
   ![image](https://user-images.githubusercontent.com/51576785/120407346-f0a0bf80-c387-11eb-9d87-a7d08f3abe67.png)


2. Generate the protein-ligand binding fingerprints using IChem program.

		run the following command to generate *.ifp file
		IChem 1a30_protein.mol2 1a30_ligand.mol2 > 1a30.ifp
 
3. Generate substructutal molecular ligand fragments using SMF program.

	    - SMF program provides GUI.
	![image](https://user-images.githubusercontent.com/51576785/120277987-b4218500-c2ef-11eb-8dee-3477b463e821.png)

	    - The user must provide all the ligands in *.sdf file format.
	
4. Generate a matrix of fingerprint from the output file IChem program using KNIME workflow (IChem_IFP_PDBBind_2015)

   => This worflow, took input of all *.ifp files from the directory, extract all relevant information and save into *.csv format.
	
5. Train, validate and test your RF and DNN model using python script.

   => To train, validate and test the RF model use the Train-Valid-Test-RF.ipynb [SMPLIP-Score]
   
     	Load the *.ipynb* file using the jupyter notebook.
   
   => To train, validate and test the DNN model use the Train_Valid_Test-DNN.py [SMPLIP-DNN]
   
   		usage argument (bash shell):
		
		python Train_Valid_Test-DNN.py > log.txt
		
		see the comment section of Train_Valid_Test-DNN.py for detailed information on file uses.

# Additional Information:

For any queries mail to Mi-hyun Kim (kmh0515@gachon.ac.kr) or Surendra Kumar (surendramph@gmail.com)

# References:

## SMPLIP-Score: predicting ligand binding affinity from simple and interpretable on-the-fly interaction fingerprint pattern descriptors
[![HTML Manuscript](https://img.shields.io/badge/manuscript-HTML-blue.svg)](https://jcheminf.biomedcentral.com/articles/10.1186/s13321-021-00507-1)
