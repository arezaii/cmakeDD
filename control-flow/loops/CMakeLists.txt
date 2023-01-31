cmake_minimum_required(VERSION 3.14)

## While

set(FOO a)
# could append another 'a' with the following command, repeat it N times...
#set(FOO ${FOO}a)

# OR use the while command
while(NOT FOO STREQUAL "aaaaaaaaaa")
	set(FOO ${FOO}a)
	message(${FOO})
endwhile()


## Foreach

foreach(WORD so long, and thanks for all the fish)
	message(${WORD})
endforeach()

foreach(i RANGE 100 105)
	message("index_${i}")
endforeach()

set(LIST1 0 1)
set(LIST2 2;3)
set(LIST3 "4;5")

foreach(i IN LISTS LIST1 LIST2 LIST3)
	message("i = ${i}")
endforeach()
