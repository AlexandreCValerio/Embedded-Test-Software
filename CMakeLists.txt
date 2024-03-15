cmake_minimum_required(VERSION 3.15)

project(
  EmbeddedTestSoftware
  VERSION 1.0
  LANGUAGES C
  )

add_library(ets
  src/conioCompat.c
  src/console.c
  src/consoleCommands.c
  src/consoleIo.c
  )

target_include_directories(ets
  PUBLIC
    inc
)

add_executable(MyExample src/main.c)

target_link_libraries(MyExample 
  PRIVATE
    ets
  )