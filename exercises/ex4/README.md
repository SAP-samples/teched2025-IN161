# Exercise 4 - Extending the Pipeline: Setup Custom Receiver Determination

In this exercise, we will create...

## Exercise 3.1 - Create Custom Integration Flow

After completing these steps you will have created...

1. Click here.
<br>![](/exercises/ex3/images/02_01_0010.png)

2.	Insert this line of code.
```abap
response->set_text( |Hello ABAP World! | ). 
```

## Exercise 3.2 - Configure the Partner Directory

After completing these steps you will have...


## Exercise 3.3 - Test and Monitor

After completing these steps you will have...

1.	Enter this code.
```abap
DATA(lt_params) = request->get_form_fields(  ).
READ TABLE lt_params REFERENCE INTO DATA(lr_params) WITH KEY name = 'cmd'.
  IF sy-subrc = 0.
    response->set_status( i_code = 200
                     i_reason = 'Everything is fine').
    RETURN.
  ENDIF.

```

2.	Click here.
<br>![](/exercises/ex3/images/02_02_0010.png)

## Summary

You've now ...

Congratulations. You have completed all exercises.
