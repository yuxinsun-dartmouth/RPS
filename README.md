# RPS

## Simulation step 
let rule 1 be P(DSU|WTL) and rule 2 be P(RPS|RPS). Assume the emission matrix under the two rules are
Q1 = [[0.1, 0.8, 0.1],
      [1/3, 1/3, 1/3],
      [0.2, 0.1, 0.7]]
and Q2 = [[1/3, 1/3, 1/3],
      [1/3, 1/3, 1/3],
      [1/3, 1/3, 1/3]] 
respectively, and the transition matrix between the two rules is 
P = [[0.9, 0.1],
        [0.9, 0.1]]. We also assume AI is playing RPS randomly at equal probability in each game. Under such assumptions, we can simulate a number of games. 
The result of the simulation is shown in rule-switching in simulation. The human RPS in simulation shows the sequence of RPS under the rules switching. The human WTS in simulation shows the sequence of WTL under the rules switching. The P(DSU|W) shows the empirical distribution is close to the assumption [0.1, 0.8, 0.1]; the ![image](https://user-images.githubusercontent.com/75051599/196277169-4489b3bb-196a-4e26-8e91-53a28af1494a.png)

shows the empirical distribution is close to the assumption [0.2, 0.1, 0.7]; the ![image](https://user-images.githubusercontent.com/75051599/196276981-3ae4ee14-c409-464d-a00d-dd1569df2a48.png)

 shows the empirical distribution is close to the assumption [1/3, 1/3, 1/3]. 

## Inference step
After confirming the simulation is consistent with the assumptions. We implemented the forward and backward algorithms for alpha and beta, which are the standard terms in EM algorithm. With alpha and beta, we can infer the posterior probabilities for the rules after under observation of all games. The result is shown in the graph ![image](https://user-images.githubusercontent.com/75051599/196276600-87e02402-e5a3-4d10-8788-9c7bda594a2a.png)

        
 
