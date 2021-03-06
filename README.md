## What's this?
Character mapping script from arabic to latin. This original style does not have same mapping. In other words, all mappings are the one-to-one correspondances. Thus, this script can map without loosing the original character information.

For latin characters, I used Latin Supplement, Latin Extended-A, Latin Extended-B characters. To make available a keyboard that includes Latin Supplement, Latin Extended-A, Latin Extended-B, please see http://symbolcodes.tlt.psu.edu/accents/codemacext.html

## Usage 
To get romanized characters, codes like below in `if __name__=='__main__'` 
````
ex_sent=u'من کتاب دادم';
ins=transliter(ex_sent);
print ins.main();
````

If you wanna get Arabic sequence form unicode sequence, use
````
ex_sent_2=u'mn tw ra dÝdm';
ins_2=transliter(ex_sent_2);
print ins_2.unicode_to_arabic();
````

## Converting table

### Note: I recommend to remove all diacritics before you convert to latin characters. To remove them, please use `def clean_up()`

This class converts arabic characters to ratin characters. Not all characters are supported, but basic characters are completly converted. I think that enought to express normal writing style.

In the function original_unicode(), character mapping chart is below.(2013/7/23)
See also: http://jrgraphix.net/research/unicode_blocks.php?block=12 

| Arabic_character | Arabic_character_commonly_called | unicode_number(Hex) | mapped_ratin |  
|-----------------:|:--------------------------------:|:-------------------:|:------------:| 
| ا | alef | U+0627 | a |  
| آ | alef_madda_above | U+0622 | ā |  
| ب | be | U+06FF | b |  
| پ | pe | U+067E | p |  
| ت | te | U+062A | t |  
| ث | se | U+062B | ç |  
| ج | jim | U+062C | j |  
| چ | ˇce | U+0686 | č |  
| ح | he | U+062D | ħ |  
| خ | xe | U+062E | x |  
| د | dal | U+062F | d |  
| ذ | zal | U+0630 | đ |  
| ر | re | U+0631 | r |  
| ز | ze | U+0632 | z |  
| ژ | ˇze | U+0698 | ž |  
| س | sin | U+0633 | s |  
| ش | ˇsin | U+0634 | š |  
| ص | sad | U+0635 | ş |  
| ض | zad | U+0636 | ź |  
| ط | ta | U+0637 | ţ |  
| ظ | za | U+0638 | ẓ |  
| ع | 'eyn | U+0639 | ' |  
| غ | qeyn | U+063A | q |  
| ف | fe | U+0641 | f |  
| ق | qaf | U+0642 | ŕ |  
| ک | persian-kaf | U+06A9 | K |  
|   | arabic-kaf | U+0643 | K |  
| گ | gaf | U+06AF | g |  
| ل | lam | U+0644 | l |  
| م | mim | U+0645 | m |  
| ن | nun | U+0646 | n |  
| و | vav | U+0645 | w |  
| ه | he | U+0647 | e | 
| ۀ | he_yeh_above | U+06C0 | X |  
| ی | persian-ye | U+06CC | y |    
| ي | arabic-ye | U+064A | Y |
| ى | arabic_alef_maksusa | U+0649 | Ý |  
| ، | arabic_comma | U+060C | , |  
| ؛ | arabic_semicolon | U+061B | ; |  
| ؟ | arabic_question | U+061F | ? |  
| ة | arabic_heh_hamza_above | U+0629 | T |  
| ٪ | arabic_percent | U+066A | % |  
|   | Zero-Width-Non-Joiner | U+200C | _ |  
|   | arabic_hamza_above | U+0654 | ú |  
|   | arabic_hamza_below | U+0655 | E |  
|   | arabic_alef_hamza_above | U+0623 | á |  
|   | arabic_hamza | U+0621 | ° |
| ٫ | arabic_decimal_separator | U+066B | ⎖ |    

## Update
* v0.01: First Version  
* v0.02: fixed bug that ث س have the same mapping 'se'. changed ث to se¥_1 and س  to se¥_2.  
* v0.03: added 'ARABIC_ALEF_MAKSUSA' and its mapping to 'Ý'. 'PERSIAN_YEH' and its mapping is changed to 'y'.  
* v0.04: changed a mapping of 'persian_kaf' to 'k'. The mappig 'ه' to 'h' is disused. Instead, 'e' is used for 'ه'. 'arabic_fathatan' is disused.  
* v0.05: Added new map for arabic tatweel and arabic decimal separator. An arabic tatweel is \u0640 in unicode and is reffered as keyname 'arabic_tatweel' in code. An arabic decimal separator is \u066b in unicode, and is reffered as keyname 'arabic_decimal_separator' in code.  
* v0.06: some character + diacritic is added. u+0625, u+0629, u+06c0, u+0695, u+0624  
* v0.07: arabic fathatan is added  
* v0.08: A bug that clean_up function does not work solved.  
* v0.09: ۀ is added   
* v0.10: Per\_Per2 module is added with in this system. About Per\_per2.rb, please look at [here](http://stp.lingfil.uu.se/~mojgan/preper.html)

