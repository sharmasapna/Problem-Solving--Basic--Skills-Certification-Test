## Problem Solving (Basic) Skills Certification Test HackerRank
### nearlySimilarRectangles
```ruby
def nearlySimilarRectangles(sides):
    # Write your code here
    #print(sides)
    dic ={}
    for val in sides:
        ratio = val[0]/val[1] 
        if ratio in dic:
            dic[ratio] +=1
        else:
            dic[ratio]  =1 
    
    def fact(n):
        if n == 0 or n == 1:
            return 1
        res = 1
        for val in range(1,n+1):
            res = res*val
        return res
    def ncr(n,r):
        ncr = fact(n)/(fact(n-r)*fact(r))
        return ncr
    #print(dic)
    res = 0
    for i,v in dic.items():
        if v >1:
            #print(v)
            comb = ncr(v,2)
            #print(comb)
            res += comb
    return (int(res))
```
### filledOrders
```ruby
def filledOrders(order, k):
    # Write your code here
    order.sort()
    c = 0
    for i in range(0,len(order)):
        if order[i]<=k:
            c+=1
            k=k-order[i]
    return c
```
