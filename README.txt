#include<iostream>
#include<cstring>
using namespace std;
void gui()//界面
{
	cout << "====================================\n" << endl;
	cout << "\t欢迎使用密码管理系统\n" << endl;
	cout << "====================================" << endl;
}
void encryption()//加密(用户输入一个字符串，系统根据规则对字符串进行加密：)
{
	int i,len;
	char x;
	char Num[16],M[16];
	cout << "请输入要加密的数字密码：";
	cin >> Num;
	for (i = 0; i < strlen(Num); i++) {//将每个字符的ASCII码加上它在字符串中的位置(1开始)和偏移值3
		M[i] = Num[i]+3+i+1;
	}
	len = strlen(Num) -1;
	cout << len;
	x = M[0];						//将字符串的第一位和最后一位调换顺序
	M[0] = M[len];
	M[len] = x;
	cout << "加密后的结果是：";
	for (i = len; i >=0; i--) {		//将字符串反转
		cout << M[i] ;
	}
	cout << endl;
}
void decrypt()//解密（用户输入一个字符串，按照上述规则字符串进行解密）
{
	int i,len;
	char x;
	char Num[15], M[15];
	cout << "请输入要解密的数字密码：";
	cin >> Num;
	len = strlen(Num) - 1;
	x = Num[0];					//先把第一个数和最后一个数做调换
	Num[0] = Num[len];
	Num[len] = x;
	for (i = len; i >= 0; i--) {	//做ASCll码换字母
		M[i] = Num[i] - 3-(len+1-i);
	}
	cout << "解密后的结果是：";
	for (i = len; i >=0; i--) {		//反着输出
		cout << M[i];
	}
	cout << endl;
}
int main()
{
	gui();
	int a;
	while (1) {							//使用循环，让用户选择所要进行操作
		cout << "\t请选择操作：" << endl;
		cout << "1.加密" << endl;
		cout << "2.解密" << endl;
		cout << "3.判断密码强度" << endl;
		cout << "4.密码生成" << endl;
		cout << "5.退出" << endl;
		cout << "请输入选择序号：";
		cin >> a;
		switch (a) {
		case 1:encryption(); break;
		case 2:decrypt(); break;
		case 5:break;
		}
		if (a == 5) {
			break;
		}
	}

	return 0;
}