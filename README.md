# -
找到频率最高的元音和辅音
int maxFreqSum(string s) {
        vector<char> y = {'a', 'e', 'i', 'o', 'u'};
        vector<char> fy;
        vector<int> yn, fyn;
        int f = (int)'z' - (int)'a';
        for (int i = 0; i < f; i++) {
            char c = static_cast<char>(i + 'a'+1);
            if (find(y.begin(), y.end(), c) == y.end()) {
                fy.push_back(c);
            }
        }
        for (char timey : y) {
            yn.push_back(count(s.begin(), s.end(), timey));
        }
        for (char timefy : fy) {
            fyn.push_back(count(s.begin(), s.end(), timefy));
        }
        int maxy = *max_element(yn.begin(), yn.end());
        int maxfy = *max_element(fyn.begin(), fyn.end());
        int sum = maxy + maxfy;
        return sum;
    }
