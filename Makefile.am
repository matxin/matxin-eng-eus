###############################################################################

LANG1=eng
LANG2=eus

PREFIX1=$(LANG1)-$(LANG2)

BASENAME=matxin-$(PREFIX1)

#	       $(PREFIX1).cfg 

TARGETS_COMMON=$(PREFIX1).verb_transfer.fst \
	       $(PREFIX1).bilingual.bin \
	       $(PREFIX1).changes_morph.bin \
 	       $(PREFIX1).changes_sint.dat \
	       $(PREFIX1).chunk_type.dat \
	       $(PREFIX1).chunk_rules.dat \
	       $(PREFIX1).interchunk_move1.dat \
	       $(PREFIX1).interchunk_move2.dat \
	       $(PREFIX1).interchunk_move3.dat \
	       $(PREFIX1).interchunk_order.dat \
	       $(PREFIX1).intrachunk_move.dat \
	       $(PREFIX1).verb_noun_subcat.dat \
	       $(PREFIX1).verb_subcat.dat \
	       $(PREFIX1).lexical_selection.dat \
	       $(PREFIX1).prep.dat \
	       $(PREFIX1).semantic.dat \
	       $(PREFIX1).morph_preproc.dat \
	       $(PREFIX1).morph_gen.bin \
	       $(PREFIX1).measures_gen.bin \
	       $(PREFIX1).morph_nolex.bin 



@ap_include@

###############################################################################

$(PREFIX1).verb_transfer.fst: $(BASENAME).verb_transfer.foma
	foma -f $< $@

$(PREFIX1).bilingual.bin: $(BASENAME).bilingual_mur.xml 
	lt-comp lr $< $@

$(PREFIX1).changes_morph.bin: $(BASENAME).changes_morph.xml
	lt-comp lr $< $@

$(PREFIX1).chunk_rules.dat: $(AP_SRC1)/matxin-$(LANG1).chunk_rules.dat
	cat $<  > $@

$(PREFIX1).changes_sint.dat: $(BASENAME).changes_sint.dat
	cp $< $@

$(PREFIX1).chunk_type.dat:  $(BASENAME).chunk_type.dat
	cp $< $@

$(PREFIX1).interchunk_move1.dat: $(BASENAME).interchunk_move1.dat
	cp $< $@

$(PREFIX1).interchunk_move2.dat: $(BASENAME).interchunk_move2.dat
	cp $< $@

$(PREFIX1).interchunk_move3.dat: $(BASENAME).interchunk_move3.dat
	cp $< $@

$(PREFIX1).interchunk_order.dat: $(BASENAME).interchunk_order.dat
	cp $< $@

$(PREFIX1).intrachunk_move.dat: $(BASENAME).intrachunk_move.dat
	cp $< $@

$(PREFIX1).lexical_selection.dat: $(BASENAME).lexical_selection.dat
	cp $< $@

$(PREFIX1).prep.dat: $(BASENAME).prep.dat
	cp $< $@


#
#
#

$(PREFIX1).verb_noun_subcat.dat: $(AP_SRC2)/$(LANG2).verb_noun_subcat.dat
	cp $< $@

$(PREFIX1).verb_subcat.dat: $(AP_SRC2)/$(LANG2).verb_subcat.dat
	cp $< $@

$(PREFIX1).morph_preproc.dat: $(AP_SRC2)/matxin-$(LANG2).morph_preproc.dat
	cp $< $@

$(PREFIX1).morph_gen.bin: $(AP_SRC2)/$(LANG2).morph_gen.bin
	cp $< $@

$(PREFIX1).measures_gen.bin: $(AP_SRC2)/$(LANG2).measures_gen.bin
	cp $< $@

$(PREFIX1).morph_nolex.bin: $(AP_SRC2)/$(LANG2).morph_nolex.bin
	cp $< $@

$(PREFIX1).semantic.dat: $(AP_SRC2)/$(LANG2).semantic.dat
	cp $< $@



###############################################################################

EXTRA_DIST= $(BASENAME).bilingual_mur.xml \
	$(BASENAME).changes_morph.xml \
	$(BASENAME).changes_sint.dat \
	$(BASENAME).chunk_type.dat \
	$(BASENAME).interchunk_move1.dat \
	$(BASENAME).interchunk_move2.dat \
	$(BASENAME).interchunk_move3.dat \
	$(BASENAME).interchunk_order.dat \
	$(BASENAME).intrachunk_move2.dat \
	$(BASENAME).intrachunk_move.dat \
	$(BASENAME).lexical_selection.dat \
	$(BASENAME).prep.dat \
	$(BASENAME).verb_transfer.foma

#	$(BASENAME).$(PREFIX1).cfg 

matxin_eng_eusdir=$(prefix)/share/matxin/$(BASENAME)
matxin_eng_eus_srcdir=$(prefix)/share/matxin/$(BASENAME)

matxin_eng_eus_DATA=$(TARGETS_COMMON)

# All modes are created by the same goal, listing several will just give problems with make -j2
noinst_DATA=modes/$(PREFIX1).mode

install-data-local: install-modes

CLEANFILES = $(TARGETS_COMMON)
clean-local:
	-rm -rf .deps modes
