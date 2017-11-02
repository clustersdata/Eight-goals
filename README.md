# -Eight-goals

 Eight goals
 
Problem Description

8球是一种台球竞赛的规则。台面上有7个红球、7个黄球以及一个黑球，当然还有一个白球。对于本题，我们使用如下的简化规则：红、黄两名选手轮流用白球击打各自颜色的球，如果将该颜色的7个球全部打进，则这名选手可以打黑球，如果打进则算他胜。如果在打进自己颜色的所有球之前就把黑球打进，则算输。如果选手不慎打进了对手的球，入球依然有效。

现在给出打进的球（白球除外）的顺序，以及黑球由哪方打进，你的任务是判定哪方是胜者。

假设不会有一杆同时打进一颗黑球和其他彩球。



Input

输入包含多组数据。每组数据第一行是一个整数N(1<=N<=15)，表示打进的球的个数，N=0表示结束。随后有一行，包含N个字符，依序表示打进的是何种球。如果是’B’，表示是红方打进的黑球，如果是’L’，表示是黄方打进的黑球。如果是’Y’则表示是黄球，’R’表示红球。字符间没有空格。
所有输入都满足如下条件：最后一颗球打进时这局比赛正好结束，而且打进的红球和黑球都不超过7个。


Output

对每组数据，输出一行。如果红方胜，输出’Red’；黄方胜，输出’Yellow’。

Sample Input

5 RYRRB 9 RRRRYRRRB 0


Sample Output

Yellow Red


代码：

#include <iostream>
 
using namespace std;

char dig[20];

int main()

{

    int n;
    
    while(cin>>n&&n)
    
    {
    
        int sum1=0,sum2=0;
        
        for(int i=0;i<n;i++)
        
          {
          
                cin>>dig[i];
                
                if(dig[i]=='R')   sum1++;
                
                if(dig[i]=='Y')   sum2++;
                
          }
          
          if(sum1<7&&sum2<7&&dig[n-1]=='L'||sum1==7&&sum2<7||sum1==7&&sum2==7&&dig[n-1]=='B')
          
                cout<<"Red"<<endl;
                
          else
          
                cout<<"Yellow"<<endl;
                

    }
    
    return 0;
    
}
