cmake_minimum_required (VERSION 3.15)

enable_testing()

set(TARGET "MyTest")

add_executable(${TARGET}
	"test_main.cpp"
)

find_package(GTest CONFIG REQUIRED)

target_link_libraries(${TARGET} PRIVATE
	GTest::gtest
	GTest::gtest_main
)

add_test(AllTestsInMain ${TARGET})
