bin_PROGRAMS=bitwise
bitwise_SOURCES= src/main.c src/misc.c \
				 src/interactive.c src/cmd.c \
				 src/stack.c src/shunting-yard.c \
				 src/help.c inc/bitwise.h inc/stack.h \
				 inc/shunting-yard.h

dist_man_MANS=bitwise.1

if COND_GCOV
MAYBE_COVERAGE=--coverage --no-inline
endif

if COND_TRACE
MAYBE_TRACE=-DTRACE
endif

if COND_DEBUG
MAYBE_DEBUG=-g -O0
endif

AM_CFLAGS = $(MAYBE_COVERAGE) $(MAYBE_DEBUG) $(MAYBE_TRACE)

check_PROGRAMS = tests/test-shunting-yard
tests_test_shunting_yard_SOURCES = src/shunting-yard.c inc/shunting-yard.h \
                                   src/stack.c inc/stack.h inc/bitwise.h \
								   src/misc.c \
                                   tests/test-shunting-yard.c
tests_test_shunting_yard_LDADD = -lcunit

TESTS = $(check_PROGRAMS)

clean-local:
		rm -f *.gcno
