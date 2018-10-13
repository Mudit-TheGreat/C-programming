# C-programming
In this repository I will be talking about C language.


#include<conio.h>

#include<stdio.h>

int list();

void deposit();

void withdraw();

void transfer();

void cd();

void last();

void loan();

int TotAmt=2000,AmtD,AmtW,AmtT,TotDip=0,TotWd=0,TotTrans=0,AmtL,TotLoan=0;

int acc;

char name[50];

void main()
{
    printf("Enter ur NAME\n");
    scanf("%s",&name);
    printf("Enter ur account no.\n");
    scanf("%d",&acc);
    system("cls");
    printf("\n \n \tHello %s \n\t we welcomes u in ur own bank.\n\t THIS BANK WORKS ON A LOCAL SERVER,\n\tSO FOR ANY INCONVENIENCE CAUSED, WE ARE SORRY.",name);
    printf("\n \n \n\t Rs. 2000 has been diposited to ur account,as a GIFT");
    getch();
    while(1)
    {
        system("cls");
    switch(list())
    {
    case 1:
        deposit();
        TotDip+=AmtD;
        break;
    case 2:
        withdraw();
        if(AmtW<TotAmt)
        {
        TotWd+=AmtW;
        }
        break;
    case 3:
        transfer();
        if(AmtT<TotAmt)
        {
            TotTrans+=AmtT;
        }
        break;
    case 4:
         loan();
        if(AmtL<5*TotAmt)
        {
            TotLoan+=AmtL;
        }
        break;
    case 5:
       cd();
        break;
    case 6:
        system("cls");
        last();
        printf("\n Press anykey");
        getch();
        exit(0);
        break;
    default:
        printf("Please enter correct value");
    }
     getch();
    }
}

int list()
{
    int ch;
    printf("\n1. deposit");
    printf("\n2. Withdraw");
    printf("\n3. Transfer");
    printf("\n4. Loan");
    printf("\n5. Check Details");
    printf("\n6. Exit");
    printf("\nChoose your option\n");
    scanf("%d",&ch);
    return(ch);
}

void deposit()
{
    printf("\nEnter the amt u want to DEPOSIT\n");
    scanf("%d",&AmtD);
    TotAmt+=AmtD;
    printf("\n \tYour total amt is now %d",TotAmt);
}
void withdraw()
{
    printf("Enter the amount u wan to WITHDRAW\n");
    scanf("%d",&AmtW);
  if(AmtW<TotAmt)
  {
    TotAmt-=AmtW;
    printf("\n \tYour total amt is now %d",TotAmt);
     }
  else
    {
    printf("\n \t re-enter withdrawal amount");
    }
}
void transfer()
{
printf("Enter the amount you want to TRANSFER\n");
scanf("%d",&AmtT);
if(AmtT<TotAmt)
{
    TotAmt-=AmtT;
    printf("\n \tYour total amt is now %d",TotAmt);
}
else
{
    printf("less amount in ur account\n");
}
}
void cd()
{
    printf("\n \t \tTotal Amount\t %d",TotAmt);
    printf("\n \t \tTotal Withdraw\t %d",TotWd);
    printf("\n \t \tTotal Deposit\t %d",TotDip);
    printf("\n \t \tTotal Transfer\t %d",TotTrans);
    printf("\n \t \tTotal Loan Taken\t %d",TotLoan);
}
void last()
{
    printf("\n \t name: %s",name);
    printf("\n \t account no.: %d",acc);
    printf("\n \t Total Amount %d",TotAmt);
    printf("\n \t Total Withdraw %d",TotWd);
    printf("\n \t Total Deposit %d",TotDip);
    printf("\n \t Total Transfer %d",TotTrans);
    printf("\n \t \tTotal Loan Taken\t %d",TotLoan);
}
void loan()
{
    printf("Please enter the amount you want.\n");
    scanf("%d",AmtL);
    if(AmtL<5*TotAmt)
    {
     TotAmt+=AmtL;
     printf("\nCONGRATULATIONS your loan has been senctioned.");

    }
    else
    {
        printf("SORRY \n\t You are not eligible for this much amount of loan\n\n\t\t Please try entering some less amount!!");
    }
}
