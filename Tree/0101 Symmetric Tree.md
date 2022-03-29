#### Things To Note: 
1. use helper function (pass in 2 nodes)!
2. remember to check if node has NO children

```cpp
bool isSymmetric(TreeNode* root) {
    if (root == nullptr) // empty tree is symmetric 
        return true;
    return helper(root->left, root->right);

}

bool helper(TreeNode* p, TreeNode* q) {
    // symmetric if BOTH p,q are nullptr
    if (p == nullptr and q == nullptr) 
        return true;

    // asymmetric if p OR q is nullptr
    else if (p == nullptr or q == nullptr) 
        return false; 

    // check p,q have same value; then compare **mirror nodes**
    // compare L subtree's L child with R subtree's R child 
    // --AND-- L subtree's R child with R subtree's L child
    else 
        return (p->val == q->val and helper(p->left, q->right) and 
                helper(p->right, q->left));
}
```
