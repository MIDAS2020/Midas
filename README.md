# Midas 

This is our implementation for the paper:

MIDAS: Towards Efficient and Effective Maintenance of Canned Patterns in Visual Graph Query Interfaces

The project consists of ClusterMaintenance and Midas. ClusterMaintenance is  implemented with C++ (C++ 14) and  Midas is implemented with Java (JDK 1.8). 


# Environments

C++ 14

JDK 1.8

Visual Studio 2019

Eclipse 2019  

Boost Graph Library (https://www.boost.org/doc/libs/1_74_0/libs/graph/doc/)

# Dataset

1) AIDS antiviral dataset

2) PubChem dataset

3) eMolecule dataset


# Example to run the codes

There is an example to run the codes. Suppose the original database contains 25000 graphs in AIDS antiviral dataset, if 15000 graphs are added into the database, ClusterMaintenance should be performed to maintain the  clusters generated from  the original database  and Midas is then to update original patterns based on the updated clusters. 

1. Run ClusterMaintenance: 

Step 1:  Import ClusterMaintenance project into Visual Studio workspace.  

Step 2: Download Boost Graph Library (BGL) from https://www.boost.org/doc/libs/1_74_0/libs/graph/doc/ and compile BGL. Then configure it for Visual Studio (see https://www.youtube.com/watch?v=CH_YZ2bePPM ).

Step 3:  Open SmallGraphClustering.h, set  databasefilename = "AIDS40k",  initialsizeofgraph = 25000, addedsizeofgraph = 15000,  and  updateclustername = "updatecluster25K+15K.txt".   By doing this,  the input file is "AIDS40k" and the output file is  "updatecluster25K+15K.txt" that record clusters for the updated database. 

Step 4:  Open the main class MidasMain.cpp, run it with Release Mode to obtain the output "updatecluster25K+15K.txt". 

2. Run Midas:

Step 1:  Import Midas project into Eclipse workspace.  

Step 2:  Place existing pattern set "GUIPatterns.txt" and updated cluster file into "patterns/GUIPatterns.txt", and place it into the folder

Step 3:  Open the  class src/main/MIDASMain.java,  for function  RunMidas(), set setDataBaseName("AIDS40k"), 
		setDbName("AIDS"),  setInitialPatternName("patterns/GUIPatterns.txt"),  and setUpdateClusterName("Clusters/updatecluster25K+15K.txt") , run this class to obtain the updated pattern set "patterns/thumbnails". 
    
