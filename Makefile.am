SUBDIRS = db helpers/memenv port table util

lib_LTLIBRARIES = libleveldb.la

libleveldbnobase_includedir = $(includedir)/leveldb
libleveldbnobase_include_HEADERS = ./include/leveldb/c.h \
				   ./include/leveldb/cache.h \
				   ./include/leveldb/comparator.h \
				   ./include/leveldb/db.h \
				   ./include/leveldb/env.h \
				   ./include/leveldb/filter_policy.h \
				   ./include/leveldb/iterator.h \
				   ./include/leveldb/options.h \
				   ./include/leveldb/slice.h \
				   ./include/leveldb/status.h \
				   ./include/leveldb/table.h \
				   ./include/leveldb/table_builder.h \
				   ./include/leveldb/write_batch.h

libleveldb_la_SOURCES =

libleveldb_la_LIBADD = @SNAPPY_LIBS@ \
		      $(top_builddir)/db/libdb.la \
		      $(top_builddir)/port/libport.la \
		      $(top_builddir)/table/libtable.la \
		      $(top_builddir)/util/libutil.la

libleveldb_la_LDFLAGS = $(AM_LDFLAGS) -version-info $(LEVELDB_VERSION_INFO)

EXTRA_DIST = doc AUTHORS LICENSE NEWS README TODO

TESTS = c_test \
	corruption_test  \
	db_test \
	dbformat_test \
	filename_test \
	log_test \
	skiplist_test \
	version_edit_test \
	version_set_test \
	write_batch_test \
	\
	memenv_test \
	\
	filter_block_test \
	table_test \
	\
	arena_test \
	bloom_test \
	cache_test \
	coding_test \
	crc32c_test \
	env_test

noinst_PROGRAMS = $(TESTS)

c_test_SOURCES = ./db/c_test.c
c_test_CFLAGS = $(AM_CXXFLAGS) -I$(top_srcdir)/include
c_test_LDADD = libleveldb.la util/libtest.la

corruption_test_SOURCES = ./db/corruption_test.cc
corruption_test_CXXFLAGS = $(AM_CXXFLAGS) -I$(top_srcdir)/include
corruption_test_LDADD = libleveldb.la util/libtest.la

db_test_SOURCES = ./db/db_test.cc
db_test_CXXFLAGS = $(AM_CXXFLAGS) -I$(top_srcdir)/include
db_test_LDADD = libleveldb.la util/libtest.la

dbformat_test_SOURCES = ./db/dbformat_test.cc
dbformat_test_CXXFLAGS = $(AM_CXXFLAGS) -I$(top_srcdir)/include
dbformat_test_LDADD = libleveldb.la util/libtest.la

filename_test_SOURCES = ./db/filename_test.cc
filename_test_CXXFLAGS = $(AM_CXXFLAGS) -I$(top_srcdir)/include
filename_test_LDADD = libleveldb.la util/libtest.la

log_test_SOURCES = ./db/log_test.cc
log_test_CXXFLAGS = $(AM_CXXFLAGS) -I$(top_srcdir)/include
log_test_LDADD = libleveldb.la util/libtest.la

skiplist_test_SOURCES = ./db/skiplist_test.cc
skiplist_test_CXXFLAGS = $(AM_CXXFLAGS) -I$(top_srcdir)/include
skiplist_test_LDADD = libleveldb.la util/libtest.la

version_edit_test_SOURCES = ./db/version_edit_test.cc
version_edit_test_CXXFLAGS = $(AM_CXXFLAGS) -I$(top_srcdir)/include
version_edit_test_LDADD = libleveldb.la util/libtest.la

version_set_test_SOURCES = ./db/version_set_test.cc
version_set_test_CXXFLAGS = $(AM_CXXFLAGS) -I$(top_srcdir)/include
version_set_test_LDADD = libleveldb.la util/libtest.la

write_batch_test_SOURCES = ./db/write_batch_test.cc
write_batch_test_CXXFLAGS = $(AM_CXXFLAGS) -I$(top_srcdir)/include
write_batch_test_LDADD = libleveldb.la util/libtest.la

memenv_test_SOURCES = ./helpers/memenv/memenv_test.cc
memenv_test_CXXFLAGS = $(AM_CXXFLAGS) -I$(top_srcdir)/include
memenv_test_LDADD = libleveldb.la helpers/memenv/libmemenv.la util/libtest.la

filter_block_test_SOURCES = ./table/filter_block_test.cc
filter_block_test_CXXFLAGS = $(AM_CXXFLAGS) -I$(top_srcdir)/include
filter_block_test_LDADD = libleveldb.la util/libtest.la

table_test_SOURCES = ./table/table_test.cc
table_test_CXXFLAGS = $(AM_CXXFLAGS) -I$(top_srcdir)/include
table_test_LDADD = libleveldb.la util/libtest.la

arena_test_SOURCES = ./util/arena_test.cc
arena_test_CXXFLAGS = $(AM_CXXFLAGS) -I$(top_srcdir)/include
arena_test_LDADD = libleveldb.la util/libtest.la

bloom_test_SOURCES = ./util/bloom_test.cc
bloom_test_CXXFLAGS = $(AM_CXXFLAGS) -I$(top_srcdir)/include
bloom_test_LDADD = libleveldb.la util/libtest.la

cache_test_SOURCES = ./util/cache_test.cc
cache_test_CXXFLAGS = $(AM_CXXFLAGS) -I$(top_srcdir)/include
cache_test_LDADD = libleveldb.la util/libtest.la

coding_test_SOURCES = ./util/coding_test.cc
coding_test_CXXFLAGS = $(AM_CXXFLAGS) -I$(top_srcdir)/include
coding_test_LDADD = libleveldb.la util/libtest.la

crc32c_test_SOURCES = ./util/crc32c_test.cc
crc32c_test_CXXFLAGS = $(AM_CXXFLAGS) -I$(top_srcdir)/include
crc32c_test_LDADD = libleveldb.la util/libtest.la

env_test_SOURCES = ./util/env_test.cc
env_test_CXXFLAGS = $(AM_CXXFLAGS) -I$(top_srcdir)/include
env_test_LDADD = libleveldb.la util/libtest.la
