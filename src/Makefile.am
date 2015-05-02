
AM_CPPFLAGS	= @GLIB_CFLAGS@ -I$(top_srcdir)/include

bin_PROGRAMS	= picocoin blkscan blkstats rawtx

if ENABLE_BRD
  bin_PROGRAMS += brd
endif

noinst_LIBRARIES= libnode.a

libnode_a_SOURCES=	\
	peerman.c	\
	peerman.h

if ENABLE_BRD
  brd_SOURCES=		\
  	brd.c		\
  	brd.h

  brd_LDADD	= libnode.a ../lib/libccoin.a \
  		  @GLIB_LIBS@ @CRYPTO_LIBS@ @EVENT_LIBS@
endif
picocoin_SOURCES=	\
	aes.c		\
	main.c		\
	net.c		\
	fakepoll.h	\
	picocoin.h	\
	wallet.c wallet.h

picocoin_LDADD	= libnode.a ../lib/libccoin.a \
		  @GLIB_LIBS@ @CRYPTO_LIBS@ @EVENT_LIBS@ @JANSSON_LIBS@

blkscan_LDADD	= ../lib/libccoin.a \
		  @GLIB_LIBS@ @ARGP_LIBS@ @CRYPTO_LIBS@
blkstats_LDADD	= ../lib/libccoin.a \
		  @GLIB_LIBS@ @ARGP_LIBS@ @CRYPTO_LIBS@
rawtx_LDADD	= ../lib/libccoin.a \
		  @GLIB_LIBS@ @CRYPTO_LIBS@ @ARGP_LIBS@ @JANSSON_LIBS@
