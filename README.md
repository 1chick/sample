void part(string _str, vector<int> &_num)
{
	int sum = 0;
	unsigned int i = 0;
	bool isNum = false;

	while (i < _str.length())
	{
		if ('0' <= _str.at(i) && _str.at(i) <= '9')
		{//还原连续的数字
			sum = sum * 10 + (_str.at(i) - '0');
			isNum = true;
		}	
		else
		{
			if(isNum){
				_num.push_back(sum);
				isNum = false;					
			}
				
			sum = 0;
		}
		i++;
	}
	
	//判断最后一个字符是否是数字
	if (isNum)
		_num.push_back(sum);
}
