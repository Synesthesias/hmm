# Add source to this project's executable.
file(GLOB ROOT_SOURCE *.cpp)
file(GLOB ROOT_HEADER *.h)

add_library(hmm ${ROOT_SOURCE} ${ROOT_HEADER})

target_include_directories(hmm PUBLIC
  $<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}>
  $<BUILD_INTERFACE:${GLM_INCLUDE_DIR}>
  $<INSTALL_INTERFACE:${CMAKE_INSTALL_INCLUDEDIR}>
)

if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET hmm PROPERTY CXX_STANDARD 20)
endif()
