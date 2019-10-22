# 3、leetcode999. 车的可用捕获量
解法一：
--  
思路：
--
    上下左右移动法。  
代码： 
--
<pre>
/**
 * @author lihe
 * @date 2019/10/22 13:14
 * @descriptor  999. 车的可用捕获量
 */
public class NumRookCaptures_999 {
    public static int numRookCaptures(char[][] board) {
        int count = 0,rockX = 0,rockY = 0;
        for (int i = 0; i < board.length; i++) {
            for (int j = 0; j < board[0].length; j++) {
                if(board[i][j] == 'R'){
                    rockX = i;
                    rockY = j;
                    break;
                }
            }
        }
        //向上
        int tempX = rockX-1,tempY = rockY;
        while(tempX >= 0){
            if(board[tempX][tempY] == 'p'){
                count ++;
                break;
            }if(board[tempX][tempY] == 'B')
                break;
            tempX --;
        }
        //向下
        tempX = rockX + 1;
        tempY = rockY;
        while(tempX <= 8){
            if(board[tempX][tempY] == 'p'){
                count ++;
                break;
            }if(board[tempX][tempY] == 'B')
                break;
            tempX ++;
        }
        //向左
        tempX = rockX;
        tempY = rockY - 1;
        while(tempY >= 0){
            if(board[tempX][tempY] == 'p'){
                count ++;
                break;
            }if(board[tempX][tempY] == 'B')
                break;
            tempY --;
        }
        //向右
        tempX = rockX;
        tempY = rockY + 1;
        while(tempY <= 8){
            if(board[tempX][tempY] == 'p'){
                count ++;
                break;
            }if(board[tempX][tempY] == 'B')
                break;
            tempY ++;
        }
        return count;
    }
    public static void main(String[] args) {
        char[][] chars = {{'.','.','.','.','.','.','.','.'},
                        {'.','.','.','p','.','.','.','.'},
                        {'.','.','.','R','.','.','.','p'},
                        {'.','.','.','.','.','.','.','.'},
                        {'.','.','.','.','.','.','.','.'},
                        {'.','.','.','p','.','.','.','.'},
                        {'.','.','.','.','.','.','.','.'},
                        {'.','.','.','.','.','.','.','.'}};
        int i = numRookCaptures(chars);
        System.out.println(i);
    }
}
</pre>
