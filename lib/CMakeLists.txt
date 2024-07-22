if (CMAKE_Fortran_COMPILER_ID)
    set(FCIDUMP_FORTRAN_SRCS "FCIdumpF.F90")
endif ()
add_library(FCIdump FCIdump.cpp FCIdump.h ${FCIDUMP_FORTRAN_SRCS})

target_compile_options(FCIdump PUBLIC -fpermissive)

### For including header files
target_include_directories(FCIdump INTERFACE ${CMAKE_CURRENT_SOURCE_DIR})
### For linking Fortran static library
target_include_directories(FCIdump INTERFACE ${PROJECT_BINARY_DIR}/lib)
