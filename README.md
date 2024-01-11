# Lexographic Indexes
Python script used to compute three different lexographic indexes for any list of sequences of characters. 
Do note that for this type of indexes the starting position is 1 and not 0 as it would be considered by Python's rules.
Each different character will be isolated from the others and three scores are computed based on its occurrence within each sequence:
- **A** corresponds to the *position* of all occurrence of a specific character. 
  Ex:In the list `[1,0,0,1,0,0]`, 1 is found in positions 1 and 4, therefore `A = [1,4]`.
- **B** corresponds to the highest position achievable for each character if moving forward, until another similar character is found.
  Ex: The list `[1,0,0,0,1,0,0]` would become [0,0,0,1,0,1], therefore `B = [4,6]`.
- **C** corresponds to the highest position achievable for each character if moving forward, until another similar character is found.
  Ex: The list `[1,0,0,0,1,0,0]` would become [1,1,0,0,0,0], therefore `C = [1,2]`.

If the sequence is composed of different characters, this operation will be done for each of them independently.
Ex: the sequence `[1,1,2,1,2,0]` will be split into 2, the 1<sup>st</sup> being `[1,1,0,1,0,0]` and the 2<sup>nd</sup> being `[0,0,2,0,2,0]`

Once all A,B and C scores are computed the indexes can be built. 

In the following formulas $T$ refers to the total number of characters (list or string length), while $e$ represents the number of events, how many times that specific character is found in the sequence.
1. The *1<sup>st</sup>* index is based on the output of the following function:
2. The *2<sup>nd</sup* index is based on the output of the following function:
3. The *3<sup>rd</sup>* index is divided in two parts;
   - the first part (*3A*) is equal to $e/T$;
   - The second part (*3B*) is based on the output of the following function:
