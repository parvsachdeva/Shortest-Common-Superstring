# Shortest-Common-Superstring
Python program containing classes to solve the problem of shortest common superstring, given a fragmented string.

## Quick Start : 

#### Import the package : 
#### from shortest_common_superstring import *

scs=ShortestCommonSuperstring(list) #e.g. list=['ATGC', 'TGCC', 'GCCA']
OR
obj1=ShortestCommonSuperstring()
obj1.load_seq(sequence, k) #k is an integer for length of k-mers
Finding SCS : 
scs=obj1.scs()


## This program contains two classes : DNA and ShortestCommonSuperstring


### 1. DNA Class :
This class provides the functionality to take a sequence and break it down into k-mers, it can also provide unique k-mers.

#### 1.1 Initialising class and loading a sequence : 
dna=DNA(sequence)

#### 1.2 Finding all k-mers in the sequence (user has to provide length of k-mers = k) : 
all_kmers=dna.all_kmer(k) #k is an integer for length of k-mers

#### 1.3 Finding unique k-mers in the sequence : 
unique_kmers=dna.unique_kmers() #all_kmers() must be run in prior


### 2. ShortestCommonSuperstring Class (This class inherits from DNA class):
This class provides the functionality to make a directed graph by calculating edge weights from the overlaps of k-mers with each others. It can recursively and greedily merge k-mers with maximum overlap and reduce the list until either the SCS is found ot there are no further overlaps.

#### 2.1 Initialising class and loading a kmers (user has to provide list of k-mers) : 
scs=ShortestCommonSuperstring(list) #e.g. list=['ATGC', 'TGCC', 'GCCA']
scs is a list object that contains the shortest common superstring. It could have multiple strings if program is not able to resolve.

#### 2.2 Initialising class if user does not have a list of kmers (user has to provide a sequence) : 
obj1=ShortestCommonSuperstring()
You will get a message : Warning! No kmers provided. You can load sequences using load_seq() function.
obj1.load_seq(sequence, k) #k is an integer for length of k-mers

Finding SCS : 
scs=obj1.scs()
