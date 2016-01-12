# PatentDisambigData
Patent Disambiguation Data (currently a placeholder)


Data will be released after peer review is complete.  For further information, email greg.morrison@imtlucca.it.

Each unique identifier is a number with a two-letter prefix:
   HA:  an assignee that was linked to a high-resoltuion address 
   HI:  an inventor that was linked to a high-resolution address WITHOUT any mobility detected
   HM:  a mobile inventor that was linked to a high-resolution address in at least one of his/her locations

Summary of files:
Patent_Disambig_high.txt is a list of patents from the EPO, PCT, and USPTO for which all assignees and inventors have been disambiguated and linked to a high-quality address.  There are four columns, delimited by a '|':
  pat:  the patent publication number
  yr:  the application year of the patent
  ass:  the assignee ID(s).  If more than one assignee is listed, they are separated by a ','
  inv:  the inventor ID(s).  If more than one inventor is listed, they are separated by a ','
There are 3583476 lines in this file.

Assignee_Names_high.txt is a list of all names associated with that assignee ID.  There are two columns, delimited by a '|'
  id:  the unique ID for that assignee (as in the Patent_Disambig_high.txt file).
  names:  All of the names associated with that ID on any linked patent.  If more than one name is linked, they are separated by a '~'
There are 254459 lines in this file

Inventor_Names_high.txt is a list of all names associated with that inventor ID.  There are two columns, delimited by a '|'
  id:  the unique ID for that inventor (as in the Patent_Disambig_high.txt file).
  names:  All of the names associated with that ID on any linked patent.  If more than one name is linked, they are separated by a '~'
There are 1366655 lines in this file
 
 
 
 
 
 
 
 
 
 
For the benchmarks, the Manually assigned disambiguated IDs are numbers with a two letter prefix: 
   first letter:  b="boston", p="paris" 
   second letter:  r="regional", e="external"
so, for example, "br1" is an assignee in the boston area, and "pe216" is an assignee outside of paris that was coassigned on a patent with a paris assignee.  
 
NOTE:  the disambiguations in Boston and Paris were performed independently, and are NOT properly cross-linked.  For example, Harvard University has two identifiers.  It's manually assigned ID in the boston area is br381, and it's manually assigned ID in the paris area is pe979.  Thus, these datasets must be treated indpendently, and the manual disambiguation IDs should NEVER be combined.  
 
 
Boston_bench.txt is a list of EPO and PCT patents with an assignee in the boston area.  There are 5 columns, delimited by a '|'
  patent:  the patent publication number
  ManualIDs:  the manually assigned identifier for the assignees on this patent.  
  Disambig:  our algorithmic disambiguation for the assignees on these patents.  IDs correspond to those in the Assignee_Names_high.txt     file where available, but some IDs will not be found in that file (low-quality assignees, for example).
  HAN:  the OECD HAN identifier from the July 2014 dataset.
  raw:  the undisambiguated names used in our benchmarking (punctuation, doublespacing, and accents removed)


Paris_bench.txt is a list of EPO and PCT patents with an assignee in the paris area.  There are 5 columns, delimited by a '|'
  patent:  the patent publication number
  ManualIDs:  the manually assigned identifier for the assignees on this patent.  
  Disambig:  our algorithmic disambiguation for the assignees on these patents.  IDs correspond to those in the Assignee_Names_high.txt     file where available, but some IDs will not be found in that file.
  HAN:  the OECD HAN identifier from the July 2014 dataset.
  raw:  the undisambiguated names used in our benchmarking (punctuation, doublespacing, and accents removed)
