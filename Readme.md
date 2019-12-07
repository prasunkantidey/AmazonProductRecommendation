AmazonReview contains the entire project with source codes.

Folder structure is 
AmazonReview/data/
AmazonReview/src/com/analysis/
AmazonReview/src/com/preprocess/


----
"data" stores all the outputs (graph pdf, reduced dataset).
Input file (For Dataset reduction or ReviewNetwork) should also be stored in this folder.


----
"analysis" has 2 python files. 
1. ARClass.py
2. ReviewNetwork.py

ARClass defines the structure of each product and stores informations from amazon data.

ReviewNetwork does all the calculation and computations.
- generates the graph and saves in pdf (if item count < 200)
- uses page rank to sort items based on helpfulness and categories
- gives 5 recommendations for any randomly selected product. 


----
"preprocess" has only 1 python file.
1. ReduceDataset.py

As name suggests, it reduces the dataset and saves the output in a txt file in "data" folder. 


----
Running the project:

1. If running with original dataset (amazon-meta.txt), then it must be reduced using ReduceDataset.py.
2. You can define your reduced filename in there. However, for now it generates "amazon_reduced_data_100.txt" for 100 items. Item count can be set in this file in "max_count" variable.
3. This expects the input file to be in "data" folder and will save the output file in same "data" folder.

Note: We already provided 2 sample reduced dataset of size 100 and 4000.
For full dataset: https://snap.stanford.edu/data/web-Amazon.html

4. To just see the recommendation, run "ReviewNetwork.py".
5. It expects an input filename as "amazon_reduced_data_100.txt". However, 100 can be changed by changing value of "input_size" variable in the file.
6. Number of recommendations per product can also be set from the file by "number_of_recommendation" variable. Currently it's set to 5.
7. If "input_size" is less then 200 items, it will show the generated graph (nodes and edges) and save it in "data" folder as pdf format.
8. Output (Recommended products) will be shown in terminal, but will not be saved in file.