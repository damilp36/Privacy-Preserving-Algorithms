#Overview

This project is targeted towards exploring ways to mitigate downcoding attack by enhancing Differential Privacy using Residue Number Systems

**Folder Structure and setup**

**The main folder contains a director for /datasets and 6 .ipynb files The files for this solution are:**

- Project.pdf - Contains an elegant description of the solution and steps

- RNS_Noise_to_Data.ipynb - A solution using RNS

- Laplace_to_Noise.ipynb - A solution using Laplase
- Laplas_NoisE_to_RNS.ipynb - A solution using Laplace on RNS
- Results_and_Comparisons.ipynb - A workbook comparing the results

**Each .ipynb notebook ( except Results_and_Comparisons.ipynb) performs the following functions**
- Imports the required libraries
- Loades the adult.data from /datasets
- Visualizes the head()
- Performs an anonymity oppression (RNS, Laplace or Laplace on RNS ) as the case may be and writes it to a new CSV file in /datasets

**In /datasets there are a number of .csv and .data files , but our focus is on**
- adult_anonymized_RNS.csv : the file containing the anonymized data from
RNS
- Adult_anonymized_laplace.csv: the file containing the anonymized data from
Laplace
- adult_anonymized_laplace_RNS.csv: the file containing the anonymized data
from Laplace + RNS
Results_and_Comparisons.ipynb performs the following functions
- Loads all the anonymized datasets from /datasets
- Calculates the MAE and RMSE

  
**And analysis of the result as well as a conclusion is given below**

**Evaluation Metrics Table:**
**RNS**
MAE (Mean Absolute Error) - 21.04
RMSE (Root Mean Squared Error) - 21.20
**Laplace**
MAE (Mean Absolute Error) - 3.01
RMSE (Root Mean Squared Error) - 4.25
**Laplace + RNS**
MAE (Mean Absolute Error) - 20.60
RMSE (Root Mean Squared Error) - 21.15

These results showcase the performance of different privacy-preserving techniques in the context of susceptibility to down-coding attacks:
Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE)
RNS: MAE of 21.04 and RMSE of 21.20
-Laplace: MAE of 3.01 and RMSE of 4.25 Laplace + RNS: MAE of 20.60 and RMSE of 21.15

**Interpretation:**
MAE and RMSE: Lower values indicate better accuracy in preserving the original data while adding noise. In this context, Laplace noise alone significantly outperforms RNS in terms of MAE and RMSE, suggesting Laplace noise might preserve data better against downcoding attacks compared to RNS.

**Understanding the Results**
Laplace Technique: The Laplace mechanism introduces noise, skewing the data slightly, but the error metrics are notably lower than those of RNS. This indicates that Laplace noise better protects against downcoding attacks.

RNS Technique: While RNS introduces noise and aims to protect privacy, its error metrics (MAE and RMSE) are higher than Laplace, suggesting it may not be as robust against down-coding attacks.

**Conclusion:**
While a larger MAE might indicate stronger privacy due to increased noise, it could also imply reduced data accuracy and utility, making the data less useful for analysis or applications, this is why RNS + Laplace may not be suitable.

Laplace alone: Has the lowest error metrics among the individual techniques, indicating better resistance to down-coding attacks compared to RNS alone.

Laplace + RNS: The combined approach doesn't seem to substantially improve the down-coding resistance compared to Laplace alone, as the error metrics are slightly higher.

Based on these results, the Laplace mechanism appears to be more effective in protecting against downcoding attacks compared to the RNS technique. However, the combined Laplace and RNS method didn't yield a significantly better result than Laplace alone.
