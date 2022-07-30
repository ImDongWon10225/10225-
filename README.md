# 첫날(임동원)-7/31
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
