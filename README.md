# memcpy-
#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>

int main(void)
{
	int i = 5, j = 0;
	char buff[10];

	memcpy(&j, &i, 4); // &j는 복사될 버퍼 주소, &i는 복사할 버퍼 주소, 4는 복사할 총 바이트 수

	printf("%d, %d \n", i, j);

	i = 100;
	j = 200;

	memcpy(buff + 0, &i, 4);
	memcpy(buff + 4, &j, 4);

	memcpy(&i, buff + 4, 4);
	memcpy(&j, buff + 0, 4);

	printf("%d, %d \n", i, j);


	return 0;
}

===============================================================================================================================================================================

#include <stdio.h>
#include <string.h>

int main(void)
{
	int ret;
	char buff1[] = { 'a', 'b', 'c', 'd' };
	char buff2[] = { 'a', 'b', 'c', 'D' };

	ret = strcmp(buff1, buff2);

	if (ret == 0)
	{
		puts("두 문자열이 같습니다");
	}

	ret = memcpy(buff1, buff2, sizeof(buff1));

	if (ret == 0)
	{
		puts("두 버퍼가 같습니다");
	}

	else
	{
		puts("두 버퍼가 다릅니다");
	}

	return 0;
}




