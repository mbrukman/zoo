extract:
	${hunter} src.ldta.2002.txt ${dialectdir}/lll1.edd raw.bgf
	${gendir}/reroot2top raw.bgf reroot.prepared.xbgf
	${tooldir}/xbgf reroot.prepared.xbgf raw.bgf grammar.bgf

roundtrip:
	make extract
	${tooldir}/bgf0edd2bnf grammar.bgf ${dialectdir}/lll1.edd tgt.grammar.txt
	cat src.ldta.2002.txt | grep -v '#' > src.prepared.nospace.txt
	perl -pi -w -e 's/\s//g;' tgt.grammar.txt src.prepared.nospace.txt
	diff tgt.grammar.txt src.prepared.nospace.txt

include ../../Makefile.grammar
