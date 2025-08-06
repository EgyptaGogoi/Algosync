# Binary Tree Right Side View - LeetCode
  
  ## Problem Description
  
  Can you solve this real interview question? Binary Tree Right Side View - Given the root of a binary tree, imagine yourself standing on the right side of it, return the values of the nodes you can see ordered from top to bottom.
  
  ### Examples:
  ```
  Example 1:

Input: root = [1,2,3,null,5,null,4]

Output: [1,3,4]

Explanation:

[https://assets.leetcode.com/uploads/2024/11/24/tmpd5jn43fs-1.png]

Example 2:

Input: root = [1,2,3,4,null,null,null,5]

Output: [1,3,4,5]

Explanation:

[https://assets.leetcode.com/uploads/2024/11/24/tmpkpe40xeh-1.png]

Example 3:

Input: root = [1,null,3]

Output: [1,3]

Example 4:

Input: root = []

Output: []
  ```
  
  ### Constraints:
  
  Constraints:

 * The number of nodes in the tree is in the range [0, 100].
 * -100 <= Node.val <= 100
  
  
  ### Approach:
  ---
  
  #### approach 1:
  

  #### Solution Language:
  ```  Python  ```
  ```
  # Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution(object):
    def rightSideView(self, root):
        """
        :type root: Optional[TreeNode]
        :rtype: List[int]
        """
        if not root:
            return []
        q = deque([root])
        res =[]

        while q:
            level = []
            l = len(q)

            for _ in range(l):
                x = q.popleft()
                level.append(x.val)
                if x.left:
                    q.append(x.left)
                if x.right:
                    q.append(x.right)
            lastEle = len(level)-1
            res.append(level[lastEle])   
        return res
  ```
  

 
  #### approach 2: 

 ``` Python``` 
  ```  

 # Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution(object):
    def rightSideView(self, root):
        """
        :type root: Optional[TreeNode]
        :rtype: List[int]
        """
        if not root:
            return []
        q = deque([root])
        res =[]

        while q:
            level = []
            l = len(q)

            for _ in range(l):
                x = q.popleft()
                level.append(x.val)
                if x.left:
                    q.append(x.left)
                if x.right:
                    q.append(x.right)
            lastEle = len(level)-1
            res.append(level[lastEle])   
        return res 

 ``` 
