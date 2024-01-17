Given two strings ransomNote and magazine, find out if you can construct the contents of ransomNote with the characters in magazine. Each character can only be used once.

```cpp
bool canConstruct(string ransomNote, string magazine) {
	unordered_map<char, int> dictionary;
	
	for(char c : magazine){
	
		if(dictionary.find(c) == dictionary.end()){
			dictionary[c] = 1;
		} else {
			dictionary[c]++;
		}

	}

	for(char c: ransomNote){
	
		if(dictionary.find(c) != dictionary.end() && dictionary[c] > 0){
			dictionary[c]--;
		} else {
			return false;
		}
	}
	return true;
}
```

## Explanation
1. Create hashmap (in cpp as unordered_map) with type char and int named dictionary.
2. for every character in string magazine, check if that character is in the hashmap (the if statement explicitly is checking if the character found equals the .end() function which always returns true if the character is not within the hashmap(?))
3. if it does not exist, add it do the hashmap, if it does exist, iterate it by one to show that there is more than one inside.
4. then, iterate through every character in the ransomNote String. if the character exists within the hashmap, and it's integer value (count) is greater than 0, remove it from the hashtable and continue. 
5. if it does not exist within the hashtable, return false, as the ransomNote could not be created from the magazine. 
6. If you successfully iterate through the entirety of the ransomNote with characters from the magazine string, than it can be created from it, so return true.