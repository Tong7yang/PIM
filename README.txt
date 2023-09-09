#include<iostream>
#include<cstring>
using namespace std;
void gui()//界面
{
	cout << "====================================\n" << endl;
	cout << "\t欢迎使用密码管理系统\n" << endl;
	cout << "====================================" << endl;
}
void encryption()//加密
{
	int i;
	char Num[15],M[15];
	cout << "请输入要加密的数字密码：";
	cin >> Num;
	for (i = 0; i < strlen(Num); i++) {
		M[i] = Num[i]+3;
	}
	cout << "加密后的结果是：";
	for (i = 0; i < strlen(Num); i++) {
		cout << M[i] ;
	}
	cout << endl;
}
void decrypt()
{
	int i;
	char Num[15], M[15];
	cout << "请输入要解密的数字密码：";
	cin >> Num;
	for (i = 0; i < strlen(Num); i++) {
		M[i] = Num[i] - 3;
	}
	cout << "解密后的结果是：";
	for (i = 0; i < strlen(Num); i++) {
		cout << M[i];
	}
	cout << endl;
}
int main()
{
	gui();
	int a;
	while (1) {
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