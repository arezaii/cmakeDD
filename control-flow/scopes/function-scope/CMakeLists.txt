cmake_minimum_required(VERSION 3.14)

set(Name Douglas)

function(print_name)
	message("Inside: before modification: ${Name}")
	set(Name Ford PARENT_SCOPE)
	message("Inside: after modification: ${Name}")
endfunction()

message("Outside: before function call: ${Name}")
print_name()
message("Outside: after function call: ${Name}")


function(mutate varName)
  SET(${varName} ${varName}${${varName}}${${varName}} PARENT_SCOPE)
endfunction()

SET(arg "foo")
mutate(arg)
MESSAGE(${arg})
