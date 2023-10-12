# laba2
SL = []
BL = []
AL = []
a = 0

cs = 0
B1 = 0
B2 = 0
B3 = 0

SumC = 0
b = 0
SumL = []
K = []

NS = input("Название магазина(через пробел): ")
NS = list(set(NS.split()))
CS = len(NS)
CB = int(input("Количество товаров: "))
for i in range(CB):
  print('')
  NB = input(f"Название {i+1} товара: ")
  AL.append(NB)
  for j in range(CS):
    P = int(input(f'Введите цену товара в магазине "{NS[j]}": '))
    AL.append(P)
    a += 1
    if a == CS:
      BL.append(AL)
      SL += copy.deepcopy(BL)
      AL.clear()
      BL.clear()
      a = 0
print('')
print("Список товаров и их стоимость в магазинах:", *NS)
for h in range(CB):
  print(*SL[h])
for t in range(1, CS + 1):
  for p in range(CB):
    SumC += SL[p][t]
    b += 1
    if b == CB:
      SumL.append(SumC)
      SumC = 0
      b = 0
print('Всего', *SumL)
MS = min(SumL)
MI = [i for i, j in enumerate(SumL) if j == MS]
print('')
if len(MI) == 1:
  print(f'Минимальное сумма стоимости товаров будет в магазине "{NS[MI[0]]}", она составила: {MS}')
else:
  for k in range(len(MI)):
    K.append(NS[MI[k]])
  print('Минимальное сумма стоимости товаров будет в магазинах:', *K, f', она составила: {MS}')
  
