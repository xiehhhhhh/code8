# code8
// 快速排序
void QuickSort(int arr[], int start, int end)
{
	if (start >= end)
		return;
	int i = start;
	int j = end;
	// 基准数
	int baseval = arr[start];
	while (i < j)
	{
		// 从右向左找比基准数小的数
		while (i < j && arr[j] >= baseval)
		{
			j--;
		}
		if (i < j)
		{
			arr[i] = arr[j];
			i++;
		}
		// 从左向右找比基准数大的数
		while (i < j && arr[i] < baseval)
		{
			i++;
		}
		if (i < j)
		{
			arr[j] = arr[i];
			j--;
		}
	}
	// 把基准数放到i的位置
	arr[i] = baseval;
	// 递归
	QuickSort(arr, start, i - 1);
	QuickSort(arr, i + 1, end);
}
