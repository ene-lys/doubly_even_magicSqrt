//DOUBLY-EVEN SQUARE MATRIX
//ONLY FOR SQUARE MATRIX OF SIZE [4*n x 4*n] 

//1. Read the value N, check if it doubly-even number
//2. Create a matrix NxN with values 0 each cell
//3. Divide into 4x4 blocks
//4. Fill the diagonal of each 4x4 block
//5. Trace through each row fill in blank cell with value n*n-Cij

#include<stdio.h>
#define MAX 16

int S[MAX][MAX] = {0};
int N;

void magicSqrt(int rs, int re, int cs, int ce);
void fill(int rs, int re, int cs, int ce);
void solution();

int main(){
    //Input  size of the square matrix
    scanf("%d", &N);

    if(N % 4 != 0){
        printf("This code is not available!.\n");
        return 1;
    }
    else {
        magicSqrt(0, N - 1, 0, N - 1);
        solution();
    }

}

//Seperate the matrix into 4x4 blocks
void magicSqrt(int rs, int re, int cs, int ce){ //Input start_row, end_row, start_col, end_col
    if(re - rs == 3 && ce - cs == 3) fill(rs, re, cs, ce);

    else {
        int midR = 0, midC = 0;

            midR = (rs + re)/2;
            midC = (cs + ce)/2;

    //Recursion until we have a 4x4 block
        magicSqrt(rs, midR, cs, midC);
        magicSqrt(rs, midR, midC + 1, ce);
        magicSqrt(midR + 1, re, cs, midC);
        magicSqrt(midR + 1, re, midC + 1, ce);
    }
}

void fill(int rs, int re, int cs, int ce){
    if((cs - rs) % 4 == 0 || (rs - cs) % 4 == 0 || ((cs + rs + 1) % 4 == 0)){ //Find diagonal cells
        S[rs][cs] = rs*N + cs + 1;
    }
    else {
        S[rs][cs] = N*N - (rs*N + cs);
    }

    if(rs == re && cs == ce) return;
    else if(cs == ce) fill(rs + 1, re, cs - 3, ce);
    else fill(rs, re, cs + 1, ce);
}

void solution(){
    for(int i = 0; i<N; i++){
        for(int u = 0; u<N; u++){
            printf("%.2d ", S[i][u]);
        }
        printf("\n");
    }

    printf("\n");
}
