def encode_text(str1, k):
    temp = ''
    for j in str1:
        if j in 'abcdefghijklmnopqrstuvwxyz':
            temp+=chr((ord(j)-ord('a')+k)%26+ord('a'))
        elif j in 'ABCDEFGHIJKLMNOPQRSTUVWXYZ':
            temp+=chr((ord(j)-ord('A')+k)%26+ord('A'))
        else:
            temp+=j
    return temp
def decode_text(str1, k):
    temp = ''
    for j in str1:
        if j in 'abcdefghijklmnopqrstuvwxyz':
            temp+=chr((ord(j)-ord('a')-k)%26+ord('a'))
        elif j in 'ABCDEFGHIJKLMNOPQRSTUVWXYZ':
            temp+=chr((ord(j)-ord('A')-k)%26+ord('A'))
        else:
            temp+=j
    return temp
def brutforce(str1):
    arr = []
    for i in range(0,26):
        temp=''
        print(str(i)+": ", end = '')
        for j in str1:
            if j in 'abcdefghijklmnopqrstuvwxyz':
                temp+=chr((ord(j)-ord('a')-i)%26+ord('a'))
            elif j in 'ABCDEFGHIJKLMNOPQRSTUVWXYZ':
                temp+=chr((ord(j)-ord('A')-i)%26+ord('A'))
            else:
                temp+=j
        print(temp)
        arr.append(temp.count('e')+temp.count('E'))
    j = 0
    m1 = arr[0]
    for i in range(1,len(arr)):
        if m1 < arr[i]:
            j = i
            m1 = arr[i]
    return j

text = input('Введите текст на английском:')
encode = encode_text(text, 8)
print("Зашифрованная фраза:",encode)
print("Брутфорс:")
k = brutforce(encode)
decode = decode_text(encode, k)
print("Скорее всего эта фраза: ",decode)
