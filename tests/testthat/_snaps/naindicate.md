# something prints

    Code
      print(rec)
    Output
      Recipe
      
      Inputs:
      
            role #variables
         outcome          1
       predictor          5
      
      Operations:
      
      Creating missing data variable indicators for all_predictors()

---

    Code
      prep(rec, training = airquality, verbose = TRUE)
    Output
      oper 1 step indicate na [training] 
      The retained training set is ~ 0.01 Mb  in memory.
      
      Recipe
      
      Inputs:
      
            role #variables
         outcome          1
       predictor          5
      
      Training data contained 153 data points and 42 incomplete rows. 
      
      Operations:
      
      Creating missing data variable indicators for Solar.R, Wind, Temp, Month, Day [trained]

# empty printing

    Code
      rec
    Output
      Recipe
      
      Inputs:
      
            role #variables
         outcome          1
       predictor         10
      
      Operations:
      
      Creating missing data variable indicators for <none>

---

    Code
      rec
    Output
      Recipe
      
      Inputs:
      
            role #variables
         outcome          1
       predictor         10
      
      Training data contained 32 data points and no missing data.
      
      Operations:
      
      Creating missing data variable indicators for <none> [trained]
