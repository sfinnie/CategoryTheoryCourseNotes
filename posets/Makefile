#dag.png: dag.dot
#dot dag.dot -Tpng -o generated/dag.png

%.png : %.dot
	    dot -Tpng -o png/$@ $<

all: $(addsuffix .png, $(basename $(wildcard *.dot)))

