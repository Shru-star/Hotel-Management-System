# didactic-sniffle
#include<iostream>
#include<conio.h>
#include<string.h>
using namespace std;

class hotel
{
protected:
  char name[10];
  char location[10];
  int rating;

public:
int price;
void in()
{
cout<<"\n Enter Hotel Name : ";
cin>>name;
cout<<"\n Enter location   : ";
cin>>location;
cout<<"\n Enter Rating     : ";
cin>>rating;
cout<<"\n Enter 1 room pri : ";
cin>>price;
}
};

class user1: virtual public hotel
{
protected:
  char uname[10];
  int u_id;

public:
int room_no;
void in1(){
cout<<"\n Enter User Name : ";
cin>>uname;
cout<<"\n Enter User ID   : ";
cin>>u_id;
cout<<"\n";
cout<<" Enter N_of_rooms  : ";
cin>>room_no;
}

void out(){
cout <<"\n ***** USER BOOKING DATA *****";
cout <<"\n User Name    : "<<uname;
cout <<"\n User ID      : "<<u_id;
cout <<"\n Room No.     : "<<room_no;

cout <<"\n \n ***** Hotel Information *****";
cout <<"\n Hotel Name   : "<<name;
cout <<"\n Location     : "<<location;
cout <<"\n Rating       : "<<rating;
cout <<"\n 1RoomPrice   : "<<price;
}

inline int Tprice(int x,int y){
return(x*y);
}
};

class vip_user: public user1
{
protected:
int position;
int vip;
public:
void ex_faci()
{
cout<<"\n Enter you are VIP user? \n Press Yes=1/No=0";
cin>>vip;
if(1==vip){
cout<<"\n Congrats you will get VIP facilities";
}
else{
cout<<"\n You are not VIP :)";
}
}
};

int main()
{
vip_user u[50];
int n,i;
clrscr();
cout<<"Enter No. of user";
cin>>n;
for(i=0; i<n; i++)
{
cout<<"\nEnter "<<i+1<<"'s information \n";
u[i].in();
u[i].in1();
u[i].out();
cout<<"\n \n Total Price : "<<u[i].Tprice(u[i].room_no,u[i].price)<<"\n";
u[i].ex_faci();
}
return 0;
}

    
