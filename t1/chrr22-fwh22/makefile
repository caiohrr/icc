LIKWID_HOME=/home/soft/likwid

CC = gcc
#CFLAGS = -Wall -Wextra -g -lm -std=gnu99 -O3 -mavx -march=native 
CFLAGS = -I${LIKWID_HOME}/include -DLIKWID_PERFMON -Wall -Wextra -lm -std=gnu11 -O3 -mavx -march=native 

LFLAGS = -L${LIKWID_HOME}/lib -llikwid -lm -g
#LFLAGS = -lm -g

objects = ajustePol.o libIntervalar.o libSistemaIntervalar.o libAjustePolinomialIntervalar.o utils.o

all: $(objects)
	$(CC) $(CFLAGS) $(objects) -o ajustePol $(LFLAGS) 

ajustePol.o: ajustePol.c
	$(CC) $(CFLAGS) -c ajustePol.c

libIntervalar.o: libIntervalar.c
	$(CC) $(CFLAGS) -c libIntervalar.c

libSistemaIntervalar.o: libIntervalar.c libSistemaIntervalar.c
	$(CC) $(CFLAGS) -c libSistemaIntervalar.c

libAjustePolinomialIntervalar.o: libIntervalar.c libSistemaIntervalar.c libAjustePolinomialIntervalar.c
	$(CC) $(CFLAGS) -c libAjustePolinomialIntervalar.c

utils.o: utils.c
	$(CC) $(CFLAGS) -c utils.c

clean:
	-rm -f *.o

purge: clean
	-rm -f ajustePol FLOPS_DP.log ENERGY.log
