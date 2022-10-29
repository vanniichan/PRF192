#include<stdio.h>
#include<math.h>
#include<string.h>
char hef[1000];
struct BAG
{
    int gam;
    int coin;
    char name;
};
typedef struct BAG BA;
int max(int a, int b) { return (a > b) ? a : b; }
void printknapSack(int W, int wt[], int val[], int n)
{   int dem[100]={0},save[100];char sav[1000];
    int i, w;
    int K[n + 1][W + 1];
    for (i = 0; i <= n; i++) {
        for (w = 0; w <= W; w++) {
            if (i == 0 || w == 0)
                K[i][w] = 0;
            else if (wt[i - 1] <= w)
                K[i][w] = max(val[i - 1] +K[i - 1][w - wt[i - 1]], K[i - 1][w]);
            else
                K[i][w] = K[i - 1][w];
        }
    }
    int op=0;
    int res = K[n][W];
    printf("\n%d\n", res);
    w = W;
    for (i = n; i > 0 && res > 0; i--) {
        if (res == K[i - 1][w])
            continue;
        else {
            save[op]= wt[i - 1];
            dem[save[op]]++;
            sav[op]= hef[i-1];
            res = res - val[i - 1];
            w = w - wt[i - 1];
            op++;
        }
    }
    for(i=op-1;i>=0;i--){
        if(dem[save[i]]!=0){
        printf("%d %c \n",dem[save[i]],sav[i]);
        dem[save[i]]=0;
        }
    }
}
int main()
{   int n,m;
BA a[1000];int b[1000],c[1000];
    scanf("%d%d",&n,&m);
    int i,j,k;
    for(i=0;i<n;i++){
        scanf("%d%d %c",&a[i].gam,&a[i].coin,&a[i].name);
    }
    int re=0,rv=0;
    for(i=0;i<n;i++){
        int f=m/a[i].gam;
        for(j=re;j<re+f;j++){
            b[j]=a[i].gam;
            //printf("%d,", b[j]);
        }
        re+=f;
    }
   // printf("\n");
    for(i=0;i<n;i++){
        int g=m/a[i].gam;
        for(j=rv;j<rv+g;j++){
            c[j]=a[i].coin;
            //printf("%d,", c[j]);
        }
        rv+=g;
    }
    int rr=0;
    for(i=0;i<n;i++){
        int ng=m/a[i].gam;
        for(j=rr;j<rr+ng;j++){
            hef[j]=a[i].name;
            printf("-");
        }
        rr+=ng;
    }
    printknapSack(m,b,c,re);
    return 0;
}
