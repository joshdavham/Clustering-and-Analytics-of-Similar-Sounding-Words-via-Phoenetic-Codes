# Clustering-and-Analytics-of-Similar-Sounding-Words-via-Phoenetic-Codes

![Screenshot from 2021-08-10 17-07-00](https://user-images.githubusercontent.com/18585507/128941296-de47b3b2-983b-4997-8839-44c7bfc114e1.png)

![download](https://user-images.githubusercontent.com/18585507/128941167-8ee5fe41-8a1e-4d92-95c1-77690e9a4c72.png)

Implementation, Proof-of-Concept and Examples demonstrating the use of a novel Phonetic Distance measure and it's corresponding Clustering technique.

The results from this original project has been since split and published into two papers which you can find here: [Identifying the Right Person in Social Networks with Double Metaphone Codes](https://ieeexplore.ieee.org/abstract/document/9443676) and here: [Analytics of Similar-Sounding Names from the Web with Phonetic Based Clustering](https://ieeexplore.ieee.org/document/9457753). Authors: Joshua D. Hamilton; Carson K. Leung; Sehaj P. Singh.

homophones.csv is a csv file containing a list of homophones and their corresponding homophonetic group memberships.
For example, 'oar', 'ore' and 'or' all belong to group 0, while 'bight', 'bite' and 'byte' all belong to group 3.

functions.py contains all of the functions that we required for our methods but couldn't find libraries for.
These functions are affinity_matrix(), DM_LD(), ED(), match() and dm().

affinity_matrix() builds a matrix of affinities between words. It requires 3 parametrs: a list of strings, an affinity type - either "double_metaphone" of "levenshtein" -, and a factor. factor==0 when computing levenshtein distances and factor==1 (strongly recommended) for computing phonetic "double_metaphone" distances.

DM_LD() computes the distance between two double-metaphone codes. It requires as pararameters two double-metaphone codes, and 
a factor (we strongly recommend factor==1).

ED() computes the levenshtein (edit) distance between two given strings if factor == 0. If factor != 0 and both given strings are phonetic codes, it calcuates a modified edit distance - a phonetic distance.

match() takes as input, two chacters and a factor. If factor == 0, then match() returns
1 if the two characters are the same, and 0 if they are not.
If factor != 0, then we will return a value between 0 and 1 depending on how similar the 
two characters sound to eachother.

The code for ED() and match() was derived from Steven Skiena's book" "The Agorithm Design Manual".
You can visit his website here: http://www.algorist.com/.

dm() is the Double Metaphone function. It takes a string as input and returns it's phonetic code(s).
The code for this function was taken from this repository: https://github.com/dracos/double-metaphone.
And the author is https://github.com/dracos.

Proof-of-Concept Implementation.ipynb contains an interactive jupyter notebook that demonstrates our clustering method.
If you would just like to see the results without running it yourself, you only need to click on that file in this git-hub repository. It contains a single, full run-through of the entire notebook. (Note that sometimes it fails to load - that's okay. Just keep trying and it will eventually load properly.)
