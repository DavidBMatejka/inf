```java
private static List<String> variation(String s) {
	if (s.length() == 1) {
		return List.of(s);
	}

	List<String> perms = new LinkedList<>();
	for (int i = 0; i < s.length(); i++) {
		String letter = s.substring(i, i + 1);
		String rest = 
			s.substring(0, i).concat(s.substring(i+1));

		List<String> prevs = variation(rest);
		for (String prev : prevs) {
			perms.add(letter.concat(prev));
		}
	}
	return perms;
}
```