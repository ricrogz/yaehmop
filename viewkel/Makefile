OBJS = main.o interface.o globals.o xstuff.o genutil.o stack.o manipulate.o \
  hierarchy.o snapshot.o fileio.o buttons.o \
  molecule.o solid_stuff.o graphs.o \
  prop_graphs.o band_graphs.o walsh_graphs.o graphics.o tek_lib.o help.o \
  FMO_diags.o orbitals.o fit_orbs.o matrix_ops.o implicit_polyg.o \
  triangles.o 3D_objects.o enhpost.o cont_plots.o contour.o labels.o \
  MO_conts.o vibrations.o valence.o polyhed.o chull.o mem_debug.o



# to change where the program looks for the atomic parameters
#   change the following:
#PARM_FILE_LOC = \"/usr/local/src/yaehmop/viewkel/atomic_parms.dat\"
#PARM_FILE_LOC = \"/home/landrum/yaehmop/viewkel/atomic_parms.dat\"
#PARM_FILE_LOC = \"/usr/local/lib/atomic_parms.dat\"
PARM_FILE_LOC = \"/home/glandrum/yaehmop/viewkel/new_atomic_parms.dat\"

# these are things you can turn on or off to make yourself happy.
OPT_FEATURES = -DTEK_GRAPHICS -DX_GRAPHICS -DINTERACTIVE_USE \
-DINCLUDE_ADF_PLOTS -DCULL_POLYGONS -DSUPPORT_COLOR_X -DINCLUDE_BOND_VALENCE \
-DSUPPORT_FATBANDS -DCHATTY_SYMMETRY -DSUPPORT_FATBANDS


CFLAGS = -g -DHIGHPREC -DPARM_FILE=$(PARM_FILE_LOC) $(OPT_FEATURES)\
-D_POSIX_SOURCE -DUSE_READLINE

LDFLAGS = -L/usr/X11R6/lib -L/usr/local/lib -lreadline -lhistory -L/usr/lib/termcap -ltermcap

CC = gcc


viewkel:  $(OBJS)
	$(CC) -o viewkel $(CFLAGS) $(OBJS) $(LDFLAGS) \
-lm -lX11

install: viewkel
	cp viewkel ../bin

.c.o: viewkel.h
	$(CC) $(CFLAGS) -c $*.c


clean:
	rm -f *.o; rm -f viewkel;

