Quick Note Before Blog is built.
---------------------------------
# [Q1: 366. Find Leaves of Binary Tree](https://leetcode.com/problems/find-leaves-of-binary-tree/)
### Pointer Pass in a function call
		```C++
		void function(TreeNode *root) {
			root = NULL;
			root->left = NULL;
			root->right = NULL;

		}
		
		int main() {
			//root!=NULL, root->left!=NULL;, root->right!=NULL;
			function(root);
			cout<<root==NULL<<root->left==NULL<<root->right==NULL<<endl;
		
		}
		```

		*result:*011
aaaa
	dddd
```C++
int main() {
	int a =  max(12,32);
	return 100;
}
```
