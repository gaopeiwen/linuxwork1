#include<stdio.h>
 #include<stdlib.h>
 #include<string.h>
 
 int main(void)
       {
  
                char buf[128] = {0};  // 这里要都初始化为0
  
                     FILE *fp = fopen("foo.txt" , "r");
  
          while (0 != fread(buf, 1, 127, fp))   // 这里不能读满，最大只能用127  
          {
               printf("%s",  buf);
               memset(buf, 0, 128);      // 这里每次都要清0
         }
     fclose(fp);
  
      return 0;
  
       }
