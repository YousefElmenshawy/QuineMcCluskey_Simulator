cmake_minimum_required(VERSION 3.30)
project(QuineMcCluskey_Simulator)

set(CMAKE_CXX_STANDARD 14)

include_directories(.)

add_executable(QuineMcCluskey_Simulator
    implicant.cpp
    implicant.h
    main.cpp
    QuineMcCluskey.cpp
    QuineMcCluskey.h
    term.cpp
    term.h)
