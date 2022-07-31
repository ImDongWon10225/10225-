# -7/30
광전효과를 표현하기 위한 금속 판을 준비한다.
광전효과는 금속 표면에 일정 에너지 이상의 빛을 쪼일 때 전자가 에너지를 얻어 튀어나오는 현상이므로 이를 표현하기 위해서는 기본적으로 금속판과 전자가 필요하다.

Web VPython 3.2

box(size = vec(400,10,200), color =vector(1.63/10,1.63/10,1.63/10)) #금속판
photon = sphere(pos = vec(0,100,0), radius = 5, color = color. red, make_trail = True) #움직이는 공, 광자를 표현함, 하지만 이후 빛의 진동수에 따라 
photon.v = vec(0,-10,0)                                                                 광자의 움직임이 바뀌도록 조정할 것임
while True :
    rate(400)
    photon.pos = photon.pos + photon.v *0.01  #v=v0 + at
    if photon.pos.y <= 10 :    
        photon.v.y = -photon.v.y

#-7/31
빛은 파동의 전달방향에 수직방향으로 매질의 움직임이 나타나는 횡파이다. 삼각함수의 그래프를 이용해 빛이 이동하는 모습을 표현해볼 것이다.

ball = sphere(make_trail = True)
for i in range(1000) :
   rate(100)
   ball.pos.x += sin(i/10)
   ball.pos.y += 0.1
for i in range(100) :
   rate(100)
   ball.pos.x -= sin(i/10)
   ball.pos.y -= 0.1
#우선 공을 이용해 공이 사인 모양으로 가도록 표현해보았다. 사인값을 나눈 것은 그래프의 모양을 더 부드럽게 만들기 위해서이다.


Web VPython 3.2

box(pos = vec(-200,0,0), size = vec(10,400,200), color =vector(163/100,163/100,163/100))

photon = sphere(pos = vec(200 ,0,0), radius = 5, color = color. red, make_trail = True)
while (photon.pos.x > 0) :
   for i in range(10000) :
    rate(1000)
    photon.pos.x -= 0.1
    photon.pos.y += sin(i/20)/10
 #공이 횡파의 형태를 이루며 나아가는 것을 표현하였다.
 

#파란 공은 금속의 자유전자, 노란 공은 광자를 표현하였고 여기서는 전자가 금속판에 무작위로 생성되게 하고 이 정보를 리스트에 저장해보았다.

Web VPython 3.2

import random 

photon = sphere(pos=vector(0,100,0), radius=5, color=color.yellow, make_trail = True)
electron = sphere(pos=vector(0,0,0), radius=7, color=color.blue, make_trail = True)
box(size = vec(400,10,200), color =vector(1.63/10,1.63/10,1.63/10), opacity =0.5)

elec=[]
pho=[]
for i in range(20):
    x=random.randint(-190, 190)
    z=random.randint(-90, 90)
    elec.append(sphere(pos=vector(x,0,z), radius=7, color=color.blue, make_trail = True))
    
for i in range(10):
    x=random.randint(-190, 190)
    z=random.randint(-90, 90)
    pho.append(sphere(pos=vector(x,100,z), radius=5, color=color.yellow, make_trail = True))
    

phox = 0 
phoy = 0

dx=float(input('0과 0.1사이의 수'))

while True :
    rate(1000) #1초에 1000번 반복
    photon.pos.x=cos(phox)
    phox += dx 
    photon.pos.y -= 0.01 #이 또한 광자가 횡파의 형태를 그리도록 표현함

  
