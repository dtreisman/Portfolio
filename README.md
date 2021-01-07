## Dani Treisman
_B.S. in Statisics from Loyola University Chicago_

_This page is a work in progress..._

### A Look at Strikeout and Homerun Rates in 2020
* It may be cliche at this point, but the 2020 MLB season has been anything but ordinary. With this season being almost a third the length of a regular season AND starting several months late, there will likely be many deviations from traditional sabermetric models and ideas.  
For example, there is an idea that the strikeout rates are correlated with the rate of homeruns. The basic idea is that players who hit more homeruns are swinging harder and being a bit less selective with the hope for a bigger payoff. It's a risk-reward trade off. This phenomenon is explained in depth in [this](https://fivethirtyeight.com/features/you-cant-have-home-runs-without-strikeouts/#:~:text=The%20defining%20characteristics%20of%20baseball,are%206.4%20strikeouts%20per%20homer.) article by Michael Salfino of FiveThirtyEight in 2019. 
There is a bit of controversy about whether high-homeruns and high-strikeouts is a good approach. However, strikeouts and homeruns are both seemingly higher than ever. While watching the first few games of the 2020 season however, it seemed (from nothing more than a gut feeling) that this season, strikeout rates were significantly higher than they should be, with homerun rates not rising as well. I decided to take a an in-depth look at strikeout and homerun rates this year compared to previous years to see if I was correct or if I was suffering from the effects of sports withdrawals. Here is a short look at some of my findings for this season.  
(Data is from [Retrosheet](https://www.retrosheet.org/) and [Baseball-Reference.com](https://www.baseball-reference.com/leagues/MLB/2020.shtml)) 

See the full report [here](https://github.com/dtreisman/HRsAndKs2020/blob/master/A%20Look%20at%20Ks%20and%20HRs%20in%202020.pdf).  


### Batting Order Optimization in R

* Comparison of several batting order strategies based on real batting statistics of the Chicago Cubs 2018 most used batting order (according to baseball-reference.com)
  + Original Order
  + Pitcher batting 8th (common approach to stimulate more offensive production)
  + Pitcher batting 1st (is it that bad?) 
  + Lineup consiting of the same batter throughout for each batter
  + 6th batter (Schwarber) batting first
  + Optimized order through simulation
  + Lineup based on On Base Percentage (decreasing)

(This project was a simulation/coding exercise. It would make more sense to use Markov Chains but this project was before I had and understanding of MC's.)

See the full report [here](https://github.com/dtreisman/Baseball-Simulation-in-R/blob/master/Batting%20Order%20Optimization.pdf).  
See the repo with code [here](https://github.com/dtreisman/Baseball-Simulation-in-R).

### Predicting House Prices in R

* Predicting house prices using machine learning
  + Multiple Imputation
  + Cross Validation
  + Gradient Boosting

See the full report [here](https://github.com/dtreisman/HousingPricesPredicitions/blob/master/HousingPrices%20-%20Predicitve%20Analysis.pdf).  
See the repo with code [here](https://github.com/dtreisman/HousingPricesPredicitions).

