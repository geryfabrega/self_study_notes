I learned this lesson on 12/13/2025

When Traversing a tree never access a child item, always traverse at the particular level, otherwise an error will be thrown.

For instance

# Good Example

```
void travel(root)
	while(root != nullptr){
	    travel(root.left);
	    std::cout << root.val;
	    travel(root.right);
    }
```

# Bad Example
```
void travel(root)
	while(root != nullptr){
	    travel(root.left);
	    std::cout << root.val;
	    std::cout << root->left->val;
	    std::cout << root->right->val:
	    travel(root.right);
    }

```
This will break! The left or right child node could be Null! Please dont do this.

