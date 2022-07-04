# mathematics-and-statistics
code for statistics count repeating numbers and delete repeated elements.


#include<iostream>
#include<cmath>
using namespace std;
int xmean(int sum, int n);
int standard_coeffient(int arr[], int sum, int n);
int main()
{
    int arr1[100], fr1[100];
    int n, i, j, ctr;
    int sum = 0;
   =
    cout << "Enter the umber of numbers you will enter :";
    cin >> n;

    for (i = 0; i < n; i++)
    {

        cin >> arr1[i];
        fr1[i] = -1;
    }



    for (i = 0; i < n; i++)
    {
        ctr = 1;
        for (j = i + 1; j < n; j++)
        {
            if (arr1[i] == arr1[j])
            {
                ctr++;
                fr1[j] = 0;
            }
        }

        if (fr1[i] != 0)
        {
            fr1[i] = ctr;
        }
    }
    cout << " The frequency of all Data : \n";
    for (i = 0; i < n; i++)
    {
        if (fr1[i] != 0)
        {
            cout << arr1[i] << " " << fr1[i] << "\n";
        }

    }
    for (int g = 0; g < n; g++)
        sum += arr1[g];


    xmean(sum, n);
    standard_coeffient(arr1, sum, n);

}

int xmean(int sum, int n)
{
    cout << "sum :" << sum << "\n";
    double x = sum / n;
    cout << "mean of the marks :" << x << "\n";

    return x;
}

int standard_coeffient(int arr[], int sum, int n)
{
    double x = sum / n;
    double P1 = 0;
    double bs;
    double s;
    for (int q = 0; q < n; q++)
    {
        P1 += (arr[q] - x) * (arr[q] - x);

    }
    bs = P1 / (n - 1);
    s = sqrt(bs);
    cout << "standard deviation of the marks : " << s << "\n";

    cout << "coefficient of variation for marks :" << (s / x) * 100 << "\n";
    cout << "QAYA9 <3" << "\n";

    return 0;
}
