ENABLE_TESTING()

FIND_PACKAGE(Check REQUIRED)
INCLUDE_DIRECTORIES(${CHECK_INCLUDE_DIRS})
SET(LIBS ${LIBS} ${CHECK_LIBRARIES} todo_lib)

INCLUDE_DIRECTORIES( . ../src)
ADD_EXECUTABLE(test_todo test_todo.c)
ADD_TEST(test_todo ${CMAKE_CURRENT_BINARY_DIR}/test_todo)
TARGET_LINK_LIBRARIES(test_todo ${LIBS})
