#include<windows.h>
#include <cstdarg>
#include <GL/glut.h>
#include <GL/glu.h>
#include<gl/glut.h>
#include <iostream>
#include <cstdio>
#include <cstdlib>
#define PI 3.1416;
#include<math.h>

using namespace std;

int y=3;

float translate_x = 0.0;
float translate_y = 0.0;
float translate_z = -30.0;
float translate_x1=0.0;
float translate_y1=0.0;
float translate_z1=-30.0;
float translate_x3=0.0;
float translate_y3=0.0;
float translate_z3=-30.0;


void drawFilledCircle(GLfloat x, GLfloat y, GLfloat radius){
	int i;
	int triangleAmount = 20; //# of triangles used to draw circle

	//GLfloat radius = 0.8f; //radius
	GLfloat twicePi = 2.0f * PI;

	glBegin(GL_TRIANGLE_FAN);
		glVertex2f(x, y); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            x + (radius * cos(i *  twicePi / triangleAmount)),
			    y + (radius * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();
}



void init()
{
glClearColor(0,0,0,0);
glShadeModel(GL_SMOOTH);
glClearDepth(1.0f);
glEnable(GL_DEPTH_TEST);
}




void reset()
{

translate_x = 0.0;
translate_y = 0.0;
translate_z = -30.0;
}

void funcTranslate_xu(void){
    translate_x-=0.5;
    //translate_x3-=0.5;
    translate_x3=-290;
    if(translate_x<=-30){
        translate_x=200;

    }
    glutPostRedisplay();

}
void funcTranslate_xl(void){
    translate_x3+=1.0;
    if(translate_x3>=290){
        translate_x3=-290;
    }
    glutPostRedisplay();

}


void funcTranslate_x(void){

    translate_x+=0.5;
    //translate_x3-=0.5;
    translate_x3=290;
    if(translate_x>=200){
        translate_x=-30;

    }
    glutPostRedisplay();

}

void funcTranslate_x3(void){
    translate_x3-=1.0;
    if(translate_x3<=-250){
        translate_x3=250;
    }
    glutPostRedisplay();
}

void funcTranslate_x2(void){
    translate_x+=0.5;
    //translate_x3-=0.5;
    translate_x3=290;
    if(translate_x>=200){
        translate_x=-30;

    }
    glutPostRedisplay();
}




void funcTranslate_y(void){
    /*translate_y+=0.2;
    if(translate_y>=31){
        translate_y=31;
    }
    glutPostRedisplay();*/
    translate_y=-14;
    translate_x+=0.5;
    //translate_x3-=0.5;
    translate_x3=290;
    translate_y3=14;
    if(translate_x>=200){
        translate_x=-30;

    }
    glutPostRedisplay();
}

void funcTranslate_y31(void){

    translate_y3=-15;
    translate_x3-=1.0;
    if(translate_x3<=-250){
        translate_x3=250;
    }
    glutPostRedisplay();
}


void funcTranslate_y2(void){
    translate_y=0;
    translate_x+=0.5;
    //translate_x3-=0.5;
    translate_y3=0;
    translate_x3=290;
    if(translate_x>=200){
        translate_x=-30;
    }
    glutPostRedisplay();
}

void funcTranslate_y32(void){
    translate_y3=-1;
    translate_x3-=1.0;
    if(translate_x3<=-120){
        translate_x3=250;
    }
    glutPostRedisplay();
}


void reshape(int w,int h)
{
glViewport(0,0, (GLsizei)w,(GLsizei)h);
glMatrixMode(GL_PROJECTION);
glLoadIdentity();
gluPerspective(100.0f, (GLfloat)w/(GLfloat)h, 1.0f, 100.0f);
glMatrixMode(GL_MODELVIEW);
glLoadIdentity();
}





/*

############################################## TRI 1 STARTS () ####################################################

*/

void Tri1(){


    // 1 NO FLYOVER
    glColor3ub(77, 77, 77);
    glBegin(GL_QUAD_STRIP);
    glVertex2i(-30,-20);
    glVertex2i(-20,-20);
    glVertex2i(-21,-18);
    glVertex2i(-11,-18);
    glVertex2i(-12,-16);
    glVertex2i(-2,-16);
    glVertex2i(-3,-14);
    glVertex2i(3,-14);

    glVertex2i(5,-10);
    glVertex2i(10,-10);

    glVertex2i(9,-8);
    glVertex2i(14,-8);

    glVertex2i(13,-6);
    glVertex2i(18,-6);

    glVertex2i(15,-5);
    glVertex2i(20,-5);

    glVertex2i(18,-3);
    glVertex2i(23,-3);

    glVertex2i(19,-2);
    glVertex2i(24,-2);

    glVertex2i(20,-1);
    glVertex2i(25,-1);

    glVertex2i(21,0);
    glVertex2i(26,0);

    glEnd();

    // 1 NO FLYOVER SHESH



    // FLYOVER ER PILAR

    glColor3ub(51, 51, 51);
    glBegin(GL_POLYGON);
    glVertex2i(8,-18);
    glVertex2i(12,-18);
    glVertex2i(12,-16);
    glVertex2i(8,-16);
    glEnd();

    glColor3ub(38, 38, 38);
    glBegin(GL_POLYGON);
    glVertex2i(9,-16);
    glVertex2i(11,-16);
    glVertex2i(11,-8);
    glVertex2i(9,-8);
    glEnd();

    // FLYOVER ER PILAR SHESH




    // 3 NO BAARI

    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(-39,-17+y);
    glVertex2i(-21,-17+y);
    glVertex2i(-21,-11+y);
    glVertex2i(-39,-11+y);
    glEnd();

    glColor3ub(0, 102, 102);
    glBegin(GL_POLYGON);
    glVertex2i(-40,-10+y);
    glVertex2i(-20,-10+y);
    glVertex2i(-16,-7+y);
    glVertex2i(-36,-7+y);
    glEnd();

    glColor3ub(0, 51, 51);
    glBegin(GL_POLYGON);
    glVertex2i(-20,-20+y);
    glVertex2i(-16,-17+y);
    glVertex2i(-16,-7+y);
    glVertex2i(-20,-10+y);
    glEnd();

    glColor3ub(0, 153, 153);
    glBegin(GL_POLYGON);
    glVertex2i(-40,-20+y);
    glVertex2i(-20,-20+y);
    glVertex2i(-20,-10+y);
    glVertex2i(-40,-10+y);
    glEnd();

    // 3 NO BAARI SHESH


    // 4 NO BAARI

    glColor3ub(255, 255, 255);
    glBegin(GL_POLYGON);
    glVertex2i(-9,-19+y);
    glVertex2i(-6,-19+y);
    glVertex2i(-6,-17+y);
    glVertex2i(-9,-17+y);
    glEnd();

    glColor3ub(255, 255, 255);
    glBegin(GL_POLYGON);
    glVertex2i(-4,-19+y);
    glVertex2i(-1,-19+y);
    glVertex2i(-1,-17+y);
    glVertex2i(-4,-17+y);
    glEnd();

    glColor3ub(255, 255, 255);
    glBegin(GL_POLYGON);
    glVertex2i(-9,-16+y);
    glVertex2i(-6,-16+y);
    glVertex2i(-6,-14+y);
    glVertex2i(-9,-14+y);
    glEnd();

    glColor3ub(255, 255, 255);
    glBegin(GL_POLYGON);
    glVertex2i(-4,-16+y);
    glVertex2i(-1,-16+y);
    glVertex2i(-1,-14+y);
    glVertex2i(-4,-14+y);
    glEnd();

    glColor3ub(255, 255, 255);
    glBegin(GL_POLYGON);
    glVertex2i(-9,-13+y);
    glVertex2i(-6,-13+y);
    glVertex2i(-6,-11+y);
    glVertex2i(-9,-11+y);
    glEnd();

    glColor3ub(255, 255, 255);
    glBegin(GL_POLYGON);
    glVertex2i(-4,-13+y);
    glVertex2i(-1,-13+y);
    glVertex2i(-1,-11+y);
    glVertex2i(-4,-11+y);
    glEnd();

    glColor3ub(255, 255, 255);
    glBegin(GL_POLYGON);
    glVertex2i(-9,-10+y);
    glVertex2i(-6,-10+y);
    glVertex2i(-6,-8+y);
    glVertex2i(-9,-8+y);
    glEnd();

    glColor3ub(255, 255, 255);
    glBegin(GL_POLYGON);
    glVertex2i(-4,-10+y);
    glVertex2i(-1,-10+y);
    glVertex2i(-1,-8+y);
    glVertex2i(-4,-8+y);
    glEnd();

    glColor3ub(255, 255, 255);
    glBegin(GL_POLYGON);
    glVertex2i(-9,-7+y);
    glVertex2i(-6,-7+y);
    glVertex2i(-6,-5+y);
    glVertex2i(-9,-5+y);
    glEnd();

    glColor3ub(255, 255, 255);
    glBegin(GL_POLYGON);
    glVertex2i(-4,-7+y);
    glVertex2i(-1,-7+y);
    glVertex2i(-1,-5+y);
    glVertex2i(-4,-5+y);
    glEnd();

    glColor3ub(255, 255, 255);
    glBegin(GL_POLYGON);
    glVertex2i(-9,-4+y);
    glVertex2i(-6,-4+y);
    glVertex2i(-6,-2+y);
    glVertex2i(-9,-2+y);
    glEnd();

    glColor3ub(255, 255, 255);
    glBegin(GL_POLYGON);
    glVertex2i(-4,-4+y);
    glVertex2i(-1,-4+y);
    glVertex2i(-1,-2+y);
    glVertex2i(-4,-2+y);
    glEnd();

    glColor3ub(255, 102, 179);
    glBegin(GL_POLYGON);
    glVertex2i(-10,-1+y);
    glVertex2i(0,-1+y);
    glVertex2i(3,2+y);
    glVertex2i(-7,2+y);
    glEnd();

    glColor3ub(255, 51, 153);
    glBegin(GL_POLYGON);
    glVertex2i(0,-20+y);
    glVertex2i(3,-17+y);
    glVertex2i(3,2+y);
    glVertex2i(0,-1+y);
    glEnd();


    glColor3ub(255, 153, 204);
    glBegin(GL_POLYGON);
    glVertex2i(-10,-20+y);
    glVertex2i(0,-20+y);
    glVertex2i(0,-1+y);
    glVertex2i(-10,-1+y);
    glEnd();

    // 4 NO BAARI SHESH



    // 5 NO BAARI

    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(14,-17+y);
    glVertex2i(32,-17+y);
    glVertex2i(32,-11+y);
    glVertex2i(14,-11+y);
    glEnd();

    glColor3ub(0, 102, 102);
    glBegin(GL_POLYGON);
    glVertex2i(13,-10+y);
    glVertex2i(33,-10+y);
    glVertex2i(36,-7+y);
    glVertex2i(16,-7+y);
    glEnd();

    glColor3ub(0, 51, 51);
    glBegin(GL_POLYGON);
    glVertex2i(33,-20+y);
    glVertex2i(36,-17+y);
    glVertex2i(36,-7+y);
    glVertex2i(33,-10+y);
    glEnd();


    glColor3ub(0, 153, 153);
    glBegin(GL_POLYGON);
    glVertex2i(13,-20+y);
    glVertex2i(33,-20+y);
    glVertex2i(33,-10+y);
    glVertex2i(13,-10+y);
    glEnd();

    // 5 NO BAARI

    // 2 NO GHASH ER UPOR 1 NO BAARI

    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(-29,-2);
    glVertex2i(-27,-2);
    glVertex2i(-27,0);
    glVertex2i(-29,0);
    glEnd();

    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(-26,-2);
    glVertex2i(-24,-2);
    glVertex2i(-24,0);
    glVertex2i(-26,0);
    glEnd();

    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(-23,-2);
    glVertex2i(-21,-2);
    glVertex2i(-21,0);
    glVertex2i(-23,0);
    glEnd();

    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(-23,-5);
    glVertex2i(-21,-5);
    glVertex2i(-21,-3);
    glVertex2i(-23,-3);
    glEnd();

    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(-26,-5);
    glVertex2i(-24,-5);
    glVertex2i(-24,-3);
    glVertex2i(-26,-3);
    glEnd();

    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(-29,-5);
    glVertex2i(-27,-5);
    glVertex2i(-27,-3);
    glVertex2i(-29,-3);
    glEnd();


    glColor3ub(82, 122, 122);
    glBegin(GL_POLYGON);
    glVertex2i(-30,3);
    glVertex2i(-20,3);
    glVertex2i(-17,6);
    glVertex2i(-27,6);
    glEnd();

    glColor3ub(82, 122, 122);
    glBegin(GL_POLYGON);
    glVertex2i(-30,1);
    glVertex2i(-20,1);
    glVertex2i(-17,4);
    glVertex2i(-27,4);
    glEnd();

    glColor3ub(82, 122, 122);
    glBegin(GL_POLYGON);
    glVertex2i(-30,5);
    glVertex2i(-20,5);
    glVertex2i(-17,8);
    glVertex2i(-27,8);
    glEnd();

    glColor3ub(61, 92, 92);
    glBegin(GL_POLYGON);
    glVertex2i(-20,5);
    glVertex2i(-20,-11);
    glVertex2i(-17,-8);
    glVertex2i(-17,8);
    glEnd();


    glColor3ub(102, 153, 153);
    glBegin(GL_POLYGON);
    glVertex2i(-30,-11);   //BAARIR SIZE
    glVertex2i(-20,-11);
    glVertex2i(-20,5);
    glVertex2i(-30,5);
    glEnd();
    // 2 NO GHASH ER UPOR 1 NO BAARI SHESH



    // 2 NO GHASH ER UPOR 2 NO BAARI



    glColor3ub(82, 122, 122);
    glBegin(GL_POLYGON);
    glVertex2i(-9,4);
    glVertex2i(1,4);
    glVertex2i(4,7);
    glVertex2i(-6,7);
    glEnd();

    glColor3ub(61, 92, 92);
    glBegin(GL_POLYGON);
    glVertex2i(1,4);
    glVertex2i(1,-12);
    glVertex2i(4,-9);
    glVertex2i(4,7);
    glEnd();


    glColor3ub(102, 153, 153);
    glBegin(GL_POLYGON);
    glVertex2i(-9,-12);   //BAARIR SIZE
    glVertex2i(1,-12);
    glVertex2i(1,4);
    glVertex2i(-9,4);
    glEnd();
    // 2 NO GHASH ER UPOR 2 NO BAARI SHESH



    // 2 NO GHASH ER UPOR 1 NO GAAS

    glColor3ub(153, 255, 51);
    drawFilledCircle(35,-1,3.5);
    drawFilledCircle(37,1,3.5);
    drawFilledCircle(39,-1,3.5);


    glColor3ub(179, 119, 0);
    glBegin(GL_POLYGON);
    glVertex2i(35,-11);
    glVertex2i(40,-11);
    glVertex2i(39,-1);
    glVertex2i(36,-1);
    glEnd();

    // 2 NO GHASH ER UPOR 1 NO GAAS SHESH



    // 2 NO GHASHER UPOR 1 NO ROAD
    glColor3ub(0, 0, 0);
    glBegin(GL_POLYGON);
    glVertex2i(-48,-20);
    glVertex2i(-44,-20);
    glVertex2i(-31,0);
    glVertex2i(-35,0);
    glEnd();
    // 2 NO GHASHER UPOR 1 NO ROAD SHESH





    // 2 NO GHASHER UPOR 2 NO ROAD
    glColor3ub(0, 0, 0);
    glBegin(GL_POLYGON);
    glVertex2i(3,-20);
    glVertex2i(7,-20);
    glVertex2i(17,0);
    glVertex2i(13,0);
    glEnd();
    // 2 NO GHASHER UPOR 2 NO ROAD SHESH


    //NICHER GHAASH
    glColor3ub(51, 204, 51);
    glBegin(GL_POLYGON);
    glVertex2i(-50,-20);
    glVertex2i(50,-20);
    glVertex2i(50,0);
    glVertex2i(-50,0);
    glEnd();
    //NICHER GHAASH

    //1 NO BAARI
    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(-39,16+y);
    glVertex2i(-36,16+y);
    glVertex2i(-36,19+y);
    glVertex2i(-39,19+y);
    glEnd();


    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(-34,16+y);
    glVertex2i(-31,16+y);
    glVertex2i(-31,19+y);
    glVertex2i(-34,19+y);
    glEnd();


    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(-39,21+y);
    glVertex2i(-36,21+y);
    glVertex2i(-36,24+y);
    glVertex2i(-39,24+y);
    glEnd();


    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(-34,21+y);
    glVertex2i(-31,21+y);
    glVertex2i(-31,24+y);
    glVertex2i(-34,24+y);
    glEnd();

    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(-39,26+y);
    glVertex2i(-36,26+y);
    glVertex2i(-36,29+y);
    glVertex2i(-39,29+y);
    glEnd();

    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(-34,26+y);
    glVertex2i(-31,26+y);
    glVertex2i(-31,29+y);
    glVertex2i(-34,29+y);
    glEnd();


    glColor3ub(179, 143, 0);
    glBegin(GL_POLYGON);
    glVertex2i(-40,30+y);
    glVertex2i(-30,30+y);
    glVertex2i(-25,34+y);
    glVertex2i(-35,34+y);
    glEnd();


    glColor3ub(102, 82, 0);
    glBegin(GL_POLYGON);
    glVertex2i(-30,15+y);
    glVertex2i(-25,20+y);
    glVertex2i(-25,34+y);
    glVertex2i(-30,30+y);
    glEnd();

    glColor3ub(255, 204, 0);
    glBegin(GL_POLYGON);
    glVertex2i(-40,15+y);   //BAARIR SIZE
    glVertex2i(-30,15+y);
    glVertex2i(-30,30+y);
    glVertex2i(-40,30+y);
    glEnd();
    // 1 NO BAARI SHESH
//1

    //1 NO BAARIR COPY
    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(-39,16+y);
    glVertex2i(-36,16+y);
    glVertex2i(-36,19+y);
    glVertex2i(-39,19+y);
    glEnd();


    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(-34,16+y);
    glVertex2i(-31,16+y);
    glVertex2i(-31,19+y);
    glVertex2i(-34,19+y);
    glEnd();


    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(-39,21+y);
    glVertex2i(-36,21+y);
    glVertex2i(-36,24+y);
    glVertex2i(-39,24+y);
    glEnd();


    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(-34,21+y);
    glVertex2i(-31,21+y);
    glVertex2i(-31,24+y);
    glVertex2i(-34,24+y);
    glEnd();

    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(41,26+y);
    glVertex2i(44,26+y);
    glVertex2i(44,29+y);
    glVertex2i(41,29+y);
    glEnd();

    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(46,26+y);
    glVertex2i(49,26+y);
    glVertex2i(49,29+y);
    glVertex2i(46,29+y);
    glEnd();

    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(46,21+y);
    glVertex2i(49,21+y);
    glVertex2i(49,24+y);
    glVertex2i(46,24+y);
    glEnd();


    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(46,16+y);
    glVertex2i(49,16+y);
    glVertex2i(49,19+y);
    glVertex2i(46,19+y);
    glEnd();

    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(41,21+y);
    glVertex2i(44,21+y);
    glVertex2i(44,24+y);
    glVertex2i(41,24+y);
    glEnd();

    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(41,16+y);
    glVertex2i(44,16+y);
    glVertex2i(44,19+y);
    glVertex2i(41,19+y);
    glEnd();


    glColor3ub(119, 51, 255);
    glBegin(GL_POLYGON);
    glVertex2i(40,30+y);
    glVertex2i(50,30+y);
    glVertex2i(50,33+y);
    glVertex2i(44,33+y);
    glEnd();


    glColor3ub(153, 102, 255);
    glBegin(GL_POLYGON);
    glVertex2i(40,15+y);   //BAARIR SIZE
    glVertex2i(50,15+y);
    glVertex2i(50,30+y);
    glVertex2i(40,30+y);
    glEnd();
    // 1 NO BAARIR COPY SHESH





    // 1 NO GAAS (TREE)

    glColor3ub(153, 255, 51);
    drawFilledCircle(-15,28,3.5);
    drawFilledCircle(-13,31,3.5);
    drawFilledCircle(-11,28,3.5);




    glColor3ub(179, 119, 0);
    glBegin(GL_POLYGON);
    glVertex2i(-15,15+y+1);
    glVertex2i(-10,15+y+1);
    glVertex2i(-11,25+y+1);
    glVertex2i(-14,25+y+1);
    glEnd();
    // 1 NO GAAS SHESH (TREE)



    // 2 NO BAARI


    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(2,16+y);
    glVertex2i(5,16+y);
    glVertex2i(5,19+y);
    glVertex2i(2,19+y);
    glEnd();

    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(6,15+y);
    glVertex2i(9,15+y);
    glVertex2i(9,21+y);
    glVertex2i(6,21+y);
    glEnd();

    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(10,16+y);
    glVertex2i(13,16+y);
    glVertex2i(13,19+y);
    glVertex2i(10,19+y);
    glEnd();


    glColor3ub(102, 102, 51);
    glBegin(GL_POLYGON);
    glVertex2i(0,15+y);
    glVertex2i(15,15+y);
    glVertex2i(15,22+y);
    glVertex2i(0,22+y);
    glEnd();

    glColor3ub(85, 85, 43);
    glBegin(GL_POLYGON);
    glVertex2i(0,22+y);
    glVertex2i(15,22+y);
    glVertex2i(7,27+y);
    glEnd();

    glColor3ub(68, 68, 34);
    glBegin(GL_POLYGON);
    glVertex2i(7,27+y);
    glVertex2i(15,22+y);
    glVertex2i(20,25+y);
    glVertex2i(13,30+y);
    glEnd();


    glColor3ub(34, 34, 17);
    glBegin(GL_POLYGON);
    glVertex2i(15,15+y);
    glVertex2i(20,18+y);
    glVertex2i(20,25+y);
    glVertex2i(15,22+y);
    glEnd();
    // 2 NO BAARI SHESH


    // 2 NO GAAS(TREE)
    glColor3ub(153, 255, 51);
    drawFilledCircle(29,28,3.5);
    drawFilledCircle(31,31,3.5);
    drawFilledCircle(33,28,3.5);


    glColor3ub(179, 119, 0);
    glBegin(GL_POLYGON);
    glVertex2i(29,15+y+1);
    glVertex2i(34,15+y+1);
    glVertex2i(33,25+y+1);
    glVertex2i(30,25+y+1);
    glEnd();

    // 2 NO GAAS SHESH(TREE)


    // 1 NO BAARIR 2 NO COPY

    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(-7,21+y);
    glVertex2i(-4,21+y);
    glVertex2i(-4,24+y);
    glVertex2i(-7,24+y);
    glEnd();

    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(-2,21+y);
    glVertex2i(1,21+y);
    glVertex2i(1,24+y);
    glVertex2i(-2,24+y);
    glEnd();

    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(-7,26+y);
    glVertex2i(-4,26+y);
    glVertex2i(-4,29+y);
    glVertex2i(-7,29+y);
    glEnd();

    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(-2,26+y);
    glVertex2i(1,26+y);
    glVertex2i(1,29+y);
    glVertex2i(-2,29+y);
    glEnd();

    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(-7,31+y);
    glVertex2i(-4,31+y);
    glVertex2i(-4,34+y);
    glVertex2i(-7,34+y);
    glEnd();

    glColor3ub(255,255,255);
    glBegin(GL_POLYGON);
    glVertex2i(-2,31+y);
    glVertex2i(1,31+y);
    glVertex2i(1,34+y);
    glVertex2i(-2,34+y);
    glEnd();


    glColor3ub(255, 119, 51);
    glBegin(GL_POLYGON);
    glVertex2i(2,20+y);
    glVertex2i(7,25+y);
    glVertex2i(7,35+y);
    glVertex2i(2,35+y);
    glEnd();

    glColor3ub(255, 153, 102);
    glBegin(GL_POLYGON);
    glVertex2i(-8,20+y);   //BAARIR SIZE
    glVertex2i(2,20+y);
    glVertex2i(2,35+y);
    glVertex2i(-8,35+y);
    glEnd();


    // 1 NO BAARIR 2 NO COPY SHESH



    // 1 NO GHASHER UPOR 1 NO ROAD
    glColor3ub(0, 0, 0);
    glBegin(GL_POLYGON);
    glVertex2i(-26,15);
    glVertex2i(-22,15);
    glVertex2i(-9,35);
    glVertex2i(-13,35);
    glEnd();
    // 1 NO GHASHER UPOR 1 NO ROAD SHESH

    // 1 NO GHASHER UPOR 2 NO ROAD
    glColor3ub(0, 0, 0);
    glBegin(GL_POLYGON);
    glVertex2i(20,15);
    glVertex2i(24,15);
    glVertex2i(37,35);
    glVertex2i(33,35);
    glEnd();

    //UPORER GHAASH
    glColor3ub(51, 204, 51);
    glBegin(GL_POLYGON);
    glVertex2i(-50,15);
    glVertex2i(50,15);
    glVertex2i(50,35);
    glVertex2i(-50,35);
    glEnd();
    //UPORER GHAASH


    // 1 NO ROAD ER UPOR DAAG
    glColor3ub(255,255,255);
    glBegin(GL_LINES);
    glVertex2i(-50,7);
    glVertex2i(-45,7);
    glEnd();

    glColor3ub(255,255,255);
    glBegin(GL_LINES);
    glVertex2i(-40,7);
    glVertex2i(-35,7);
    glEnd();

    glColor3ub(255,255,255);
    glBegin(GL_LINES);
    glVertex2i(-30,7);
    glVertex2i(-25,7);
    glEnd();

    glColor3ub(255,255,255);
    glBegin(GL_LINES);
    glVertex2i(-20,7);
    glVertex2i(-15,7);
    glEnd();

    glColor3ub(255,255,255);
    glBegin(GL_LINES);
    glVertex2i(-10,7);
    glVertex2i(-5,7);
    glEnd();

    glColor3ub(255,255,255);
    glBegin(GL_LINES);
    glVertex2i(0,7);
    glVertex2i(5,7);
    glEnd();

    glColor3ub(255,255,255);
    glBegin(GL_LINES);
    glVertex2i(10,7);
    glVertex2i(15,7);
    glEnd();

    glColor3ub(255,255,255);
    glBegin(GL_LINES);
    glVertex2i(20,7);
    glVertex2i(25,7);
    glEnd();

    glColor3ub(255,255,255);
    glBegin(GL_LINES);
    glVertex2i(30,7);
    glVertex2i(35,7);
    glEnd();

    glColor3ub(255,255,255);
    glBegin(GL_LINES);
    glVertex2i(40,7);
    glVertex2i(45,7);
    glEnd();

    // 1 NO ROAD ER DAAG SHESH

    // 2 NO ROAD ER 1 NO DAAG
    for(int i=-50;i<50;i+=10){
        glColor3ub(255,255,255);
        glBegin(GL_LINES);
        glVertex2i(i,-25);
        glVertex2i(i+5,-25);
        glEnd();
    }
    // 2 NO ROAD ER 1 NO DAAG SHESH

    // 2 NO ROAD ER 2 NO DAAG
    for(int i=-50;i<50;i+=10){
        glColor3ub(255,255,255);
        glBegin(GL_LINES);
        glVertex2i(i,-30);
        glVertex2i(i+5,-30);
        glEnd();
    }

    // 2 NO ROAD ER 2 NO DAAG SHESH



    glFlush ();
}



/*

############################################## END TRI 1 () ####################################################

*/



/*

@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@ TRI () @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

*/

void Tri(){


    glColor3ub(89, 89, 89);
    drawFilledCircle(-95,16,1.5);


    glColor3ub(89, 89, 89);
    drawFilledCircle(-85,16,1.5);


    glColor3ub(89, 89, 89);
    glBegin(GL_POLYGON);
    glVertex2i(-89,21);
    glVertex2i(-85,21);
    glVertex2i(-86,24);
    glVertex2i(-89,24);
    glEnd();

    glColor3ub(89, 89, 89);
    glBegin(GL_POLYGON);
    glVertex2i(-95,21);
    glVertex2i(-91,21);
    glVertex2i(-91,24);
    glVertex2i(-94,24);
    glEnd();

    glColor3ub(204, 0, 0);
    glBegin(GL_TRIANGLE_FAN);
    glVertex2i(-100,16);
    glVertex2i(-80,16);
    glVertex2i(-80,20);
    glVertex2i(-84,20);
    glVertex2i(-86,25);
    glVertex2i(-94,25);
    glVertex2i(-96,20);
    glVertex2i(-100,20);
    glEnd();



    glFlush ();

}



void Tri2(){

    glColor3ub(89, 89, 89);
    drawFilledCircle(-95,-72,1.5);



    glColor3ub(89, 89, 89);
    drawFilledCircle(-85,-72,1.5);


    glColor3ub(89, 89, 89);
    glBegin(GL_POLYGON);
    glVertex2i(-89,-65);
    glVertex2i(-85,-65);
    glVertex2i(-86,-62);
    glVertex2i(-89,-62);
    glEnd();

    glColor3ub(89, 89, 89);
    glBegin(GL_POLYGON);
    glVertex2i(-95,-65);
    glVertex2i(-91,-65);
    glVertex2i(-91,-62);
    glVertex2i(-94,-62);
    glEnd();


    glColor3ub(204, 0, 0);
    glBegin(GL_TRIANGLE_FAN);
    glVertex2i(-100,-72);
    glVertex2i(-80,-72);
    glVertex2i(-80,-66);
    glVertex2i(-84,-66);
    glVertex2i(-86,-61);
    glVertex2i(-94,-61);
    glVertex2i(-96,-66);
    glVertex2i(-100,-66);
    glEnd();



    glFlush ();

}

/*

@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@ END TRI () @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

*/



void myDisplay()
{
glClear(GL_COLOR_BUFFER_BIT | GL_DEPTH_BUFFER_BIT);
glLoadIdentity();
glTranslated(translate_x1,translate_y1,translate_z1);
Tri1();
glTranslatef(translate_x, translate_y, translate_z);
Tri();
Tri();
Tri();

glTranslatef(translate_x3,translate_y3,translate_z3);
Tri2();
Tri2();
Tri2();

glutSwapBuffers();
}





void mouse(int button,int state,int x,int y)
{
switch(button)
{
case GLUT_LEFT_BUTTON:
if(state==GLUT_DOWN)

    glutIdleFunc(funcTranslate_xu);

break;

case GLUT_RIGHT_BUTTON:
if(state==GLUT_DOWN)

    glutIdleFunc(funcTranslate_xl);

break;
default:
break;
}
}




void keyboard(unsigned char key, int x, int y)
{

if(key=='s')
{
    glutIdleFunc(funcTranslate_y);

}
else if(key=='w')
{
    glutIdleFunc(funcTranslate_y2);

}
else if(key=='a'){
    glutIdleFunc(funcTranslate_x);
}
else if(key=='f'){
    glutIdleFunc(funcTranslate_x3);
}
else if(key=='t'){
    glutIdleFunc(funcTranslate_y32);
}
else if(key=='g'){
    glutIdleFunc(funcTranslate_y31);
}
else if(key=='r')
{
reset();
glutPostRedisplay();
}

}


int main(int argc, char** argv)
{
glutInit(&argc, argv);
glutInitDisplayMode (GLUT_SINGLE | GLUT_RGB);
glutInitWindowSize (1024, 768);
glutInitWindowPosition (0, 0);
glutCreateWindow ("Rotation");
init ();
glutDisplayFunc(myDisplay);
glutReshapeFunc(reshape);
glutMouseFunc(mouse);
glutKeyboardFunc(keyboard);


glutMainLoop();
return 0;
}
