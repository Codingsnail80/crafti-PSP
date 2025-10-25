cmake_minimum_required(VERSION 3.11)

project(crafti)

add_executable(${PROJECT_NAME} main.cpp
    nGL/fastmath.cpp
    nGL/gldrawarray.cpp
    nGL/texturetools.cpp
    nGL/fastmath.h
    nGL/fix.h
    nGL/gl.h
    nGL/glconfig.h
    nGL/gldrawarray.h
    nGL/texturetools.h
    nGL/triangle.inc.h
    aabb.cpp
    aabb.h
    billboardrenderer.cpp
    billboardrenderer.h
    blocklisttask.cpp
    blocklisttask.h
    blockrenderer.cpp
    blockrenderer.h
    cakerenderer.cpp
    cakerenderer.h
    chunk.cpp
    chunk.h
    colorrenderer.cpp
    colorrenderer.h
    doorrenderer.cpp
    doorrenderer.h
    fluidrenderer.cpp
    fluidrenderer.h
    font.cpp
    font.h
    glassrenderer.cpp
    glassrenderer.h
    glconfig.h
    gldrawable.h
    helptask.cpp
    helptask.h
    inventory.cpp
    inventory.h
    lamprenderer.cpp
    lamprenderer.h
    leavesrenderer.cpp
    leavesrenderer.h
    libndls.h
    menutask.cpp
    menutask.h
    particle.cpp
    particle.h
    perlinnoise.cpp
    perlinnoise.h
    pressurerenderer.cpp
    pressurerenderer.h
    redtorchrenderer.cpp
    redtorchrenderer.h
    settingstask.cpp
    settingstask.h
    switchrenderer.cpp
    switchrenderer.h
    task.cpp
    task.h
    terrain.cpp
    terrain.h
    tntrenderer.cpp
    tntrenderer.h
    torchrenderer.cpp
    torchrenderer.h
    wheatrenderer.cpp
    wheatrenderer.h
    wirerenderer.cpp
    wirerenderer.h
    world.cpp
    world.h
    worldtask.cpp
    worldtask.h
)

include(FindPkgConfig)
pkg_search_module(SDL REQUIRED sdl)

target_include_directories(${PROJECT_NAME} PRIVATE ${SDL_INCLUDE_DIRS})

add_subdirectory(nGL)

target_link_libraries(${PROJECT_NAME} PRIVATE nGL
    ${SDL_LIBRARIES}
    pspgu
    pspge
    pspdebug
    pspdisplay
    pspkernel
    m
    z
    pspsdk
)

# Create an EBOOT.PBP file
create_pbp_file(
    TARGET ${PROJECT_NAME}
    ICON_PATH NULL
    BACKGROUND_PATH NULL
    PREVIEW_PATH NULL
    TITLE "Crafti PSP"
    VERSION 01.00
)
