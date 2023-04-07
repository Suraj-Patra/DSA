<pre>
Faulty Keyboard

Some of the keys on your keyboard are faulty. When you press a key, it may register more than once. That means if you want to type "code", the keyboard may interpret it as "code", "cccoddee" or "coode" or "codeeeee", etc. So, by pressing the keys C, O, D, and E in that order, you may get any of the above-mentioned words.
However, there are certain words that you will not get like, "cddde", "cod", "coeeeeed", etc.
You will be given 'N' pairs of words. The first word of each pair is what you intended to write and the second one is what the keyboard interprets it as. You need to figure out whether the second word can actually be a possible interpretation of the first word.
</pre>


```CPP
    /*
        Time Complexity : O(N+M)
        Space Complexity: O(N+M)
    */

    #include<vector>

    vector<pair<char, int>> makeGroups(string s) {
        vector<pair<char, int>> ret;
        char currChar = s[0];
        int currCharCount = 1;

        for(int i=1; i<s.length(); i++) {
            if(s[i]==currChar) {
                ++currCharCount;
            } else {
                ret.push_back(make_pair(currChar, currCharCount));
                currChar = s[i];
                currCharCount = 1;
            }
        }

        ret.push_back(make_pair(currChar, currCharCount));
        return ret;
    }

    bool canType(string s1, string s2) {
        vector<pair<char, int>> group1 = makeGroups(s1);
        vector<pair<char, int>> group2 = makeGroups(s2);

        if(group1.size()!=group2.size()) {
            return false;
        }

        for(int i=0; i<group1.size(); i++) {
            if(group1[i].first!=group2[i].first) {
                return false;
            } else if(group1[i].second>group2[i].second) {
                return false;
            }
        }

        return true;
    }



















