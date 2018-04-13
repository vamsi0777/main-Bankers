# main-Bankers
Main function for bankers algo.
int main()
{
	int i, j, sum;
	char ch;
	printf("\nEnter the number of processes and the number of resources:\n");
	scanf("%d%d", &n, &m);
	printf("\nEnter maximum instances of resources\n");
	for (j = 0; j < m; j++)
	{
		scanf("%d", &maxres[j]);
		avail[j] = maxres[j];
	}
	printf("\nEnter the Allocated Matrix:\n");
	for (i = 0; i < n; i++)
	{
		for (j = 0; j < m; j++)
			scanf("%d", &allocation[i][j]);
	}
	printf("\nEnter the Max Matrix:\n");
	for (i = 0; i < n; i++)
	{
		for (j = 0; j < m; j++)
		{
			scanf("%d", &max[i][j]);
			need[i][j] = max[i][j] - allocation[i][j];
		}
	}
	printf("\nMatrix is:\n");
	for (i = 0; i < n; i++)
	{
		for (j = 0; j < m; j++)
			printf("%d ", need[i][j]);
		printf("\n");
	}
	for (j = 0; j < m; j++)
	{
		sum = 0;
		for (i = 0; i < n; i++)
			sum += allocation[i][j];
		avail[j] -= sum;
	}
	iamsafe();
	getch();
}
