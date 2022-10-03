# Devika
#Read a matrix dimension , and print the matrix filled with consecutive numbers starting from 1

print("Enter the number of rows of the matrix")
row=int(input(''))
print("Enter the number of column of the matrix")
col=int(input(''))
print("Display Matrix")

mat = [[0 for x in range(row)] for y in range(col)] 
mat[0][0]=1
mat[col-1][row-1]=row*col
imax=0
jmax=0
i=1
j=0

for count in range(2,(col*row)):
    if(i>imax):
        imax=i
    if(j>jmax):
        jmax=j
    mat[i][j]=count
    if(i==0 or j==row-1):
        if(imax>=col-1):
            i=col-1
        else:
            i=imax+1
        for col in range(row):
            if(mat[i][col]==0):
                j=col
                break
    elif(i!=0):
        j+=1
        i-=1
    elif(i==j):
        j+=1
        i-=1


for i in mat:
    for j in i:
        print(j,end=' ')
    print('')
