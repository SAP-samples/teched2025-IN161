# Exercise 3 - Extending the Pipeline: Setup Custom Header Properties

In this exercise, we will create...

## Exercise 3.1 - Add Custom Header Properties

After completing these steps you will have created...

1. Click here.
<br>![](/exercises/ex3/images/02_01_0010.png)

2.	Insert this line of code.
```abap
response->set_text( |Hello ABAP World! | ). 
```



## Exercise 3.2 - Test and Monitor

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

Continue to - [Exercise 4 - Setup Custom Receiver Determination](../ex4/README.md)
