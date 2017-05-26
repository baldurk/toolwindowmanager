project(twm-example)

set(SOURCES
    main.cpp
    MainWindow.cpp)

set(HEADERS
    MainWindow.h)

set(MOC_SOURCES
    MainWindow.h)

set(UI_FILES
    MainWindow.ui)

find_package(Qt5Core)
find_package(Qt5Widgets)

qt5_wrap_ui(OUT_UI_FILES ${UI_FILES})
qt5_wrap_cpp(OUT_MOC_FILES ${MOC_SOURCES})

add_executable(twm_example WIN32 ${SOURCES} ${HEADERS}
    ${OUT_UI_FILES} ${OUT_MOC_FILES})
target_link_libraries(twm_example toolwindowmanager)
target_include_directories(twm_example
    PRIVATE ${CMAKE_CURRENT_BINARY_DIR})

if(WIN32)
	find_package(Qt5WinExtras)
	target_link_libraries(twm_example Qt5::WinExtras)
endif()