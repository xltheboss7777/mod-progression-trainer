# Wir binden die Datei direkt in die globale Script-Bibliothek ein
# Das umgeht den anfälligen automatischen gen_scriptloader von Docker
target_sources(scripts PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}/src/mod_progression_trainer.cpp
)

message(STATUS "--> Mod-Progression-Trainer manuell in Scripts injiziert (Docker-Safe)!")
