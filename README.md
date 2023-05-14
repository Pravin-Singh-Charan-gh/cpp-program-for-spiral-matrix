    vector<int> spiralOrder(vector<vector<int>>& matrix) {
        int row=matrix.size(),col=matrix[0].size();
        int total=row*col;
        int srow=0,scol=0;
        int erow=row-1,ecol=col-1;
        int count=0;
        vector<int>ans;
        while(count<total){
            for(int i=scol;i<=ecol && count<total;count++,i++)
             ans.push_back(matrix[srow][i]);
             srow++;

            for(int i=srow;i<=erow && count<total;count++,i++)
             ans.push_back(matrix[i][ecol]);
             ecol--;

            for(int i=ecol;i>=scol && count<total;count++,i--)
             ans.push_back(matrix[erow][i]);
             erow--;

            for(int i=erow;i>=srow && count<total;count++,i--)
             ans.push_back(matrix[i][scol]);
             scol++;  
        }
        return ans;
    }
