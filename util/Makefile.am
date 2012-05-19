noinst_LTLIBRARIES = libutil.la libtest.la

libutil_la_SOURCES = arena.h \
		     coding.h \
		     crc32c.h \
		     hash.h \
		     histogram.h \
		     logging.h \
		     mutexlock.h \
		     posix_logger.h \
		     random.h \
		     arena.cc \
		     bloom.cc \
		     cache.cc \
		     coding.cc \
		     comparator.cc \
		     crc32c.cc \
		     env.cc \
		     env_posix.cc \
		     filter_policy.cc \
		     hash.cc \
		     histogram.cc \
		     logging.cc \
		     options.cc \
		     status.cc

libtest_la_SOURCES = testharness.cc \
		     testutil.cc

libutil_la_CXXFLAGS = $(AM_CXXFLAGS) -I$(top_srcdir) -I$(top_srcdir)/include
libtest_la_CXXFLAGS = $(AM_CXXFLAGS) -I$(top_srcdir) -I$(top_srcdir)/include
