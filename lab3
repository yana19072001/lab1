def binstr16(str1):
    return ''.join(format(ord(x), '016b') for x in str1)
def binstr32(str1):
    return ''.join(format(ord(x), '032b') for x in str1)
def bin4(it):
    k = bin(it)[2:]
    return (4 - len(k))*'0'+k
def change(x):
    array = []
    for i in range(0,len(x),4):
        array.append(int(x[i:i+4],2))
    s1 = [9,6,3,2,8,11,1,7,10,4,14,15,12,0,13,5][array[0]]
    s2 = [3,7,14,9,8,10,15,0,5,2,6,12,11,4,13,1][array[1]]
    s3 = [14,4,6,2,11,3,13,8,12,15,5,10,0,7,1,9][array[2]]
    s4 = [14,7,10,12,13,1,3,9,0,2,11,4,15,8,5,6][array[3]]
    s5 = [11,5,1,9,8,13,15,0,14,4,2,3,12,7,10,6][array[4]]
    s6 = [3,10,13,12,1,2,0,11,7,5,9,4,8,15,14,6][array[5]]
    s7 = [1,13,2,9,7,10,6,0,8,12,4,5,15,3,11,14][array[6]]
    s8 = [11,10,15,5,0,12,14,8,6,2,3,9,1,7,13,4][array[7]]
    res = bin4(s1)+bin4(s2)+bin4(s3)+bin4(s4)+bin4(s5)+bin4(s6)+bin4(s7)+bin4(s8)
    return res
def strbin(bin1):
    array = ''
    for i in range(0,len(bin1),16):
        array+= chr(int(bin1[i:i+16],2))
    return array

def xor(str1, str2):
    res =''
    for i in range(len(str1)):
        if str1[i] == str2[i]:
            res+='0'
        else:
            res+='1'
    return res
def encr(key256, mess):
    array = []
    for i in range(0,len(mess), 64):
        array.append(mess[i:i+64])
    keys = []
    for i in range(0, len(key256), 32):
        keys.append(key256[i:i+32])
    res = ''
    for g in array: 
        r = g[32:]
        l = g[:32]
        i=1
        while i < 33:
            if i <25:
                j = (i-1)%8
            else:
                j = (32-i)%8
            r1 = bin((int(r,2)+int(keys[j],2))%2**32)[2:]
            r1 = (32-len(r1))*'0'+r1
            r1 = change(r1)
            r1 = r1[11:]+r1[:11]
            r1 = xor(r1, l)
            l1 = r
            
            r = r1
            l = l1
            i+=1
            
        res += l+r
    return res
def decr(key256, mess, count):
    array = []
    for i in range(0,len(mess), 64):
        array.append(mess[i:i+64])
    keys = []
    for i in range(0, len(key256), 32):
        keys.append(key256[i:i+32])
    res = ''
    for g in array: 
        r = g[32:]
        l = g[:32]
        i=1
        while i < 33:
            if i <9:
                j = (i-1)%8
            else:
                j = (32-i)%8
            l1 = bin((int(l,2)+int(keys[j],2))%2**32)[2:]
            l1 = (32-len(l1))*'0'+l1
            l1 = change(l1)
            l1 = l1[11:]+l1[:11]
            l1 = xor(l1, r)
            r1 = l

            r = r1
            l = l1
            i+=1
        res += l+r
    return res[:-count]
mess = input("Введите вашу фразу:\n")
mess = binstr16(mess)
count = (64 - len(mess)%64)
mess+= count*'0'
key = "zaqwsxcderfvbgty"
key = binstr16(key)
encrypt_text= encr(key, mess)
print("Зашифрованная фраза:")
print(strbin(encrypt_text))
decrypt_text = decr(key, encrypt_text, count)
print("Расшифрованная фраза:")
print(strbin(decrypt_text))
