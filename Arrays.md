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
          
### 3.  [Party of couples](https://practice.geeksforgeeks.org/problems/alone-in-couple5507/1)
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
### 4. [Rotate an array](https://practice.geeksforgeeks.org/problems/reversal-algorithm5340/1?utm_source=gfg&utm_medium=article_practice_tab&utm_campaign=article_practice_tab)
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

### 5. [Leaders in an array](https://practice.geeksforgeeks.org/problems/leaders-in-an-array-1587115620/1?utm_source=gfg&utm_medium=article&utm_campaign=bottom_sticky_on_article)
    
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
      
### 6. [Product array](https://practice.geeksforgeeks.org/problems/product-array-puzzle4525/1?utm_source=gfg&utm_medium=article&utm_campaign=bottom_sticky_on_article)
    class Solution:
        def productExceptSelf(self, nums, n):
            #code here
            p=[]
            for i in range(n):
                prod=1
                for j in range(n):
                    if j==i:
                        continue
                    prod=prod*nums[j]
                p.append(prod)
            return p
            
### 7. [Find 2 repeating elements](https://practice.geeksforgeeks.org/problems/two-repeated-elements-1587115621/1?utm_source=gfg&utm_medium=article&utm_campaign=bottom_sticky_on_article)
    Method 1:
    def twoRepeated(self, arr , N):
        Your code here
         m={}
         res=[]
         for i in range(N):
             if arr[i] in m:
                 m[arr[i]]+=1
             else:
                 m[arr[i]]=1
        
         for key in m:
             if m[key]==2:
                 res.append(key)
         return res
    
    Method 2: 
    def twoRepeated(self, arr , N):
        count=[0]*N
        res=[]
        for i in range(N):
            if count[arr[i]]==1 :
                res.append(arr[i])
            else:
                count[arr[i]]+=1
                
                
        return res
        
### 8. [Missing number in an array](https://practice.geeksforgeeks.org/problems/missing-number-in-array1416/1?utm_source=gfg&utm_medium=article_practice_tab&utm_campaign=article_practice_tab)
    Method 1:
    class Solution:
    def MissingNumber(self,arr,n):
        total=n*(n+1)/2
            sumofarr=sum(arr)
            return int(total-sumofarr)
    
    Method 2:
    class Solution:
    def MissingNumber(self,arr,n):
        # code 
        size=n-1
        arr.sort()
        #dealing with single element
        if size==1:
            if arr[0]!=1:
                return 1
            else:
                return n
        # dealing with multiple element
        if arr[0]!=1:
            return 1
        else:
            for i in range(size-1):
                if(arr[i+1]-arr[i]>1):
                    return arr[i]+1
            return n
                   
### 9. [Trapping rainwater](https://practice.geeksforgeeks.org/problems/trapping-rain-water-1587115621/1?utm_source=gfg&utm_medium=article&utm_campaign=bottom_sticky_on_article)
    class Solution:
    def trappingWater(self, arr,n):
        #Code here
        leftmax=0
        rightmax=0
        ans=0
        left=0
        right=n-1
        while(left<right):
            if (arr[left]<arr[right]):
                if (leftmax>arr[left]):
                    ans +=(leftmax-arr[left])
                    left+=1
                else:
                    leftmax=arr[left]
                    left+=1
            else:
                if rightmax>arr[right]:
                    ans=ans + rightmax-arr[right]
                    right-=1
                else:
                    rightmax=arr[right]
                    right-=1
        return ans


### 10. [Merge arrays](https://practice.geeksforgeeks.org/problems/merge-two-sorted-arrays-1587115620/1?utm_source=gfg&utm_medium=article&utm_campaign=bottom_sticky_on_article)
    class Solution:
    
    #Function to merge the arrays.
    def merge(self,arr1,arr2,n,m):
        #code here
        arr3 = arr1+arr2
        arr3.sort()
        for i in range(len(arr3)):
            if i<n:
                arr1[i]=arr3[i]
            else:
                arr2[i-n]=arr3[i]
        return arr3  

### 11. [Nuts and Bolts](https://practice.geeksforgeeks.org/problems/nuts-and-bolts-problem0431/1?utm_source=gfg&utm_medium=article&utm_campaign=bottom_sticky_on_article)
    class Solution:

	def matchPairs(self,nuts, bolts, n):
		# code here
		for i in range(n):
		    for j in range(i,n):
		        if nuts[i]==bolts[j]:
		            temp=bolts[j]
		            bolts[j]=bolts[i]
		            bolts[i]=temp
		            break
		nuts.sort()
		bolts.sort()
### 12. [Common Elements](https://practice.geeksforgeeks.org/problems/common-elements1132/1?utm_source=gfg&utm_medium=article&utm_campaign=bottom_sticky_on_article)
	class Solution:
    def commonElements (self,A, B, C, n1, n2, n3):
        # your code here
        res=[]
        set1=set()
        set2=set()
        set3=set()
        for i in range(n1):
            set1.add(A[i])
        for i in range(n2):
            set2.add(B[i])
        for i in range(n3):
            if (C[i] in set1 and C[i] in set2):
                if C[i] not in res:
                    res.append(C[i])
        return res

### 13. [Greater on right side](https://practice.geeksforgeeks.org/problems/greater-on-right-side4305/1)
	class Solution:

	def nextGreatest(self,arr, n):
		# code  here
		#for i in range(n-1):
		#arr[i]=max(arr[i+1:n:1])
		#arr[n-1]=-1
		maxele=-1
		for i in range(n-1,-1,-1):
		    temp=arr[i]
		    arr[i]=maxele
		    maxele=max(maxele,temp)
		    
		    		    

### 14. [Two numbers with odd occurrences](https://practice.geeksforgeeks.org/problems/two-numbers-with-odd-occurrences5846/1?utm_source=gfg&utm_medium=article&utm_campaign=bottom_sticky_on_article)
	class Solution:
	    def twoOddNum(self, arr, n):
		# code here
		map={}
		res=[]
		for i in range(n):
		    if arr[i] in map:
			map[arr[i]]+=1
		    else:
			map[arr[i]]=1
		for key in map:
		    if map[key]%2!=0:
			res.append(key)
		res.sort(reverse=True)
		return res
		
### 15. 








