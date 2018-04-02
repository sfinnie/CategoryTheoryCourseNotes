#dag.png: dag.dot
#dot dag.dot -Tpng -o generated/dag.png

%.png : %.dot
	    dot -Tpng -o img/$@ $<

all: $(addsuffix .png, $(basename $(wildcard *.dot)))

