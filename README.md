# Python-Transform
Christopher Lu

To identify if something is piglatin, you can look at the last two characters of each word. If the last two characters of each word are always ay, then it i likely piglatin.
Another thing you could do is see if every word has a dash in it. If they all have dashes, then it is likely in pig latin.
In order to decode piglatin, if the last three characters are way, then you can simply have the decoded word to be the uncoded word minus the "-way" section (unless the it is as-way, because then it could be either "was" or "as")
If the last 4 characters are "quay" then you can simply add on "qu" and subtract "-quay" from the encoded word to get the original word.
These would be the first two limiting conditions in an if logic code.
For everything else, you could tell a for loop to go through the word and find the index of the dash. You could store the section of the word from the dash onwards into a variable (excluding the dash), and then select do variable[:-2] to not include the "Ay". The you can create a variable for the new word and have this variable to be the first part of the new word, and then you concatenate
the encoded word up to the index of the dash.

Other than using the eye test, there isn't really a way to identify if something has been encoded with rot13. If it doesn't make sense, then it is probably encoded.
In order to decode/encode the rot13, you would create two strings. One string would contain 2 alphabets--1 capitalized and the other lower case. The other variable would be 2 alphabets, but instead of starting at a, they would start at n, the middle of the alphabet. What happens is that you make a for loop to iterate through each character in the word, and find the character in one of the alphabet variables and identify it's index. Then find the character that is in the same index in the other variable to find the encoded/decoded character.
