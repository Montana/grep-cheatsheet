# grep-cheatsheet

My grep cheatsheet for when I'm in `vim`: 

| -i 	| grep -i ^DA demo.txt                  	| Forgets about case sensitivity                     	|
|----	|---------------------------------------	|----------------------------------------------------	|
| -w 	| grep -w "of" demo.txt                 	| Search only for the full word                      	|
| -A 	| grep -A 3 'Exception' error.log       	| Display 3 lines after matching string              	|
| -B 	| grep -B 4 'Exception' error.log       	| Display 4 lines before matching string             	|
| -C 	| grep -C 5 'Exception' error.log       	| Display 5 lines around matching string             	|
| -r 	| grep -r 'quickref.me' /var/log/nginx/ 	| Recursive search (within subdirs)                  	|
| -v 	| grep -v 'warning' /var/log/syslog     	| Return all lines which don't match the pattern     	|
| -e 	| grep -e '^al' filename                	| Use regex (lines starting with 'al')               	|
| -E 	| grep -E 'ja(s\|cks)on' filename       	| Extended regex (lines containing jason or jackson) 	|
| -c 	| grep -c 'error' /var/log/syslog       	| Count the number of matches                        	|
| -l 	| grep -l 'robot' /var/log/*            	| Print the name of the file(s) of matches           	|
| -o 	| grep -o search_string filename        	| Only show the matching part of the string          	|
| -n 	| grep -n "go" demo.txt                 	| Show the line numbers of the matches               	|


## Repeat Pattern (Grep + Regex) 

```bash
grep "^[A-Z].*\.$" GPL-3
```

## Grouping (Grep + Regex) 

```bash
grep "\(grouping\)" file.txt
grep -E "(grouping)" file.txt
egrep "(grouping)" file.txt
```

## Match Repetition (Grep + Regex)

Say we have a file that contains this text:

```bash
changed, so that their problems will not be attributed erron*eou*sly to
authors of prev*ious* versions.
receive it, in any medium, provided that you conspic*uou*sly and
give under the prev*iou*s paragraph, plus a right to possession of the
covered work so as to satisfy simultaneously your obligations under this
```
I'd run: 

```bash
grep -E "[AEIOUaeiou]{3}" GPL-3
```

Some things that would be highlighted for me in that text string would be: 

```bash
eou
iou
uou
```
