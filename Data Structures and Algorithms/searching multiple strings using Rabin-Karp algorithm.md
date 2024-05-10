#assignment #Algorithm 

You're tasked with developing a search engine for a digital library containing millions of documents. To enhance search accuracy, you've decided to implement the Rabin-Karp algorithm for string matching. However, your challenge is to extend the algorithm to handle multiple patterns simultaneously, efficiently detecting occurrences of any of the given patterns within the documents. How would you modify the Rabin-Karp algorithm to accommodate this requirement while ensuring optimal performance?


| Sample Input                                                                    | Sample Output                                                                                                   |
| :------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------- |
| Text: The quick brown fox jumps over the lazy dog.<br>Patterns: quick, fox, dog | - Pattern "quick" found at index 4.<br>- Pattern "fox" found at index 16.<br>- Pattern "dog" found at index 35. |



```cpp
#include <iostream>
#include <vector>
#include <string>
#include <unordered_map>
using namespace std;
#define d 256 
void search(const vector<string>& patterns, const string& text, int q) {
int numPatterns = patterns.size();
int N = text.length();
unordered_map<string, vector<int>> patternMap;
for (int k = 0; k < numPatterns; k++) {
const string& pat = patterns[k];
int M = pat.length();
int p = 0, t = 0, h = 1;
// Calculate the hash value of pattern and first window of text
for (int i = 0; i < M; i++) {
p = (d * p + pat[i]) % q;
t = (d * t + text[i]) % q;
}
// Calculate h = pow(d, M-1) % q
for (int i = 0; i < M - 1; i++)
h = (h * d) % q;
// Slide the pattern over text one by one
for (int i = 0; i <= N - M; i++) {
// Check the hash values of current window of text and pattern
if (p == t) {
// Check for characters one by one
int j = 0;
for (j = 0; j < M; j++) {
if (text[i + j] != pat[j])
break;
}
// If pat[0...M-1] = text[i, i+1, ...i+M-1]
if (j == M)
patternMap[pat].push_back(i);
} 
// Calculate hash value for the next window of text: Remove leading digit, add trailing digit
if (i < N - M) {
t = (d * (t - text[i] * h) + text[i + M]) % q; 
// We might get negative value of t, converting it to positive
if (t < 0)
t = (t + q);
}
}
} 
// Print the occurrences
for (const auto& pattern : patterns) {
if (patternMap.count(pattern) > 0) {
cout << "Pattern '" << pattern << "' found at indexes: ";
const vector<int>& indexes = patternMap[pattern];
for (int index : indexes) {
cout << index << " ";
}
cout << endl;
} else {
cout << "Pattern '" << pattern << "' not found." << endl;
}
}
} 

int main() {
string text = "UNITED INTERNATIONAL UNIVERSITY. UNITED WE STAND, DIVIDE WE FALL";
vector<string> patterns = {"UNITED", "FALL"};
int q = 101;
search(patterns, text, q);
return 0;
}
```


