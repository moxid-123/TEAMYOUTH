//TEAM YOUTH
#include<stdio.h>
#include<string.h>
#define current 5;
//suppose the patient in the hospital at reception is 5
struct patient
{
    

    char clinic[20];
    char firstname[50];
    char lastname[50];
    int age;
    int ID;
    char address[50];
};
struct emergency
{
    char clinic[20];
};
void medicalstoreandreception(int n,int specifictreatment);
void generalclinic(char clinic[20])
{
    char gd[20];
    printf("please tell your general disease");
    scanf("%s",gd);
    int n;

    if(strcpy(gd,"cough"))
    {
        printf("please dont eat sweet or any sugar things and drink only hotwater\n");
        //input from doctor;
        printf("the no of required medicine is:\n");
        scanf("%d",&n);
        medicalstoreandreception(n,0);    
    }
    else if(strcpy(gd,"virus"))
    {
        printf("eat only home food and healthy food and dont drink coldwater and if possibel wear mask if you go outside\n");
        scanf("%d",&n);
        medicalstoreandreception(n,0);
    }
    else if(strcpy(gd,"coldcough"))
    {
        printf("not drink cold water,cold drinks and drink only hotwater and drink tumeric-milk\n");
        scanf("%d",n);
        medicalstoreandreception(n,0);

    }

    
}

int main()
{
    printf("Welcome to the ND desai Hospital\n");
    int n;
    scanf("%d",&n);
    struct emergency e;
    printf("Enter 1 for emergency and 0 for normal\n");
    scanf("%d",&n);
    switch (n)
    {
    case 1:
        printf("please enter clicnic in form of General-clinic,Heart-clinic,\n");
        scanf("%s",e.clinic);
        if(e.clinic=="General-clinic")
        {
            generalclinic(e.clinic);
        }
        
        break;
    
    case 0:
        printf("please go in the general queue\n");
        break;
    default:
        printf("Invalid number\n");
        
    }

    return 0;
}

void medicalstoreandreception(int n,int specifictreatment)
{
   int cost=20*n;
   printf("the total cost of medicine is %d\n",cost);
   int Case=100;
   printf("the total cost of medicine and case of patient is %d\n",Case+cost+specifictreatment);

}
