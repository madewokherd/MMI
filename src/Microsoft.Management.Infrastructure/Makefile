
COMPILE_LIB=csc -target:library

LIB_FLAGS=-unsafe -delaysign+ -keyfile:../../winfx.pub -nostdlib -noconfig -lib:$(MONO_PREFIX)/lib/mono/4.5-api

LIB_REFS=-r:mscorlib.dll -r:System.dll -r:System.Core.dll

LIB_SRCS=$(shell cat sources.list)

all: Microsoft.Management.Infrastructure.dll

clean:
	rm -f Microsoft.Management.Infrastructure.dll

Microsoft.Management.Infrastructure.dll: sources.list $(LIB_SRCS)
	$(COMPILE_LIB) $(LIB_FLAGS) $(LIB_REFS) -out:$@ @sources.list
	sn -R $@ ../../mono.snk
