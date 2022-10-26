// #include <stdio.h>
// #include <math.h>
// #include <stdbool.h>
// #include <stdlib.h>

// //A.最小公倍数
// int gcd(int m,int n){
//     return m%n==0?n:gcd(n,m%n);
// }
// int main(){
//     int m,n;
//     while(~scanf("%d%d",&m,&n)){
//         printf("%d\n",m/gcd(m,n)*n);
//     }
//     return 0;
// }

// //B.还是最小公倍数
// int gcd(int a,int b){
//     return a%b==0?b:gcd(b,a%b);
// }
// int main(){
//     int c,ans,n,num;
//     scanf("%d",&c);
//     while(c--){
//         scanf("%d",&n);
//         ans=1;
//         while(n--){
//             scanf("%d",&num);
//             ans=ans/gcd(ans,num)*num;
//         }
//         printf("%d\n",ans);
//     }
//     return 0;
// }

// //C. 计算N的N次幂的个位数//4循环
// int main(){
//     int t,n,ans,a,b;
//     scanf("%d",&t);
//     while(t--){
//         scanf("%d",&n);
//         b=n%4;
//         if(b==0)b=4;
//         a=n%10;
//         ans=1;
//         while(b--){
//             ans*=a;
//             ans%=10;
//         }
//         printf("%d\n",ans);
//     }
//     return 0;
// }

// //D. 人见人爱A^B//快速幂 //二分法
//  int power(int a,int n){
//      int ans;
//      if(a>=1000)a%=1000;
//      if(n==0){
//          ans=1;
//      }else{
//          ans=power(a*a,n/2);
//          if(n%2!=0)ans*=a;
//          if(ans>1000)ans%=1000;
//      }
//      return ans;
//  }
//  int main(){
//      int a,b,c;
//      while(scanf("%d %d",&a,&b)==2){
//         if(a==0&&b==0)break;
//         c=power(a,b);
//         printf("%d\n",c);
//      }
//      return 0;
//  }

// //e.斐波那契数列 // fn%3=fn-1%3+fn-2%3//利用抽屉原理确定多少项以内一定会出现循环
//  int main(){
//      int n;
//      while(scanf("%d",&n)==1){
//          if(n%4==2){
//              printf("yes\n");
//          }else printf("no\n");
//      }
//      return 0;
//  }

// //f.解方程/ /二分法
// double Y;
// double left,right,mid;
// double f(double x){
//     return 8*pow(x,4.0)+7*pow(x,3.0)+2*pow(x,2.0)+3*x+6;
//     }
// int main(){
//     int t;
//     scanf("%d",&t);
//     while(t--){
//         scanf("%lf",&Y);
//         if(f(0)<=Y&&Y<=f(100)){
//             left=0; right=100;
//             while(right-left>1e-7){
//                 mid=(left+right)/2;
//                 double ans=f(mid);
//                 if(ans>Y)
//                     right=mid-1e-7;
//                 else
//                     left=mid+1e-7;
//             }
//             printf("%.4f\n",(left+right)/2);
//         }
//         else printf("No solution!\n");
//     }
// }

// //G.老鼠和猫的交易 //四舍五入算法，sort函数
// #include<stdio.h>
// #include<stdlib.h>
// #include<math.h>
// int main()
// {   int m, n, k;
//     int j[10000]={0}, f[10000]={0};
//     double money[10000] = {0}, gain = 0;
//     while (scanf("%d %d", &m, &n) == 2)
//     {
//         int count = n;
//         if (m == -1 && n == -1)
//             break;
//         for (int p = 0; p < n; p++)
//         {
//             scanf("%d %d", &j[p], &f[p]);
//             money[p] = j[p] * 1.0 / f[p];
//         }
//         while (m-0<1e-5 && count != 0)
//         {
//             for (k = 0; k < n; k++)
//             {
//                 int judge = 1;
//                 for (int i = 0; i < n; i++)
//                 {
//                     if (money[k] < money[i])
//                         judge = 0;
//                 }
//                 if (judge == 1)
//                     break;
//             }
//             if (f[k] <= m)
//             {
//                 gain += j[k];
//                 m -= f[k];
//                 count--;
//             }
//             else
//             {
//                 gain = gain + m * money[k];
//                 m = 0;
//             }
//             money[k] = 0;
//         }
//         gain*=1000;
// 		gain=(int)(gain+0.5);
// 		gain/=1000;
//         printf("%.3lf\n", gain);
//         gain = 0;
//     }
//     return 0;
// }

// //H.田忌赛马
// #include<bits/stdc++.h>
// using namespace std;
// bool cmp(int a,int b){
// 	return a>b;
// }
// int main(){
// 	int n,i,k,money=0;
// 	int a[1000]={0},b[1000]={0};
// 	while(cin>>n){
// 		if(n==0)break;
// 		for(i=0;i<n;i++){
// 			cin>>a[i];	
// 		}
// 		for(i=0;i<n;i++){
// 			cin>>b[i];
// 		}
// 		sort(a,a+n,cmp);
// 		sort(b,b+n,cmp);
// 		for(i=0,k=0;k<n;){
// 			if(a[i]>b[k]){
// 				money+=200;
// 				i++;
// 				k++; 
// 			}else{
// 				k++;
// 			}
// 		}money=money-200*(n-i);
// 		cout<<money<<endl;
// 		money=0;
// 	}
// 	return 0;
// } 

// //I.搬桌子    
// int main(){
//     int t,n,a,b;
//     scanf("%d",&t);
//     for(int i=0;i<t;i++){
//         int f[200]={0};
//         scanf("%d",&n);
//         for(int k=0;k<n;k++){
//             scanf("%d %d",&a,&b);
//             a=(a-1)/2;
//             b=(b-1)/2;
//             if(a>b){
//                 int q=a;
//                 a=b;
//                 b=q;
//             }
//             for(int j=a;j<=b;j++){
//                 f[j]++;
//             }
//         }
//         int max=-1;
//         for(int j=0;j<200;j++){
//             if(f[j]>max)
//             max=f[j];
//         }printf("%d\n",max*10);
//     }
//     return 0;
// }

// //J.今年暑假不AC
// struct ti{
// 	int s,e;
// }t[100];
// bool cmp(ti x,ti y)
// {
// 	return x.e<y.e;
// }
// int main(){
// 	int n,time=0,count=1;
// 	while(cin>>n){
// 	if(n==0)break;
// 	for(int i=0;i<n;i++){
// 		cin>>t[i].s>>t[i].e;
// 	}sort(t,t+n,cmp);
// 	time=t[0].e;
// 	for(int i=1;i<n;i++){
// 		if(t[i].s>=time){
// 			time=t[i].e;
// 			count++;
// 		}
// 	}cout<<count<<endl;
// 	count=1;
// }
// 	return 0;
// }

// //K.奋勇争先续
// struct order{
// 	char name[10];
// 	int num;
// 	int time;
// }stu[1000];
// bool cmp(order x,order y){
// 	if(x.num!=y.num)return x.num>y.num;
// 	else return x.time<y.time;
// }
// int main(){
// 	int c,n,m;
// 	cin>>c;
// 	for(int i=0;i<c;i++){
// 		cin>>n>>m;
// 		for(int k=0;k<n;k++){
// 			cin>>stu[k].name>>stu[k].num>>stu[k].time;
// 		}
// 		sort(stu,stu+n,cmp);
// 		for(int k=0;k<m;k++){
// 			cout<<stu[k].name<<' '<<stu[k].num<<' '<<stu[k].time<<endl;
// 		}
// 	}
// 	return 0;
// } 

// //L. Degree Sequence of Graph G//可图性
// bool cmp(int x,int y){
// 	return x>y;
// }
// int main(){
// 	int t,n;
// 	cin>>t;
// 	for(int i=0;i<t;i++){
// 		int a[1001]={0};
// 		cin>>n;
// 		for(int k=0;k<n;k++){
// 			cin>>a[k];
// 		}
// 		for(int j=0;j<n;j++){
// 		    sort(a,a+n,cmp);
// 			for(int k=0;k<a[0];k++){
// 				a[k+1]-=1;
// 			}
// 			for(int k=0;k<n;k++){
// 				a[k]=a[k+1];
// 			}
// 		}int judge=1;
// 		for(int k=0;k<n;k++){
// 			if(a[k]<0){
// 			judge=0;
// 			break;
// 			}
// 		}if(judge==1){
// 			cout<<"yes"<<endl;
// 		}else{
// 			cout<<"no"<<endl;
// 		}
// 	}
// 	return 0;
// } 

// //M.畅通工程 //并查集//findx//merge
// ////int set[1000];
// int findx(int a){
//     while(set[a]!=a)
//     a=set[a];
//     return a;
// }
// void merge(int a,int b){
//     a=findx(a);
//     b=findx(b);
//     if(a!=b)
//     set[b]=a;
// }
// int main(){
//     int n,m,i,count=0,a,b;
//     while(scanf("%d",&n),n){
//         for(i=1;i<=n;i++)
//             set[i]=i;
// /////   for(scanf("%d",&m);m>0;m--){
//             scanf("%d %d",&a,&b);
//             merge(a,b);
//         }
//     for(count=0,i=1;i<=n;i++)
//             if(set[i]==i)count++;
//         printf("%d\n",count-1);
//     }
//     return 0;
// }

// //N.还是畅通工程 merge延迟
// #include <iostream>
// #include <algorithm>
// using namespace std;
// int boss[10000];
// struct ab {
// 	int set1;
// 	int set2;
// 	long long distance;
// } vil[10000];
// int findx(int a) {
// 	int r=a;
// 	if( r==boss[r])return r;
// 	boss[r]=findx(boss[r]);
// 	return boss[r];
// }
// void merge(int a,int b) {
// 	boss[a]=b;
// }
// bool cmp(ab x,ab y) {
// 	return x.distance<y.distance;
// }
// int main() {
// 	int n,i,num;
// 	long long count;
// 	cin>>n;
// 	while(n!=0) {
// 		for(i=1; i<=n; i++) {
// 			boss[i]=i;
// 		}
// 		for(i=1; i<=n*(n-1)/2; i++) {
// 			cin>>vil[i].set1>>vil[i].set2>>vil[i].distance;
// 		}
// 		sort(vil+1,vil+n*(n-1)/2+1,cmp);
// 		for(count=0,i=1,num=0; num<n-1; i++) {
// 			int fa,fb;
// 			fa=findx(vil[i].set1);
// 			fb=findx(vil[i].set2);
// 			if(fa!=fb) {
// 				merge(fa,fb);
// 				count+=vil[i].distance;
// 				num++;
// 			}
// 		}
// 		cout<<count<<endl;
// 		cin>>n;
// 	}
// 	return 0;
// }

// //O.畅通工程
// #include <iostream>
// #include <algorithm>
// using namespace std;
// int boss[10000];
// struct giao{
// 	int set1;
// 	int set2;
// 	int distance;
// }v[10000];
// int findx(int a){
// 	while(boss[a]!=a)
// 	a=boss[a];
// 	return a;
// }
// void merge(int a,int b){
// 	boss[a]=b;
// }
// bool cmp(giao x,giao y){
// 	return x.distance<y.distance;
// }
// int main(){
// 	int n,m,i,mon,count;
// 	while(scanf("%d",&n)==1,n){
// 		scanf("%d",&m);
// 		for(i=0;i<=m;i++)
// 			boss[i]=i;
// 		for(i=1;i<=n;i++)
// 			cin>>v[i].set1>>v[i].set2>>v[i].distance;
// 		sort(v+1,v+n+1,cmp);
// 		for(mon=0,count=0,i=1;i<=n;i++){
// 			int fa,fb;
// 			fa=findx(v[i].set1);
// 			fb=findx(v[i].set2);
// 			if(fa!=fb){
// 				merge(fa,fb);
// 				mon+=v[i].distance;
// 				count++;
// 			}
// 		}if(count<m-1)
// 			printf("?\n");
// 		else printf("%d\n",mon);
// 	}
// 	return 0;
// }

// //P.继续畅通工程//少打了个等号，现在很想死//
// #include <iostream>
// #include <algorithm>
// using namespace std;
// int boss[10000];
// struct giao{
// 	int set1;
// 	int set2;
// 	long long distance;
// 	int judge;
// }v[10000];
// int findx(int a){
// 	int r=a;
// 	if(r==boss[r])return r;
// 	boss[r]=findx(boss[r]);
// 	return boss[r];
// }
// void merge(int a,int b){
// 	boss[a]=b;
// }
// bool cmp(giao x,giao y){
// 	return x.distance<y.distance;
// }
// int main(){
// 	int n,i,k,count,fa,fb;
// 	while(scanf("%d",&n)==1,n)
// 	{
// 		for(i=1;i<=n;i++)
// 			boss[i]=i;
// 		for(i=1;i<=n*(n-1)/2;i++){
// 			cin>>v[i].set1>>v[i].set2>>v[i].distance>>v[i].judge;
// 			if(v[i].judge)
// 				v[i].distance=0;
// 		}
// 		sort(v+1,v+n*(n-1)/2+1,cmp);
// 		long long mon=0;
// 		for(i=1,count=0;count<n-1;i++)
// 		{
// 			fa=findx(v[i].set1);
// 			fb=findx(v[i].set2);
// 			if(fa!=fb){
// 				merge(fa,fb);
// 				mon+=v[i].distance;
// 				count++;
// 			}
// 		}cout<<mon<<endl;
// 	}
// 	return 0;
// }

// //Q.小希的迷宫（0.0）
// int p[100001]={0};
// int findx(int a){
// 	if(a==p[a])return a;
// 	p[a]=findx(p[a]);
// 	return p[a];
// }
// void merge(int a,int b){
// 	p[a]=b;
// }
// int main(){
// 	int m,n,fa,fb,i,judge,sum;
// 	scanf("%d %d",&m,&n);
// 	while(m!=-1&&n!=-1)
// 	{
// 		if(p[m]==0)p[m]=m;
// 		if(p[n]==0)p[n]=n;
// 		if(m==0&&n==0)
// 		{
// 			for(i=1;i<=100000;i++){
// 				if(p[i]==i)sum++;
// 				p[i]=0;
// 			}
// 			if(judge&&(sum==0||sum==1)){
// 				printf("Yes\n");
// 			}
// 			else{
// 				printf("No\n");
// 			}sum=0;
// 			scanf("%d %d",&m,&n);
// 			if(m==-1&&n==-1)break;
// 			if(m==0&&n==0){judge=1;continue;}
// 			if(p[m]==0)p[m]=m;
// 			if(p[n]==0)p[n]=n;		
// 		}
// 			judge=1;
// 			fa=findx(m);
// 			fb=findx(n);
// 			if(fa!=fb)
// 			{
// 				merge(fa,fb);
// 				scanf("%d %d",&m,&n);
// 			}
// 			else
// 			{	
// 				judge=0;
// 				scanf("%d %d",&m,&n);
// 				while(m!=0&&n!=0){
// 					scanf("%d %d",&m,&n);
// 				}
// 			}
// 	}
// 	return 0;
// }

// int f(int a){
//     if(a==1)return 1;
//     if(a==2)return 2;
//     return f(a-1)+f(a-2);
// }

// //I.超级楼梯
// int main(){
//     int n,i,m,sum;
//     scanf("%d",&n);
//     for(i=0;i<n;i++){
//         scanf("%d",&m);
//         sum=f(m-1);
//         printf("%d\n",sum);
//     }
//     return 0;
// }

// //S.一只小蜜蜂//long long//超时
// #include <iostream>
// #include <algorithm>
// using namespace std;
// long long num[50]={0};
// long long f(int n){
//     long long back=0;
//     if(n==1)back=0;
//     else if(n==2)back=1;
//     else if(n==3)back=2;
//     else if(num[n-1]!=0&&num[n-2]!=0)
//         back=num[n-1]+num[n-2];
//     else if(num[n-1]==0&&num[n-2]!=0)
//         back=num[n-2]+f(n-1);
//     else if(num[n-2]==0&&num[n-1]!=0)
//         back=num[n-1]+f(n-2);
//     else if(num[n-1]==0&&num[n-2]==0)
//         back=f(n-1)+f(n-2);
//     num[n]=back;
//     return back;
// }
// int main(){
//     int n,a,b;
//     long long ans;
//     scanf("%d",&n);
//     while(n--){
//         scanf("%d%d",&a,&b);
//         if(num[b-a+1]==0)num[b-a+1]=f(b-a+1);
//         ans=num[b-a+1];
//         printf("%lld\n",ans);
//     }
//     return 0;
// }

// //S.一只小蜜蜂//超过20项便不适合递归，项数少用for循环解决
// int main(){
//     int n,i;
//     scanf("%d",&n);
//     int start,end;
//     double way[51];
//     way[2]=1;
//     way[3]=2;
//     for(int i=4;i<50;i++)
//         way[i]=way[i-1]+way[i-2];
//     while(n--){
//         scanf("%d%d",&start,&end);
//         printf("%.0f\n",way[end-start+1]);
//     }
//     return 0;
// }

// //T.骨牌铺方格//完全没看出来和上一道题的区别
// #include <iostream>
// #include <algorithm>
// using namespace std;
// long long num[51]={0};
// long long f(int n){
//     long long back;
//     if(n==1)back=1;
//     else if(n==2)back=2;
//     else {
//         if(num[n-1]==0)num[n-1]=f(n-1);
//         if(num[n-2]==0)num[n-2]=f(n-2);   
//         back=num[n-1]+num[n-2];
//     }    
//     return back;
// }
// int main(){
//     int n;
//     long long ans;
//     while(scanf("%d",&n)==1){
//         ans=f(n);
//         printf("%lld\n",ans);
//     }
//     return 0;
// }

// //U.折线分割平面
// int num[10001]={0};
// int main(){
//     int c,n,max=1;
//     num[1]=2;
//     scanf("%d",&c);
//     while(c--){
//         scanf("%d",&n);
//         if(n>max){
//         for(int i=max+1;i<=n;i++){
//             num[i]=num[i-1]+4*i-3;
//         }}
//         printf("%d\n",num[n]);
//     }
//     return 0;
// }

// //V. 悼念512汶川大地震遇难同胞——重建希望小学
// #include <iostream>
// #include <algorithm>
// using namespace std;
// int num[31]={0};
// int f(int n){
//     if(n==1)return 1;
//     if(n==2)return 3;
//     if(num[n-1]==0)num[n-1]=f(n-1);
//     if(num[n-2]==0)num[n-2]=f(n-2);
//     return num[n-1]+2*num[n-2];
// }
// int main(){
//     int c,n,ans;
//     scanf("%d",&c);
//     while(c--){
//         scanf("%d",&n);
//         ans=f(n);
//         printf("%d\n",ans);
//     }
//     return 0;
// }

// //W. Tiling_easy version
// #include <iostream>
// #include <algorithm>
// using namespace std;
// int num[31]={0};
// int f(int n){
//     if(n==1)return 1;
//     if(n==2)return 3;
//     if(num[n-1]==0)num[n-1]=f(n-1);
//     if(num[n-2]==0)num[n-2]=f(n-2);
//     return num[n-1]+2*num[n-2];
// }
// int main(){
//     int t,n,ans;
//     scanf("%d",&t);
//     while(t--){
//         scanf("%d",&n);
//         ans=f(n);
//         printf("%d\n",ans);
//     }
//     return 0;
// }

// //X. 阿牛的EOF牛肉串
// #include <iostream>
// #include <algorithm>
// using namespace std;
// int main(){
//     long long a[40]={0};
//     int n;
//     a[1]=3;
//     a[2]=8;
//     for(int i=3;i<40;i++)
//         a[i]=2*(a[i-1]+a[i-2]);
//         while(cin>>n)
//             cout<<a[n]<<endl;  
//     return 0;
// }

// //Y. 不容易系列之(3)—— LELE的RPG难题
// #include <iostream>
// #include <algorithm>
// using namespace std;
// int main(){
//     int n,ans;
//     double num[51]={0};
//     num[1]=3;
//     num[2]=6;
//     num[3]=6;
//     for(int i=4;i<=50;i++){
//         num[i]=num[i-1]+2*num[i-2];
//     }
//     while(scanf("%d",&n)==1){
//         printf("%.0f\n",num[n]);
//     }
//     return 0;
// }

// //A.数塔 //dp经典
// int main(){
//     int c,n;
//     long long a[101][101]={0};
//     scanf("%d",&c);
//     while(c--){
//         scanf("%d",&n);
//         for(int i=1;i<=n;i++){
//             for(int k=1;k<=i;k++)
//             scanf("%lld",&a[i][k]);
//         }
//         for(int i=n;i>1;i--){
//             for(int k=1;k<=i;k++){
//                 if(a[i][k]>a[i][k+1])a[i-1][k]=a[i][k]+a[i-1][k];
//                 else a[i-1][k]=a[i][k+1]+a[i-1][k];
//             }
//         }
//         printf("%lld\n",a[1][1]);
//     }
//     return 0;
// }

// //B. 最少拦截系统//最长有序子数列
// #include <iostream>
// #include <algorithm>
// using namespace std;
// int main()
// {
//     int n, ans, max = 0;
//     int a[10000] = {0};
//     int b[10000] = {0};
//     while (cin >> n)
//     {
//         for (int i = 1; i <= n; i++)//存储数据
//         {
//             cin >> a[i];
//             b[i]=1;//初始化
//         }
//         for (int i = 1; i <= n; i++)
//         {
//             for (int k = 1; k <= i; k++)
//             {
//                 if (a[i] > a[k])//寻找递增数//扫描子问题
//                 {
//                     if(b[i]<b[k]+1)//寻找最优子问题
//                     b[i] = b[k] + 1;//链接
//                 }
//             }
//         }
//         for (int i = 1; i <= n; i++)//扫描最优解
//         {
//             if (b[i] > max)
//                 max = b[i];
//         }
//         printf("%d\n", max);
//         max = 0;
//     }
//     return 0;
// }

// //C.搬寝室 //没有自己做出来的题，好好看看
// #include<cstdio>
// #include<cstring>
// #include<iostream>
// #include<algorithm>
// #include<queue>
// #include<vector>
// using namespace std;
// const int INF = 1000000000 ;
// int n,k,a[2005],dp[2005][1200];
// int main(){
//     while(~scanf("%d%d",&n,&k)){
//         for(int i=0;i<n;i++)
//             scanf("%d",&a[i]);
//         sort(a,a+n);
//         for(int i=1;i<=n;i++)
//             for(int j=1;j<=k;j++) dp[i][j]=INF;
//         for(int i=2;i<=n;i++){
//             for(int j=1;j*2<=i;j++){
//                 dp[i][j]=min(dp[i-1][j],dp[i-2][j-1]+(a[i-1]-a[i-2])*(a[i-1]-a[i-2]));
//             }
//         }
//         printf("%d\n",dp[n][k]);
//     }
//     return 0;
// }

// //D.免费馅饼//下次我一定好好读题 泪目了//
// int a[15][100050];
// int main(){
//     int n,x,t,m,c;
//     while(~scanf("%d",&n),n){
//         m=0;
//         for(int i=0;i<11;i++)
//             for(int k=0;k<100050;k++)a[i][k]=0;
//         while(n--){
//             scanf("%d%d",&x,&t);
//             a[x][t]++;
//             m=max(m,t);
//         }
//         for(int i=m;i>=1;i--){
//             for(int k=0;k<=10;k++){
//                 if(k==0)a[k][i-1]=a[k][i-1]+max(a[k][i],a[k+1][i]);
//                 else a[k][i-1]=a[k][i-1]+max(a[k-1][i],max(a[k][i],a[k+1][i]));
//             }
//         }
//         printf("%d\n",a[5][0]);
//     }
//     return 0;
// }

