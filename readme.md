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
### unexpected-demands
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
### vowel-substring
```ruby
def findSubstring(s, k):
    # Write your code here
    vowels = {"a","e","i","o","u"}
    i=0
    res = ""
    substr = s[0:k]
    vowel_count = 0
    for val in substr:
            if val in vowels:
                vowel_count +=1
    max_v = vowel_count
    if   vowel_count >0:
        res = substr          
    start = 1
    end = start+k
    while end <=len(s):
        #print("startend",start,end)
        if s[start-1] in vowels:
            vowel_count -=1
            #print("start",s[start],vowel_count)
        if s[end-1] in vowels:
            vowel_count +=1
            #print(s[end-1],vowel_count)
        if vowel_count > max_v:
            #print(start,end)
            res = s[start:end]
            max_v = vowel_count
        #print(s[start],s[end-1])
        #print(start,end,vowel_count,max_v,s[start:end])
        start+=1
        end+=1 
    if res:
        return res
    else :
        return "Not found!"
    ```
