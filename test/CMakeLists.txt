
find_library (cmocka NAMES multimap.a multimap)

include_directories (${MULTIMAP_PUBLIC_INCLUDE_DIR})

set (MULTIMAP_TESTSUITE_SOURCES
    "multimap_testsuite.c"
)

add_executable (multimap_testsuite EXCLUDE_FROM_ALL ${MULTIMAP_TESTSUITE_SOURCES})

add_test (NAME multimap_testsuite COMMAND multimap_testsuite)
add_dependencies (build_and_test multimap_testsuite)

add_definitions ("-Wall")
add_definitions ("-Werror")

target_link_libraries (multimap_testsuite void-multimap)
target_link_libraries (multimap_testsuite cmocka)
