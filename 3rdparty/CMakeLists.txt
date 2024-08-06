#----------------------------------------------------
if(${BUILD_TESTS})
    # git submodules
    if(${GIT_FOUND})
        execute_process(
        COMMAND ${GIT_EXECUTABLE} submodule update --init 3rdparty/gtest
        WORKING_DIRECTORY ${PROJECT_SOURCE_DIR}
    )
    endif()

    add_subdirectory(gtest)
    set(GTEST_INCLUDE_DIRS "${CMAKE_CURRENT_SOURCE_DIR}/gtest/googletest/include" PARENT_SCOPE)
    message("${GTEST_INCLUDE_DIRS}*")
    set(GTEST_LIBRARY "gtest" PARENT_SCOPE)
endif()
#----------------------------------------------------
