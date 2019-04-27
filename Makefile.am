
bin_PROGRAMS = AtomicParsley
noinst_HEADERS = src/AtomDefs.h src/AtomicParsley.h src/CDtoc.h \
  src/ap_types.h src/id3v2.h src/id3v2defs.h src/id3v2types.h \
  src/util.h

AM_CPPFLAGS = -DHAVE_CONFIG_H

if DARWIN
AM_CPPFLAGS += -DDARWIN_PLATFORM
AM_LDFLAGS = -framework Foundation -framework IOKit
endif

AtomicParsley_SOURCES = \
	src/util.cpp \
	src/arrays.cpp \
	src/iconv.cpp \
	src/parsley.cpp \
	src/extracts.cpp \
	src/sha1.cpp \
	src/uuid.cpp \
	src/id3v2.cpp \
	src/metalist.cpp \
	src/CDtoc.cpp \
	src/compress.cpp \
	src/main.cpp 


if NEED_GETOPT
AtomicParsley_SOURCES += \
	src/extras/getopt.c \
	src/extras/getopt1.c
endif

