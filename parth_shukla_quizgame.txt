#include <iostream>
#include <vector>
#include <algorithm>

using namespace std;

int main() {
    int t;
    cin >> t;

    for (int test = 0; test < t; ++test) {
        int numJars, numChildren;
        cin >> numJars >> numChildren;

        vector<int> jarCookies(numJars);

        for (int i = 0; i < numJars; ++i) {
            cin >> jarCookies[i];
        }

        sort(jarCookies.rbegin(), jarCookies.rend());

        vector<int> distribution;

        for (int i = 0; i < numJars; ++i) {
            if (jarCookies[i] >= numChildren) {
                distribution.push_back(jarCookies[i] % numChildren);
            }
        }

        if (distribution.empty()) {
            cout << -1 << endl;
        } else {
            for (int i = 0; i < distribution.size(); ++i) {
                cout << distribution[i] << " ";
            }
            cout << endl;
        }
    }

    return 0;
}
#quizzzz game