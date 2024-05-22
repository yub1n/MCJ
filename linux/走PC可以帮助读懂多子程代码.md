# 走 PC 可以帮助读懂多子程代码

不用 PC 分析，就会以为只能创建一个子进程。

```c
#include <stdio.h>
#include <unistd.h>

int main(){
    int pid = fork();
    if (pid == 0) {
        printf("I'm child1.\n");
    }
    else {
        pid = fork();
        if (pid == 0) {
            printf("I'm child2.\n");
        } else {
            printf("I'm parent.\n");
        }
    }
    return 0;
}

```

首先，PC 指向第一行代码，创建了第一个子进程，然后父进程和子进程的 PC 同时往下走到第二行，父进程跳到下一个 else，子进程进入 if 代码块，输出，然后退出程序；父进程创建第二个子进程，然后同理跳到 else，输出最后退出；第二个子程序输出后退出。

以上三个输出语句顺序随机。
