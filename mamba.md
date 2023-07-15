create enviroment.yml
	name: MOJproj
	channels:
		- conda-forge
		- base
		- Python
	dependencies:
		- Python
		- pandas
		- numpy
		- matplotlib
		- sklearn
mamba env create -f environmebt.yml

