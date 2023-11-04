def func(str1,str2):
    array = []
    for i in str2:
        array.append(ord(i)- ord('A'))
    res = ''
    for i in range(len(str1)):
        res += chr((ord(str1[i])-ord("A")+array[i%len(array)])%26+ord('A'))
    return res
def defunc(stru,strk):
    array = []
    for i in strk:
        array.append(ord(i) - ord('A'))
    array2 = []
    for i in stru:
        array2.append(ord(i) - ord('A'))
    str1 = "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
    
    res = ''
    for i in range(len(stru)):
        k = chr(array[i%len(array)]+ord('A'))
        str2 =  str1[str1.find(k):]+str1[:str1.find(k)]
        res += chr( str2.find(stru[i])+ord('A') )
    return res
t = input("Введите фразу\n")
f = input("Введите кодовую фразу\n")
print("Ваша фраза: ", func(t.upper(), f.upper()))
print("Изначальная фраза: ",defunc(func(t.upper(), f.upper()),f.upper()))
