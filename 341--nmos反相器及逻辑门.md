###3.4.1 NMOS反相器及逻辑门 
1.增强型负载管反相器一般的反相器由一个NMOS 管和一个负载电阻RD串联组成。<p>如图3-16所示。 
![](/assets/85.PNG)
<p>
####(1)工作原理与逻辑功能 
为了使它的输出低电平接近于0V，负载电阻RD的阻值必须很大。但在集成电路中制造大电阻将占用很大的芯片面积。这会使集成度大大下降，若用一个MOS管来代替大电阻RD，就形成由两个MOS管组成的反相器，作为负载用的MOS管称为**负载管**，<p>
**另一个MOS管称为工作管**，<p>
如图3-17所示。 
![](/assets/86.PNG)
<p>
**工作原理与逻辑功能 **<p>
一般NMOS电源电压VDD≤15V，典型数据为 +12V。NMOS增强型管的开启电压V<sub>TN</sub>= 3.5V，一般在单沟道NMOS电路中，V<sub>TN</sub>取4V值进行分析。<p>
①v<sub>I</sub>为低电平(1V)。由于v<sub>I</sub><VT2 (4V)，使T1管
截止；而T<sub>2</sub>管因V<sub>G2</sub>=V<sub>D2</sub>=V<sub>DD</sub> = 12V，因此V<sub>GS2</sub>>V<sub>T2</sub> (4V)，便导通。输出电压v<sub>0</sub>=V<sub>DD</sub>>V<sub>T2</sub>=12V-4V=8V,为输出高电平(V<sub>OH</sub>)。 
②v<sub>I</sub>为高电平。由于v<sub>I</sub>>V<sub>T1</sub>(4V)，使T1管导通； 同时T<sub>2</sub>管的V<sub>GS2</sub>也大于V<sub>T2</sub>(4V)，亦可导通。n 则输出电压v0为： 
![](/assets/87.PNG)
由于T1管和T2管的跨导之间具有g<sub>m1</sub>》g<sub>m2</sub>的关 系，所以T1、T2导通后，漏源电阻r<sub>DS1</sub><<<sub>rDS2</sub>,输出电压v<sub>0</sub>=V<sub>OL</sub>≈1V。若令A=v<sub>I</sub>,L=v<sub>0</sub>时，输入与输出的逻辑关系为：L=!A 
####(2) 传输特性及性能
典型NMOS增强型负载管反相器的传输特性如图 3-18所示。其输出高电平V<sub>OH</sub>=V<sub>DD</sub>-V<sub>T2</sub>=8V。输出低电平V<sub>OL</sub>≈1V，特性曲线在v<sub>I</sub>≥4V后转折，由输出 n 8V向1V逐渐过渡。输入低电平噪声容限： n V<sub>NL</sub> = V<sub>OFF</sub>- V<sub>IL</sub>=4.5V-1V n =3.5V <p>
![](/assets/88.PNG)
<p>
####输入高电平噪声容限： 
V<sub>NH</sub> = V<sub>IH</sub> – V<sub>ON</sub> = 8V - 5V = 3V <p>
结果分析：<p>
结果可以看出MOS电路抗干扰能力很强。 <p>
V<sub>OFF</sub>决定于开启电压V<sub>T1</sub>，若提高V<sub>T1</sub>，就可增大V<sub>OFF</sub>, 从而提高输入低电平时抗干扰能力。<p>
由图3-18还可以看出，减小g<sub>m2</sub>, 增大g<sub>m1</sub>可使传输特性陡峭，也就是说跨导比g<sub>m2</sub>/g<sub>m1</sub>越小越好，对输入高电平的抗干扰能力提高有较大好处。
####2. NMOS逻辑门 
#####(1)与非门 
NMOS与非门电路如图3-19所示，T1,T2是两个串接的工作管；T3是负载管，它们均为NMOS增强管，跨导g<sub>m1</sub>= g<sub>m2</sub>>>g<sub>m3</sub>。<p>
下面介绍电路的逻辑功能： <p>
![](/assets/89.PNG)
图 3-19<p>
######①输入全高电平：
当A、B端全为高电平(8V)时，则工作管 T1,T2都因栅源电压大于它们的开启电压而 导通；此时负载管T3因栅极与漏极短接， 而 使栅极电位为V<sub>DD</sub> (12V)，它的栅源电压 V<sub>GS3</sub>>V<sub>T3</sub>，因此也导通。其输出端L的电平为： <p>
V<sub>OL</sub> =(r<sub>DS1</sub>+r<sub>DS2</sub>）/（r<sub>DS1</sub>+r<sub>DS2</sub>+r<sub>DS3</sub>）·V<sub>DD</sub> <p>
由于工作管的跨导比负载管的跨导要大得多， 即g<sub>m1</sub>=g<sub>m2</sub>>>g<sub>m3</sub>,因此它们导通之后漏源电阻的 关系为：<p>
r<sub>DS1</sub> = r<sub>DS2</sub><<r<sub>DS3</sub><p>
这就使输出端L的电平V<sub>OL</sub>≈1V,为低电平。<P>
######②输入有低电平：
当输入A、B中有低电平时，工作管T1,T2中必有管 子因栅源电压小于它们的开启电压而截止,输出L与 地之间就无通路；此时，负载管T3因栅极电位为V<sub>DD</sub> (12V)，栅源电压V<sub>GS3</sub>大于开启电压V<sub>T3</sub>而导通。其输出端L的电平为：<p>
V<sub>OL</sub>= V<sub>DD</sub>- V<sub>T3</sub>=12V-4V=8V <p>
即输出为高电平。 通过以上分析可知，图3-19所示电路当“输入全高 时则输出为低，输入有低时则输出为高” 。是个正逻辑与非门，其输入、输出逻辑关系为:<p>
 L = !(A·B) 
#####(2) 或非门 
NMOS或非门电路如图3-20所示。并联T1,T2管为工作管；T3管为栅漏短接的负载管，均为NMOS增强型管，工作管的跨导比负载管跨导大得多, 即g<sub>m1</sub> = g<sub>m2</sub>>>g<sub>m3</sub>。电路的逻辑功能为：
![](/assets/90.PNG) 
图 3-20 <p>
######①当输入有高电平。 
 A、B输入若有高电平(8Ｖ)，则工作管T1,T2中就有 管子因栅源电压大于它的开启电压而导通，输出L到 地有通路；负载管T3也因栅极电位为V<sub>DD</sub>, V<sub>GS3</sub>可大于 VT3而导通。这时输出端L的电平V<sub>OL</sub>为：<p>
 V<sub>OL</sub>= (V<sub>DD</sub>)/(r<sub>DS1,2</sub> + r<sub>DS3</sub>)·r<sub>DS1,2</sub> <p>
 r<sub>DS1,2</sub>是A、B输入有高电平时，输出L到地的等效电阻。 若A、B中一个为高电平，r<sub>DS1,2</sub>就是导通管子的漏源电阻，若A、B均为高电平，r<sub>DS1，2</sub>就是两个管子导通漏 源电阻并联值。显然r<sub>DS1,2</sub>要比r<sub>DS3</sub>小得多，这是因为 g<sub>m1</sub>=g<sub>m2</sub>>>g<sub>m3</sub>，因此在输入有高电平的条件下， 输出端L的电平V<sub>OL</sub>≈1V 为低电平。<p>
######②当输入全低电平。 
A、B输入若全为低电平(1V)时，则工作管T1,T2均因 栅源电压小于它们的开启电压而截止，输出L到地就无通路；负载管T3则因栅极电位为V<sub>DD</sub>, V<sub>GS3</sub>>V<sub>T3</sub>而导 通。输出端L的电平V<sub>OL</sub>为：<p>
V<sub>OL</sub> = V<sub>DD</sub> - V<sub>T3</sub> = 12V - 4V = 8V n 即输出高电平。通过以上分析可知，图3.3.5电路“输入有高输出则 低，输入全低输出则高” ，因此是个正逻辑的或非门，具有以下的输入、输出逻辑关系：<p>
L = !(A+B)
####(3) 与或非门
如图3-21所示的是一个NMOS与或非门电路，图中T1,T2,T3均为工作管，T4为负载管，它们均为增强型NMOS管。工作管的跨导都比负载管大很多，它们的基极B均接地。 
![](/assets/91.PNG)
<p>
####电路的逻辑功能分析 
**①当输入A、B全高或输入C为高电平时**，输出 端L到地有通路(T1、T2通或T3通)，此时T4是 导通的，因此根据跨导比，L输出为低电平，且接近为1V。 
**②当A、B中有低，且C为低电平时**，L输出到地 无通路， 而T4是导通的，L输出为高电平为<p>
 (V<sub>OH</sub>=V<sub>DD</sub>-V<sub>T4</sub>=8V)。<p> 
 因此，该电路为与或非门： L=!(AB+C) <p>
####分析总结： 
由上述NMOS门电路可总结出如下规律：**工作管相串，起“与”的作用；工作管相并，起 “或”的作用；先串后并，则是先 “与”后“或” ；先并后串，则是先 “或”后“与” ；工作管组和一个负载管串联后，在它们连接点引出的输出起倒相作用**。根据以上的总结规律，我们不难推出图3-22 电路也是一个或与非门，其输入、输出逻辑 关系表达式为： <p>
L = !((A+B)(C+D)) 






 















