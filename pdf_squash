#!/bin/bash
SOURCE=$1
TERGET=$2
echo $SOURCE
echo $TARGET

while true
do
	sleep 40
	echo 'waking up'
	echo $(ls $SOURCE)
	if ! [ -z "$(ls -A $SOURCE)" ];
	then
		echo 'theres something'
		for i in $SOURCE*
		do
			OUT="$2sq_$(basename "$i")"
			IN="$i"
			echo "$IN <--- THIS IS IN"
			echo "$OUT <--this is out"
			gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dPDFSETTINGS=/ebook -dNOPAUSE -dQUIET -dBATCH -sOutputFile="$OUT" "$IN"
			rm "$i" -f
		done
	else
		echo 'nothing here, i sleep'
	fi
done
