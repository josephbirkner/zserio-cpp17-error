project(zseiro-test)

# Assume zserio submodule is cloned under deps/zserio
add_subdirectory(zserio/compiler/extensions/cpp/runtime/src)
set(ZSERIO_REPO_ROOT "${CMAKE_CURRENT_LIST_DIR}/zserio")

add_subdirectory(zserio-cmake-helper)

add_zserio_library(mylib
  ROOT ${CMAKE_CURRENT_LIST_DIR}
  ENTRY test.zs)

target_compile_features(mylib PUBLIC cxx_std_17)
