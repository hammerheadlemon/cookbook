If you want to ignore the whole content of a directory except one file inside
it, you could write a pair of rules for each directory in the file path. Eg
.gitignore to ignore the pippo folder except from pippo/pluto/paperino.xml
.gitignore

pippo/*
!pippo/pluto
pippo/pluto/*
!pippo/pluto/paperino.xml


