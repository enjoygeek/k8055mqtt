dnl Require autoconf version >= 2.60
AC_PREREQ(2.60)


dnl ############# Initialization

AC_INIT([k8055mqtt], [0.1], [njh@aelius.com], k8055mqtt)

AC_CONFIG_SRCDIR([src/k8055mqtt.c])
AC_CONFIG_AUX_DIR(build-scripts)
AC_CONFIG_MACRO_DIR(build-scripts)
AM_INIT_AUTOMAKE([1.10])


dnl ############# Compiler and tools Checks

AC_PROG_CC
AC_PROG_INSTALL
AC_PROG_LN_S

AC_C_BIGENDIAN
AC_C_INLINE
AC_C_CONST


dnl ############## Header and function checks

AC_HEADER_STDC
AC_CHECK_HEADERS([stdlib.h])
AC_FUNC_MALLOC
AC_FUNC_REALLOC


dnl ############## Check for packages we depend upon

PKG_CHECK_MODULES(LIBUSB, libusb-1.0 >= 1.0.8)

AC_CHECK_LIB([mosquitto], [mosquitto_lib_init],, AC_ERROR([Misssing mosquitto client library]))
AC_CHECK_FUNC([mosquitto_connack_string],, AC_ERROR([Misssing the mosquitto_connack_string function]))
AC_CHECK_FUNC([mosquitto_log_callback_set],, AC_ERROR([Misssing the mosquitto_log_callback_set function]))
AC_CHECK_HEADERS([mosquitto.h], [], [AC_ERROR([Missing mosquitto header file])])


dnl ############## Output files

AC_CONFIG_HEADERS([src/config.h])

AC_CONFIG_FILES([
  Makefile
  src/Makefile
])

AC_OUTPUT
