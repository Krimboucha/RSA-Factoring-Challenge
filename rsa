#include <stdio.h>

/**
 * _atoi - converts a string to an integer.
 * @s: pointer to char
 *
 * Return: int
 */
int _atoi(char *s)
{
	unsigned int num;
	int sign;
	int i;

	num = 0;
	sign = 1;
	i = 0;

	while (s[i])
	{
		if (s[i] == '-')
		{
			sign *= -1;
		}
		if ((s[i] >= '0') && (s[i] <= '9'))
		{
			num *= 10;
			num += (s[i] - '0');
		}
		else
		{
			if (num)
			{
				break;
			}
		}
		i++;
	}
	num *= sign;
	return (num);
}
int main(int argc, char *argv[])
{
	if (argc != 2)
	{
		printf("Usage: %s <file>\n", argv[0]);
		return (1);
	}
	FILE *file = fopen(argv[1], "r");
	if (file == NULL)
	{
		printf("Error opening file.\n");
		return (1);
	}
	char line[25];
	while (fgets(line, sizeof(line), file))
	{
		int num = _atoi(line);

		if (num <= 1)
			printf("%d has no valid factorization.\n", num);
		else
		{
			int p = 2;
			while (p * p <= num)
			{
			if (num % p == 0)
			{
				int q = num / p;
				printf("%d=%d*%d\n", num, p, q);
				break;
				}
				p++;
			}
		}
	}
	fclose(file);
	return (0);
}
