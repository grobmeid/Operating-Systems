# Operating-Systems
This repository is used for referencing. 
Code was created in order to learn about the process of an operating system. 
Owner of code:        Drew Grobmeier
Contact Information:  grobmeid@my.erau.edu
                      602-920-2138
                      
/**************************************************************************************************************************
*Authour:	Drew Grobmeier
*Class:		CS420
*Assignment:	Programming Assignment 1
*
*
*
*********************************************#include directives***********************************************************/
#include <sys/types.h>
#include <stdio.h>
#include <unistd.h>
/*******************************************#define directives*************************************************************/

#define MAX_COUNT 4

/********************************************End of Directives*************************************************************/
/************************************************MAIN**********************************************************************/
main() {
/**************************************************************************************************************************/
int childCount = 0;
int parent = 1; 
pid_t x;
/**************************************************************************************************************************/
for( childCount = 1; (childCount < MAX_COUNT && parent); childCount++) {
	x = fork();
	if ( x == 0 )
	{
		parent = 0;
		printf("	I am child #%d, my pid is %d; my parent's pid is %d\n" , childCount, getpid(), getppid() );
/**************************************************************************************************************************/
	if (childCount == 2)
		{
			execv ("child2Replacement.exe" , NULL);
		}
	}
/**************************************************************************************************************************/
	else if ( x > 0 ) {
		printf("Parent, my pid is %d: Spawned child #%d whose pid is %d \n" , getpid(), childCount, x );
	}

}
}
/***********************************************END OF CODE***************************************************************/
