                                            ****2D GRID -BFS**
                    
ll dis[10001][10001]={0};
ll vis[10001][10001]={0};
char a[10001][10001];
ll dx[4]={-1,0,0,1};
ll dy[4]={0,1,-1,0};
ll n;
bool isValid(ll x,ll y)
{
    if(x>n||y>n||x<1||y<1)
    return false;
    if(vis[x][y]==1||a[x][y]=='T')
    return false;
    return true;
}


void dfs(ll x,ll y)
{
    queue<pii>q;
    q.push({x,y});
    dis[x][y]=0;
    vis[x][y]=0;

    while(!q.empty())
    {
        ll curr_x=q.front().ff;
        ll curr_y=q.front().ss;
        q.pop();
        f(i,0,4)
        if(isValid(curr_x+dx[i],curr_y+dy[i]))
        {
            ll new_x=curr_x+dx[i];
            ll new_y=curr_y+dy[i];
            dis[new_x][new_y]=dis[curr_x][curr_y]+1;
            vis[new_x][new_y]=1;
            q.push({new_x,new_y});
       }
    }
}
 
int main()
{
    teji;
    ll t=1;
    // cin>>t;
    while(t--)
    {
       cin>>n;
       pii src,des;
    //    char a[n+1][n+1];
       f(i,1,n+1)
       {
           f(j,1,n+1)
           {
            cin>>a[i][j];
            if(a[i][j]=='S')
            src={i,j};
            if(a[i][j]=='E')
            des={i,j};
           }
           
       }
       dfs(src.ff,src.ss);
       cout<<dis[des.ff][des.ss]<<endl;
    }
    
}
  
