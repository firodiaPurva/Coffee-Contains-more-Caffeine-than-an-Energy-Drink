## Introduction
In a world where drink choices play a significant role in our daily lives, the question of caffeine and calorie content has become increasingly relevant. This project embarks on a journey to unravel the mysteries surrounding the nutritional composition of popular drinks, with a particular focus on the age-old debate: coffee vs. energy drinks. Caffeine, a stimulant found in various drinks, has long been associated with diverse health outcomes, while calories serve as a crucial metric in assessing the nutritional impact of our favorite drinks.

The research question at the heart of this investigation is taken from [Coffee vs. Energy Drinks: Which is Better?](https://www.commonroomroasters.com/blogs/specialty-coffee/coffee-vs-energy-drinks#:~:text=Bottom%20line%3A%20coffee%20has%20a,eliminate%20the%20stimulation%20from%20caffeine), which states that coffee contains more caffeine and fewer calories when compared to energy drinks and other drinks. The significance of this inquiry lies not only in satisfying our curiosity but in informing everyday decisions regarding drink consumption and promoting healthier lifestyle choices.

To understand the nuances of this comparison, we delve into a rich dataset gathered from a myriad of popular drinks, aiming to provide insights accessible to individuals from all walks of life. This introduction sets the stage by elucidating the widespread implications of our drink choices, introducing the historical context of caffeine consumption, and highlighting the contemporary importance of informed decision-making in nutritional preferences. As we navigate through the subsequent sections, we will unveil our methodology and present findings that challenge conventional wisdom regarding coffee, energy drinks, and their nutritional impact.

## Dataset
The dataset utilized in this project was gathered through web scraping from the website [Caffeine Informer](https://www.caffeineinformer.com/the-caffeine-database), a comprehensive resource providing information about various drinks and their caffeine and calorie content. Web scraping was conducted in Python using Beautiful Soup to extract all the features.

While the dataset aims to provide a broad representation of popular drinks, it is essential to acknowledge potential biases. The information is sourced from a specific website, and the representation may be influenced by the content available on that platform. Bias may arise from the selection of drinks featured on the website, potentially favoring those with higher or lower caffeine content. Additionally, the accuracy of the data relies on the reliability of the source and the precision of the web scraping process.

## Data Preprocessing
- **Renamed Features**: For consistency and clarity.
- **Missing Values**: Checked for missing values and found none, indicating the completeness of the dataset.
- **Calculated Calories per floz**: Created a new feature named `calories_per_floz`.
- **Dropped Unnecessary Columns**: Removed irrelevant columns to streamline the analysis.

### Exploratory Data Analysis (EDA)
To gain insights into the dataset and lay the foundation for our analyses, we performed exploratory data analysis (EDA). This involved generating summary statistics, visualizing distributions, and identifying patterns in the key variables—volume, calories, caffeine content, and drink type. EDA aided in understanding the data's structure, uncovering potential outliers, and informing subsequent analytical decisions.

### Statistical Analyses

#### Two Sample z-tests
Conducted upper and lower-tailed two-sample z-tests using manual calculations and the BDSA package in R to compare caffeine content and calorie count between two samples (coffee and energy drinks, coffee and other drinks). These tests are appropriate for comparing means between two samples and are relevant to our research questions.

- **Central Limit Theorem (CLT)**: States that the distribution of sample means resembles the normal distribution if the sample size is > 30.
- **Significance Level (α)**: Set at 0.05 (5%).
- **p-value**: The probability, calculated given that the null hypothesis is true, of getting the value of the test statistic as extreme as the value from the sample.

#### Correlation Analysis
Calculated the correlation coefficient to assess the relationship between caffeine content and calorie count. This provided insights into potential associations between these key variables.

### Results

#### Test 1 - Upper Tailed Two Sample z-test
- **Null Hypothesis (H0)**: There is no significant difference in caffeine content between coffee and an energy drink.
- **Alternative Hypothesis (H1)**: Coffee contains more caffeine than an energy drink.
- **Result**: There is strong evidence to reject the null hypothesis as p-value < 0.05. So, we can conclude that coffee contains more caffeine than an energy drink.

#### Test 2 - Lower Tailed Two Sample z-test
- **Null Hypothesis (H0)**: There is no significant difference in calorie count between coffee and an energy drink.
- **Alternative Hypothesis (H1)**: Coffee contains fewer calories than an energy drink.
- **Result**: There is no strong evidence to reject the null hypothesis as p-value > 0.05.

#### Test 3 - Upper Tailed Two Sample z-test
- **Null Hypothesis (H0)**: There is no significant difference in caffeine content between coffee and other drinks.
- **Alternative Hypothesis (H1)**: Coffee contains more caffeine than other drinks.
- **Result**: There is no strong evidence to reject the null hypothesis as p-value > 0.05.

#### Test 4 - Lower Tailed Two Sample z-test
- **Null Hypothesis (H0)**: There is no significant difference in calorie content between coffee and other drinks.
- **Alternative Hypothesis (H1)**: Coffee contains fewer calories than other drinks.
- **Result**: There is no strong evidence to reject the null hypothesis as p-value > 0.05.

### Correlation Analysis
- **Correlation Coefficient**: 0.08885294. Since the correlation coefficient is close to 0, there is no statistically significant relationship between caffeine content and calorie count.

## Conclusion
This study set out to unravel the age-old debate between coffee and energy drinks, examining their caffeine and calorie content alongside other drinks. The exploration journey uncovered intriguing insights, challenging certain preconceptions. Contrary to the claims from [Coffee vs. Energy Drinks: Which is Better?](https://www.commonroomroasters.com/blogs/specialty-coffee/coffee-vs-energy-drinks#:~:text=Bottom%20line%3A%20coffee%20has%20a,eliminate%20the%20stimulation%20from%20caffeine) and common belief, our findings reveal that coffee does indeed contain more caffeine than an energy drink but there is no strong evidence for other claims. This result is supported by robust statistical evidence, emphasizing the importance of evidence-based decision-making when it comes to choosing a drink for that much-needed energy boost.

On the calorie front, the study found no significant differences between coffee and energy drinks, or between coffee and other drink types. This challenges the notion that coffee is inherently a low-calorie option and underscores the need for a nuanced understanding of nutritional aspects when making drink choices. The weak positive correlation between caffeine and calorie content suggests a nuanced relationship that varies among drink types. While caffeine and calories show a slight tendency to increase together, the overall connection is subtle and influenced by the diversity of drinks in the dataset.

### Implications
Individuals seeking caffeinated beverages can make more informed choices based on their preferences for caffeine content without significant differences in calories impact. The study highlights the importance of considering nutritional nuances when evaluating popular drink choices, challenging assumptions, and promoting evidence-based decision-making.

### Future Plans
In the future, we could explore how the caffeine and calorie content of different drinks have changed over time using time series analysis and use clustering algorithms to segment drinks based on their nutritional profiles to identify groups of drinks that share similar characteristics in terms of caffeine, calories, and other nutritional components. This study provides valuable insights into the nutritional landscape of popular drinks, offering a nuanced understanding of caffeine and caloric comparisons. As individuals continue to make choices that impact their daily lives, this research contributes to a more informed and evidence-based approach in selecting drinks that align with their preferences and health goals.

## Files in the Repository
- **caffeine_data_scraping.py**: This script is used to scrape caffeine and calorie content data from the Caffeine Informer database.
- **main_analysis.py**: This script performs data analysis, visualization, and hypothesis testing on the scraped data.

## Usage

To run the project, follow these steps:

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/firodiaPurva/Coffee-Contains-more-Caffeine-than-an-Energy-Drink.git
   ```

2. **Install Dependencies if any**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the Web Scraper**:
   ```bash
   python caffeine_data_scraping.py
   ```

4. **Conduct Data Analysis**:
   ```bash
   python main_analysis.py
   ```

## Practical Significance

According to Common Room Roasters, coffee generally has a higher caffeine content compared to energy drinks. This aligns with the findings of this project, providing both statistical and practical significance to the results.
