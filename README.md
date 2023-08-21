#include <iostream>
#include <vector>
using namespace std;
int area(vector<int>& h)
{
    int r = h.size() - 1;
    int l = 0;
    int maxWater = 0;

    while (l < r) 
    {
        int minimum_Height = min(h[l], h[r]);
    // here l represent height and l and r represent left and right
        int width = r - l;
        int current_Water = minimum_Height * width;
        maxWater = max(maxWater, current_Water);

        if (h[l] < h[r]) {
            l++;
        } else {
            r--;
        }
    }

    return maxWater;
}

int main() {
    vector<int> h1 = {1,8,6,2,5,4,8,3,7};
    cout << "Output: " << area(h1) << endl;

    vector<int> h2 = {1,1};
    cout << "Output: " << area(h2) << endl;

    return 0;
}
