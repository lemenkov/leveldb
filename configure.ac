AC_INIT([leveldb], [1.4.0], [http://groups.google.com/group/leveldb])

AC_CANONICAL_TARGET

AM_INIT_AUTOMAKE([dist-bzip2 no-dist-gzip tar-ustar foreign])

AC_SUBST(LEVELDB_VERSION_INFO, [1:4:0])

# Checks for programs.
AC_PROG_CXX
#AC_PROG_CC
AC_PROG_LIBTOOL
AC_PROG_INSTALL

AC_LANG_CPLUSPLUS

# Checks for libraries.
# FIXME: Replace `main' with a function in `-lkyotocabinet':
#AC_CHECK_LIB([kyotocabinet], [main])
# FIXME: Replace `main' with a function in `-lsqlite3':
#AC_CHECK_LIB([sqlite3], [main])

AC_CHECK_LIB(
	     [snappy],
	     [snappy_compress],
	     [
	      CXXFLAGS="$CXXFLAGS -DSNAPPY"
	      SNAPPY_LIBS="-lsnappy"
	      AC_SUBST([SNAPPY_LIBS])
	     ],
	     [AC_MSG_ERROR([snappy library not found])],
	     []
	    )

# Checks for header files.
AC_CHECK_HEADERS([fcntl.h stddef.h stdint.h stdlib.h string.h sys/time.h unistd.h])

case "$target_os" in
	linux*)
		CXXFLAGS="$CXXFLAGS -fno-builtin-memcmp -pthread -DOS_LINUX -DLEVELDB_PLATFORM_POSIX"
		;;
	darwin*)
		CXXFLAGS="$CXXFLAGS -fno-builtin-memcmp -DOS_MACOSX -DLEVELDB_PLATFORM_POSIX"
		;;
	freebsd*)
		CXXFLAGS="$CXXFLAGS -fno-builtin-memcmp -D_REENTRANT -DOS_FREEBSD -DLEVELDB_PLATFORM_POSIX"
		;;
	openbsd*)
		CXXFLAGS="$CXXFLAGS -fno-builtin-memcmp -D_REENTRANT -DOS_OPENBSD -DLEVELDB_PLATFORM_POSIX"
		;;
	netbsd*)
		CXXFLAGS="$CXXFLAGS -fno-builtin-memcmp -D_REENTRANT -DOS_NETBSD -DLEVELDB_PLATFORM_POSIX"
		;;
	*solaris*)
		CXXFLAGS="$CXXFLAGS -fno-builtin-memcmp -D_REENTRANT -DOS_SOLARIS -DLEVELDB_PLATFORM_POSIX"
		;;
	*)
		AC_MSG_ERROR([No support for this OS ($target_os) yet])
		;;
esac

# Checks for typedefs, structures, and compiler characteristics.
#AC_CHECK_HEADER_STDBOOL
AC_C_INLINE
AC_TYPE_INT16_T
AC_TYPE_INT32_T
AC_TYPE_INT64_T
AC_TYPE_INT8_T
AC_TYPE_OFF_T
AC_TYPE_SIZE_T
AC_TYPE_SSIZE_T
AC_TYPE_UINT16_T
AC_TYPE_UINT32_T
AC_TYPE_UINT64_T
AC_TYPE_UINT8_T

# Checks for library functions.
AC_FUNC_ERROR_AT_LINE
AC_FUNC_MALLOC
AC_FUNC_MMAP
AC_CHECK_FUNCS([fdatasync ftruncate getpagesize gettimeofday localtime_r memset mkdir munmap rmdir sqrt strchr strdup strerror strrchr strstr strtoull])

AC_CONFIG_FILES([
Makefile
db/Makefile
helpers/memenv/Makefile
port/Makefile
table/Makefile
util/Makefile
])

AC_OUTPUT
