# BUG LOG

[  FAILED  ] FieldTest.constructorWithArgument
// This test fails because when you call the constructor for
Field with an argument, such as 20 in this case, it will make
the map the correct size, but it doesn't store the size in
FIELD_DIMENSION (and it couldn't anyway because it's const).
When placing a mine at 19, 19, which should be in bounds, it
fails because it checks against FIELD_DIMENSION, which is by
default 10.