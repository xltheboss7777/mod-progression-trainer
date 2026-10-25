# Wir nutzen den universellen CMake-Standard statt dem AC-eigenen Makro
add_library(mod-progression-trainer OBJECT
    src/mod_progression_trainer.cpp
)

# Wir sagen dem Haupt-Compiler, wo er die Header-Dateien des Cores findet
target_include_directories(mod-progression-trainer PRIVATE
    ${CMAKE_SOURCE_DIR}/src/server/shared
    ${CMAKE_SOURCE_DIR}/src/server/game
    ${CMAKE_SOURCE_DIR}/src/server/database
)

# Wir hängen unser Skript an die globalen Weltskripte an
target_link_libraries(scripts INTERFACE mod-progression-trainer)

message(STATUS "--> mod-progression-trainer erfolgreich via Native-CMake geladen!")
