#include <cmath>
#include <cstdio>
#include <vector>
#include <iostream>
#include <algorithm>

using namespace std;

void print(int arr[][9]){
	for(int i=0;i<9;i++){		
		for(int j=0;j<9;j++){
			cout<<arr[i][j]<<" ";}
		cout<<endl;}	
}

bool first(int arr[][9], int row, int col, int num){
	for(int i=0;i<=8;i++)
		if(arr[row][i]==num)
			return false;
	for(int i=0;i<=8;i++)
		if(arr[i][col]==num)
			return false;
	int startr = row-row%3,
		startc = col - col%3;
	for(int i=0;i<3;i++)
		for(int j=0;j<3;j++)
			if(arr[i+startr][j+startc]==num)
				return false;
	return true;
	}

bool solve(int arr[][9], int row, int col){
	int N=9;
	if(row==N-1 && col==N)
		return true;
	if(col==N){
		row++;
		col=0;}
	if(arr[row][col]>0)
		return solve(arr, row, col+1);
	for(int num=1;num<=N;num++){
		if(first(arr, row, col, num)){
			arr[row][col]=num;
			if(solve(arr, row, col+1))
				return true;
		}
		arr[row][col]=0;
	}
	return false;
}

int main() {
	int sudoku[9][9]=
		{{0,2,6,0,0,3,5,0,0},
		{8,0,0,6,9,0,0,7,4},
		{7,3,0,1,8,5,2,9,0},
		{0,8,0,0,4,9,7,1,0},
		{1,0,5,2,6,0,0,4,0},
		{0,9,3,5,0,0,8,0,2},
		{0,6,9,7,0,4,1,0,8},
		{2,0,0,0,3,0,0,0,7},
		{5,4,0,0,0,1,6,3,0}};
		

	if(solve(sudoku, 0,0))
		print(sudoku);
	else
		cout<<"no solution exists"<<endl;
	return 0;
}
