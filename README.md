java c
PHY254H1-F 
Problem set #1 
Fall 2024 
Due 22 September 2024 at 11:59 p.m. 
Preliminary question If you haven’t yet, read the “Homework set policy” document in the “Prac ticalities” module on Quercus. Did you read and understand the policy? If you did, write down
“I have read and I understand the homework set policy in this course.”
in your copy. You should answer this question truthfully before continuing with this homework set.
For all questions, if we derived a formula during a lecture or in the lecture notes, you may re-use it without justification other than a simple reference to the notes or textbook.
1   Rise and fall of a baseball [40%] 
A baseball is thrown vertically up with speed v0 and is subject to a quadratic drag with magnitude |Fdrag(v)| = cv2, with c = ∞D2 the friction coefficient, gamma a proportionality constant and D the diameter of the ball.
1.1. Preliminary question: imagine that the ball has been falling vertically for ever, such that fric-tion and gravity balance perfectly, the ball no longer accelerates, and it is falling with terminal velocity vter. Find the expression of vter. (Note: by definition, vter is a positive quantity.)
1.2. Write the equation of motion for the upward journey (measure y vertically up) and show that it can be re-written as

1.3. Solve the equation of motion by separating the variables. Integrate to find v as a function of t, y in terms of v, and v as a function of y.
Hint: ∫ dx/(1 + x2) = arctanx. For other formulas, don’t hesitate to use symbolic software or websites.
1.4. Show that the baseball’s maximum height is

1.5. If v0 = 20 m s-1, the weight of the ball is m = 0.15 kg, ∞ = 0.25 N s2 m°4 and D = 7 cm, what is ymax? Compare with the value in a vacuum.
1.6. Write the equation of motion for the downward journey. (Notice that with a quadratic drag the downward equation is different from the upward one.) Find v as a function of y.
1.7. Given that the downward journey starts at ymax given by equation (2) above, show that the speed when the ball returns to the ground is

1.8. Discuss this result for the cases of very weak and very strong air resistance. What is the nu-merical value of this speed for the baseball of part 1.5.?
2   Computational rise and fall of a baseball [20%] 
We now integrate the equations of motion for the problem above numerically. In class, we saw the Euler-Cromer method, which is well-suited for problems subjected to position-dependent forces. Here, we don’t need the two-step procedure because the drag depends directly on the velocity. We can therefore use a simple forward-Euler method to integrate the velocity. The goal of this question is to illustrate how to estimate errors of a numerical method. Here, the error is easy to measure: we just have to compare with the analytical formulas for v.
Note that in part 1.6., we did not ask you to compute v as a function of t in the downward journey like we did for the upward one in part 1.3.. A similar calculation would give

the time at which y = ymax and v = 0. Equating v = vg , we find that the ball hits the ground at

2.1. Complete the starter code quadratic_drag.py to integrate the equation v˙ =··· from t = 0 to t = tg . You can divide this time interval in 50 time steps to start.
Superpose on the same plot the curves from the analytical expressions for v(t) and the solu-tion you obtained via the forward Euler integration.
Notes:
• Recall that your markers w代 写PHY254H1-F Problem set #1 Fall 2024Python
代做程序编程语言on’t look at your code! Only submit the figure and any com-ments you find relevant.
• You will have to figure out a way to deal with the fact that the equation of motion changes after the ball reaches maximum height. Explain how you did.
2.2. In your previous plot, you should have found that dividing the interval into 50 time steps gave you a visually good result. And yet, the numerical integration is based on approximate formulas, which results in errors. In general, it is hard to calculate the error, but here, we are lucky to have the exact analytical solution to compare: we can define the error as

i.e., the absolute value of the difference between analytical (exact) and numerical values at the end of the integration. This is called the “global error” of the method.
Numerical integration methods are often characterised by their “order”: that is, if dt is the time step,
• a first-order method is such that ≤ / dt,
• a second-order method is such that ≤ / (dt)2,
• a nth-order method is such that ≤ / (dt)n.
Reduce the number of time steps in your numerical integration (i.e., increase dt) until you find a visually noticeable error in your plot. Then, try a few different values of dt in-between, until you have enough values to plot a good-looking ≤ vs. dt curve. What does this curve look like? What do you conclude about the order n of the forward Euler method?
Notes:
• Don’t expect a “perfect” ≤ vs. dt curve, you will have to make a judgment call.
• In order to justify your conclusion, include a few representative curves, as well as your final ≤ vs. dt curve, and comment everything. Explain how you reached your conclusion as if you were addressing a complete beginner.
3   Polar coordinates [20%] 
This is Morin, Exercise 3.68, page 83.
Consider a particle thatfeels an angular force only, oftheform. Fθ = 3mθ˙. Show that r =± √Ar4 +B, where A and B are constants of integration, determined by the initial conditions. Also, show that if the particle starts with θ˙ ≠ 0 and r > 0, it reaches r → ∞ in a ﬁnite time. 
Note:  There is nothing all that physical about this force.  It simply makes the F = ma equations solvable. 
4   Vibration kinematics [20%] 
4.1.  Consider the vibrations x1 = 3cos(25t/4+π/5) and x2 = 4cos(7t +π/8). 4.1.1.  What is the expected period for x1 + x2? 
4.1.2.  What is the beat frequency? (i.e., the frequency at which minima in the combined signal occur.) 
4.1.3.  Using Python, plot position versus time, velocity versus time, and the phase space tra- jectory (i.e., velocity versus position),for x1, x2, and x = x1 + x2 . 
4.1.4.  A solution to Newton’s equation mx = F(x, v) for motion along the x axis is uniquely de- termined by its initial conditions, which turns out to imply that the phase space trajec- tory of such a solution should never cross itself. Indeed, imagine that the initial condi- tion was exactly at a crossing: the system could take either route, which doesn’t happen inF(~) = m a(~) problems where a complete set of initial conditions leads to a unique so- lution. What does this suggest about the combined motion x, given your phase space plot? 
4.2.  Express z = 5sin(!t)+6cos(!t) in the form. z = Re £Aei(!t+φ) § and sketch it by hand or plot them in Python in the complex plane at t = π/! (i.e., at one half period). Do the math, don’t ask Python the answer right away (but you can check your ﬁnal results with Python). 







         
加QQ：99515681  WX：codinghelp
