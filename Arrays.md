### 2. [Majority Element](https://practice.geeksforgeeks.org/problems/majority-element-1587115620/1?utm_source=gfg&utm_medium=article&utm_campaign=bottom_sticky_on_article)
    class Solution:
      def majorityElement(self, A, N):
          #Your code herel
          # for i in range(N):
          #     count=0
          #     for j in range(N):
          #         if (A[i]==A[j]):
          #             count=count+1
          #     if count>N/2:
          #         return A[i]
          # return -1
          m={}
          for i in range(N):
              if A[i] in m:
                  m[A[i]]+=1
              else:
                  m[A[i]]=1

          for key in m:
              if m[key]>N/2:
                  return key

          return -1
          
### 3.  [Find the number occuring odd number of times](https://practice.geeksforgeeks.org/problems/alone-in-couple5507/1)
    #User function Template for python3

    class Solution:
        def findSingle(self, N, arr):
            # code here
            m={}

            for i in range(N):
                if arr[i] in m:
                    m[arr[i]]+=1
                else:
                    m[arr[i]]=1
            for key in m:
                if m[key]==1:
                    return key        
### 5. [Rotate an array](https://practice.geeksforgeeks.org/problems/reversal-algorithm5340/1?utm_source=gfg&utm_medium=article_practice_tab&utm_campaign=article_practice_tab)
    class Solution:
    
    def reverseArray(self,arr,start,end):
        while(start<end):
            temp = arr[start]
            arr[start] = arr[end]
            arr[end] = temp
            start+=1
            end-=1
            
    def leftRotate(self, arr, n, d):
        # code here
        if d==0:
            return
            
        d=d%n
        ob.reverseArray(arr,0,d-1)
        ob.reverseArray(arr,d,n-1)
        ob.reverseArray(arr,0,n-1)

### 6. [Leaders in an array](https://practice.geeksforgeeks.org/problems/leaders-in-an-array-1587115620/1?utm_source=gfg&utm_medium=article&utm_campaign=bottom_sticky_on_article)
    
class Solution:
    #Back-end complete function Template for Python 3
    
    #Function to find the leaders in the array.
    def leaders(self, arr, N):
        #Code here
        res=[arr[N-1]]
        for i in range(N-2,-1,-1):
            flag=True
            for j in range(N-1,i,-1):
                if(arr[i]<arr[j]):
                    flag=False
                    break
            if flag==True:
                res.insert(0,arr[i])
        return res
      
###                 
                
                
                
                
                
