# 剑指offer

### 栈的压入弹出序列

模拟

```cpp
public:
    bool IsPopOrder(vector<int> pushV,vector<int> popV) {
        if(pushV.size() == 0) return false;
        vector<int> stack;
        for(int i = 0,j = 0 ;i < pushV.size();){
            stack.push_back(pushV[i++]);
            while(j < popV.size() && stack.back() == popV[j]){
                stack.pop_back();
                j++;
            }      
        }
        return stack.empty();
    }
};
```

### 二叉搜索树的后序遍历序列

1. 后序遍历的性质
2. 二叉搜索树的性质

```cpp
class Solution {
    bool judge(vector<int>& a, int l, int r){
        if(l >= r) return true;
        int i = r;
        while(i > l && a[i - 1] > a[r]) --i;
        for(int j = i - 1; j >= l; --j) if(a[j] > a[r]) return false;
        return judge(a, l, i - 1) && (judge(a, i, r - 1));
    }
public:
    bool VerifySquenceOfBST(vector<int> a) {
        if(!a.size()) return false;
        return judge(a, 0, a.size() - 1);
    }
};
```

**&lt;剑&gt;字符串的排列**　我的方法：大致结构：“for循环”套“递归”。注意点：1. 避免重复\(为什么，当前选中的位置，对于两个相同的字符，不能算两次～\)  
**&lt;剑&gt;字符串的组合** 　  
**&lt;剑&gt;**

\*\*\*\*



