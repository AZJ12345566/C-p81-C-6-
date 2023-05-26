# C-p81-C-6-
C语言学习笔记 p81 C语言预处理（6）
#include<stdio.h>
#include<stddef.h>
strtuct S
{
      char c1;//0
      int a;//4-7
      char c2;//8
};

//宏求偏移量
#define OFFSETOF(struct_name,member_name) (int)&(((struct_name*)0)->member_name)
int main()
{
      struct S s;
      printf("%d\n",OFFSETOF(struct S s,c1);
      printf("%d\n",OFFSETOF(struct S s,a);
      printf("%d\n",OFFSETOF(struct S s,c2);
      return 0;
}

联合体
union Un
{
      short s[7];//14
      int n;//4
};//联合体的变量共用空间
int main()
{
      printf("%d\n",sizeof(union Un);
      return 0;
}//输出为16



int main()
{
      union
      {
              short k;//2
              char i[2];//2
      }*s=a;
      s=&a;
      s->i[0]=0x39;
      s->i[1]=0x38;
      printf("%x\n",a.k);
      return 0;
}

int  main()
{
      int arr[]={1,2,3,4,5,1,2,3};
      int sz=sizeof(arr)/sizeof(arr[0]);
      int i=0;
      int ret=0;
      for(i=0;i<sz;i++)
      {
            ret^=arr[i];//ret得到的结果是两个“单身”
      }
      
      //分离
      int m=0;
      for(i=0;i<32;i++)//一个整形在二进制里有32个比特位，故需要遍历32个位置，但找到一个1之后就无需在找了
      {
            if(((ret>>i)&1)==1)
            {
                  m=i;//m的位置为1，由于ret的m的位置为1，而ret是有两个不同的数字按位异或得到的，所以这两个数字的m的位置的值一定不同
                  break;
            }
      }
      int x=0;
      int y=0;
      for(i=0;i<sz;i++)
      {
            if(((arr[i]>>m)&1)==1)
            {
                  x^=arr[i];//由于x是0，不影响结果，得到的结果是其中一个“单身狗”
            }
            else
            {
                  y^=arr[i];//得到的结果是另一个“单身狗”
            }
      }
      printf("x=%d,y=%d"x,y);
      return 0;
}






