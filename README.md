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
The result of the simulation is shown in rule-switching in simulation as follows
![image](https://user-images.githubusercontent.com/75051599/196277623-b086ac0a-9bcc-4d25-a212-78538883aefb.png)

The human RPS in simulation shows the sequence of RPS under the rules switching. ![image](https://user-images.githubusercontent.com/75051599/196277802-48b22532-63e4-47fe-9588-93eba86c774a.png)

The human WTS in simulation shows the sequence of WTL under the rules switching. ![image](https://user-images.githubusercontent.com/75051599/196277903-d3fff47b-8dfb-4de2-8473-264ce4dca1c1.png)

The graph shows the empirical distribution is close to the assumption [0.1, 0.8, 0.1];
![image](https://user-images.githubusercontent.com/75051599/196277452-e803f755-0adb-48ae-b5f4-234479411f5f.png)

The next graph shows the empirical distribution is close to the assumption [0.2, 0.1, 0.7]; 
![image](https://user-images.githubusercontent.com/75051599/196277169-4489b3bb-196a-4e26-8e91-53a28af1494a.png)

The next graph shows the empirical distribution is close to the assumption [1/3, 1/3, 1/3]. 
![image](https://user-images.githubusercontent.com/75051599/196276981-3ae4ee14-c409-464d-a00d-dd1569df2a48.png)

 

## Inference step
After confirming the simulation is consistent with the assumptions. We implemented the forward and backward algorithms for alpha and beta, which are the standard terms in EM algorithm. With alpha and beta, we can infer the posterior probabilities for the rules after under observation of all games. The result is shown in the graph ![image](https://user-images.githubusercontent.com/75051599/196276600-87e02402-e5a3-4d10-8788-9c7bda594a2a.png)

To show how inference is close to the likelihood of rules at each game, we plot the normalized likelihood of two rules. 
![image](https://user-images.githubusercontent.com/75051599/196278925-ca6b33d3-208b-4a24-9f28-88e610d914ec.png)

Next we start with the known Q1 and Q2 and use EM to learn P transition only. We run a simulation of 1000 games multiple times and plot the distribution of P[1,1] and P[2,2] as follows:

![image](https://user-images.githubusercontent.com/75051599/197563987-e93bfb1e-734e-4b1a-b0d5-728dd1f56614.png)

![image](https://user-images.githubusercontent.com/75051599/197564370-c1e68c9d-5f8a-4b9f-bdcb-7d60df92d80a.png)





        
 
