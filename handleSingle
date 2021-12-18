#include<stdio.h>

#define MAXLEN 100

int tape[MAXLEN];	/*最大长度100的纸袋*/
//int a;		/*纸带的下标*/
int graph[2][MAXLEN];	/*纸带下面的图，最多两行*/
//int xiabiao;	/*图的下标*/

int handleSingle(int** G, int kuan, int gao, int &xiabiao,int &a)
{
	//显示当前格子正在被处理（拿圈圈上）

	//如果xiabiao已经从图的右边出去了，即到了一行中最后一个元素的右边，结束，return 0
	//否则return 1
	//从右边出去只可能是因为xiabiao++了
	switch (G[xiabiao / kuan][xiabiao % kuan])
	{
	case 0:	/*向右移动*/
		xiabiao++;
		if (xiabiao % kuan == 0)
			return 0;
		break;
	case 1:	/*向上移动*/
		xiabiao -= kuan;
		break;
	case 2:	/*向下移动*/
		xiabiao += kuan;
		break;
	case 3:	/*向左移动*/
		xiabiao--;
		break;
	case 4:	/*把数字0写到纸带*/
		tape[a++] = 0;
		//修改纸带打印出来的数字
		xiabiao++;	/*默认向右*/
		if (xiabiao % kuan == 0)
			return 0;
		break;
	case 5:	/*把数字1写到纸带*/
		tape[a++] = 1;
		//修改纸带打印出来的数字
		xiabiao++;
		if (xiabiao % kuan == 0)
			return 0;
		break;
	}
	//上一步没有return就说明没有结束，return 1
	return 1;
}
