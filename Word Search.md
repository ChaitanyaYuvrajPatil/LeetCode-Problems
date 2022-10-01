## Problem : Word Search

Problem link : https://leetcode.com/problems/word-search/description/

### Solution :
- backtracking problem

```C++
class Solution {
public:
    bool exist(vector<vector<char>>& board, string word) {
        
        for(int i=0;i<board.size();i++)
        {
            for(int j=0;j<board[0].size();j++)
            {
                if(word[0] == board[i][j] && track(board,i,j,word,0)) 
                    return true;
            }
        }

        return false;
    }

    bool track(vector<vector<char>>& board,int i,int j,string word,int pos)
    {
        if(pos == word.size()) return true;
        if(i<0 || j<0 || i>=board.size() || j>=board[0].size()) return false;
        if(word[pos] != board[i][j]) return false;
        char temp = board[i][j];
        board[i][j] = '*';

        if(track(board,i+1,j,word,pos+1)||
           track(board,i-1,j,word,pos+1)||
           track(board,i,j+1,word,pos+1)||
           track(board,i,j-1,word,pos+1))
           return true;

        board[i][j] = temp;

        return false;
    }
};
```
