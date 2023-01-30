
message("Inside subdirectory Matryoshka: before modification: ${Name}")
set(Name Ford PARENT_SCOPE)
message("Inside subdirectory Matryoshka: after modification: ${Name}")

add_subdirectory(Matryoshka1)
message("Inside subdirectory Matryoshka: after adding Matryoshka1 subdirectory, name is ${Name}")
