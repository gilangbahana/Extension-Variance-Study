# What is the Optimum Drilling Spacing? – Extension Variance Study in Nickel Laterite Deposit

## Background and Principles
- Harry Parker propose a concept that resource confidence can be directly estimated using statistical means to calculate the probability that tonnage/grade/product content falls within a certain accuracy for period of time (Yeates et al, 2006). Resource model parent block size.
  - Drilling sufficient to estimate the tonnage, grade, and metal content on quarterly production increments to within 15% at 90% confidence is adequate to define a measured resources.
  - Drilling sufficient to estimate the tonnage, grade, and metal content on annual production increments to within 15% at 90% confidence is adequate to define an indicated resources

- To get the desired relative accuracy, kriging variance can be used. 

- Assume the error is normally distributed, and deduce relative confidence 90% interval.

- Create the block related to the actual or anticipated mining production.
<img width="699" height="422" alt="Drillhole spacing analysis" src="https://github.com/user-attachments/assets/d7244302-456e-4f32-b391-61e3f4d12bec" />


## Workflow
<img width="908" height="389" alt="Workflow" src="https://github.com/user-attachments/assets/04e090a8-83c8-483b-98bd-96cf33d9c251" />

## What Data do We Need?
- Variogram Parameter for each domain
- Kriging variance at different block size (In this study, we use block size as a direct proxy for drilling grid spacing):
  - Block 5×5 m   ≈   5 m drill grid
  - Block 50×50 m   ≈   50 m drill grid
  - Block 200×200 m   ≈   200 m drill grid
- For each block size, we place one pseudo-drillhole composite at the block centroid. Kriging that single sample to the block gives the extension variance — the uncertainty of estimating that block with one central drillhole.
- Running this for all block sizes in one pass produces the curve that drives the final recommendation.
- Mining rate or volume (as proxy of the production)
- Average grade data for each domains.

<img width="805" height="515" alt="image" src="https://github.com/user-attachments/assets/0f635a13-1c0f-43cc-baee-fee472b22fbc" />

## Robust Variogram for each Domain (Limonite and Saprolite)
<img width="3168" height="1414" alt="EDA Limonite" src="https://github.com/user-attachments/assets/8347638c-9cfb-4612-b3a6-d80b35d0cfc6" />
<img width="3167" height="1413" alt="EDA Saprolite" src="https://github.com/user-attachments/assets/bc1fef90-2b8c-47fc-b1e6-c402c28968ac" />

## Extension Variance – a review
- Extension variance is the uncertainty introduced when estimating a large block Z(V) using a single composite sample Z(v). As the block grows larger (wider drill spacing), the extension variance increases, meaning lower confidence in the estimated grade.
- Conceptually, it is simply the variance of estimating the block (Z(V)) using the composite (Z(v)).
- The formula for extension variance:
	σ²𝐸 (𝑣,𝑉)=2𝛾 ̅(𝑣,𝑉)− 𝛾 ̅(𝑣,𝑣)− 𝛾 ̅(𝑉,𝑉)

Where:
- σ²𝐸 (𝑣,𝑉)  = extension variance from composite to block
- 𝛾 ̅(𝑣,𝑉)  = average variogram value of composite to block
- 𝛾 ̅(𝑣,𝑣)= average variogram value between every possible point in the block
- 𝛾 ̅(𝑉,𝑉) = average variogram value of block
- 𝑣 = composite (data point)
- 𝑉 = block (estimated volume)

Global estimation variance:
	 σ²𝐸𝑆𝑇=1/𝑛 σ²𝐸 (𝑣,𝑉)

Because we’re using kriging to estimate the value, the variance of the estimate is in the form of kriging variance.
- σ²𝐾=1/𝑛 σ²𝐸 (𝑣,𝑉)
- the n = 1
- σ²𝐾=σ²𝐸 (𝑣,𝑉)

The kriging variance = extension variance when n = 1.

## From Kriging Variance to Confidence Interval
- Harry Parker propose max 15% error @90% Confidence Interval:
- Assuming a normal distribution, 90% CI = 1.645

Relative accuracy for 90% CI is:
- 1.645 * Standardized Error (SERR) / Mean

Standardized Error is:
- "SERR"=  σ/√𝑛 = √(1/𝑛 σ^2 )

Where:
- σ = standard deviation
- σ² = variance
- n = number of points
<img width="558" height="489" alt="image" src="https://github.com/user-attachments/assets/3b9a0705-b91e-42f0-96d1-26152d0cdc20" />

## Study Assumptions
- Annual production: 1,500,000 tonnes
- Density limonite: 1.98 ton/m³
- Density saprolite: 1.6 ton/m³
- Mean Ni (LIM): 0.905%
- Mean Ni (SAP): 1.057%
- CI confidence: 90% (z = 1.645)
- Threshold: ≤15% relative
- Bench height: 5m

## Results Limonite
- Production volume: Quarterly = 189,394 m³ · Annual = 757,576 m³ · Mean Ni = 0.905%
- Measured Spacing: 50×50 m
  - Relative 90% CI = 14% — just under the 15% threshold.
  - At 75×75m, CI jumps to 21% — non-compliant.
- Indicated Spacing: 100×100 m — CI = 15%, exactly at the threshold.
  - The next wider spacing (150×150m) breaches at 22%.
<img width="692" height="417" alt="16 - DHSA for Limonite" src="https://github.com/user-attachments/assets/1a70f4a9-173f-4900-9ccd-d2e34200d45f" />
<img width="1413" height="1502" alt="16 - Measured and Indicated" src="https://github.com/user-attachments/assets/051ccf92-aa9f-4172-887d-6bf0b2557ab5" />

## Results Saprolite
- Production volume: Quarterly = 234,375 m³ · Annual = 937,500 m³ · Mean Ni = 1.057%
- Measured Spacing: 50×50 m — CI = 11%, comfortably under threshold.
  - Note: SAP's higher mean Ni (1.057%) reduces relative error for same absolute variance.
- Indicated Spacing: 100×100 m — CI = 13%, under threshold.
  - SAP is slightly more conservative than LIM at this spacing.
<img width="691" height="417" alt="17 - DHSA Saprolite" src="https://github.com/user-attachments/assets/3c88b5c0-8f86-4925-b41b-b23c0943eb61" />
<img width="1484" height="1487" alt="17 - Measured and Indicated" src="https://github.com/user-attachments/assets/6da3b798-5ea3-4906-b1c4-8ff8849dc188" />
 
## Summary
- Measured
  - Optimum spacing: 50 × 50 m
  - LIM: 14%   SAP: 11%   (both ≤15%)
  - Quarterly production period = Parker criterion: ±15% @ 90% CI

- Indicated
  - Optimum spacing: 100 × 100 m
  - LIM: 15%   SAP: 13%   (both ≤15%)
  - Annual production period = Parker criterion: ±15% @ 90% CI

## Conclusions
- By having a robust variogram model, theoretically we can predict the variability influenced by different data configuration (or drill spacing).
- The relative confidence interval is influenced by mining rate volume (bigger volume produce smaller error), variogram (spatial relationship between data point and estimated block), and mean of the data
- Every element and domain has its own relative error due to their inherent characteristics.
- The Optimum drilling spacing both for Limonite and Saprolite are 50x50 for Measured and 100x100 for Indicated.

## Presentation Deck
[Extension Variance - Porto.pdf](https://github.com/user-attachments/files/28310281/Extension.Variance.-.Porto.pdf)






