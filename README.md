# -codeblocks-gmp-
在codeblocks安装gmp大整数库的方法
====
下载gmp压缩包，并解压
-------
与codeblocks链接
--------

  1.在codeblocks中Settings->Link settings 的link libraries中添加gmp相关.a类型库文件。这些文件都放在lib文件夹下<br>
  
  2.Settings->Search directories->Compiler 添加include目录，解压后的gmp文件夹里面有include目录<br>
  
  3.Settings->Search directories->Linker 添加lib目录，解压后的gmp文件夹里面有lib目录<br>
  
测试---------代码如下
```
#include <iostream>
#include <cstdlib>
#include <math.h>
#include <fstream>
#include <gmpxx.h>
#include <gmp.h>
using namespace std;
int main(void)
{
	mpz_t dataout, base;
	mpz_inits(dataout,base,NULL);
	int n = 223;
	mpz_set_str(base,"2",10);
	mpz_pow_ui(dataout,base,n);
	mpz_sub_ui(dataout,dataout,1);
	mpz_out_str(stdout,10,dataout);
	cout<<endl;
	system("pause");
	return 0;
 }
```

Ps.
[附gmp官方文档](https://gmplib.org/gmp-man-6.1.2.pdf)
  
