Schedular:

Deceides which pod on which Node and informs to APi server. Then APi server informs to kubelet in that Node and creates it.

If the application needs 10 CPU and Windows Server. We won't be having all nodes of 10 CPUs. Schedular will eliminates the unfits ones and selects the good fit.
Schedular Ranks the node list for a best fit. 
In the above case, it searches the more than 10 CPU and then minise the particular CPU with the Node's CPU and finds the best.
We can write the schedular 
