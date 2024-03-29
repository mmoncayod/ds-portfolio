##Data Science Portfolio

# Education

- Bioengineering, PhD.
- Bioengineering, MsC.
- Biologist

# Experience

+ **Data scientist** @ My Pet's City / Booking platform for veterinary services
+ **CPO** @ Raiil / AI / SaaS / E-commerce / Restaurant-Supplier ordering platform
+ **CEO** & Co-founder Raiil / AI / SaaS / E-commerce / Restaurant-Supplier ordering platform
+ **Startup analyst** @ Bioexpert network / BI & Reporting
+ **Professor in Bioengineering** @ Universidad Militar Nueva Granada
+ **Patent analyst** @ Government Patent Office Colombia
+ **Research Stay** @ Andalucian Centre for Nanomedicine and Biotechnology
+ **Internal Strategy and Data Consultant** @ REFGENCOL
+ **Medical Translator** @ AMOLCA Editorial
+ **Frontend Web Developer** - Freelance

# Projects
+ ## **ML model to create personalized treatment protocols for pets**
  + Overview
  + Data collection
  + Data cleaning and preprocessing
  + Exploratory data analysis (EDA)
  + Feature engineering
  + Model selection
  + Model training
  + Model evaluation
  + Model deployment
  + Conclusions and future steps
    
+ ## **Product recommendation system for restaurants**
  + #### **Overview**
    
For Raiil, a company committed to streamlining the restaurant supply chain through transparent order management, tracking, and payments, I developed a product recommendation system, tailored for restaurants. This innovative system leverages historical ordering data to deliver personalized product suggestions, enhancing the connections between restaurants and suppliers and facilitating a more efficient supply chain process.

  + #### **Data collection**

    Raill didn`t have enough data to develop the model, so I created Python scripts to simulate artificial data to train a machine-learning model.

  + **Simulating the data for Restaurants, Products, Suppliers, and Orders.**

    I used the Faker library to simulate addresses and company names.

  +  **Helper functions**

**Helper functions for Restaurants**

  ![Texto alternativo](/assets/img/helper-function-restaurants.png)

**Helper functions for Products**
  
  ![Texto alternativo](/assets/img/helper-function-products.png)
  
**Helper functions for Suppliers**

  ![Texto alternativo](/assets/img/helper-function-suppliers.png)

**Helper functions for Orders**

  ![Texto alternativo](/assets/img/helper-function-orders.png)

  Once the helper function for simulating the data was scripted I created a Pandas Data Frame for each entity. The restaurant data frame is presented as follows:

  ![Texto alternativo](/assets/img/restaurant-data-frame.png)

  ![Texto alternativo](/assets/img/restaurants-data-frame-table.png)

  To see the complete data frame set visit: [link](https://github.com/mmoncayod/ds-portfolio/blob/main/1_data_simulation.ipynb) 

  + **Verifying data frames relationships**

  ![Texto alternativo](/assets/img/data-frames-relationship.png)

  + **Exporting data frames**

 After creating the data frames, they were exported to CSV files to undergo further data cleaning and processing.
    
  + #### **Data cleaning and preprocessing**

**Verifying Total entries - non-null values and data types**

![Texto alternativo](/assets/img/data-entries-commands.png)

![Texto alternativo](/assets/img/data-entries-restaurants.png)

**Verifying null values within data frames**

![Texto alternativo](/assets/img/nule-values-commands.png)

![Texto alternativo](/assets/img/nule-values-restaurants.png)

No null values were detected.

**Identifying duplicates and outliers within data frames**

Outliers

![Texto alternativo](/assets/img/outliers.png)

![Texto alternativo](/assets/img/outliers-result.png)

Duplicates

Every column within each row should match every column within the other row to be considered a duplicate.

Ej:

row 1: 1, 'Restaurant Name', 'Location', 'Italian', 'Medium', '$$'

row 2: 1, 'Restaurant Name', 'Location', 'Italian', 'Medium', '$$'

An empty data frame means there are no duplicated rows.

![Texto alternativo](/assets/img/duplicates.png)

![Texto alternativo](/assets/img/duplicates-result.png)

**Verifying data relationship**

* Orders-Restaurants Relationships (Every Restaurant ID in orders_df should exist in restaurant_df)
* Orders-Products Relationships(Every Product ID in orders_df should exist in products_df)
* Products-Suppliers Relationships(Every Supplier ID in products_df should exist in suppliers_df)
* Products-Suppliers Relationships(Every Supplier ID in products_df should exist in suppliers_df)

![Texto alternativo](/assets/img/data-relationship.png)

See the complete analysis in Jupiter Notebook: [link](https://github.com/mmoncayod/ds-portfolio/blob/main/2_data_cleaning.ipynb) 

Results were not good enough having discordating data. For example. Incoherent restaurant, supplier or product names. I used a real data set having real restaurant, supplier and product names and used Chat GPT-4 to complete the data set with made up information like, location, size, quentity etc. 

  + Exploratory data analysis (EDA)
![Texto alternativo](/assets/img/total-order-price.png)








  + Feature engineering
  + Model selection
  + Model training
  + Model evaluation
  + Model Deployment
  + Conclusions and future steps

+ ## **Genetic Diversity Analysis in _Diaphorina citri_ Using Mitochondrial DNA Sequencing**
  
**Objective:** To analyze the mitochondrial DNA sequences of _Diaphorina citri_ to assess genetic diversity and population structure, and predict the potential spread and evolution of the citrus greening disease.

**Overview:** _Diaphorina citri_, the Asian citrus psyllid, is a vector for the bacterium _Candidatus Liberibacter_ which causes the citrus greening disease, severely impacting citrus production worldwide and understanding the genetic variation within _D. citri_ populations is crucial for developing effective management strategies against the spread of the disease.

**Extract-Transform-Load:** The project utilized mitochondrial DNA sequences of _D. citri_ collected from eight locations across two Colombian regions, Valle del Cauca and Quindío. **Macrogen Korea sequenced mitochondrial DNA.**

  + **Phed quality system as criteria for sequence cutting**
    
      ![Texto alternativo](/assets/img/prhed_punctuation.png)
      
  + **Phed system assigns a score as follows:**
    
      ![Texto alternativo](/assets/img/phred_results.png)

     + Where:
      + Scores of 20 or more: High quality, with an error rate of 1% or less.
      + Scores of 30 or more: Very high quality, with an error rate of 0.1% or less.
      + Scores below 20: Low to moderate quality, with an error rate greater than 1%.

    Phred quality scores tell you the reliability of each base read during sequencing. By trimming sequences based on these scores, you are removing sections of sequences with a high probability of being in error, which can distort your results during alignment and subsequent analyses.

    + **Saving the trimmed sequences for alignment in Clutscal Omega**
      
       ![Texto alternativo](/assets/img/trimmed-1.png)

      See the complete code to get consensus sequences in Jupiter Notebook [link](https://github.com/mmoncayod/ds-portfolio/blob/main/1.ETL.ipynb) 
   
    + **Sequence aligning**
      
      + First: Assemble forward and reverse reads to obtain complete sequences for each sample
   
        + Function to create consensus sequences
     
      ![Texto alternativo](/assets/img/concensus_sequence_1.png)
   
        + Function to check and merge FASTA files
      
      ![Texto alternativo](/assets/img/concensus_sequence_2.png)
   
      + Second: Align those sequences within each population to compare between samples - Biopython
     
      + Aligned sequences for E population
   
      ![Texto alternativo](/assets/img/aligned_sequence_E.png)
   
      + Aligned sequences for V population
   
      ![Texto alternativo](/assets/img/aligned_sequence_V.png)
      
      See the complete code to get consensus sequences in Jupiter Notebook [link](https://github.com/mmoncayod/ds-portfolio/blob/main/1.ETL.ipynb) 

  + **Exploratory data analysis (EDA):**
    + **Haplotypes analysis for COI gene in D. Citri DNA sequences**

      ![Texto alternativo](/assets/img/haplotypes-dashboard.png)

      The V population showed lower haplotype frequencies compared to the E population, with 14 and 17 different matrilineal lineages respectively, indicating diverse and representative genetic variability suitable for intraspecific variability analyses in these regions. The most frequent haplotypes in V were 1, 8, 10, and 11, with 8 appearing four times across two locations. In contrast, E's most common were 3 and 8, with haplotype 3 found twice in San Juan.

       Both La Rivera (V) and Calarcá (E) had the highest haplotype diversity with seven each. Despite some haplotype overlap, natural barriers likely limit gene flow between populations.

      There are signs of mitochondrial heteroplasmy in individuals from Jamaica and Brazil in V, and both regions exhibit a significant number of unique haplotypes, which might be explained by point mutations leading to unique proteins that respond differently to environmental selection pressures, or multiple introductions into already variable populations.

      See the complete interactive dashboard in Tableu [link](https://public.tableau.com/app/profile/miguel.ngel.moncayo.donoso/viz/HaplotypesanalysisforCOIgeneinD_CitriDNAsequences/Dashboard1)

  + **Conclusions and future perspectives:**

The genetic structuring results indicate that _D. citri_ populations in V and E populations are expanding, yet no significant genetic differentiation exists that might give rise to new biotypes capable of adapting to novel environments or hosting other variants of the _Candidatus liberibacter_ bacterium.
    

    
 
