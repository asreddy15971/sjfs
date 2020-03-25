#include<stdio.h>
#include<conio.h>
int main()
{
  long int n,i=0,j=0,k = 1;
  double priority[n],avg_wt,avg_tat, b_time = 0,bt[n],at[n],wt[n],tat[n], p[n], temp, ct[n],min,sum=0,sum2=0,wt_final,tat_final, wt_avg,tat_avg;
  printf("Enter Number of Processes : ");
  scanf("%ld",&n ); 
  
  for(i=0;i<n;i++)
  {
    printf("\n Burst Time [%d] : ", i+1 );
    scanf("%lf", &bt[i]);
    printf("Arrival Time  [%d] : ", i+1 );
    scanf("%lf", &at[i] );
    p[i]=i+1;
  }
 


  printf("\n\n\t\t\t-------- Sorting Processes according to Arrivaltime --------\n");
  for(i=0;i<n;i++)
  {
    for(j=0;j<n;j++)
    {
      if(at[i]<at[j])
      {
        
        temp = bt[j];
        bt[j] = bt[i];
        bt[i] = temp;
	
	      temp = p[j];
        p[j] = p[i];
        p[i] = temp;

	      temp = at[j];
        at[j] = at[i];
        at[i] = temp;
      
      }
    }
  }
  

  printf("\t\t\t| Process | Arrival Time | Burst Time |\n");
  
  for(i=0;i<n;i++)
  {
    printf("\t\t\t|  P[%0.0lf]   |       %0.0lf      |     %0.0lf      |\n",p[i],at[i],bt[i]);
  }
   printf("\t\t\t---------------------------------------\n");
  
  for(j=0;j<n;j++)
  {
    b_time = b_time + bt[j];
    min = bt[k];

    for(i=k;i<n;i++)
    {
      if((b_time >= at[i])&&(bt[i]<min))
      {
        temp = bt[k];
        bt[k] = bt[i];
        bt[i] = temp;

        temp = at[k];
        at[k] = at[i];
        at[i] = temp;

        temp = p[k];
        p[k] = p[i];
        p[i] = temp;
      }
    }
    k++;
  }
  wt[0] = 0;
  for(i=1;i<n;i++)
  {
    sum += bt[i-1];
    wt[i] = sum - at[i];
    wt_final += wt[i]; 
  }
  wt_avg = wt_final/n;
  for(i=0;i<n;i++)
  {
    sum2 += bt[i];
    tat[i] = sum2 - at[i];
    tat_final += tat[i];
  }
  tat_avg=tat_final/n;

  printf("\t\t\t| Process | Arrival Time | Burst Time |  Waiting Time  |  Turn Around Time  |\n");
  for(i=0;i<n;i++)
  {
    printf("\t\t\t|  P[%0.0lf]   |       %0.0lf      |     %0.0lf      |        %0.0lf       |         %0.0lf          |\n",p[i],at[i],bt[i],tat[i]);
  }
    
  
  ct[0] = bt[0];
  for(i=1;i<n;i++)
  {
    ct[i] = ct[i-1] + bt[i];
  }

  for(i=0;i<n;i++)
  {
    priority[i] = 1+wt[i]/ct[i];
    printf("%lf\n",priority[i]);
  }
   printf("\t\t\t-----------------------------------------------------------------------------\n");

  printf("\t\t\t| Process | Arrival Time | Burst Time |  Waiting Time  |  Turn Around Time  |\n");
  printf("\t\t\t|  P[%0.0lf]   |       %0.0lf      |     %0.0lf      |        %0.0lf       |         %0.0lf          |\n",p[i],at[i],bt[i],tat[i]);
  for(i=n-1;i>0;i--)
  {
    printf("\t\t\t|  P[%0.0lf]   |       %0.0lf      |     %0.0lf      |        %0.0lf       |         %0.0lf          |\n",p[i],at[i],bt[i],tat[i]);
  }

  printf("\n\n\n\t\t\tAverage Turn Around Time : %lf",tat_avg);
  printf("\n\t\t\tAverage Waiting Time     : %lf\n\n",wt_avg);
	
  getch();
  return 0;
}
