# Stone-Paper-Scissors-game
#This is my 2nd project using C graphics,I hope you will enjoy it

/*this is the source code of the game stone paper scissor,try this code on your turbo c++ compiler because this compiler does not support graphics programs,this is made by Shaiv Aghori(Ravi Raj Rajput)*/

#include<stdio.h>
#include<dos.h>
#include<conio.h>
#include<graphics.h>
#include<stdlib.h>
#include<time.h>

int result(char you,int cpu);
void instruction();
void hoot();
void stone();
void paper();
void scissor();

int main()
{
clrscr();
int you,cpu,res;
int gdriver = DETECT,gmode; 
initgraph(&gdriver,&gmode,"C:\\TC\\BGI");
while(1){
instruction();
you=getch();
if(you=='7')
exit(0);
srand(time(NULL));
cpu=rand()%3;

delay(1000);
cleardevice();
hoot();

cleardevice();
res=result(you,cpu);
delay(2000);

cleardevice();
setcolor(RED);
settextstyle(TRIPLEX_FONT,HORIZ_DIR,6);

if(res==0){
outtextxy(150,150," SAME CHOICE");
setcolor(YELLOW);
circle(250,100,40);
setfillstyle(SOLID_FILL,YELLOW);
floodfill(250,100,YELLOW);

setcolor(BLACK);
circle(230,80,4);
circle(270,80,4);
setfillstyle(SOLID_FILL,BLACK);
bar(230,110,270,112);
}
else if(res==1){
outtextxy(150,150,"YOU WIN");
setcolor(YELLOW);
circle(250,100,40);
setfillstyle(SOLID_FILL,YELLOW);
floodfill(250,100,YELLOW);

setcolor(BLACK);
circle(230,80,4);
circle(270,80,4);
arc(250,100,225,315,20);
}
else if(res==-1){
outtextxy(150,150,"YOU LOST");
setcolor(YELLOW);
circle(250,100,40);
setfillstyle(SOLID_FILL,YELLOW);
floodfill(250,100,YELLOW);

setcolor(BLACK);
circle(230,80,4);
circle(270,80,4);
arc(250,140,45,135,20);
}
else{
outtextxy(150,150,"INVALID CHOICE");
setcolor(YELLOW);
circle(250,100,40);
setfillstyle(SOLID_FILL,YELLOW);
floodfill(250,100,YELLOW);

setcolor(BLACK);
line(225,75,235,85);
line(225,85,235,75);

line(265,75,275,85);
line(265,85,275,75);

setfillstyle(SOLID_FILL,BLACK);
bar(230,110,270,112);
}
setcolor(YELLOW);
settextstyle(DEFAULT_FONT,HORIZ_DIR,2);
outtextxy(10,250,"Press any key to go back on main menu");
getch();
cleardevice();
}
return 0;
}


void hoot()
{
setbkcolor(0);
stone();
delay(1000);
cleardevice();
paper();
delay(1000);
cleardevice();
scissor();
delay(1000);
cleardevice();
}

void stone()
{
int i;
setcolor(8);

for(i=0;i<30;i++)
ellipse(100,100,0,180,i,2*i);

setcolor(YELLOW);
settextstyle(DEFAULT_FONT,HORIZ_DIR,2);
outtextxy(70,120,"STONE");
}

void paper()
{
setfillstyle(SOLID_FILL,15);
bar(200,20,250,90);
setcolor(YELLOW);
settextstyle(DEFAULT_FONT,HORIZ_DIR,2);
outtextxy(200,110,"PAPER");
}

void scissor()
{
setcolor(15);
line(300,100,320,120);
line(300,120,320,100);
circle(298,100,2);
circle(298,120,2);
setcolor(YELLOW);
settextstyle(DEFAULT_FONT,HORIZ_DIR,2);
outtextxy(290,140,"SCISSOR");
}

void instruction()
{
setbkcolor(9);
setcolor(YELLOW);
settextstyle(DEFAULT_FONT,HORIZ_DIR,2);
outtextxy(0,5,"~~~~~~~~~~~STONE--PAPER--SCISSOR~~~~~~~~~~~~");
setlinestyle(1,0,3);
line(0,25,650,25);

setcolor(RED);
outtextxy(190,50,"WELCOME TO THE GAME");
setlinestyle(2,0,3);
line(180,70,500,70);

setcolor(13);
outtextxy(190,100,"****INSTRUCTIONS****");
setlinestyle(0,0,3);
line(180,120,520,120);

setcolor(15);
outtextxy(10,150,"a) Press 0 for STONE.");
outtextxy(10,170,"b) Press 1 for PAPER.");
outtextxy(10,190,"c) Press 2 for SCISSOR.");
outtextxy(10,210,"d) Press 7 for EXIT THE GAME.");

setcolor(15);
settextstyle(DEFAULT_FONT,HORIZ_DIR,1);
outtextxy(400,350,"Made by: Ravi Raj Rajput");
outtextxy(450,360,"(Bhakt of Mahakal)");
}

int result(char you,int cpu)
{
setcolor(YELLOW);
settextstyle(DEFAULT_FONT,HORIZ_DIR,2);

if(you=='0'&&cpu==0){
outtextxy(10,150," Your Choice: STONE");
outtextxy(10,180," Cpu Choice: STONE");
return (0);
}

else if(you=='0'&&cpu==1){
outtextxy(10,150," Your Choice: STONE");
outtextxy(10,180," Cpu Choice: PAPER");
return (-1);
}
else if(you=='0'&&cpu==2){
outtextxy(10,150," Your Choice: STONE");
outtextxy(10,180," Cpu Choice: SCISSOR");
return (1);
}

else if(you=='1'&&cpu==0){
outtextxy(10,150," Your Choice: PAPER");
outtextxy(10,180," Cpu Choice: STONE");
return (1);
}
else if(you=='1'&&cpu==1){
outtextxy(10,150," Your Choice: PAPER");
outtextxy(10,180," Cpu Choice: PAPER");
return (0);
}

else if(you=='1'&&cpu==2){
outtextxy(10,150," Your Choice: PAPER");
outtextxy(10,180," Cpu Choice: SCISSOR");
return (-1);
}
else if(you=='2'&&cpu==0){
outtextxy(10,150," Your Choice: SCISSOR");
outtextxy(10,180," Cpu Choice: STONE");
return (-1);
}
else if(you=='2'&&cpu==1){
outtextxy(10,150," Your Choice: SCISSOR");
outtextxy(10,180," Cpu Choice: PAPER");
return (1);
}
else if(you=='2'&&cpu==2){
outtextxy(10,150," Your Choice: SCISSOR");
outtextxy(10,180," Cpu Choice: SCISSOR");
return (0);
}

else{
outtextxy(10,150," Your Choice: INVALID");
outtextxy(10,180," Cpu Choice: DEFAULT");
return (2);
}
}
