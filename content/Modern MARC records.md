# **Details and Decisions on Modern MARC Records**

## **041 Language Code**

New shapes for language. Basically, this maps information to/from the 041 in MARC. 

Still support simple, standard X bf:language Y, which ultimately supports the language code found in the 008 

If the resource being described is accompanied by a summary or abstract, libretto, table of contents, accompanying material other than librettos and transcripts, or accompanying transcripts for audiovisual materials, use the bf:accompaniedBy relationship to capture the type of accompanying material and its language. This instruction basically maps to the 041 $b, $d, $e, $f, $g, and $t. 

If the resource contains subtitles, intertitles, an intermediate translation, captions, accessible audio, or accessible visual language, use a note to capture what is in a specific language and the language itself. This instruction basically maps to the 041 $h, $i, $j, $k, $m, $n, $p, $q, and $r. 

If the language of the resource being cataloged is different than the original language of the resource, add a note indicating the original language. 

## **043 Geographic Area Code**

If in MARC a cataloger would enter an 043 (GAC), in BIBFRAME the cataloger should choose the most geographically relevant entry from LCSH or the Names file.  Catalogers should not enter GACs in BIBFRAME. 

## **Admin Metadata** 

There are now multiple Admin Metadata resources per resource. 

One is substantially larger than the others and contains properties like descriptionLevel or descriptionStandard.  Catalogers should edit this one Admin Metadata and can ignore the others. 

## **Cataloging multiple resources in a single MARC record – DRAFT 09/05/2023**

Cataloging multiple resources within a single MARC record is a widely-used practice. The MARC record could describe a print map with the digitized image added in an 856 field, a book with a CD in a pocket,  a CD-DVD combo pack, or the contents of a resource presented in two different carriers.

A few changes to existing MARC cataloging procedures will ensure that the records are cleaner and more consistent. These changes will also create cleaner and more consistent Works and Instances in BIBFRAME.

1) When multiple 007 and 300 fields are created, they should be “paired” – the content in the first 007 field and the first 300 field should refer to the same resource, the second 007 field and the second 300 field should refer to the same resource, etc.

Example: Resource presented in different carriers on one record.
007   vdumgaizu
007   vdumhaizu
007   mrucu-ufnnaeakuau199308
007   murcu-ufnnaeaiuau199308
007   mrucu-ufnnaeajuau199308
300  $a 1 videodisc of 1 (laser) (ca. 102 min.) : $b sd., b&w and col. ; $c 12 in. viewing copy.
300  $a 1 videodisc of 1 (CED) (ca. 102 min.) : $b sd., b&w and col. ; $c 12 in. viewing copy.
300  $a 8 reels of 10 (r3-10) (ca. 7040 ft.) : $b si., yellow ; $c 35 mm. masterpos.
300  $a 8 reels of 10 (r3-10) (ca. 7040 ft.) : $b si., cyan ; $c 35 mm. masterpos.
300  $a 8 reels of 10 (r3-10) (ca. 7040 ft.) : $b si., magenta ; $c 35 mm. masterpos.

Example: Accompanying material included on record for resource.
007   sd fsngnnmmned 
007   vd cvaizs
300	$a 1 audio disc : $b digital ; $c 4 3/4 inches. 
300   $a 1 videodisc : $b sound, color ; $c 4 3/4 inches.

2) Any 007 field for an electronic resource should be the final 007 field in a record. It does not need to be paired with a 300 field.
Example: Non-electronic version and electronic version of a resource on one record.
007   aj|canzn 
007   cr |||||||||||
300    $a 1 map : $b color ; $c 30 x 68 cm, on sheet 31 x 69 cm, folded to 23 x 11 cm
856 41 $d g4002o $f ct010927
$u https://hdl.loc.gov/loc.gmd/g4002o.ct010927

3) If the accompanying material that could be listed in 300 $e is reflected in a separate 007 field, repeat the 300 field instead of using 300 $e. A 1:1 relationship between 007 and 300 fields for non-electronic resources is ideal. Follow the instructions for options 1a and 2a in the LC-PCC Policy Statement for 3.1.4 in original RDA.
Example: Accompanying material included on record for resource.
007   sd fsngnnmmned 
007   vd cvaizs
300	$a 1 audio disc : $b digital ; $c 4 3/4 inches. 
300   $a 1 videodisc : $b sound, color ; $c 4 3/4 inches.

007   vd cvaizk
007   sd fungnn|||eu
300   $a 1 videodisc (110 minutes) : $b sound, color ; $c 4 3/4 in.
300   $a 1 audio disc : $b digital ; $c 4 3/4 in.

4) If the accompanying material is not coded in a separate 007 field, it can be described in a 300 $e field as described for options 1b and 2b in the LC-PCC Policy Statement for 3.1.4 in original RDA.
Example: Accompanying material included on record for resource.
300   $a 76 pages : $b color illustrations ; $c 24 cm + $e 1 sound disc (digital ; 4 3/4 in.)
300   $a 1 audio disc : $b digital ; $c 4 3/4 in. + $e 1 accompanying booklet (45 pages : color illustrations ; 13 cm)
300   $a 174 pages ; $c 28 cm + $e 1 computer disc (4 3/4 inches)

5) If $3 labels are used in the 3XX fields, use consistent text and repeat the field if necessary. Each $3 should refer to a single resource.
Example: Different resources included on one record.
300  $3 audio disc $a 3 audio discs : $b digital, CD audio ; $c 4 3/4 in.
300  $3 videodisc $a 1 videodisc (39 min.) : $b sound, color ; $c 4 3/4 in.
336  $3 audio disc $a performed music $b prm $2 rdacontent
336  $3 videodisc $a performed music $b prm $2 rdacontent
336  $3 videodisc $a two-dimensional moving image $b tdm $2 rdacontent
337  $3 audio disc $a audio $b s $2 rdamedia
337  $3 videodisc $a video $b v $2 rdamedia
338  $3 audio disc $a audio disc $b sd $2 rdacarrier
338  $3 videodisc $a videodisc $b vd $2 rdacarrier
344  $3 audio disc $a digital $2 rdatr
344  $3 videodisc $a digital $2 rdatr
344  $3 audio disc $b optical $2 rdarm
344  $3 videodisc $b optical $2 rdarm

## **EDTF** 

Catalogers will need to learn a few EDTF patterns 

- YYYY for simple years 
- YYYX to indicate unknown (currently ‘u’ is used) 
- YYYY/YYYY to indicate to/from ranges 
- YYYY/.. to indicate a range with a defined start date but no current end date 

See [https://www.loc.gov/standards/datetime/](https://www.loc.gov/standards/datetime/) for more information. 

## **Hubs**

Hubs are the BIBFRAME equivalent of access points for works and expressions in MARC. 

Hubs have been and continue to be created from all Title and Name/Title MARC authorities and from access points in MARC bibs (but only those not accounted for in the authority file). 

In BIBFRAME, catalogers should associate the resource being cataloged with a Hub if they would enter an access point in MARC.  Said another way, a relationship to a Hub should be established if in MARC a cataloger were to enter a Title or NameTitle in these fields: 130, 240, 600, 610, 611, 630, 700, 710, 711, 730, 800, 810, 811, 830.  

NB: If in MARC a record would have a 1XX+240 combination or a 130, in BIBFRAME this is handled as a relationship between the resource being described and a Hub.   

The cataloger should always search for an existing Hub in the system first. 

But, if an existing Hub is not found, the cataloger will need to create a Hub in one of two ways: 

1. If cataloger working in MARC would need to create a Title or Name/Title Authority record to complete their work in MARC, catalogers should do the same when working in Bibframe:  go create the appropriate MARC Title or Name/Title Authority record.  Once saved (in Voyager), the Authority record will automatically sync over to the BF system at which time it will be converted to a Hub and available for use in Marva.  Catalogers should then complete the description in Marva by associating the resource being described with the new Hub. 

2. Otherwise, if a Title or Name/Title Auth record does not need to be created, the cataloger should open a new Marva window and create a Hub and save it to the system.  It will be immediately available for use in the Marva editor and the cataloger can complete the description in the original Marva window.   

**Info/Expectations for recording relationships: Works **

Sometimes, as in MARC, there is a desire to create a relationship to a specific manifestation.  This most often occurs with serials, specifically the 760-787 range (the “linking entry” fields). 

BIBFRAME supports these and the cataloger should choose an appropriate relationship from the drop down and then associate another, existing BF Work/Expression resource with the one being cataloged. 

If the target Work/Expression resource does not exist, it should be created in MARC (so it gets a Voyager ID). 

## **Provision Activity**

Catalogers should:

1. Check to make sure an EDTF coded date is in at least one Provision Activity 
2. Check to make sure a bf:place with a MARC Country URI is present in at least one Provision Activity
3. Create a Provision Activity for each place and agent grouping per activity.  

If in MARC one might do this: 

264 #1 $a New York : $b Academic Press, Inc. ; $a London : $b Butterworth-Springer, Ltd., $c 1950-1962. 

In BIBFRAME, the cataloger should create two provision activity resources, one with the New York / Academic Press combination and the second with the London / Butterworth combination. 

## **ScriptShifter** 

Catalogers will need to know how to set up ScriptShifter for non-Latin cataloging. 

## **Series** 

Series, regardless of whether they are transcribed or not, are handled as a relationship between the resource being described and a Series Hub. 

Series, regardless of whether they are transcribed or not, are at the Work/Expression level, as are all relationships. 

Catalogers should first search for an existing Series Hub.  If found, it can be selected and used.  This is the equivalent of assigning an 800, 810, 811, or 830. 

If there is no Series Hub, a cataloger can enter a Series by ‘transcribing’ it in the title field of an inline resource. 

## **Work/Expression Titles** 

See the rules about creating relationships with Hubs if in MARC a record would have a uniform title. 

Because what is called in MARC the “uniform title” is handled as a relationship (to a Hub) in Bibframe, the cataloger can enter the full title in the Work/Expression, just as is done at the Instance level. 
