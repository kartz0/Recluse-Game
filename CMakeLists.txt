cmake_minimum_required(VERSION 3.0)
project("Recluse")


set(RECLUSE_NAME         "Recluse")
set(RECLUSE_EXE          ${RECLUSE_NAME})
set(RECLUSE_ENGINE       "Engine")

set(RECLUSE_LIB_DIR      ${CMAKE_SOURCE_DIR}/Libs)
set(RECLUSE_SOURCE_DIR   ${CMAKE_SOURCE_DIR}/Engine)
set(RECLUSE_TEST_DIR     ${CMAKE_SOURCE_DIR}/Test)

set(RECLUSE_ASSIMP__DIR  ${RECLUSE_LIB_DIR}/Assimp)
set(RECLUSE_OZZ_DIR      ${RECLUSE_LIB_DIR}/Ozz)
set(RECLUSE_FREETYPE_DIR ${RECLUSE_LIB_DIR}/FreeType)

# Libraries that REQUIRE enviroment variables set up.
set(RECLUSE_PHYSX_DIR    $ENV{PHYSXDIR})
set(RECLUSE_WWISE_DIR    $ENV{WWISESDK})

set(RECLUSE_THIRDPARTY_INCLUDE_DIRS
  ${RECLUSE_FREETYPE_DIR}/include
  ${RECLUSE_PHYSX_DIR}/include
)

set(RECLUSE_RENDERER     "Renderer")
set(RECLUSE_PHYSICS      "Physics")
set(RECLUSE_GAME         "Recluse")
set(RECLUSE_SHADER       "Shaders")
set(RECLUSE_CORE         "Core")
set(RECLUSE_AUDIO        "Audio")
set(RECLUSE_ANIMATION    "Animation")
set(RECLUSE_FILESYSTEM   "Filesystem")
set(RECLUSE_UI           "UI")
set(RECLUSE_SHADERS      "Shaders")

set(RECLUSE_RENDERER_INCLUDE_DIR   ${RECLUSE_SOURCE_DIR}/Renderer/Public)
set(RECLUSE_PHYSICS_INCLUDE_DIR    ${RECLUSE_SOURCE_DIR}/Physics/Public)
set(RECLUSE_ANIMATION_INCLUDE_DIR  ${RECLUSE_SOURCE_DIR}/Animation/Public)
set(RECLUSE_AUDIO_INCLUDE_DIR      ${RECLUSE_SOURCE_DIR}/Audio/Public)
set(RECLUSE_CORE_INCLUDE_DIR       ${RECLUSE_SOURCE_DIR}/Core/Public)
set(RECLUSE_SHADER_DIR             ${RECLUSE_SOURCE_DIR}/Shader)
set(RECLUSE_GAME_INCLUDE_DIR       ${RECLUSE_SOURCE_DIR}/Game/Public)
set(RECLUSE_UI_INCLUDE_DIR         ${RECLUSE_SOURCE_DIR}/UI/Public)
set(RECLUSE_FILESYSTEM_INCLUDE_DIR ${RECLUSE_SOURCE_DIR}/Filesystem/Public)
set(RECLUSE_SHADERS_INCLUDE_DIR    ${CMAKE_CURRENT_SOURCE_DIR}/Shaders)

set(RECLUSE_ENGINE_INCLUDE_DIRS
  ${RECLUSE_THIRDPARTY_INCLUDE_DIRS}
  ${RECLUSE_RENDERER_INCLUDE_DIR}
  ${RECLUSE_PHYSICS_INCLUDE_DIR}
  ${RECLUSE_ANIMATION_INCLUDE_DIR}
  ${RECLUSE_AUDIO_INCLUDE_DIR}
  ${RECLUSE_CORE_INCLUDE_DIR}
  ${RECLUSE_SHADER_DIR}
  ${RECLUSE_GAME_INCLUDE_DIR}
  ${RECLUSE_UI_INCLUDE_DIR}
  ${RECLUSE_FILESYSTEM_INCLUDE_DIR}
)

set(RECLUSE_ENGINE_LINK_LIBRARIES
  ${RECLUSE_RENDERER}
  ${RECLUSE_GAME}
  ${RECLUSE_PHYSICS}
  ${RECLUSE_ANIMATION}
  ${RECLUSE_CORE}
  ${RECLUSE_AUDIO}
  ${RECLUSE_UI}
  ${RECLUSE_FILESYSTEM}
)

# find vulkan render API.
find_package(Vulkan)

# Add directory.
add_subdirectory(${RECLUSE_SOURCE_DIR})
add_subdirectory(${RECLUSE_TEST_DIR})