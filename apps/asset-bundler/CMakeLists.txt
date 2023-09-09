project(asset-bundler)

add_library(${PROJECT_NAME} STATIC
    ./asset-bundler/asset_bundler.h
    ./asset-bundler/asset_bundler.cpp

    ./asset-bundler/loaders/iloader.h
    ./asset-bundler/loaders/wavefront_loader.h
    ./asset-bundler/loaders/wavefront_loader.cpp

    ./asset-bundler/objects/iserializable.h
    ./asset-bundler/objects/mesh.h
    ./asset-bundler/objects/mesh.cpp
)

include_directories(../asset-bundler/)

include_directories(../logger/)
target_link_libraries(${PROJECT_NAME} PRIVATE logger)

find_package(glm CONFIG REQUIRED)
target_link_libraries(${PROJECT_NAME} PRIVATE glm::glm)