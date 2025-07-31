# Binary Tree Zigzag Level Order Traversal - LeetCode
  
  ## Problem Description
  
  Can you solve this real interview question? Binary Tree Zigzag Level Order Traversal - Given the root of a binary tree, return the zigzag level order traversal of its nodes' values. (i.e., from left to right, then right to left for the next level and alternate between).
  
  ### Examples:
  ```
  Example 1:

[https://assets.leetcode.com/uploads/2021/02/19/tree1.jpg]


Input: root = [3,9,20,null,null,15,7]
Output: [[3],[20,9],[15,7]]


Example 2:


Input: root = [1]
Output: [[1]]


Example 3:


Input: root = []
Output: []
  ```
  
  ### Constraints:
  
  Constraints:

 * The number of nodes in the tree is in the range [0, 2000].
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
    def zigzagLevelOrder(self, root):
        """
        :type root: Optional[TreeNode]
        :rtype: List[List[int]]
        """
        if not root:
            return []

        q = deque([root])
        res = []
        rev = False
        while q:
            l_size = len(q)
            level = []

            for _ in range(l_size):
                x = q.popleft()
                level.append(x.val)
                if x.left:
                    q.append(x.left)
                if x.right:
                    q.append(x.right)
            if rev: 
                level.reverse()
                rev = False
            else:
                rev = True
            res.append(level)
        
        return res
  ```
  