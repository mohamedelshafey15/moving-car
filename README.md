# moving-car
from OpenGL.GL import*
from OpenGL.GLU import*
from OpenGL.GLUT import*
import numpy as np
from math import *

def myInit():
    glMatrixMode(GL_PROJECTION)
    gluPerspective(72,1,1,30)
    gluLookAt(8,9,10,
             0,0,0
             ,0,1,0)
    glClearColor(1,1,1,0)

    glClear(GL_COLOR_BUFFER_BIT)


def drawXYZ():
    glBegin(GL_LINES)
    glColor3f(0, 0, 0)
    glVertex(0, 10, 0)
    glVertex(0, -10, 0)
    glVertex(10, 0, 0)
    glVertex(-10, 0, 0)
    glVertex(0, 0, 10)
    glVertex(0, 0, -10)
    glEnd()


angle = 0
Trans = 0
forward = True


def frontWindow():
    glLoadIdentity()
    glTranslate(Trans, 1, 0)

    glColor3f(1, 1, 0.8)

    glBegin(GL_POLYGON)

    glVertex(1.2, .9, -1.05)
    glVertex(1.2, .9, 1.5)
    glVertex(1.2, -0.25, 1.5)
    glVertex(1.2, -0.25, -1.05)

    glEnd()

def SideWindow():
    glLoadIdentity()
    glTranslate(Trans, 1, 3.5)

    glColor3f(1, 1, 0.8)

    glBegin(GL_POLYGON)

    glVertex(-0.5, 0.9, -1.5)
    glVertex(0.7, 0.9, -1.5)
    glVertex(0.7, -0.25, -1.5)
    glVertex(-0.5, -0.25, -1.5)

    glEnd()


def street():
    glLoadIdentity()
    glColor3f(.2, .2, .2)
    glBegin(GL_POLYGON)
    glVertex(10, 0, 3)
    glVertex(10, 0, -1.5)
    glVertex(-25, 0, -1.5)
    glVertex(-20, 0, 3)
    glEnd()

    glColor3f(1, 1, 1)
    glBegin(GL_POLYGON)
    glVertex(6, 0, .7)
    glVertex(4, 0, .7)
    glVertex(4, 0, 1.2)
    glVertex(6, 0, 1.2)

    glEnd()

    glColor3f(1, 1, 1)
    glBegin(GL_POLYGON)
    glVertex(9, 0, .7)
    glVertex(7, 0, .7)
    glVertex(7, 0, 1.2)
    glVertex(9, 0, 1.2)

    glEnd()

    glColor3f(1, 1, 1)
    glBegin(GL_POLYGON)
    glVertex(3, 0, .7)
    glVertex(1, 0, .7)
    glVertex(1, 0, 1.2)
    glVertex(3, 0, 1.2)

    glEnd()

    glColor3f(1, 1, 1)
    glBegin(GL_POLYGON)
    glVertex(0, 0, .7)
    glVertex(-2, 0, .7)
    glVertex(-2, 0, 1.2)
    glVertex(0, 0, 1.2)

    glEnd()
    glColor3f(1, 1, 1)
    glBegin(GL_POLYGON)
    glVertex(-3, 0, .7)
    glVertex(-5, 0, .7)
    glVertex(-5, 0, 1.2)
    glVertex(-3, 0, 1.2)

    glEnd()
    glColor3f(1, 1, 1)
    glBegin(GL_POLYGON)
    glVertex(-6, 0, .7)
    glVertex(-8, 0, .7)
    glVertex(-8, 0, 1.2)
    glVertex(-6, 0, 1.2)

    glEnd()
    glColor3f(1, 1, 1)
    glBegin(GL_POLYGON)
    glVertex(-9, 0, .7)
    glVertex(-11, 0, .7)
    glVertex(-11, 0, 1.2)
    glVertex(-9, 0, 1.2)

    glEnd()
    glColor3f(1, 1, 1)
    glBegin(GL_POLYGON)
    glVertex(-12, 0, .7)
    glVertex(-14, 0, .7)
    glVertex(-14, 0, 1.2)
    glVertex(-12, 0, 1.2)

    glEnd()
    glColor3f(1, 1, 1)
    glBegin(GL_POLYGON)
    glVertex(-15, 0, .7)
    glVertex(-17, 0, .7)
    glVertex(-17, 0, 1.2)
    glVertex(-15, 0, 1.2)

    glEnd()

    glColor3f(0, 0, 0)
    glBegin(GL_LINE_LOOP)
    glVertex(10, 0, 3)
    glVertex(10, 0, -1.5)
    glVertex(-25, 0, -1.5)
    glVertex(-20, 0, 3)

    glEnd()
def draw():
    glMatrixMode(GL_MODELVIEW)
    glLoadIdentity()
    global angle
    global Trans
    global forward





    glClear(GL_COLOR_BUFFER_BIT)
    #drawXYZ()
    glColor3f(.6, .9, 0)
    glBegin(GL_QUADS)
    glVertex(5000, -20.25 , -61)
    glVertex(-5000, 221.25 , -60)
    glVertex(-3000, -123.25  , -60)
    glVertex(-3000, -13.25  , 51)
    glEnd()
    street()
    glColor3f(.1,0,.6)
    glTranslate(Trans, 0, 0)
    glScale(1,0.25,0.5)
    glutSolidCube(5)
    glTranslate(0,5,0)
    glScale(0.5,1,1)
    glutSolidCube(5)




    glColor3f(0, 0, 0)
    glLoadIdentity()
    glTranslate(Trans+0.5*5, -0.5* 0.25*5, 0.5 *0.5*5)
    glRotate(angle, 0, 0, 1)
    glutSolidTorus(0.125, 0.5, 20, 20)


    glColor3f(0, 0, 0)

    glLoadIdentity()
    glTranslate(Trans+0.5 * 5, -0.5 * 0.25 * 5, -0.5 * 0.5 * 5)
    glRotate(angle, 0, 0, 1)
    glutSolidTorus(0.125, 0.5, 20, 20)

    glColor3f(0, 0, 0)

    glLoadIdentity()
    glTranslate(Trans-0.5 * 5, -0.5 * 0.25 * 5, 0.5 * 0.5 * 5)
    glRotate(angle, 0, 0, 1)
    glutSolidTorus(0.125, 0.5, 20, 20)

    glColor3f(1, 1, 1)
    glLoadIdentity()
    glTranslate(Trans + 0.5 * 5, 0.5 * 0.25 * 5, 0.5 * 0.5 * 5)

    glutSolidSphere( 0.25, 15, 15)

    glColor3f(1, 1, 1)
    glLoadIdentity()
    glTranslate(Trans + 0.5 * 5, 0.5 * 0.25 * 5, -0.5 * 0.5 * 0.25)

    glutSolidSphere(0.25, 15, 15)


    frontWindow()

    SideWindow()

    glutSwapBuffers()
    if forward :
        angle -= 0.1
        Trans += 0.001
        if Trans > 5 :
            forward = False
    else:
        angle += 0.1
        Trans -= 0.001
        if Trans< -5:
            forward = True

glutInit()
glutInitDisplayMode(GLUT_DOUBLE | GLUT_RGB)
glutInitWindowSize(900, 900)
glutCreateWindow(b"Moving Car")
myInit()
glutDisplayFunc(draw)
glutIdleFunc(draw)
glutMainLoop()
