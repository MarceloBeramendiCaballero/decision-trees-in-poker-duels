<h1> Decision trees as a computational model for mental heuristics in human decision-making: a study of poker duels

 ### [Project Report](https://drive.google.com/file/d/1kzSpuYn2CBFP_Y5qcQrWPmEzANEyOyiU/view?usp=sharing)

<h2>Description</h2>

In Texas Hold'em Poker, it is often said that “you don’t play the cards, you play the players”. This implies that choices which may be correct against one player could be incorrect against another. Some computer models have validated this idea by implementing opponent modeling [1,2]. These models, instead of just making decisions based on the current game state, model the decision making process of the opponent, so that they can exploit their specific weaknesses. 

However, it is one thing to say that opponent modeling is a strategy that works, and a completely different thing to claim that professional poker players are actually performing the mental operation of modeling their opponents. So how can we tell if professional poker players are actually modeling the way their opponents play? It could perfectly be the case that they think they are playing the player and not the cards, but that they really play same against all of their opponents without realizing it. I propose modeling the decision-making process of professional poker players with decision trees to study this. Comparing the resulting tree structure from training the algorithm in relevant datasets could give us an insight into how professional poker players play the game.

I collected data from the show High Stakes Duel, which can be found in the PokerGo streaming platform. I analyzed two duels. The first duel features Phil Hellmuth versus Daniel Negreanu, and the second duel features Phil Hellmuth versus Tom Dwan. These three players are professionals who have been playing the game for years. They have faced each other multiple times, so they are not new to each other’s playstyle. Under the pressure to make decisions quickly with the goal of earning money, it is reasonable to believe they would employ mental heuristics. This mental heuristic could be a decision tree, since people need good rules of thumb to make good choices with the available information, and decision trees thrive doing that. If it is true that poker players are modeling the way their opponents play to change their own strategy, then the decision tree we get for Phil Hellmuth when he plays versus Daniel Negreanu should be different than the decision tree we get when he plays versus Tom Dwan.

Using TensorFlow's dataforest package, I was able to generate decision trees for Phil Hellmuth in different game states. One of the scenarios I looked at was when Hellmuth had to decide between checking and raising (folding is not a real option in these cases because staying in the round is free). The image below shows the resulting decision trees for Hellmuth vs Negreanu and Hellmuth vs Dwan.

<p align="center">
  <img src="https://i.imgur.com/6LuyXb7.png" height="90%" width="90%" alt="Poster"/>

These results are very encouraging because there are very significant differences between both decision trees. The most notable one is that in the Hellmuth vs Negreanu tree, the second layer of the tree shows us that Hellmuth is more likely to raise in either high or low card rankings, but more likely to check in intermediate hand rankings. This makes sense because if you have high chances of winning, you want to maximize your profits. Similarly, if your hand is bad but you don't want to lose money, sometimes you want to bluff, so you raise. However, Hellmuth does not follow the same behavior when playing versus Dwan. In the Hellmuth vs Dwan tree, the second layer shows us that whenever Hellmuth's hand ranking was bad, his preferred option was checking, showing he is less willing to bluff Dwan than he is to bluff Negreanu. This, along with several other findings which can be found in the attached project report, allow us to support the hypothesis that  professional poker players do in fact take into account the playstyle of their opponents when evaluating what decision to make.

While this project only had about 140 data points, and had a very simple design, it is a very important proof of concept: it shows how useful decision trees can be used to study human decision-making. 


<h2>Acknowledgements</h2>
This short paper was one of three class projects I did for COGS 316 at CWRU: Decision-Making, which was taught by Dr. Mark Turner.


<h2>References</h2>
[1] Billings, D., Papp, D., Schaeffer, J., & Szafron, D. (1998). Opponent Modeling in Poker. 7.

[2] Yan, X., Xia, L., Yang, J., & Zhao, Q. (2020). Opponent Modeling in Poker Games. 2020 IEEE 9th Data Driven Control and Learning Systems Conference (DDCLS), 1090–1097. 
