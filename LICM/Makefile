
OPTIMIZER := lib_loop_invariant_code_motion.so
OBJs := $(subst .cpp,.o,$(wildcard lib/*.cpp))

LLVM_VERSION ?= 14

#OPTIONS := -DHashTableImpl
#OPTIONS := -DRecursiveImpl
OPTIONS := -DMetadataImpl

CXXFLAGS := $(shell llvm-config-$(LLVM_VERSION) --cxxflags) -fPIC $(OPTIONS) -O2

all: $(OPTIMIZER) 

$(OPTIMIZER): $(OBJs)
	$(CXX) -dylib -shared $^ -o $@

.PHONY: clean
clean:
	$(RM) $(OPTIMIZER) $(OBJs)
