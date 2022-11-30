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
          
### 3.           
