project(DemoApplication)

add_executable(DemoApplication
  main.cpp
  IMGUIApplication.cpp
)

target_link_libraries(DemoApplication
   PRIVATE
      project::warnings_options
      project::warning_suppressions
      imgui::demo
      imgui::imgui
)

if(MSVC)
  target_link_options(${PROJECT_NAME} PRIVATE
    /SUBSYSTEM:WINDOWS
  )
endif()

install(TARGETS DemoApplication DESTINATION .)
