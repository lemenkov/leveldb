noinst_LTLIBRARIES = libdb.la

libdb_la_SOURCES = builder.cc \
		   builder.h \
		   c.cc \
		   db_impl.cc \
		   db_impl.h \
		   db_iter.cc \
		   db_iter.h \
		   dbformat.cc \
		   dbformat.h \
		   filename.cc \
		   filename.h \
		   log_format.h \
		   log_reader.cc \
		   log_reader.h \
		   log_writer.cc \
		   log_writer.h \
		   memtable.cc \
		   memtable.h \
		   repair.cc \
		   skiplist.h \
		   snapshot.h \
		   table_cache.cc \
		   table_cache.h \
		   version_edit.cc \
		   version_edit.h \
		   version_set.cc \
		   version_set.h \
		   write_batch.cc \
		   write_batch_internal.h

libdb_la_CXXFLAGS = $(AM_CXXFLAGS) -I$(top_srcdir) -I$(top_srcdir)/include
