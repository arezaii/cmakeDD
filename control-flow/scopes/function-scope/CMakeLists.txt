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
