cmake_minimum_required(VERSION 3.26)
project(VulkanTest)

set(CMAKE_CXX_STANDARD 17)

# Path to VulkanSDK and GLFW
set(VULKAN_PATH "C:/VulkanSDK")
set(GLFW_PATH "C:/glfw-3.3.8.bin.WIN64")

# Find Vulkan package
find_package(Vulkan REQUIRED)

# Manually specify the path to GLFW headers and libraries
include_directories(${GLFW_PATH}/include)
link_directories(${GLFW_PATH}/lib-mingw-w64)  # Use MinGW directory

# Add the executable
add_executable(VulkanTest main.cpp)

# Link Vulkan and GLFW libraries to your project
target_link_libraries(VulkanTest Vulkan::Vulkan)
target_link_libraries(VulkanTest glfw3)
