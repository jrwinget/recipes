# check_name() is used

    Code
      prep(rec, training = dat)
    Condition
      Error in `step_indicate_na()`:
      Caused by error in `bake()`:
      ! Name collision occured. The following variable names already exists:
      i  na_ind_mpg

# empty printing

    Code
      rec
    Message
      
      -- Recipe ----------------------------------------------------------------------
      
      -- Inputs 
      Number of variables by role
      outcome:    1
      predictor: 10
      
      -- Operations 
      * Creating missing data variable indicators for: <none>

---

    Code
      rec
    Message
      
      -- Recipe ----------------------------------------------------------------------
      
      -- Inputs 
      Number of variables by role
      outcome:    1
      predictor: 10
      
      -- Training information 
      Training data contained 32 data points and no incomplete rows.
      
      -- Operations 
      * Creating missing data variable indicators for: <none> | Trained

# printing

    Code
      print(rec)
    Message
      
      -- Recipe ----------------------------------------------------------------------
      
      -- Inputs 
      Number of variables by role
      outcome:   1
      predictor: 5
      
      -- Operations 
      * Creating missing data variable indicators for: all_predictors()

---

    Code
      prep(rec)
    Message
      
      -- Recipe ----------------------------------------------------------------------
      
      -- Inputs 
      Number of variables by role
      outcome:   1
      predictor: 5
      
      -- Training information 
      Training data contained 153 data points and 42 incomplete rows.
      
      -- Operations 
      * Creating missing data variable indicators for: Solar.R, Wind, ... | Trained
