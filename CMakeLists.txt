project(replay-source)

if(MSVC)
	set(replay-source_PLATFORM_DEPS
		w32-pthreads)
endif()

set(replay-source_HEADERS
	replay.h)
set(replay-source_SOURCES
	replay-source.c
	replay-filter.c)

add_library(replay-source MODULE
	${replay-source_HEADERS}
	${replay-source_SOURCES})
target_link_libraries(replay-source
	libobs
	${replay-source_PLATFORM_DEPS})

install_obs_plugin_with_data(replay-source data)