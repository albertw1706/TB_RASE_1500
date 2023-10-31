#
# Author:  Karel Brinda <kbrinda@hsph.harvard.edu>
#
# License: MIT
#

include ../init.mk
.PHONY: tree

# trick to ensure that path is exported
all:
	$(MAKE) -C .. tree

tree: .complete

.complete:
	rase_db_prepare_tree.py \
		--in-newick ../published/1500_tb.newick \
		--out-newick tree.newick \
		--metadata ../published/RASE_DB_1500.tsv \
		--node-col 0 \
		--taxid-col 0 \
		--phylogroup-col 1

	touch $@

clean:
	rm -f _*.newick .complete

cleanall: clean
	rm -f *.newick
