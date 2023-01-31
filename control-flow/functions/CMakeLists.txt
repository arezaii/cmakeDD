cmake_minimum_required(VERSION 3.14)


function(print_name_single_deref name_arg)
  message("Single deref, name is ${name_arg}")
endfunction()

function(print_name_double_deref name_arg)
  message("Double deref, name is ${${name_arg}}")
endfunction()


# redefining existing function with same name (note that argument name/count is not considered)
function(print_detail name_arg)
	message("1. My name is ${${name_arg}}")
endfunction()

function(print_detail name_arg)
	message("2. My name is ${${name_arg}}")
endfunction()


set(Name Douglas)

print_name_single_deref(Name)
print_name_single_deref(${Name})

print_name_double_deref(Name)
print_name_double_deref(${Name})

_print_detail(Name)
print_detail(Name)

function(print_name_opt name_var)
	message("My name is ${${name_var}}")

	if(DEFINED ARGV1)
		message("Hello, my name is ${ARGV1}")
	endif()

	message("ARGC=	${ARGC}")
	message("ARGV=	${ARGV}")
	message("ARGN=	${ARGN}")

	if(DEFINED ARGV0)
		message("ARGV0=	${ARGV0}")
	endif()
	if(DEFINED ARGV1)
		message("ARGV1=	${ARGV1}")
	endif()
	if(DEFINED ARGV2)
		message("ARGV2=	${ARGV2}")
	endif()
	if(DEFINED ARGV3)
		message("ARGV3=	${ARGV3}")
	endif()
endfunction()

print_name_opt(Name Ford Marvin)
