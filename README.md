# little-pearl
void display(void)
{
	glClear(GL_COLOR_BUFFER_BIT | GL_DEPTH_BUFFER_BIT);
	glMatrixMode(GL_MODELVIEW);
	glLoadIdentity();

	gluLookAt(0.0, 0.0, 8.0, /* Eye pos XYZ */
		0.0, 0.0, 0.0, /* Target pos XYZ */
		0.0, 1.0, 0.0); /* Up vector */

	//do something awesome here
	// Press Rnter to start the animation
	//世界时钟，控制旋转的速度
	static float fSpin = 0.0f;
	fSpin += 0.1f;
	if (fSpin > 360.0f)
	{
	fSpin -= 360.0;
	}

	glutKeyboardFunc(keyboard);
	// Color Cube 
							glDisable(GL_LIGHTING);
							glEnable(GL_BLEND);
							
							glTranslated(0.0, 1, -2);
							glRotatef(fSpin, 1.0f, 1.0f, 0.0f);
							//glRotatef(30, 0.0f, 1.0f, 0.0f);

														glBegin(GL_QUADS);
														//红色绘制第一个四边形    front 
													

														glColor4f(1.0f, 0.0f, 0.0f, 0.5);
														glVertex3f(0.0f, 0.0f, 0.0f);
														glVertex3f(1.0f, 0.0f, 0.0f);
														glVertex3f(1.0f, 1.0f, 0.0f);
														glVertex3f(0.0f, 1.0f, 0.0f);
																					 //back
														glColor4f(0.0f, 1.0f, 0.0f, 0.5);
														glVertex3f(0.0f, 0.0f, -1);
														glVertex3f(1.0f, 0.0f, -1);
														glVertex3f(1.0f, 1.0f, -1);
														glVertex3f(0.0f, 1.0f, -1);
														//left
														glColor4f(0.0f, 0.0f, 1.0f, 0.5);
														glVertex3f(0.0f, 0.0f, 0.0);
														glVertex3f(0.0, 0.0f, -1);
														glVertex3f(0.0, 1.0f, -1);
														glVertex3f(0.0f, 1.0f, 0);
														//right	
														glColor4f(0.8f,0.8f, 0.3f, 0.5);
														glVertex3f(1.0, 0.0f, 0.0);
														glVertex3f(1.0, 0.0f, -1);
														glVertex3f(1.0, 1.0f, -1);
														glVertex3f(1.0, 1.0f, 0);
														//up
														glColor4f(0.3f, 0.8f,0.8f, 0.5);
														glVertex3f(0.0, 1.0, 0.0);
														glVertex3f(1.0, 1.0, 0);
														glVertex3f(1.0, 1.0f, -1);
														glVertex3f(0.0, 1.0f, -1);
														//buttom
														glColor4f(0.5f,0.3f, 0.5f,0.5);
														glVertex3f(0.0, 0.0, 0.0);
														glVertex3f(1.0, 0.0, 0);
														glVertex3f(1.0, 0.0f, -1);
														glVertex3f(0.0, 0.0, -1);

														glEnd();						

														glRotatef(-fSpin, 1.0f, 1.0f, 0.0f);
														glTranslated(0.0, -1.0, 2);

							glEnable(GL_LIGHTING);
							glDepthMask(GL_TRUE);
							


//没有输入Enter 


		if(!enter)    
		{ 
		///苹果
					glTranslatef(2.0f, 0.0f, 0.0f); 
						glRotatef(fSpin, 0.0f, 1.0f, 0.0f);
   
										GLUquadricObj* quadraticSphere1;
										quadraticSphere1 = gluNewQuadric();
										gluSphere(quadraticSphere1, 0.9,32, 32); //半径为0.9的球，移动到屏幕（2，0，0）处

								glTranslatef(0.0f, 0.9, 0.0f);
									glRotatef(270.0f,1.0f, 0.0f, 0.0f);
										   glutSolidCone(0.05, 0.3, 16,16); //半径为0.1 的锥体，移动到屏幕(2.0f, 1.25f, 0.0f)处
									glRotatef(-270.0f, 1.0f, 0.0f, 0.0f);
								glTranslatef(0.0f, -0.9, 0.0f);

							   glTranslatef(-0.3f, 1.0, 0.0f);
								   glRotatef(150.0f, 1.0f, 0.0f,1.0f);
										   glutSolidCone(0.05, 0.3, 16, 16); //半径为0.1 的锥体，移动到屏幕(1.75f, 1.1f, 0.0f)处
								   glRotatef(-150.0f, 1.0f, 0.0f, 1.0f);
								glTranslatef(0.3f,- 1.0, 0.0f);

						glRotatef(-fSpin, 0.0f, 1.0f, 0.0f);
					glTranslatef(-2.0f, 0.0f, 0.0f);





		 //圆锥和圆锥构成笔 
   
				glTranslatef(-2.0f,0.0f, 0.0f);
				   glRotatef(fSpin, 0.0f, 1.0f, 0.0f);				
		  					glRotatef(335.0f, 0.0f, 0.0f, 1.0f);
							glTranslatef(0.0f, -1.0f, 0.0f);
								   glRotatef(270.0f, 1.0f, 0.0f, 0.0f);

										   GLUquadricObj* quadraticCylinder1;  // 笔身
										   quadraticCylinder1 = gluNewQuadric();
										  gluCylinder(quadraticCylinder1, 0.1, 0.1, 2.0, 32, 32);//笔身圆柱，上顶面中心在(-2.0f, 0.0f, 0.0f)，半径0.1，高2.0
								  glRotatef(-270.0f, 1.0f, 0.0f, 0.0f);
		
								 glTranslatef(0.0f,2.0f, 0.0f); //此处为Cone与圆柱的旋转原点相似，不需再移动回 glTranslatef(0.0f,-2.0f, 0.0f)
										  glRotatef(-90.0f, 1.0f, 0.0f, 0.0f);  // 笔头圆锥
										  glutSolidCone(0.1, 0.25, 16, 16);
										  glRotatef(90.0f, 1.0f, 0.0f, 0.0f);
				
						  glTranslatef(0.0f, 1.0f, 0.0f);
						  glRotatef(-335.0f, 0.0f, 0.0f, 1.0f);		

				 glRotatef(-fSpin, 0.0f, 1.0f, 0.0f);
			  glTranslatef(2.0f, 0.0f, 0.0f);



		}
	
	

// Press Enter

else
{
	///苹果
		
   
								GLUquadricObj* quadraticSphere1;
								quadraticSphere1 = gluNewQuadric();
								gluSphere(quadraticSphere1, 0.9,32, 32); //半径为0.9 的球，移动到屏幕（2，0，0）处

						glTranslatef(0.0f, 0.9, 0.0f);
							glRotatef(270.0f,1.0f, 0.0f, 0.0f);
								   glutSolidCone(0.05, 0.3, 16,16); //半径为0.05 的锥体，移动到屏幕(2.0f, 1.25f, 0.0f)处
							glRotatef(-270.0f, 1.0f, 0.0f, 0.0f);
						glTranslatef(0.0f, -0.9, 0.0f);

					   glTranslatef(-0.3f, 1.0, 0.0f);
						   glRotatef(150.0f, 1.0f, 0.0f,1.0f);
								   glutSolidCone(0.05, 0.3, 16, 16); //半径为0.05 的锥体，移动到屏幕(1.75f, 1.1f, 0.0f)处
						   glRotatef(-150.0f, 1.0f, 0.0f, 1.0f);
						glTranslatef(0.3f,- 1.0, 0.0f);

		




 //圆锥和圆锥构成笔 插入苹果
   
		glTranslatef(-1,2, 0.0f);
		  // glRotatef(fSpin, 0.0f, 1.0f, 0.0f);				
		  			glRotatef(-90, 0.0f, 0.0f, 1.0f); //插入苹果
							glTranslatef(2.0f, 0.0f, 0.0f);
								   glRotatef(270.0f, 1.0f, 0.0f, 0.0f);

										   GLUquadricObj* quadraticCylinder1;  // 笔身
										   quadraticCylinder1 = gluNewQuadric();
										  gluCylinder(quadraticCylinder1, 0.1, 0.1, 2.0, 32, 32);//笔身圆柱，上顶面中心在(-2.0f, 0.0f, 0.0f)，半径0.1，高2.0
								  glRotatef(-270.0f, 1.0f, 0.0f, 0.0f);
		
								 glTranslatef(0.0f,2.0f, 0.0f); //此处为Cone与圆柱的旋转原点相似，不需再移动回 glTranslatef(0.0f,-2.0f, 0.0f)
										  glRotatef(-90.0f, 1.0f, 0.0f, 0.0f);  // 笔头圆锥
										  glutSolidCone(0.1, 0.25, 16, 16);
										  glRotatef(90.0f, 1.0f, 0.0f, 0.0f);
				
						  glTranslatef(-2.0f, 0.0f, 0.0f);
				 glRotatef(90, 0.0f, 0.0f, 1.0f);		

	  glTranslatef(0.5, -2.0, 0.0f);
}




	 


						

	glutSwapBuffers();
}
