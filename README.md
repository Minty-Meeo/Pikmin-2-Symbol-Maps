# Pikmin 2 Symbol Maps
For many years, it was thought Pikmin 2 had no symbol map.  For 3 years and 4 months, it was believed only USA Demo 1 had a symbol map.  Now, with the power of a really big Excel spreadsheet, even more versions can have approximations of their long-lost symbol map created.

## Pikmin 2 (USA Demo 1).MAP
The original symbol map.  This was found in zz_pikmin2.tgc from Interactive Multi-Game Kiosk Demo Disc 17 USA.

## Pikmin 2 (USA v1.00).MAP
A port of the original symbol map for the retail USA version of Pikmin 2 (MD5: 66F8D886AFA0742CD9901D1BFE3B114F).  Here are some known differences:
* .text
	* [rootCallback__8JASTrackFPv 	JSystem.a JASTrack.cpp] is larger
	* [setCentering__Q32og9newScreen8TitleMsgFQ42og9newScreen8TitleMsg13EnumCentering 	plugProjectOgawaU.a ogTitleMsg.cpp] is smaller
	* [doCreate__Q28Morimura16TChallengeSelectFP10JKRArchive 	plugProjectMorimuraU.a challengeSelect2D.cpp] is smaller
	* [doUpdate__Q28Morimura16TChallengeSelectFv 	plugProjectMorimuraU.a challengeSelect2D.cpp] is smaller
	* [doUpdateStateOpen__Q33ebi6Screen7TOptionFv 	plugProjectEbisawaU.a ebiScreenOption.cpp] is smaller
	* [doUpdateStateWait__Q33ebi6Screen7TOptionFv 	plugProjectEbisawaU.a ebiScreenOption.cpp] is smaller
	* [__ct__7SectionFP10JFWDisplayP7JKRHeapb 	sysGCU.a section.cpp] is smaller
	* [run__7SectionFv 	sysGCU.a section.cpp] is smaller
	* [drawEpilepsy__11BootSectionFR8Graphics 	sysGCU.a bootSection.cpp] is now used.
	* [doUpdate__11BootSectionFv 	sysGCU.a bootSection.cpp] is larger
	* [updateLoadResourceFirst__11BootSectionFv 	sysGCU.a bootSection.cpp] is smaller
* .rodata
	* [@3199 	sysGCU.a pikmin2THPPlayer.cpp], [@3201 	sysGCU.a pikmin2THPPlayer.cpp], [@3203 	sysGCU.a pikmin2THPPlayer.cpp], [@3205 	sysGCU.a pikmin2THPPlayer.cpp], [@3207 	sysGCU.a pikmin2THPPlayer.cpp], and [@3209 	sysGCU.a pikmin2THPPlayer.cpp] no longer exist.  These were the filepaths for the extra teleprompter INIs that USA Demo 1 was known to require.
* .data
	* [c32    JSystem.a JASTrack.cpp] no longer exists.  Due to this, JasTrack.cpp's .data closure symbol is no longer 32 byte aligned.
* .sdata
	* A new symbol, [zz_80514788 	JSystem.a JASTrack.cpp], has been added.  It has suspiciously similar XREFs to the now nonexistent [c32    JSystem.a JASTrack.cpp].  A closure symbol for it has also been added, since JASTrack.cpp had no .sdata before now.
* .sdata2
	* [@5089 	sysGCU.a bootSection.cpp], [@5090 	sysGCU.a bootSection.cpp], and [@5091 	sysGCU.a bootSection.cpp] are now used.  These are the floats referenced by [drawEpilepsy__11BootSectionFR8Graphics 	sysGCU.a bootSection.cpp], hence why they were unused in USA Demo 1.
	* A new symbol, [zz_80520a7c 	sysGCU.a bootSection.cpp], has been added.  It is referenced by [__ct__10TinyPikminFv 	sysGCU.a bootSection.cpp]
* Memory Map has been updated.
* Linker Generated Symbols has been updated.
* Link Map has not been ported, yet.  I am not confident I could catch every difference by hand.