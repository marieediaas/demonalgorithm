import math
import random as rd
import matplotlib.pyplot as plt

esys = 10                            #Energia total do sistema
edemon = 0                           #Energia inicial do demônio
N = 40                               #Número de partículas
v0 = (math.sqrt(2*esys/N))           #Velocidade inicial por partícula dada a energia total do sistema
v = list(range(40))                  #Vetor que guarda todas as velocidades das N partículas
accm = 0                             #Contador de mudanças aceitas
somadasvel = 0                       #Soma das velocidades após mudanças
vq = 0                               #Variável utilizada para contar a energia total do sistema após mudanças
tt = 0                               #Variável que contabiliza o tempo
mediasv = list(range(1000))          #Vetor que guarda a media das velocidades por tempo t
temp = list(range(1000))             #Vetor que guarda a informação do t
velpar1 = list(range(1000))          #Vetor que guarda a velocidade da particula 1

for i in range(40):                  #Dando a mesma velocidade inicial para todas as particulas
 v[i] = v0
 
 
for t in range(1000):
#No laço a seguir, N vezes escolhemos uma partícula para mudar sua velocidadee vemos se a mudança é aceita
 
 for i in range(40):
   r = rd.randint(0,(N-1)) #Escolhe uma partícula aleatoriamente
   #print("Particula escolhida",r)
   dv = rd.uniform(-v0,v0) #Gera uma mudança de velocidade
   #print("Mudanca na velocidade", dv)
   dE = (0.5*((v[r]+dv)**2 - v[r]**2)) #Calcula a mudança na energia
   #print("mudanca na energia",dE)
   
   if(dE <= 0):
     edemon = edemon - dE
     accm += 1 #Mudança aceita
     v[r] = v[r] + dv #Nova velocidade da particula r
     
   if(dE>0 and dE<=edemon):
      edemon = edemon - dE
      accm += 1 #Mudança aceita
      v[r] = v[r] + dv #Nova velocidade da particula r
 for j in v:
   somadasvel += j
   mediav = (somadasvel/40) #Media das velocidades da particulas
   mediasv[t] = mediav #Media das velocidades no tempo t
   tt += 1 #Variavel tempo incrementada
   temp[t] = tt #Vetor do tempo guarda o valor de tt
   velpar1[t] = v[1] #Vetor que guarda a velocidade da particula 1 no tempo t
   
#No laço a seguir calcula-se a energia total do sistema baseado nas novas velocidades das particulas

for q in range(40):
 vq = vq + (v[q]**2)/2
 
print("Energia Total do Sistema",vq)
print("Energia do demonio",edemon)

'''Plotando o grafico da velocidade de uma particula especifica em
funcao do tempo'''
plt.plot(temp,velpar1)
plt.axis([0, 100, -50, 100])
plt.xlabel("Tempo")
plt.ylabel("Velocidade da Particula 1")
plt.show()

'''Plotando o grafico da media das velocidades das particulas em funcao
do tempo'''
plt.plot(temp, mediasv)
plt.axis([0, 1000, -50, 100])
plt.xlabel("Tempo")
plt.ylabel("Média das velocidades das partículas")
plt.show()
