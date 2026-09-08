pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = audio_memlogger.pc
EXTRA_DIST = $(pkgconfig_DATA)

AM_CFLAGS = -Wall -Werror

AM_CFLAGS += -I ${top_srcdir}
AM_CPPFLAGS = -I ${top_srcdir}/armemlog/inc

armemlogger_headers = ${top_srcdir}/armemlog/inc/graph_queue.h \
              ${top_srcdir}/armemlog/inc/kpi_queue.h \
              ${top_srcdir}/armemlog/inc/mem_logger.h \
              ${top_srcdir}/armemlog/inc/pal_state_queue.h \
              ${top_srcdir}/armemlog/inc/spf_reset_queue.h

# Header installation path
library_include_HEADERS = $(armemlogger_headers)
library_includedir = $(includedir)

# Library build
lib_LTLIBRARIES      = libarmemlog.la
libarmemlog_la_SOURCES   = armemlog/src/mem_logger.cpp
libarmemlog_la_CPPFLAGS := $(AM_CPPFLAGS)
libarmemlog_la_CFLAGS = $(AM_CFLAGS)
libarmemlog_la_LDFLAGS   = -llog -lexpat -lar-osal -shared -avoid-version
