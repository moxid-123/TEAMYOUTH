//TEAM YOUTH
#include<stdio.h>
#include<string.h>
#include<stdlib.h>
struct patient
{
    char clinic[20];
    char firstname[50];
    char lastname[50];
    int age;
    int ID;
    char address[100];
    struct patient*next;
};
struct emergency
{
    char clinic[20];
};
void medicalstoreandreception(int n,int c,int specifictreatment);
void generalclinic()
{
    int temp;
    printf("please enter 1 for first time and 0 for more than first time\n");
    scanf("%d",&temp);
    char gd[20];
    printf("please tell your general disease like virus cough and coldcough\n");
    scanf("%s",gd);
    int n;
    if(strcmp(gd,"cough")==0)
    {
        printf("please dont eat sweet or any sugar things and drink only hotwater\n");
        //input from doctor;
        printf("the no of required medicine is(from doctor):\n");
        scanf("%d",&n);
        if(temp==1)
        {
                medicalstoreandreception(n,temp,0);    
        }
        else 
        {
            medicalstoreandreception(n,temp,0);
        }
    }
    else if(strcmp(gd,"virus")==0)
    {
        printf("eat only home food and healthy food and dont drink coldwater and if possibel wear mask if you go outside\n");
        printf("the no of required medicine is (input from doctor):\n");
        scanf("%d",&n);
        if(temp==1)
        {
                medicalstoreandreception(n,temp,0);    
        }
        else 
        {
            medicalstoreandreception(n,temp,0);
        }
    }
    else if(strcmp(gd,"coldcough")==0)
    {
        printf("not drink cold water,cold drinks and drink only hotwater and drink tumeric-milk\n");
        printf("the no of required medicine is (input from doctor):\n");
        scanf("%d",&n);
         if(temp==1)
        {
                medicalstoreandreception(n,temp,0);    
        }
        else 
        {
            medicalstoreandreception(n,temp,0);
        }
    }

    
}
void Heartclinic()
{
    int temp;
    printf("please enter 1 for first time and 0 for more than first time\n");
    scanf("%d",&temp);
    char p[100];
    printf("Kindly tell your problem regarding to heart\n");
    scanf("%s",p);
    int ec=1000;
    printf("Heart treatment:- %d\n",ec);
    int n;
    printf("the no of required medicine is(from doctor) and heartpump of 1000:\n");
    scanf("%d",&n);
    if(temp==1)
        {
                medicalstoreandreception(n,temp,1000);    
        }
        else 
        {
            medicalstoreandreception(n,temp,1000);
        }
}
void Lungsclinic()
{
    int temp;
    printf("please enter 1 for first time and 0 for more than first time\n");
    scanf("%d",&temp);
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
        if(temp==1)
        {
                    medicalstoreandreception(3,temp,5000);

        }
        else 
        {
                    medicalstoreandreception(3,temp,5000);
        }
        break;
    case 0:
        printf("use inhaler of 20 and 3 medicines of 20 and mask therapy of thousand\n");
        if(temp==1)
        {
        medicalstoreandreception(4,temp,1000);
        }
        else 
        {
        medicalstoreandreception(4,temp,1000);
        }
        break;
    default:
        printf("invalid number");
        goto again;
        break;
    }

}
void cardioclinic()
{
    int temp;
    printf("please enter 1 for first time and 0 for more than first time\n");
    scanf("%d",&temp);
    char p[100];
    printf("Kindly tell your problem regarding to which cardio part you are suffered\n");
    scanf("%s",p);
    int operation;
    printf("for doctor 1 for operation and 0 for normal treatments:\n");
    again : scanf("%d",&operation);// input of doctor for operation 1 for not operation is 0
    switch (operation)
    {
    case 1:
    if(temp==1)
        {
         printf("operation of cost 7000 3 medicines of 20 rupees daily after breakfast,lunch and dinner and 50 rupees of relief spray \n");
         medicalstoreandreception(3,temp,7000);
        }
        else 
        {
         printf("operation of cost 7000 3 medicines of 20 rupees daily after breakfast,lunch and dinner and 50 rupees of relief spray \n");
         medicalstoreandreception(3,temp,7000);
        }
        
        break;
    case 0:
        if(temp==1)
        {
         printf("2 medicines of 20 and cardio exercise of one month for 500\n");
         medicalstoreandreception(2,temp,500);
        }
        else 
        {
         printf("2 medicines of 20 and cardio exercise of one month for 500\n");
         medicalstoreandreception(2,temp,500);
        }
        
        break;
    default:
        printf("invalid number");
        goto again;
        break;
    }

}
void get_patient_data_treat(struct patient*ptr)
{
    while(ptr!=NULL)
    {
        scanf("%s %s %s %d %d %s",(ptr->clinic),(ptr->firstname),(ptr->lastname),&(ptr->age),&(ptr->ID),(ptr->address));
         if(strcmp(ptr->clinic,"General-clinic")==0)
        {
            generalclinic();
        }
        else if(strcmp(ptr->clinic,"Heart-clinic")==0)
        {
            Heartclinic();
        }
        else if(strcmp(ptr->clinic,"lungs-clinic")==0)
        {
            Lungsclinic();
        }
        else if(strcmp(ptr->clinic,"Cardio-clinic")==0)
        {
            cardioclinic();
        }
        else
        {
            printf("Sorry we don't have these clinic in our hospital\n");
        } 
        ptr=ptr->next;
    }
}
struct patient * insertAtEnd(struct patient *head){
    struct patient * ptr = (struct patient *) malloc(sizeof(struct patient));
    struct patient * p = head;
 
    while(p->next!=NULL){
        p = p->next;
    }
    p->next = ptr;
    ptr->next = NULL;
    return head;
}
void search(struct patient *ptr,int number)
{
   struct patient *current=ptr;
   while(current!=NULL)
   {
    if(current->ID==number)
    {
        if(strcmp(current->clinic,"General-clinic")==0)
        {
            generalclinic();
            return;
        }
        else if(strcmp(current->clinic,"Heart-clinic")==0)
        {
            Heartclinic();
            return;
        }
        else if(strcmp(current->clinic,"lungs-clinic")==0)
        {
            Lungsclinic();
            return;
        }
        else if(strcmp(current->clinic,"Cardio-clinic")==0)
        {
            cardioclinic();
            return;
        }
    }
    else
    {
        printf("No data found");
        return;
    }
    current=current->next;
   }
}
void get_data(struct patient *ptr)
{
    printf("Enter Name,Age,Mobile No and address");
    scanf("%s %s %d %d %s",(ptr->firstname),(ptr->lastname),&(ptr->age),&(ptr->ID),(ptr->address));
}
void tosee_patients(struct patient *ptr,int number)
{
    while(ptr!=NULL)
    {
        if(ptr->ID==number)
        {
            printf("Goto %s\n",ptr->clinic);
            return ;
        }
        ptr=ptr->next;
    }
    printf("patient is not in hospital it is discharge\n");
}
int main()
{
    printf("Welcome to the ND desai Hospital\n");
    struct emergency e;
    struct patient *head;
    head=(struct patient *)malloc(sizeof(struct patient));
    int i;
    int number;
    int n,t;
    label :printf("Enter 1 for emergency and 0 for normal and 2 for existing patient and 3 for exit\n");
    scanf("%d",&n);
    switch (n)
    {
    case 1:
        printf("please enter clinic in form of General-clinic,Heart-clinic,lungs-clinic and Cardio-clinic\n");
        scanf("%s",e.clinic);
        if(strcmp(head->clinic,"General-clinic")==0)
        {
            generalclinic();
            strcpy(head->clinic,e.clinic);
            printf("Please fill the form details for Entry in Hospital\n");
            get_data(head);
        }
        else if(strcmp(head->clinic,"Heart-clinic")==0)
        {
            Heartclinic();
            strcpy(head->clinic,e.clinic);
            printf("Please fill the form details for Entry in Hospital\n");
            get_data(head);
        }
        else if(strcmp(head->clinic,"lungs-clinic")==0)
        {
            Lungsclinic();
            strcpy(head->clinic,e.clinic);
            printf("Please fill the form details for Entry in Hospital\n");
            get_data(head);
        }
        else if(strcmp(head->clinic,"Cardio-clinic")==0)
        {
            cardioclinic();
            strcpy(head->clinic,e.clinic);
            printf("Please fill the form details for Entry in Hospital \n");
            get_data(head);
        }
        else
        {
            printf("Sorry we don't have these clinic in our hospital\n");
        }
        
        break;
    
    case 0:
        printf("please go in the general queue\n");
        printf("Please fill the form of Hospital in block-letters only Clinic Name Age Mobile.No Address\n");
        insertAtEnd(head);
        get_patient_data_treat(head);
        break;
    case 2:
        printf("for treatment press 1 or to see patients see press any other.\n");
        scanf("%d",&t);
        if(t==1)
        {
        printf("Please tell your ID\n");
        scanf("%d",&number);
        search(head,number);
        }
        else
        {
           printf("Please tell ID number of patients you are here to see\n");
           scanf("%d",&number);
           tosee_patients(head,number);
        }
        break;
    case 3:
        printf("Bye have a nice day\n");
        exit(1);
        break;
    default:
        printf("Invalid number\n");
    }
    goto label;
    return 0;
}

void medicalstoreandreception(int n,int c,int specifictreatment)
{
   int cost=20*n;
   printf("the total cost of medicine is %d\n",cost);
   int Case;
   if(c==1)
   {
       Case=100;
        printf("the total cost of medicine and case of patient is %d\n",Case+cost+specifictreatment);
   }
   else
   {
        Case=0;
        printf("the total cost of medicine and case of patient is %d\n",Case+cost+specifictreatment);
   }
}
