#include <stdio.h>
#include <stdlib.h>

typedef int sort_t;

void heap_down(sort_t* sort_data, int n, int i)
{

    int lchild, rchild, pos, tmp;
    while(1)
    {
        lchild = 2*i+1;//left child
        rchild = 2*i+2;//right child
        pos = i;
        tmp = 0;

            if(lchild > n && rchild > n)
                break;
            if(rchild > n)
            {
                if(sort_data[i] > sort_data[lchild])
                    pos = lchild;
            }
            else
            {
                tmp = sort_data[lchild] > sort_data[rchild] ? rchild : lchild;
                if(sort_data[i] > sort_data[tmp])
                    pos = tmp;
            }
            if(pos != i)
            {
                sort_t swp = sort_data[i];
                sort_data[i] = sort_data[pos];
                sort_data[pos] = swp;
                i = pos;
                continue;
            }
            break;
    }
}

void create_heap(sort_t* sort_data, int n)
{
    int pos = n/2 -1;//first not leaf position
    int i = pos;
    for(;i >= 0;i--)
    {
        heap_down(sort_data, n, i);
    }
}


void heap_sort(sort_t* sort_data, int n)
{
    create_heap(sort_data, n);
    int i = 0;
    for(; i < n-1; i++)
    {
        sort_t swp = sort_data[0];
        sort_data[0] = sort_data[n-i-1];
        sort_data[n-i-1] = swp;
        heap_down(sort_data, n-(i+2), 0);
    }
}
