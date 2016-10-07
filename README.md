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
If we want to the value of pointer root also can be changed, we need to pass the reference of the pointer.
```C++
void function(TreeNode *&root) {
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
Looks wired, but it does work. However, new problems show up.
### Parameters pass in the recursive program
```C++
//Correct Recursive Function Call
void getHeight(TreeNode *root){
	if(root == NULL) return -1;
	int height = 1 + max(getHeight(root->left),getHeight(root->right));
	return height;
}


//Wrong Recursive Function Call
void getHeight(TreeNode *&root){
	if(root == NULL) return -1;
	int height = 1 + max(getHeight(root->left),getHeight(root->right));
	return height;
}
```
Because recursive function call need [Value Pass] in the function calls

### More attention on the NULL pointer process.
There are many position we can deal with the NULL judgement or children's NULL judgement.
+ Outside of the recursive function
+ On the begin of the recursive function
+ When we set a *if* statement to judge if the node is a NULL, then there is no need to judge its children again, because the children-judgement will be executed on the next level of recursive.

### Read more standard program on BOOKS!
