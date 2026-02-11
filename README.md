class Solution {
public:
    int romanToInt(std::string s) {

        std::unordered_map<char, int> romanMap = {
            {'I', 1},
            {'V', 5},
            {'X', 10},
            {'L', 50},
            {'C', 100},
            {'D', 500},
            {'M', 1000}
        };
        
        int total = 0;
        int n = s.length();

        total = romanMap[s[n - 1]];

        for (int i = n - 2; i >= 0; --i) {
            int currentValue = romanMap[s[i]];
            int nextValue = romanMap[s[i + 1]];

            if (currentValue < nextValue) {

                total -= currentValue;
            } else {

                total += currentValue;
            }
        }
        
        return total;
    }
};

 



