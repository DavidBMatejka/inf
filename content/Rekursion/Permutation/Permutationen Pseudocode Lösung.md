```
void permutationen(String s) {
	1. Falls s.length() == 1, gib das Element zurück
	
	2. Sonst:
		1. Erstelle eine leere Liste
		2. Wiederhole für jedes Element in s
			1. Schreibe Element ganz nach vorne
			2. String rest = Text ohne Element
			3. hänge jede Sub-Permutation aus 
				permutationen(rest) an das Element an 
				und füge es der Liste hinzu
	1. Gib die Liste der Permutationen zurück
}
```