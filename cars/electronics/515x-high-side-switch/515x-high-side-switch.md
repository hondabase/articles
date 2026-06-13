---
summary: 'Honda uses a 5 pin high side switch in a lot of their OBD1 and OBD2 ECUs to control solenoids like auto trans and VTEC solenoids.'
applies_to:
  obd: [1, 2]
  brand: Honda
complexity: intermediate
tags:
  - ecu
  - reference
  - tuning
  - rom
  - sensors
---

# 515X High Side Switch

Honda uses a 5 pin high side switch in a lot of their [OBD1](/cars/electronics/obd1) and [OBD2](/cars/electronics/obd2) [ECU](/cars/electronics/ecu)s to control solenoids like auto trans and VTEC solenoids. Allegro / Sanken is the OEM for this part. The following parts are known to work: SK-5050S (original - 1720 boards usually)
 SK-5151S (higher current version of 5050 - 11F0/1980 boards usually)
 SK-5154S (higher current version of 5151 - [OBD2](/cars/electronics/obd2) boards usually)
 SI-5151S (part number change on SK-5151S)
 SI-5154S (part number change on SK-5154S)
 SI-5151SG (part number change on SI-5151S)
 SI-5154SG (part number change on SI-5154S)
 These parts are often quite difficult to get ahold of due to Allegro not selling less than 500pcs@$1.50ea and few electroncs distributors stocking them. Look for periodic groupbuys on the forum. There have been [reports](/pgmfi/forum/) of an [International Rectifier](/pgmfi/forum/) part that is a replacement. New forum link: [Replacement for SI-5151S](/pgmfi/forum/topic.php?id=181) (Please log in to see pics in forum) Edit this if you know more. Tried a pair of ir6220 in a known good P13. Worked fine! [http://www.digikey.com](http://www.digikey.com) and type IR6220-ND on the parts search, they are $4.63/ea All you do is move the #3 leg to the #5 spot in the board and move pin #5 into #3 spot on the board. It's really easy to do.. just use some heat shrink or insulation on leg 3 to avoid contact between legs...refer to this post for a picture: [http://forum.pgmfi.org/viewtopic.php?t=181](/pgmfi/forum/topic.php?id=181)a picture is worth more than a thousand words ![dsc00595.jpg](http://forum.pgmfi.org/files/dsc00595.jpg)( That would be the actual ir6220 replacement: IPS521 ) search bait: SK5050 SK5151 SK-5050 SK-5151
