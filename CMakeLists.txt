# Dodaj pliki źródłowe
project(FirstProject)

set(IS_MACOS False)

if (IS_MACOS)

message("macmamacmcamcamcamcamcamcamcamcamcamcamcamcamcmaamcmcamcam")

set(SOURCES
    main.cpp
)

set(PROJECT_NAME "FirstProject")

# Ustaw ustawienia dla aplikacji macOS .app
set(MACOSX_BUNDLE_BUNDLE_NAME "FirstProject")
set(MACOSX_BUNDLE_GUI_IDENTIFIER "com.twoja.nazwa.${PROJECT_NAME}")
set(MACOSX_BUNDLE_ICON_FILE "Icon.icns")
set(MACOSX_BUNDLE_INFO_PLIST "${CMAKE_CURRENT_SOURCE_DIR}/Info.plist")

# Dodaj plik ikony (opcjonalne)
set_source_files_properties(${CMAKE_CURRENT_SOURCE_DIR}/Icon.icns PROPERTIES MACOSX_PACKAGE_LOCATION Resources)

# Dodaj pliki do aplikacji
add_executable(${PROJECT_NAME} MACOSX_BUNDLE ${SOURCES} ${CMAKE_CURRENT_SOURCE_DIR}/Icon.icns)

# Ustaw flagi kompilatora
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

else()

message("XDDSDASDASDASDADASDASDASDADSADASDASDASD")

set(SOURCES
    main.cpp
)

set(PROJECT_NAME "FirstProject")

# Dodaj plik ikony (opcjonalne)
#set_source_files_properties(${CMAKE_CURRENT_SOURCE_DIR}/Icon.icns PROPERTIES MACOSX_PACKAGE_LOCATION Resources)

# Dodaj pliki do aplikacji
add_executable(${PROJECT_NAME} ${SOURCES})

# Ustaw flagi kompilatora
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

endif()

# Dodaj inne biblioteki i ustawienia
# target_link_libraries(${PROJECT_NAME} <biblioteki>)

# Dodaj inne pliki do aplikacji (np. zasoby)
# file(COPY "resources" DESTINATION "${CMAKE_BINARY_DIR}/${PROJECT_NAME}.app/Contents/Resources")