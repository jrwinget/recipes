# error checks

    Code
      rec %>% step_window(y1, size = 6)
    Condition
      Error in `step_window()`:
      ! `size` should be odd.

---

    Code
      rec %>% step_window(y1, size = NA)
    Condition
      Error in `step_window()`:
      ! `size` needs a value.

---

    Code
      rec %>% step_window(y1, statistic = "average")
    Condition
      Error in `step_window()`:
      ! `statistic` should be one of: 'mean', 'median', 'sd', 'var', 'sum', 'prod', 'min', 'max'

---

    Code
      rec %>% step_window(y1, size = 1)
    Condition
      Error in `step_window()`:
      ! `size` should be at least 3.

---

    Code
      rec %>% step_window(y1, size = 2)
    Condition
      Error in `step_window()`:
      ! `size` should be odd.

---

    Code
      rec %>% step_window(y1, size = -1)
    Condition
      Error in `step_window()`:
      ! `size` should be at least 3.

---

    Code
      rec %>% step_window(y1, size = pi)
    Condition
      Warning:
      `size` was not an integer (3.14159265358979) and was converted to 3.
    Message
      
      -- Recipe ----------------------------------------------------------------------
      
      -- Inputs 
      Number of variables by role
      predictor: 6
      
      -- Operations 
      * Moving 3-point mean on: y1

---

    Code
      prep(rec %>% step_window(fac), training = sim_dat)
    Condition
      Error in `step_window()`:
      Caused by error in `prep()`:
      ! All columns selected for the step should be double, or integer.

---

    Code
      prep(rec %>% step_window(y1, size = 1000L), training = sim_dat)
    Condition
      Error in `step_window()`:
      ! `size` should be odd.

---

    Code
      prep(bad_names, training = sim_dat)
    Condition
      Error in `step_window()`:
      Caused by error in `prep()`:
      ! There were 2 term(s) selected but 1 values for the new features were passed to `names`.

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
      * Moving 3-point mean on: <none>

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
      * Moving 3-point mean on: <none> | Trained

---

    Code
      print(rec)
    Message
      
      -- Recipe ----------------------------------------------------------------------
      
      -- Inputs 
      Number of variables by role
      outcome:    1
      predictor: 10
      
      -- Operations 
      * Moving 3-point mean on: <none>

---

    Code
      prep(rec)
    Message
      
      -- Recipe ----------------------------------------------------------------------
      
      -- Inputs 
      Number of variables by role
      outcome:    1
      predictor: 10
      
      -- Training information 
      Training data contained 32 data points and no incomplete rows.
      
      -- Operations 
      * Moving 3-point mean on: <none> | Trained
