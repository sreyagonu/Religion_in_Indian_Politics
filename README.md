# Religiosity, Caste, and Gender as Predictors of BJP Support in India

The project examines whether personal religiosity predicts support for the Bharatiya Janata Party (BJP) among Hindu voters and whether that relationship holds across caste groups and genders using the Pew Research Center survey data on 29, 999 Indian adults. The central finding is that religiosity is a reliable predictor of BJP support with roughly a 20 percentage point gap between highly religious and non-religious Hindu voters. The pattern is consistent across most caste and gender subgroups, with a notable exception for Scheduled Tribes (STs) as other structural factors could have shaped their voting behavior. 

# Data

I am using the Pew Research Center's "Religion in India: Tolerance and Segregation" survey, conducted from November 17, 2019 to March 23, 2020. The dataset is not included in this repository. Instead, the dataset and survey can be downloaded directly from Pew's website and the dataset CSV could be placed in a data/ folder to reproduce the analysis.

# Methodology

My analysis constructs a religiosity index from two indicators of solitary religious engagement: frequency of reading religious books (Q50) and frequency of watching religious programs (Q39a). I chose to analyze two forms of solitary religious practices as most common measures like attending temple, going to religious events, or even praying at home are more social events in Indian culture. Furthermore, according to Kumar (2009), public religious events were further promoted by Hindu right-wing parties like the BJP during the Ayodhya campaign. Since increased public participation in social religious events was partially impacted by the BJP, it would have not been an accurate measure at understanding the true relationship between a person’s religiosity and their voting preferences. By focusing on activities that require individual initiative outside of a communal setting, like  reading religious books and watching religious programs, the index is then able to isolate a stronger signal of personal religious commitment to truly understand voting behaviors. 

Both indicators are collapsed from seven-point frequency scales into four levels (most days, few times a month, few times a year, never), then summed to create a composite score ranging from 2 to 8. This sum is grouped into four categories: Highly Religious (2–3), Moderately Religious (4–5), Minimally Religious (6–7), and Not Religious (8). The analysis is restricted to Hindu respondents only, and vote choice is coded as BJP, Indian National Congress (INC), or Other.

# Key Findings

## Religiosity and Caste
Higher religiosity correlates with BJP support across all four caste groups, but the strength of the relationship varies considerably.
<img width="1035" height="617" alt="Screenshot 2026-02-06 at 6 20 35 AM" src="https://github.com/user-attachments/assets/e37b7077-2834-46e7-9ffa-fbd41d6fffd8" />
The effect is strongest among Other Backward Classes (OBCs), where 74% of highly religious respondents voted BJP compared to just 44% of non-religious respondents, which is a 30 percentage point gap. Comparatively, among Scheduled Castes respondents, the gap between Highly Religious votes and Not Religious is only 24 points (62% to 38%), and General caste voters have the second lowest variability with only a 19 point loss (67% to 48%).
The Scheduled Tribes (STs) seem to follow a completely different pattern altogether. Highly religious ST respondents supported BJP at 68%, while non-religious ST respondents also supported BJP at 65%. Interestingly, the ST vote share seemed to have a semi-gradual decline until Not Religious. The deviation in voting patterns would suggest that other factors other than religiosity are potentially influencing people’s vote shares for the BJP. A potential explanation could be the BJP’s efforts in the past decade in expanding government and education quotas for STs, however that might not fully explain why there was still a gradual decline in vote share between Highly, Mostly, and Minimally Religious. More research is needed to fully understand the STs voting behaviors. 

## Religiosity and Gender
The religiosity-BJP relationship holds for both men and women as the support percentages seem to stay consistent between the two groups. BJP support drops from 68% among highly religious voters to 47% among non-religious voters for both genders, totalling to a 21 percentage point decline.
<img width="1051" height="642" alt="Screenshot 2026-02-06 at 6 37 43 AM" src="https://github.com/user-attachments/assets/7227b320-6e1d-4139-b959-7ee3f046169c" />
The main gender difference appears in support for "Other" parties: women show higher support for Other parties across most religiosity levels. It is worth noting that the difference is only a couple of points between men and women and it also seems like the Not Religious vote share is almost the same between the genders.
<img width="1031" height="607" alt="Screenshot 2026-02-06 at 6 43 42 AM" src="https://github.com/user-attachments/assets/1a9e64e0-1407-46d7-95d1-df6969b2c4b7" />
Furthermore, the INC vote share remains relatively stable while being slightly lower than the vote share for Other across religiosity levels for both genders. The stability and smaller vote share suggests that the voters BJP loses as religiosity decreases are flowing primarily to regional and smaller parties rather than to the national opposition, like the INC. 
<img width="1179" height="703" alt="Screenshot 2026-02-06 at 6 51 28 AM" src="https://github.com/user-attachments/assets/b0186784-c17e-407a-b985-298264a695fe" />

## Party Closeness as a Robustness Check
Q77a captures behavior in a single election, which may not reflect general voting patterns. To understand underlying partisan identity, the analysis examines party closeness (QPTY: which party respondents feel closest to). If we look at the produced crosstabs, it seems that party closeness mirrors the vote choice patterns closely as there aren’t many deviations from the patterns previously observed. It is worth noting that as religiosity decreases, men maintain a slightly higher BJP affinity while women shift slightly towards INC and Other parties, suggesting gender moderates the religiosity-partisanship relationship at the level of identity rather than just vote choice. 

# Limitations and Future Work
This analysis is cross-sectional and descriptive and the correlations shown here cannot establish that religiosity causes BJP support. A logistic regression controlling for age, income, education, region, and urban/rural status would help isolate the independent effect of religiosity, although multicollinearity among these demographic controls would need to be assessed. Additionally, the religiosity index treats book reading and show watching as equally weighted, which may not reflect the accessibility constraints faced by lower-income or less-educated respondents, as reading religious texts is more time-intensive, educationally demanding, and costly than watching religious programs. 

# Reproducing This Analysis:
The full R code is in religious_politics_code.Rmd

To run it: Download the Pew Research dataset from this link: https://www.pewresearch.org/religion/2021/06/29/religion-in-india-tolerance-and-segregation/

Place the CSV in a data/folder at the root of the repo as india_religion_data_pew.csv

Then open the .Rmd file in RStudio and knit 



