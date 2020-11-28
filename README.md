# CISC251 - Data Analytics Final Project #

## Data Wrangling ##

Given six files, as described in the project.html page on OnQ, the first step was to manipulate the csv files such that speeches, mostfreq1000docword, mostfreq1000word, and winners were all one file. Speeches became the first column (titled Speeches); mostfreq1000word became the column headers for mostfreq1000docword (by transposing it); and the winners file became the last column (titled win/loss). Similarly, the same was done for the deception files, including adding POS tags to the words using a POS tagger online (http://nlp.stanford.edu:8080/parser/index.jsp). There is also a column for political party which was not used.

After doing this, the data was split into year and president (includes rest of text) and group the columns together by their POS in alphabetical order which neatly displays similar POS groups. All of this was done in an R program. These files, mostfreq1000wordData.csv and deceptionwordData.csv, are the input files for KNIME.

With clustering in mind, mostfreq1000wordNeat.csv was transposed and then had attributes removed, only keeping the column for words, and speeches as headers. The mostfreqPOS.csv file contains the frequencies of the words by POS per speech which will be used in clustering and for predicting if any POS tag affects the outcome. 

The online tool used to transpose the files: https://www.convertcsv.com/transpose-csv.htm.

## Data Visualization ##

To visualize the data, column graphs were plotted for each POS tag by the normalized sum of frequencies per word to make the graphs more easily comparable. Then, a column graph was created for total frequency per POS tag. They can be seen at: https://dennish3.github.io/

# Files #

- Folders contain manipulated data of the original files. The original files will not be shared, nor will the project description.
- Workflow includes all KNIME workflows used in this project
- Correlation1000words.csv: contiains the correlation values of all 1000 words
- DBSCAN epsilon.ipynb: program that optimizes the epsilon parameter for DBSCAN clustering
- K-means.ipynb: program that performs k-means clustering (source: https://medium.com/@lucasdesa/text-clustering-with-k-means-a039d84a941b)
