set(CMAKE_CXX_FLAGS_RELEASE "-march=core2 -fomit-frame-pointer -fexpensive-optimizations -O3")
add_definitions(
	-Wall -Wextra
	-fexceptions
	-Wno-unused-value -Wno-unused
	-fno-strict-aliasing
	-ffast-math -fno-math-errno)

include_directories(../inc)
include_directories(../crnlib)

add_executable(crunch
	corpus_gen.cpp
	corpus_gen.h
	corpus_test.cpp
	corpus_test.h
	crunch.cpp)
target_link_libraries(crunch crnlib pthread)
