set(MY_LIST cmake;is neat)

message("the list contains ${MY_LIST}")

set(FOO a b c;d "e;f" 2.7 "Hello There")
message( ${FOO} )

list(APPEND FOO 4.2 XX)
message( ${FOO} )

list(REMOVE_AT FOO 2 -3)
message( ${FOO} )

list(REMOVE_ITEM FOO a 2.7)
message( ${FOO} )

list(INSERT FOO 2 XX 2.7)
message( ${FOO} )

list(REVERSE FOO)
message( ${FOO} )

list(REMOVE_DUPLICATES FOO)
message( ${FOO} )

list(SORT FOO)
message( ${FOO} )

list( LENGTH FOO len_var )
list( GET FOO 2 5 6 sub_list )

list( SUBLIST FOO 2 -1 sub_list2 )
list( JOIN FOO ++ str_list )
list( FIND FOO XX find_var )

message( "len_var: ${len_var}" )
message( "sub_list: ${sub_list}" )
message( "sub_list2: ${sub_list2}" )
message( "str_list: ${str_list}" )
message( "find_var: ${find_var}" )

# a list of lists
set(list_of_lists a b c)
set(a 1 2 3)
set(b 4;5;6)
set(c "7;8;9")
# be sure to double-dereference the items!
foreach(list_name IN LISTS list_of_lists)
  foreach(value IN LISTS ${list_name})
    message(${value})
  endforeach()
endforeach()
