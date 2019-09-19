# Console Pascal triangle

Examples: 


<img src="https://sun9-3.userapi.com/c850228/v850228533/1e5d64/sZu5wPDaUaw.jpg" width="300">

<img src="https://sun9-14.userapi.com/c857724/v857724533/7b8b0/beYnNshU24E.jpg" width="300">

# Code:

#include <iostream>
#include <conio.h>

using namespace std;
int main()
{
    long int r, k, max; //rzad, kolumna
    
    cout << "This program prints the Pascal triangle\n";
    cout << "enter level: ";
    
    cin >> r;
    
    r = r - 1;
    k = r;
    max = r;
    
    long int tab[ r + 1 ][ k + 1 ]; //create two-dimensional tables
    for( r = 0; r <= max; r++ )
    {
        for( k = 0; k <= max; k++ )
        {
            tab[ r ][ k ] = 0;
        }
    } // clean the whiteboard
    
    tab[ 0 ][ 0 ] = 1;
    tab[ 1 ][ 0 ] = 1;
    tab[ 1 ][ 1 ] = 1;
    
    for( long int r = 2; r <= max; r++ )
    {
        for( long int k = 0; k <= r; k++ )
        {
            if( r == k ) tab[ k ][ r ] = 1;
            
            if( k == 0 ) tab[ k ][ r ] = 1;
            
            tab[ r ][ k ] = tab[ r - 1 ][ k - 1 ] + tab[ r - 1 ][ k ];
        }
    } //calculation of cell values
    
	for( r = 0; r <= max; r++ )
    {
        for( k = 0; k <= r; k++ )
        {
            cout << tab[ r ][ k ] << " ";
        }
        cout << endl;
    } //writing the result on the screen
    
    r=2;
    k=0;
    tab[ r ][ k ] = tab[ r - 1 ][ k - 1 ] + tab[ r - 1 ][ k ];
    
    cout << tab[2 ][ 2 ] << " ";
    
    
    
    
}
