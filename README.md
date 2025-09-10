Is It Possible to Forecast GDP Like the Weather? An Experiment in Machine Learning
For a long time, GDP has been regarded as the ultimate goal in economics. Politicians brag about it, analysts fixate on it, and whole policy discussions center on whether it's rising or falling. Beneath the glitzy figures, however, comes a significant query: can we forecast GDP in advance, and is it truly universal?
I was first struck by this idea when I was an international economics undergraduate. "If GDP is growing, why do some societies still feel less prosperous than others?" was a question I frequently posed to my instructors. Almost invariably, their responses veered into sociology, politics, or history. Yes, you make valid concerns, but I was hoping for something more quantifiable.
The subject came up again recently while watching the debates over Romania's fiscal deficit. By formula, GDP is simply the sum of government spending, investment, consumption, and trade balance. However, those are outputs - snapshots of past events. Instead, what if GDP were modeled as an input-driven system?
To put it another way, could machine learning predict GDP for every nation in the globe based on current economic fundamentals?
Preparing a global dataset
I got my hands dirty and combed through World Bank and IMF datasets to test this. I created a dataset containing 2,041 rows and 33 economic indicators - from exports, debt levels, and unemployment to demographics and tax rates - after cleaning, filtering, and removing missing values.
The trick is that I removed the names of the countries and the years.
Why? Because I wanted to investigate if GDP follows norms that are universal and cross national boundaries. The majority of forecasting models focus on a single nation at a time. Mine viewed every nation, every year, as a single, vast economic cosmos.
Eliminating nation names and years from the dataset was an important methodological decision. Traditional forecasting models, which concentrate on a single nation at a time, are not like this. In order to find the universal drivers of GDP, I trained the model on all nations at once by removing geographic and temporal identifiers. The resulting dataset had the following variables:
The proportion of the working-age population
Rate of corporate taxes
Revenues and expenditures of the general government
Consumer price inflation
The population and its growth
Exchange rates, imports, and exports
GDP shares by industry, manufacturing, and services
Rents from natural resources
Rates of unemployment, 
Current GDP
And of course Next Year GDP
Dataframe after deleting country_name and year columns (Shown in Excel)Implementing ML Algorithm
I used a number of machine learning models, however the greatest results were obtained with XGBoost regression. After dividing the dataset into training and testing sets (80/20), the scales were normalized using logarithmic transformations. The outcomes were remarkable:
Score for R2: 0.99
Mean Absolute Percentage Error, or MAPE, is 0.09.
The predictive power of the model was exceptionally high. It's interesting to note that the biggest predicting failures occurred after significant worldwide shocks: The Financial Crisis of 2008, 2014 (Collapse of Oil Prices)
MAPE by year"Second Revolutionary idea" is …
In order to advance the experiment, I trained the model solely on structural and policy-related factors, completely excluding the GDP (or any GDP related monetary variables) for the current year. The performance was still powerful even at that point:
Score for R2: 0.97
MAPE: 0.13
This proves that GDP can, in fact, be accurately predicted using only economic inputs and not historical GDP levels.
Potential Use
Transparency on Economic Decision-makings
Making the model available to the public allowed both citizens and officials to observe how monetary or fiscal policies made today impact prosperity in the future. Such openness can give economic discussions a data-driven basis in a time of conflict between authoritarian centralism and populist movements.
Assessing Institutional and Political Impacts
We can model the effects of various institutional contexts on GDP by adding more variables, such as a democracy index or political stability indices. The model might demonstrate, for instance, how political repression or conflict changes Russia's GDP trajectory or how democratic resilience affects economic results in other countries.
Conclusion
Despite frequent criticism that it is an unreliable indicator of wealth, GDP is nevertheless a significant economic indicator. This test demonstrates that GDP forecasting is not limited to conventional country-specific models. Machine learning offers a transparent and flexible method for predicting future economic performance by utilizing universal economic inputs; this instrument has the potential to transform policymaking and the public's perception of wealth.
Open To Colab…
This project is only getting started. My ultimate objective is to improve the model, broaden its use, and make it available to the general public and politicians. However, I think teamwork is essential for this to occur. I'm excited to get in touch with academics, data scientists, economists, and organizations that value open, forward-looking economic forecasting. By combining our resources and expertise, we can transform this model from an academic experiment into a tool that guides practical decisions, giving citizens, businesses, and governments a greater understanding of their economies' future.
Github link: heyder20012001/GDP_forecast
