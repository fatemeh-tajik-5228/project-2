# project-2
#include <iostream> 
using namespace std ;
// baresi motegharen ya pad_motegharen ya tarayayi darad ya na
int main () {
		int n ;
	cout << "Andaze matris ra vared kon(satr=sotoon): " ;
	cin >> n ;
	int A[n][n] ;
	cout << "matris rabeteh ra vared kon(0 or 1)" << "\n" ;
	for(int i=0 ; i<n ; i++) {
		cout << "satr" << i+1 << ": " ;
		for(int j=0 ; j<n ; j++) {
			cin >> A[i][j] ;
		}
	}
	
	bool motegharen = true ;
	for(int i=0 ; i<n ; i++) {
		for(int j=0 ; j<n ; j++){
		    if(A[i][j] != A[j][i]) {
		        motegharen = false ;
		    }
		} 
		if(!motegharen) break ;
	}
	
	bool pad_motegharen = true ;
	for(int i=0 ; i<=n ; i++) {
		for(int j=0 ; j<n ; j++){
		    if(i != j && A[i][j] == 1 && A[j][i] !=0 ) {
		        pad_motegharen = !pad_motegharen ;
		    	break ;
		    }
		} 
		if(!pad_motegharen) break ;
	}
	
	bool tarayayi = true ;
	for(int i=0 ; i<n ; i++) {
		for(int j=0 ; j<n ; j++){
		    if(A[i][j] == 1) {
		    	for(int k=0 ; k<n ; k++) {
		    		if(A[j][k] == 1 && A[i][k] != 1) {
					    tarayayi = false ;
					    break ;
					}
				}
			}
			if(!tarayayi) break ;
		}
		if(!tarayayi) break ;
	}
	
	cout << "\nnatije baresi: \n" ;
	cout << "khasiyat motegharen:" << (motegharen ? "darad" : "Nadarad") << "\n" ;
	cout << "khasiyat pad_motagharen:" << (pad_motegharen ? "Darad" : "Nadarad") << "\n";
	cout << "khasiyat tarayayi:" << (tarayayi ? "Darad" : "Nadarad") << "\n" ;
	return 0 ;
} 
