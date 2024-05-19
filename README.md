# -
Калькулятор на С++
class Drob {
private:
int chisl;
int znamen;
int NOD(int x, int y)
{
if (y == 0)
return NOD(y, x % y);
}
public:
void input(int c, int z)
{
chisl = c;
znamen = z;
}
void mult(int x)
{
chisl *= x;
cout << "Дробь: " << chisl << '/' << znamen << endl;
}
void div(int x)
{
znamen *= x;
cout << "Дробь: " << chisl << '/' << znamen << endl;
}
void sum(int x)
{
chisl += (x * znamen);
cout << "Дробь: " << chisl << '/' << znamen << endl;
}
void sub(int x)
{
chisl -= (x * znamen);
cout << "Дробь: " << chisl << '/' << znamen << endl;
}
void show()
{
cout << "Текущаяя дробь: " << chisl << '/' << znamen << endl;
}
int peredacha()
{
return NOD(chisl, znamen);
}
void reduct(int x)
{
chisl /= x;
znamen /= x;
}
};
int main() {
setlocale(0, "");
int a, b, m;
char c = 'y';
cout << "Введите числитель:" << endl;
cin >> a;
cout << "Введите знаменатель:" << endl;
cin >> b;
Drob obj;
obj.input(a, b);
do {
obj.reduct(obj.peredacha());
obj.show();
cout << "1:Прибавить к дроби число" << endl;
cout << "2:Отнять от дроби число" << endl;
cout << "3:Умножить дробное число" << endl;
cout << "4:Разделить дробь на число" << endl;
cout << "Выберите действие" << '\n';
cin >> m;
switch (m)
{
case 1:
cout << "Введите слагаемое" << endl;
cin >> a;
obj.sum(a);
break;
case 2:
cout << "Введите вычитаемое" << endl;
cin >> a;
obj.sub(a);
break;
case 3:
cout << "Введите множитель" << endl;
cin >> a;
obj.mult(a);
break;
case 4:
cout << "Введите делитель" << endl;
cin >> a;
obj.div(a);
break;
default:
cout << "Введите правильно" << endl;
}
cout << "Продолжить работу?(y/n)" << endl;
cin >> c;
} while (c != 'n');
return 0;
}
