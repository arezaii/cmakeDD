cmake_minimum_required(VERSION 3.14)

set(NAME Zaphod)
set(OTHER_NAME Ford)
set(AGE 42)

message("My name is ${NAME} and I'm ${AGE} years old")
set(NAME OTHER_NAME)
message("My name is ${${NAME}} and I'm ${AGE} years old")

# Try different ways of setting the variable's value to see how it affects the
# dereferncing both with and without quotes
set(VAR aa bb cc)
#set(VAR aa;bb;cc)
#set(VAR "aa" "bb" "cc")
#set(VAR "aa bb cc")
#set(VAR "aa;bb;cc")

message(Unquoted: ${VAR})

message(Quoted: "${VAR}")
