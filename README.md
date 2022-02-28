## Processing of macroinvertebrates sampling
Project for Python Programming for Water Resources Engineering and Research -
Water Resources Engineering and Management (WAREM) - Universität Stuttgart

*** 

![Cover](https://github.com/abiledezma/PMIS_ATAF/blob/main/Cover.jpg)


>   ***Goals***: 
> 
> Process data from a sample of macroinvertebrates that was originated by the Kicking Method. Determine the number of organisms per area and compare them with a data base that contains previous information on the site in a percentage basis. 

>   ***Requirements***: 
>
>Python libraries: **numpy** including *matplotlib*; **pandas** including *DataFrame*, *read_excel* and *merge*; **PIL** including *Image*; **os**, **XlsxWriter** and **comtypes**
> 
> Data: two excel files, one containing the information from the sampling site and other the results from previous studies.

You can clone the repository here:

```
git clone https://github.com/abiledezma/PMIS_ATAF.git
```


### Theoretical backgroud
Water quality is a term used to express the physicochemical, 
hydrological and biological characteristics of water. 
The knowledge of the condition of a water body is essential
to be able to make decisions about the actions that it may require. 
These decisions vary in their complexity and affect large and small 
scale communities, which makes it imperative to have relevant information.
The assessment of a water body can be fully achieved evaluating the three
aspects mentioned above. Different methods for obtaining this information
have been developed over time, from real-life measurements in gauging 
stations to annual surveying. One of the most widespread methods is the
use of aquatic macroinvertebrates as indicators of water quality 
([Chapman 1996](https://www.researchgate.net/publication/237320993_Water_Quality_Assessments_-_A_Guide_to_Use_of_Biota_Sediments_and_Water_in_Environmental_Monitoring_-_Second_Edition)).

A broad variety of sampling methods and devices to determine the 
water quality are standardized in the European guideline 
EN ISO 10870:2012. The appropriate sampling method depends on the
goal of the sampling campaign, the type of water body and the type
of benthic invertebrate that is examined. The variety of sampling devices
ranges from simple kick nets, applicable in wadable streams, to more 
advanced samplers, for instance the Van Veen Grab, which is designed 
to collect big samples from deep water bodies
([DIN EN ISO 10870:2012](https://www.beuth.de/de/norm/din-en-iso-10870/152469102)).

One of the more simple methods to quantify 
macroinvertebrates is the Kick Sampling method. This is an 
active sampling method appropriate for stagnant and running waters.
Different configurations of the device needed to perform this method can
be used 
([DIN EN ISO 10870:2012](https://www.beuth.de/de/norm/din-en-iso-10870/152469102)).

![Mesh of a sampling](https://github.com/abiledezma/PMIS_ATAF/blob/main/KickSampling.jpg)

([Dynamic Aqua-Supply](https://dynamicaquasupply.com/collections/nets/products/aquatic-invertebrate-kick-net))

### Definition of the input

The input for this program are two excel sheets with one page each.
- *Sample data*: a one sheet excel file containing in the first column 
the name of macroinvertebrates and in the second the amount of each that
were obtained in the current sampling site.
- *Data base*: a one sheet excel file containing in the first column 
the name of macroinvertebrates and in the second the amount of each
that were observed in previous studies relevant to the site.
- *mesh*: a number that defines the size of the mesh used in the 
Kick sampling method in meters [m]
- *criteria*: a number that will be used to determine the meaningful
percentage difference between the *Sample data* and the *Data base*

### Overal functionality of the program

The aim of this program is to process the data from a sampling 
site by comparing it with previuos information of the site. 
To fulfill that aim the program is devided into 5 steps
 1. The program will read the data given by the user
(*Sample data* and *Data base*, *mesh* and *criteria*)
 2. The percetage of each organism in *Data base* is computed.
 3. Then, using the *Sample Data* and the size of the *mesh*, 
 4. the amount of macroorganisms per area will be calculated 
along with the percentage of each.
 5. A comparaison of the percentage of each organism found in 
the site (*Sample data*) with the percentage of the organisms
shown in previous studies (*Data base*) will be made
 6. Using the *criteria* defined, the organisms under and 
above of it will be shown in a bar-graph. 

This is organized in XX scripts that are called by the 'main'. 
In the following graph the code diagram is shown.

![CodeBlock](https://github.com/abiledezma/PMIS_ATAF/blob/main/CodeBlock.jpg)

### Run instrucctions

After downloading the repository open the main script and run it.
A pop out window will ask for the location of the *Sample data* file.
The file must be saved in your computer. You just have to copy the path
in which is located, for example: 
> C:\Users\User\Documents\WAREM

At the end of the path is necessary to type the name of the file and
the extension it has, for example: 

> \Upstream.xlsx

So the final path that is needed as an input would be in this example: 
> C:\Users\User\Documents\WAREM\Upstream.xlsx

After providing the path, you have to click on the button **Add Sample Path**.
And then, close the window.
Then, the program will ask the same for the *Data base* file
and same operation must be done: select the correct path and type the name
of the file with its extension, click on **Add Database Path** and close the window.

This will be followed by another pop out window that will ask for the size of 
the *mesh*. In which a number with decimals stated as a point should be typed,
then click on **Add Mesh** and close the window.

Similar, a pop out window will  ask for the *criteria* and exatly the same as
with the *mesh* should be done.

If every input is correctly defined the program will generate 3 files.
They will be kept in a folder named *Data*. And they are:
1. **Results_Final.jpg**: a jpg file that is the final graph showing the
percentage of the *Data base* in <span style="color: blue"> blue</span>,
the *Sampling data* in <span style="color: orange"> orange</span>, and
the difference between both in <span style="color: green"> green</span>.
2. **Results_Final.xlsx**: an Excel file that shows the graph described
in 1 and a table that contains the species name, the amount and percentage of
each specie in the sample and the data and the difference between both. In this
last column the numbers in <span style="color: red"> red</span> mean they are
below the criteria stated in the input. Also colored in 
<span style="color: yellow"> yellow</span> will be the rows in which there is no
data to compare between the *Data base* and the *Sample data*
3. **Results_Final.pdf**: a pdf file that shows the same information as in point 2.
