//TEAM YOUTH
#include<stdio.h>
#include<string.h>
#define current 5
//suppose the patient in the hospital at reception is 5
struct patient
{
    

    char clinic[20];
    char firstname[50];
    char lastname[50];
    int age;
    int ID;
    char address[100];
};
void data(struct patient p);
struct emergency
{
    char clinic[20];
};
void medicalstoreandreception(int n,int specifictreatment);
void generalclinic()
{
    char gd[20];
    printf("please tell your general disease like virus cough and coldcough");
    scanf("%s",gd);
    int n;

    if(strcmp(gd,"cough")==0)
    {
        printf("please dont eat sweet or any sugar things and drink only hotwater\n");
        //input from doctor;
        printf("the no of required medicine is:\n");
        scanf("%d",&n);
        medicalstoreandreception(n,0);    
    }
    else if(strcmp(gd,"virus")==0)
    {
        printf("eat only home food and healthy food and dont drink coldwater and if possibel wear mask if you go outside\n");
        printf("the no of required medicine is:\n");
        scanf("%d",&n);
        medicalstoreandreception(n,0);
    }
    else if(strcmp(gd,"coldcough")==0)
    {
        printf("not drink cold water,cold drinks and drink only hotwater and drink tumeric-milk\n");
        printf("the no of required medicine is:\n");
        scanf("%d",&n);
        medicalstoreandreception(n,0);

    }

    
}
void Heartclinic()
{
    char p[100];
    printf("Kindly tell your problem regarding to heart\n");
    scanf("%s",p);
        int ec=1000;
    printf(" %d\n",ec);
    int n;
            printf("the no of required medicine is:\n");
    scanf("%d",&n);
    medicalstoreandreception(n,ec);
}
void Lungsclinic()
{
     char p[100];
    printf("Kindly tell your problem regarding to lungs\n");
    scanf("%s",p);
    int operation;
    printf("for doctor 1 for operation and 0 for normal treatments:\n");
    again : scanf("%d",&operation);// input of doctor for operation 1 for not operation is 0
    switch (operation)
    {
    case 1:
        printf("operation of cost 5000 3 medicines of 20 rupees daily after breakfast,lunch and dinner\n");
        medicalstoreandreception(3,5000);
        break;
    case 0:
        printf("use inhaler of 20 and 3 medicines of 20 and mask therapy of thousand\n");
        medicalstoreandreception(4,1000);
        break;
    default:
        printf("invalid number");
        goto again;
        break;
    }

}
void cardioclinic()
{
     char p[100];
    printf("Kindly tell your problem regarding to which cardio part you are suffered\n");
    scanf("%s",p);
    int operation;
       printf("for doctor 1 for operation and 0 for normal treatments:\n");
    again : scanf("%d",&operation);// input of doctor for operation 1 for not operation is 0
    switch (operation)
    {
    case 1:
        printf("operation of cost 7000 3 medicines of 20 rupees daily after breakfast,lunch and dinner and 50 rupees of relief spray \n");
        medicalstoreandreception(3,7000);
        break;
    case 0:
        printf("2 medicines of 20 and cardio exercise of one month for 500\n");
        medicalstoreandreception(2,500);
        break;
    default:
        printf("invalid number");
        goto again;
        break;
    }

}
void printdata(struct  patient p);
int main()
{
    printf("Welcome to the ND desai Hospital\n");
    struct emergency e;
    struct patient p;
    int n;
    printf("Enter 1 for emergency and 0 for normal\n");
    scanf("%d",&n);
    switch (n)
    {
    case 1:
        printf("please enter clinic in form of General-clinic,Heart-clinic,lungs-clinic and Cardio-clinic\n");
        scanf("%s",e.clinic);
        if(strcmp(e.clinic,"General-clinic")==0)
        {
            generalclinic();
            strcpy(p.clinic,e.clinic);
           printf("Please fill the form details\n");
           scanf("%s %s %d %d %s",p.firstname,p.lastname,&p.age,&p.ID,p.address);
             printf("Name:-%s %s \nAge:-%d \nMobileNo:-%d\n Clinic:-%s\n Address:-%s\n",p.firstname,p.lastname,p.ID,p.clinic,p.address);

        }
        else if(strcmp(e.clinic,"Heart-clinic")==0)
        {
            Heartclinic();
            strcpy(p.clinic,e.clinic);
            printf("Please fill the form details\n");
            scanf("%s %s %d %d %s",p.firstname,p.lastname,&p.age,&p.ID,p.address);       
             printf("Name:-%s %s \nAge:-%d \nMobileNo:-%d\n Clinic:-%s\n Address:-%s\n",p.firstname,p.lastname,p.ID,p.clinic,p.address);

        }
        else if(strcmp(e.clinic,"lungs-clinic")==0)
        {
            Lungsclinic();
            strcpy(p.clinic,e.clinic);
            printf("Please fill the form details\n");
            scanf("%s %s %d %d %s",p.firstname,p.lastname,&p.age,&p.ID,p.address);
            printf("Name:-%s %s \nAge:-%d \nMobileNo:-%d\n Clinic:-%s\n Address:-%s\n",p.firstname,p.lastname,p.ID,p.clinic,p.address);

        }
        else if(strcmp(e.clinic,"Cardio-clinic")==0)
        {
            cardioclinic();
            strcpy(p.clinic,e.clinic);
           printf("Please fill the form details\n");
           scanf("%s %s %d %d %s",p.firstname,p.lastname,&p.age,&p.ID,p.address);
            printf("Name:-%s %s \nAge:-%d \nMobileNo:-%d\n Clinic:-%s\n Address:-%s\n",p.firstname,p.lastname,p.ID,p.clinic,p.address);

        }
        else
        {
            printf("Sorry we don't have these clinic in our hospital\n");
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

