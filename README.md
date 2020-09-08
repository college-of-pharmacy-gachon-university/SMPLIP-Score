# SMPLIP-Score
SMPLIP-Score was develped for prediction of absolute ligand-protein binding affinities.

Requirments:

The followng necessary packages should be installed in your system to process, generate fingerprint and train and test your model.

1. KNIME analytics platform (> 3.5)
2. Community nodes and schrodinger nodes should be installed (For schrodinger node please follow this link: https://www.schrodinger.com/kb/1085)
3. IChem program (http://bioinfo-pharma.u-strasbg.fr/labwebsite/download.html) [License can be obtained upon request to Dr. Didier Rognan]
4. SMF program (http://vpsolovev.ru/programs/smf/)
5. python >3.0
5. Keras (2.3.1)
6. Tensorflow (2.1.0)
7. Scikit Learn (0.22)
7. Jupyter Notebook

Procedures:

1. Process the protein PDB files using KNIME workflow (PDBbind_v2015_Preprocessing).

a. This will generate correct PDB files in *.mol2 file format.

2. Generate the protein-ligand binding fingerprints using IChem program.

program usage:
IChem 1a30_protein.mol2 1a30_ligand.mol2 > 1a30.ifp
 
3. Generate substructutal molecular ligand fragments using SMF program.

a. SMF program provides GUI.
b. Provide all the ligands in *.sdf file format
	
4. Generate a matrix of fingerprint from the output file IChem program using KNIME workflow (IChem_IFP_PDBBind_2015)

a. This worflow, took input of all *.ifp files from directory, extract all relevant information and save into *.csv format.
	
5. Train, validate and test your RF and DNN model using python script.

a. To train, validate and test the RF model use the Train-Valid-Test-RF.ipynb [SMPLIP-Score]
b. To train, validate and test the DNN model use the Train_Valid_Test-DNN.py

Additional Information:

For any queries mail to Mi-hyun Kim (kmh0515@gachon.ac.kr) or Surendra Kumar (surendramph@gmail.com)
