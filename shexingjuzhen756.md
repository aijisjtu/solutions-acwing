### 756 蛇形矩阵

微软面试题[https://www.acwing.com/problem/content/description/758/](https://www.acwing.com/problem/content/description/758/)

技巧：

- 偏移量
- 拐弯条件

```cpp
#include<iostream>
using namespace std;

const int N =110;
int n, m;
int q[N][N];

int main(){
cin >> n >> m;
int dx[] = {-1,0,1,0}, dy[] = {0,1,0,-1};
int x = 0, y = 0, d = 1;
for (int i = 1; i <= n * m; i ++){
    q[x][y] = i;
    int a = x + dx[d], b = y + dy[d];
    if ( a < 0 || a >= n || b < 0 || b >= m|| q[a][b]){
        d = (d + 1) % 4;
        a = x + dx[d], b = y + dy[d];
        }
        x= a, y = b;
    }
for ( int i = 0; i < n; i ++ ){
    for (int j = 0; j < m; j ++ )
        cout<<q[i][j]<<' ';
        cout<<endl;
    }
    return 0;
}
```
