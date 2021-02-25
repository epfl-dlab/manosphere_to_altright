# Code for: "Are Anti-Feminist Communities Gateways to the Far Right? Evidence from Reddit and YouTube"

Brief description of files (in `./analyses`):

- `final_graphs.ipynb`: create all figures shown in the paper.
- `(overview|migration|similarity)_(reddit|youtube).ipyb`: create helper files.
- `helpers.py` and `helpers_plot.py`: auxiliary functions and variables;

## Helper Files

We provide files both in `.pickle` and `.json` (or `.csv`, when appropriate). Files relative to Reddit are appended with `-reddit`.

- `comment-stats`: contains number of comments per year per community. Format:

```json
{
"UNIX_DATE": {"COMMUNITY1": "NUM_COMMENTS", ...}
}
```

- `user_df`: csv/pickle contains dataframe with user migrations. The appendix global contains the Manosphere aggregated. 
Fields explained below:
    1. `mean`, `lower`, `upper`: mean estimated migration along with 95% CIs. 
    2. `start`: date we started tracking in UNIX time. 
    4. `idx`: id of the date of the current observation. 0: 2006-2012, 1: 2013-2015, 2: 2016, 3: 2017, 4:2018.
    3. `idxo`: id of the date we started tracking. (same as above)
    5. `numUsersStart`: number of users tracked in the starting date.
    6. `numUsersTracked`, `pUsersTracked`: number and percentage of users we managed to track.
    7. `numUsersInfected`, `pUsersInfected`: number of users tracked that commented in Alt-right subreddits/channels.
    8. `constraint`: name of the starting constraint (which community users had to comment in).
    
- `intersections`: pickle file contains one dataframe for each combination of two communities (`x` and `y`). 
Dataframe contains number of users in each community in each year, as well as set operators. Names are self-explanatory

```
{
("COMMUNITY1", "COMMUNITY2)": pandas.DataFrame(...) 
}
```
