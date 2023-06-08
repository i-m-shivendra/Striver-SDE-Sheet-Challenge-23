#include <bits/stdc++.h>
bool isSafe(int x, int y, int n, vector<vector<int>> &visited, vector<vector<int>> &maze) {
  if((x >= 0 && x < n) && (y >= 0 && y < n) && visited[x][y] == 0 && maze[x][y] == 1) return true;
  return false;
}

void findPath(int x, int y, vector<vector<int>> &maze, int n, vector<vector<int>> &visited, vector<vector<int>> &ans) {
  // Base Case
  if (x == n - 1 && y == n - 1) {
    vector<int> temp;
    visited[x][y] = 1;
    
    for (int i = 0; i < n; i++)
      for (int j = 0; j < n; j++)
        temp.push_back(visited[i][j]);

    visited[x][y] = 0;
    ans.push_back(temp);
    

    return;
  }

  visited[x][y] = 1;

  // Down
  int newX = x + 1;
  int newY = y;
  if(isSafe(newX, newY, n, visited, maze)) {
    findPath(newX, newY, maze, n, visited, ans);
  }

  // Up
  newX = x - 1;
  newY = y;
  if(isSafe(newX, newY, n, visited, maze)) {
    findPath(newX, newY, maze, n, visited, ans);
  }


  // Left
  newX = x;
  newY = y - 1;
  if(isSafe(newX, newY, n, visited, maze)) {
    findPath(newX, newY, maze, n, visited, ans);
  }

  // Right
  newX = x;
  newY = y + 1;
  if(isSafe(newX, newY, n, visited, maze)) {
    findPath(newX, newY, maze, n, visited, ans);
  }

  visited[x][y] = 0;
}

vector<vector<int>> ratInAMaze(vector<vector<int>> &maze, int n){
  vector<vector<int>> visited(n, vector<int> (n, 0));
  vector<vector<int>> ans;

  if(maze[0][0] == 0) return ans;
  findPath(0, 0, maze, n, visited, ans);

  return ans;

}
