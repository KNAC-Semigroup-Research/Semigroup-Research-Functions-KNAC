Required Packages:
Sage and Numericalsemigroup.sage from,
https://github.com/coneill-math/numsgps-sage

 Kunz-Poset.sage and PlotKunzPoset.sage from,
https://github.com/coneill-math/kunzpolyhedron
Instructions for download of these pack-
ages can be found on their respective github README files. You will also need to
download the Kunz Face Data sets derived in https://doi.org/10.1142/S021819672050023X. The
file location of this data should be the same file location you use for the f ile location
variable at the beginning of the python file in [4]. The Kunz face data is used to
calculate possible posets, which we use to find real semigroups.

For the following functions you will need a folder called csv_creations in the same folder as
the Kunz face data.

csv creation no repeats(min elem, dimension = 0, csv file path
= file location), creates a csv file into the same file location as csv file location. 
It stores into the folder called csv creations, and is the same folder that is holding the folder for 
the Kunz Face Data. This folder will hold all the csv files for the following functions.
The min elem variable states the minimum element of the numerical semigroups we
are looking for. The dimension variable has a range of 1 to (min elem - 1). This
function uses multiple gigabytes of RAM as the minimal element increases above 10.
The dimension variable splits the creation of the csv file into smaller parts to prevent
the program from stopping due to running out of RAM during calculations. If you
have the adequate RAM, leave the dimension variable equal to 0, if not then assign
it a value from the range given. The resulting csv files records the minimal element,
embedding dimension, type, minimal trades, and, optionally, the dimension of the Kunz
face. The csv file does not store full repeated lines of values, as we are only looking for
the possible values for the previously stated m, e, t, and n.

If we separated the data for a particular minimal element by dimensions into multiple
csv files, the function, merging csvs(min elem, csv f ile path = file location), takes the
multiple csv files and merges them into one.

The function, first 3 columns(min elem, csv f ile path = f ile location), deletes the
last two columns of a csv file from a given minimal element value. It also deletes
repeated full row values. This leaves us with a list of minimal elements, embedding
dimensions, and types of possible numerical semigroups. This list is what we used to
create the staircase image that is featured in the next section, Figure 2. You will know
that the previous three functions were executed correctly if the function prints, “CSV
file ’{csv file path}’ created successfully.”

The function, poset finder(min elem, embed dim, T ype, dimension = 0, csv f ile path
= f ile location), creates a list of posets that can be printed in the following cell. In
this cell, set the particular min elem, embed dim, and type values of interest. The
last line of that cell then prints the posets using HTML. We manually sorted through
these printed posets in order to find the patterns that would eventually lead us to our
generalized poset
