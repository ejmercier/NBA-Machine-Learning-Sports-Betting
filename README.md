# NBA Sports Betting Using Machine Learning 🏀
<img src="https://github.com/kyleskom/NBA-Machine-Learning-Sports-Betting/blob/master/Screenshots/output.png" width="1010" height="292" />

A machine learning AI used to predict the winners and under/overs of NBA games. 

## About

Takes all team data from the 2007-08 season to current season, matched with odds of those games, using a neural network to predict winning bets for today's games.  
  
  Achieves ~75% accuracy on money lines and ~58% on under/overs. 

## Betting Strategy
Outputs expected value for teams money lines to provide better insight. The fraction of your bankroll to bet based on the Kelly Criterion is also outputted.   
  
  Note that a popular, less risky approach is to bet 50% of the stake recommended by the Kelly Criterion.

## Installation
*Side comment:
Make sure you use Python 3.8. If for some reason "python3" does not work, try using "python" instead.*
### Installing the source code
```
git clone https://github.com/kyleskom/NBA-Machine-Learning-Sports-Betting.git
```

### Create environment

Navigate into to project and create an environment
```
cd NBA-Machine-Learning-Sports-Betting 
```
```
python3 -m venv env
```
### Activate environment
On Windows:
```
source env\Scripts\activate.bat 
```
On Unix/MacOS:
```
source env/bin/activate
```

### Install packages
```
python3 -m pip install -r requirements.txt
```
## Packages Used

In particular the packages/libraries used are...

* Tensorflow - Machine learning library
* XGBoost - Gradient boosting framework
* Numpy - Package for scientific computing in Python
* Pandas - Data manipulation and analysis
* Colorama - Color text output
* Tqdm - Progress bars
* Requests - Http library
* Scikit_learn - Machine learning library

## Usage

<img src="https://github.com/kyleskom/NBA-Machine-Learning-Sports-Betting/blob/master/Screenshots/Expected_value.png" width="1010" height="424" />

Make sure all packages above are installed.

```
python3 main.py -xgb -odds=fanduel
```
*Note: 
Odds data will be automatically fetched from **sbrodds** if the -odds option is provided with a sportsbook.  Options include: fanduel, draftkings, betmgm, pointsbet, caesars, wynn, bet_rivers_ny*

If `-odds` is not given, enter the under/over and odds for today's games manually after starting the script.

Optionally, you can add '-kc' as a command line argument to see the recommended fraction of your bankroll to wager based on the model's edge

## How to get new Data and Train Models
### Create dataset with the latest data for 2022-23 season
```
cd src/Process-Data
python -m Get_Data
python -m Get_Odds_Data
python -m Create_Games

```
### Train models
```
cd ../Train-Models
python -m XGBoost_Model_ML
python -m XGBoost_Model_UO
```
## Flask Web App
<img src="https://github.com/kyleskom/NBA-Machine-Learning-Sports-Betting/blob/master/Screenshots/Flask-App.png" width="922" height="580" />

This repo also includes a small Flask application to help view the data from this tool in the browser.  To run it:
```
cd Flask
flask --debug run
```

## Contributing

All contributions welcomed and encouraged.  
 
Please abide by the Open Source Contributing Guidelines: 
https://opensource.guide/how-to-contribute/ 
