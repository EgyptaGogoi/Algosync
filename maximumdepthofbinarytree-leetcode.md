# Maximum Depth of Binary Tree - LeetCode
  
  ## Problem Description
  
  Can you solve this real interview question? Maximum Depth of Binary Tree - Given the root of a binary tree, return its maximum depth.

A binary tree's maximum depth is the number of nodes along the longest path from the root node down to the farthest leaf node.
  
  ### Examples:
  ```
  Example 1:

[https://assets.leetcode.com/uploads/2020/11/26/tmp-tree.jpg]


Input: root = [3,9,20,null,null,15,7]
Output: 3


Example 2:


Input: root = [1,null,2]
Output: 2
  ```
  
  ### Constraints:
  
  Constraints:

 * The number of nodes in the tree is in the range [0, 104].
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
    def maxDepth(self, root):
        """
        :type root: Optional[TreeNode]
        :rtype: int
        """
        def func(root, count):
            if root:
                count += 1
                if not root.left and not root.right:
                    return count
                return max(func(root.left, count), func(root.right, count))
            return 0
        return func(root, 0)
  ```
  