# Wir registrieren eine Funktion, die AzerothCore erst ausführt, 
# NACHDEM der gesamte Core-Quellcode erfolgreich eingelesen wurde.
macro(AFTER_SRC_LOAD)

    # Jetzt existiert das Ziel "scripts" und wir können unsere Datei sicher anhängen
    target_sources(scripts PRIVATE
        ${CMAKE_CURRENT_SOURCE_DIR}/src/mod_progression_trainer.cpp
    )
    
    message(STATUS "--> [SUCCESS] mod-progression-trainer wurde erfolgreich über AFTER_SRC_LOAD injiziert!")

endmacro()
