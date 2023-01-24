class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        test = ""
        # Result
        max_length = 0
        
        # Return zero or 1 if string is empty or only 1 length
        if len(s) == 0 or len(s) == 1:
            return len(s)
        
        for c in s:
            # If string already contains the character
            # Then substring after repeating character
            if c in test:
                test = test[test.index(c)+1:]
            test = test + c
            if max_length < len(test):
                max_length = len(test)
        return max_length