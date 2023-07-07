## Dani Treisman
_M.S. in Data Science from Depaul University_  
_B.S. in Statistics from Loyola University Chicago_

_This page is a work in progress..._

### Manager Scorecards  

*  Inspired by [Umpire Scorecards](https://twitter.com/UmpScorecards?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor), I wanted to create a way to evaluate the decision-making of MLB managers. This is a complex task because it's hard to evaluate more than just _when_ a pitcher should be removed, but _who_ should replace them. Using the scraped rosters below, I developed a methodology to score MLB manager pitching change decisions using a run expectancy framework to determine which pitcher should be pitching at any given at-bat. These values are aggregated every game and posted to Twitter daily using GitHub Actions. 

The repo can be found [here](https://github.com/dtreisman/ManagerScorecards)  

### Daily MLB Active Roster Scraper  

*  There is currently no public data source for daily active MLB rosters that includes the player IDs *and* specific player positions (rather than the general categories the MLB API provides). This repo provides a script to pull the current daily active rosters from ESPN team roster pages and is scheduled using GitHub Actions in order to compile a data source for historical active rosters by day with specific position information.
The first available day of rosters is 07/05/2022. Data is updated at 20:00 UTC.

The repo can be found [here](https://github.com/dtreisman/DailyMLBRosters)  



### An Analysis of Quarterback Ability to Hit Receivers In-Stride Using NFL Player Tracking Data
*  This report is an investigation into the ability of NFL quarterbacks to hit receivers *in-stride*. This 'ability' is defined here as the quarterback's skill in preventing extreme orientation, acceleration, and speed changes for the receiver (i.e. back-shoulder catches), from the moment of the throw to the moment the pass arrives at the receiver. This work provides a starting point for more specific methods of quarterback evaluation using frame-level player tracking data and provides evidence that quarterbacks do have some ability to hit receivers in-stride. The main findings in this paper are: 1) the aggregated (by QB) *observed-expected* values for receiver Acceleration Difference Over Expected correlate moderately with average Completion Probability Over Expected (CPOE), 2) Average (by QB) receiver Speed Difference Over Expected and Yards After Catch difference from pass forward to pass arrival (xYAC Difference) are highly correlated, and 3) average Acceleration and Speed differences Over Expected are stable for QBs within-season.

The repo with the code and detailed report can be found [here](https://github.com/dtreisman/NFL_InStrideAccuracy)  
The recorded presentation can be found [here](https://www.youtube.com/watch?v=_wI7nHjozTk)


### Analyzing Route and Coverage Combinations in the NFL
* The prompt for the [2021 Sports Info Solutions Analytics Challenge](https://github.com/SportsInfoSolutions/AnalyticsChallenge2021) was: *Which route combinations were most popular in the NFL in 2020? Of these route combinations, which perform best against each coverage type?*. For my submission, I analyzed route and coverage combinations and their effect on completion probability.

The repo with the code and detailed report can be found [here](https://github.com/dtreisman/SISAnalyticsChallenge2021)


### A Framework for Assessing Goal Scoring and Play Making Skill in the NWHL
* The inaugural Big Data Cup, a hockey analytics competition run by [Stathletes](https://www.stathletes.com/big-data-cup/), set out to provide new opportunities for hockey analytics and to promote women's hockey and research. For the competition, I attempted to create a framework for assessing player skill in terms of shooting and passing ability. I used a layered approach, first building a model for expected goals (*xG*) on every shot, then using those predictions as the response in Generalized Linear Mixed Models to determine player effects. I found that the random intercepts for players' shooting ability correlated with the estimated *xG* on shots with an R-squared of 0.14. The league's best shooters generated an estimated 0.083 to 0.16 *xG* based on skill alone, adjusted for other situational factors.

The repo can be found [here](https://github.com/dtreisman/BigDataCup2021)

### Tackle Probability and the Value of a Tackle  
* For this year's [Big Data Bowl](https://operations.nfl.com/gameday/analytics/big-data-bowl/), a data science competition hosted by the NFL on [Kaggle](www.kaggle.com), I attempted to quantify the value of a tackle by a defensive player in the NFL using the supplied player tracking data. There are many metrics for evaluating offensive players, so for this year's Big Data Bowl, the challenge was to find ways to better evaluate defense in an NFL game. Since they left the submission requirements open-ended, we were free to come up with our own ideas rather than try to build the best model to compare against true values, like in most Kaggle competitions. 
* For my model, I used player tracking information such as the *x* and *y* coordinated of each player, as well as the *defender distance to the receiver* to predict the probability of each player making the tackle. I utilized extreme gradient boosting with `{xgboost}` and built a multiclass classifier to predict the tackle probability for each defensive player on the field. 
* After determining tackle probability for each player on each play, I then used *yac-epa over expected* (*yac-epa - xyac-epa*) from [nflfastR](https://www.nflfastr.com/) to quantify the value of each tackle. *yac-epa* is the expected points added to the offense as a result of the yards gained after the catch. *xyac-epa* is the expected value of *yac-epa* based on various factors such as how far down the field the offense is, and the time left in the game. Whatever the actual *yac-epa* value is, includes the all actions of the defender after the catch was made that have an effect on the opposing offense's EPA, namely, pass coverage and the tackle. Removing the expected *yac-epa* will let us remove any effect on the offense's EPA from pass coverage, leaving only the effect of the tackle. That remaining *yac-epa* can be credited proportionally based on the tackle probabilities of each defender. 

[Check out the notebook here](https://www.kaggle.com/danitreisman/tackle-probability-and-the-value-of-a-tackle) with my methodology, code, and a short analysis of the results. 


### A Look at Strikeout and Homerun Rates in 2020
* It may be cliche at this point, but the 2020 MLB season has been anything but ordinary. With this season being almost a third the length of a regular season AND starting several months late, there will likely be many deviations from traditional sabermetric models and ideas.  
For example, there is an idea that the strikeout rates are correlated with the rate of home runs. The basic idea is that players who hit more home runs are swinging harder and being a bit less selective with the hope of a bigger payoff. It's a risk-reward trade-off. This phenomenon is explained in depth in [this](https://fivethirtyeight.com/features/you-cant-have-home-runs-without-strikeouts/#:~:text=The%20defining%20characteristics%20of%20baseball,are%206.4%20strikeouts%20per%20homer.) article by Michael Salfino of FiveThirtyEight in 2019. 
There is a bit of controversy about whether high-homeruns and high-strikeouts are a good approach. However, strikeouts and home runs are both seemingly higher than ever. While watching the first few games of the 2020 season however, it seemed (from nothing more than a gut feeling) that this season, strikeout rates were significantly higher than they should be, with homerun rates not rising as well. I decided to take an in-depth look at strikeout and homerun rates this year compared to previous years to see if I was correct or if I was suffering from the effects of sports withdrawals. Here is a short look at some of my findings for this season.  
(Data is from [Retrosheet](https://www.retrosheet.org/) and [Baseball-Reference.com](https://www.baseball-reference.com/leagues/MLB/2020.shtml)) 

See the full report [here](https://github.com/dtreisman/HRsAndKs2020/blob/master/A%20Look%20at%20Ks%20and%20HRs%20in%202020.pdf).  


### Batting Order Optimization in R

* Comparison of several batting order strategies based on real batting statistics of the Chicago Cubs 2018 most-used batting order (according to baseball-reference.com)
  + Original Order
  + Pitcher batting 8th (a common approach to stimulate more offensive production)
  + Pitcher batting 1st (is it that bad?) 
  + Lineup consisting of the same batter throughout for each batter
  + 6th batter (Schwarber) batting first
  + Optimized order through simulation
  + Lineup based on On Base Percentage (decreasing)

(This project was a simulation/coding exercise. It would make more sense to use Markov Chains but this project was before I had and understanding of MC's.)

See the full report [here](https://github.com/dtreisman/Baseball-Simulation-in-R/blob/master/Batting%20Order%20Optimization.pdf).  
See the repo with code [here](https://github.com/dtreisman/Baseball-Simulation-in-R).

