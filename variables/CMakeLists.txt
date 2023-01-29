cmake_minimum_required(VERSION 3.14)

set(NAME Douglas)

set(AGE 42)

message("My name is a ${NAME} and my age is ${AGE}")

# Try different ways of setting the variable's value to see how it affects the
# dereferncing both with and without quotes
set(VAR aa bb cc)
#set(VAR aa;bb;cc)
#set(VAR "aa" "bb" "cc")
#set(VAR "aa bb cc")
#set(VAR "aa;bb;cc")

message(Unquoted: ${VAR})

message(Quoted: "${VAR}")
