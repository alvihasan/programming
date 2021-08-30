// A C++ program to find maximal
// Bipartite matching.
#include <iostream>
#include <string.h>
#include<bits/stdc++.h>
using namespace std;

// M is number of applicants
// and N is number of jobs
int M,N;
int bpGraph[105][105];
int matchR[105];
int seen[105];

// A DFS based recursive function
// that returns true if a matching
// for vertex u is possible
int bpm(int u)
{
	// Try every job one by one
	for (int v = 0; v < N; v++)
	{
		// If applicant u is interested in
		// job v and v is not visited
		if (bpGraph[u][v] && !seen[v])
		{
			// Mark v as visited
			seen[v] = 1;

			// If job 'v' is not assigned to an
			// applicant OR previously assigned
			// applicant for job v (which is matchR[v])
			// has an alternate job available.
			// Since v is marked as visited in
			// the above line, matchR[v] in the following
			// recursive call will not get job 'v' again
			if (matchR[v] < 0 || bpm(matchR[v]))
			{
				matchR[v] = u;
				return 1;
			}
		}
	}
	return 0;
}

// Returns maximum number
// of matching from M to N
int maxBPM()
{
	// An array to keep track of the
	// applicants assigned to jobs.
	// The value of matchR[i] is the
	// applicant number assigned to job i,
	// the value -1 indicates nobody is
	// assigned.

	// Initially all jobs are available
	memset(matchR, -1, sizeof(matchR));

	// Count of jobs assigned to applicants
	int result = 0;
	for (int u = 0; u < M; u++)
	{
		// Mark all jobs as not seen
		// for next applicant.
		memset(seen, 0, sizeof(seen));

		// Find if the applicant 'u' can get a job
		if (bpm(u))
			result++;
	}
	return result;
}

// Driver Code
int main()
{
	// Let us create a bpGraph
	// shown in the above example
	int t,a1,b1;
	int a[105],b[105];
	cin>>t;
	while(t--)
    {
        memset(bpGraph, 0, sizeof(bpGraph));
        cin>>M;
        for(int i=0;i<M;i++)
            cin>>a[i];
        cin>>N;
        for(int i=0;i<N;i++)
            cin>>b[i];

    for(int i=0;i<N;i++)
    {
        b1=b[i];
        for(int j=0;j<M;j++)
        {
            a1=a[j];
            if(b1%a1==0)
        {


           bpGraph[j][i]=1;
        }
        }

    }

	cout << "Maximum number of applicants that can get job is "<< maxBPM()<<endl;
    }
	return 0;
}

