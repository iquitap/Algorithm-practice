//最小生成树 prim算法

#include <iostream>
#include <math.h>
#include <queue>
#include <algorithm>
#include <string>
#include <assert.h>
#define MAX 27+5
#define Inf 1e9
using namespace std;
int d[MAX][MAX];
int visit[MAX];
int ans[MAX];
int tot;
int n;
void init(void){
    for(int i = 0 ; i < n;i++)
    {
        for(int j = 0 ; j < n ; j++)
        {
            if(i == j)
                d[i][j] = 0;
            else
                d[i][j] = Inf;
        }
    }
    for(int i = 0 ; i < n;i++)
        ans[i] = Inf;
    memset(visit,0,sizeof(visit));
    tot = 0;
    return;
}
void add_edge(int m,int n,int dis)
{
    d[m][n] = d[m][n] < dis ? d[m][n] : dis;
    return;
}
void prim(void)
{
    int me,nv;
    for(int i = 0 ; i < n ;i++)
    {
        ans[i] = d[0][i];
    }
    for(int i = 0;i < n;i++)
    {
        me = Inf;
        for(int j = 0 ; j < n ;j++)
        {
            if(!visit[j] && ans[j] < me)
            {
                nv = j;
                me = ans[j];
            }
        }
        visit[nv] = 1;
        for(int j = 0 ; j < n;j++)
        {
            if(!visit[j] && ans[j] > d[nv][j])
                ans[j] = d[nv][j];
        }
    }
    return;
}
void check(void)
{
    for(int i = 0 ; i < n ;i++)
    {
        for(int j = 0 ; j < n ; j++)
        {
            cout << d[i][j] << " ";
        }
        cout << endl;
    }
    for(int i = 0 ; i < n ; i++)
        cout << ans[i] << " ";
    cout << endl;
}
int main()
{
    char res,des;
    int nn,dis;
    while(cin >> n && n){
        init();
        //cout << "check first" << endl;
        //check();
        for(int i = 0 ; i < n - 1 ;i++){
            cin >> res >> nn;
            for(int j = 0 ; j < nn ; j++)
            {
                cin >> des >> dis;
                add_edge(res-'A',des-'A',dis);
                add_edge(des-'A',res-'A',dis);
            }
        }
        prim();
        //check();
        for(int i = 0 ; i < n;i++)
            tot += ans[i];
        cout << tot << endl;
    }
    return 0;
}
