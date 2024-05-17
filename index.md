# project
## Week 6 (4/30)
1. **Survey Data from NHANES**
   - import the survey data from the 1999-2000 NANES
   - use the stata command as follows
     ```stata
     import sasxport5 "https://wwwn.cdc.gov/Nchs/Nhanes/1999-2000/DEMO.XPT", clear
     ```
2. **Mortality Follow-up Data from NCHS**
   - click this [Link](https://ftp.cdc.gov/pub/)
   - click as follows
     - Health Statistics
       - NCHS
         - Datalinkage
           - Linked Mortality
             -```Stata_ReadInProgramALlSurveys.do```

# project
3. **Create followup.do filw**
    - use the do file from NCHS
    - edit the absolute file path
    - edit ```SURVEY``` and change it into ```NHANES_1999_2000```
    - save it as ```followup.do```
4. **Merge Data between NHANES and NCHS**
    - use the following stata commands
    ```stata
      //use your own username/project repo instead of the class repo below
      global repo "https://raw.githubusercontent.com/vrshank/project/main/"
      do ${repo}followup.do
      save followup, replace 
      import sasxport5 "https://wwwn.cdc.gov/Nchs/Nhanes/1999-2000/DEMO.XPT", clear
      merge 1:1 seqn using followup
      lookfor follow
    ```
5. **Prepare for Week 7**
     - import the specific health questionnair data
## Week 7 (5/7)

1. **Use nonparametric (Kaplan-Meier) method**
   - click [here](nonpara.png) for K-M figure.
2. **Use semiparametric (Cox Regression) method**
   - click [here](semipara_unadj.png) for the figure outlining HRs.
3. **Use parametric (Weibull regression) method**
   - click [here](semipara_adj.png) for HRs adjusing for age.
4. **Compare the adjusted figure with unadjusted one**
   - click [here](unadj_adj.png) for a combined figure
6. **for HW7, adjusted for age, race, and two additional variables**
   - click [here](scenario.png) for the scenario of 40 year-old male who self-describes as being in good health with citizenship and with the household size of 6 compared with a person with the household size of 4.
7. **for the whole do.file**
   - click [here](dyndoc.html) for the whole analysis.
