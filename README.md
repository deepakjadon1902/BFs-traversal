class Solution {
//Function to return Breadth First Traversal of given graph.
    public ArrayList<Integer> bfsOfGraph(int V, ArrayList<ArrayList<Integer>> adj) {
// Code here
        ArrayList<Integer>ans= new ArrayList<>();
        Queue<Integer>q = new LinkedList<>();
        int n = adj.size();
        boolean[]visited = new boolean[n];
        q.add(0);
        visited[0] = true;
        while(!q.isEmpty()){
            int pop = q.poll();
            ans.add (pop);
            for(int i = 0;i<adj.get(pop).size();i++){
                int curr = adj.get(pop).get(i);
                if(!ans.contains(curr) && visited[curr] != true){
                    q.add (curr);
                    visited[curr] = true;
                }
            }
        }
        return ans;
}
}
