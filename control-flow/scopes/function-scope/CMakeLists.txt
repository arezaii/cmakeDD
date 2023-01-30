cmake_minimum_required(VERSION 3.14)

set(Name Douglas)

function(print_name)
	message("Inside function: before modification: ${Name}")
	set(Name Ford PARENT_SCOPE)
	message("Inside function: after modification: ${Name}")
endfunction()

message("Outside function: before function call: ${Name}")
print_name()
message("Outside function: after function call: ${Name}")
