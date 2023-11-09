# Ex. No: 7 PL/SQL program -BIGGEST OF THREE NUMBERS  
### DATE: 
### AIM: 
To create PL/SQL program to find biggest of three numbers.

### ALGORITHM:
1. Declare the variable a, b, c and assign value in Declare section.
2. begin the section
3. Find biggest of three numbers
4. Display the result.
5. End the begin section.

### Program:
```

DECLARE
  
  num1 NUMBER := 10; 
  num2 NUMBER := 20; 
  num3 NUMBER := 15;
  biggest NUMBER;
BEGIN
  
  IF num1 >= num2 AND num1 >= num3 THEN
    biggest := num1;
  ELSIF num2 >= num1 AND num2 >= num3 THEN
    biggest := num2;
  ELSE
    biggest := num3;
  END IF;


  DBMS_OUTPUT.PUT_LINE('The biggest number is: ' || biggest);
END;
/

```

### Output:
![Screenshot 2023-10-20 134256](https://github.com/Lakshmipriya2005/DBMS/assets/115525361/c45bc1ec-23a9-4554-9b19-91b8a9ce15d2)


### Result:
Thust the program was performed sucessfully.
