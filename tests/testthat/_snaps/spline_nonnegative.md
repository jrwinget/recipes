# errors if degree > deg_free (#1170)

    Code
      recipe(~., data = mtcars) %>% step_spline_nonnegative(mpg, degree = 3,
        deg_free = 3, complete_set = TRUE) %>% prep()
    Condition
      Error in `step_spline_nonnegative()`:
      Caused by error in `prep()`:
      ! `degree` (3) must be less than to `deg_free` (3) when `complete_set = FALSE`.

---

    Code
      recipe(~., data = mtcars) %>% step_spline_nonnegative(mpg, degree = 4,
        deg_free = 3, complete_set = FALSE) %>% prep()
    Condition
      Error in `step_spline_nonnegative()`:
      Caused by error in `prep()`:
      ! `degree` (4) must be less than or equal to `deg_free` (3) when `complete_set = TRUE`.

# check_name() is used

    Code
      prep(rec, training = dat)
    Condition
      Error in `step_spline_nonnegative()`:
      Caused by error in `bake()`:
      ! Name collision occurred. The following variable names already exist:
      * `mpg_01`

# bake method errors when needed non-standard role columns are missing

    Code
      bake(rec_trained, new_data = mtcars[, -3])
    Condition
      Error in `step_spline_nonnegative()`:
      ! The following required column is missing from `new_data`: disp.

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
      * Non-negative spline expansion: <none>

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
      * Non-negative spline expansion: <none> | Trained

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
      * Non-negative spline expansion: carbon and hydrogen

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
      Training data contained 536 data points and no incomplete rows.
      
      -- Operations 
      * Non-negative spline expansion: carbon and hydrogen | Trained

