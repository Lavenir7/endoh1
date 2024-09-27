# endoh1
[IOCCC-2012-endoh1](https://github.com/ioccc-src/temp-test-ioccc/tree/master/2012/endoh1)

    ,___. ,.       ,.    ,.   ,___. ,.              ,.       ,.
    |/--' ||       `'    ||   |/--' `'              ||       |\_.
    |\__. || ,. ,. ,. ,__/|   |\__. ,. ,____. ,. ,. ||  ,_.  |/-'  ,_.  ,__.
    |/--' || || || || |/-\|   `--\| || |/\/\| || || || ,/-\. ||   ,/-\. |/-\.
    ||    || `\_/| || |\_/|   ,__/| || |||||| `\_/| || `\_/\.`\_. `\_/' || `'
    `'    `'  `--' `' `---'   `---' `' `'`'`'  `--' `'  `-'`' `-'  `-'  `'

## 文件说明
文件|说明
:-:|:-:
[endoh1.c](https://github.com/Lavenir7/endoh1/blob/main/code/endoh1.c)|源码
[endoh1_color.c](https://github.com/Lavenir7/endoh1/blob/main/code/endoh1_color.c)|源码（对密度进行色彩模拟）
[endoh1.alt.c](https://github.com/Lavenir7/endoh1/blob/main/code/endoh1.alt.c)|备选源码
[endoh1_color.alt.c](https://github.com/Lavenir7/endoh1/blob/main/code/endoh1_color.alt.c)|备选源码
[*.txt](https://github.com/Lavenir7/endoh1/blob/main/txt)|各种初始状态的文本

## 运行
### GCC命令（Windows10/11）
```sh
gcc -DG=1 -DP=4 -DV=4 .\code\endoh1.c -o endoh1 -lm
```
gcc版本：Mingw-win64-8.1.0

### 运行（Windows10/11）
```sh
.\endoh1 < .\code\endoh1.c
.\endoh1 < .\txt\logo.txt
```

---  
---  

### GCC命令说明
```sh
gcc -Wall -W -pedantic -D_BSD_SOURCE -std=c99 -DG=1 -DP=4 -DV=8 endoh1.c -o endoh1 -lm
```
命令|说明
:-:|:-:
`-Wall` | 显示所有的警告信息
`-W` | -Wextra简写，显示额外的警告信息，这些警告信息不包含在-Wall中
`-pedantic` | 编译时严格遵循C语言标准
`-D_BSD_SOURCE` | 定义宏_BSD_SOURCE
`-std=c99` | 指定使用C99标准来编译程序
`-DG=1 -DP=4 -DV=8` | 定义宏G,P,V（G:重力，P:压力，V:粘度）
`endoh1.c` | C源文件名称
`-o endoh1` | 指定输出文件名称
`-lm` | 让链接器（linker）链接数学库libm，-l选项用于指定要链接的库，m是数学库libm的简写

---  

## 补充：宏_BSD_SOURCE?
```C
/* asprintf() does not appear on linux without this */
#define _GNU_SOURCE

/* gettimeofday() does not appear on linux without this. */
#define _BSD_SOURCE

/* modern glibc will complain about the above if it doesn't see this. */
#define _DEFAULT_SOURCE
```
