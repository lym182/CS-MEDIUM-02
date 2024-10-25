# 2024090914025-李伊眉-CS-05
1.二进制转十进制
![72e83041-6fc4-401f-b2fe-e8dd27338656](https://github.com/user-attachments/assets/307f8919-c8fd-4553-b25b-586c42627466)
![4850f39b-bc13-491d-a558-19ceca471627](https://github.com/user-attachments/assets/2098a750-14d5-4aa2-9a82-0d872553f61c)
![9f447e8a-fd10-41f2-b07d-409815923c6c](https://github.com/user-attachments/assets/36b72ae9-f10c-416f-8292-49f2b2bc289d)
![3d7c8c96-6d1c-4327-b069-1bfb46539014](https://github.com/user-attachments/assets/82664472-6216-408e-a90a-1aadcf547886)
![17aec4cf-b8c4-4fff-b122-56ae6f04e2c3](https://github.com/user-attachments/assets/fa26dee0-809d-4ee0-b5d7-caed265a3d96)
```
#include <stdio.h>
#include <math.h>
#include <string.h>
int main(void)
{
    char number01[20];
    int temp1[20] = {0};
    printf("输入一个二进制数：");
    scanf("%s",number01);
    int length01 = strlen(number01);
    int integar_len01, a;
    double integar_part = 0.0;
    double fractional_part = 0.0;
    for(a = 0; a < length01; a++){
        if(number01 [a] == '.')
        {
            integar_len01 = a;
        }
    }
    for(int i = 0; i < length01; i++)
    {
        if(number01[i] >= '0' && number01[i] <= '9'){
            temp1[i] = number01[i] - '0';
        }
        if(i < integar_len01){
            integar_part += temp1[i] * pow(2, integar_len01 - i - 1);
        }
        else if(i > integar_len01){
            fractional_part += temp1[i] * pow(2, - i + integar_len01);
        }
    }
    printf("%f",integar_part + fractional_part);
    printf("\n");
    return 0;
}
```
2.问题回答
- 计算机对数据的存储是先将十进制转化为二进制，再将二进制转化为十进制，而十进制的 0.1 和 0.2 在二进制下是无限循环小数，所以存储时存储的是近似值，做加法时也是用二进制直接加减得到近似值从而导致精度丢失。
- 用高精度数值计算库或者特定情况下可转为整数计算后再返还为小数。
