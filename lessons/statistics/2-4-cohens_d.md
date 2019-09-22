[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)
#Calculates Cohen's d to quantify the difference in the total weight in lbs between first borns and others,

def Ch2_Ex4():
    import nsfg
    import math
    preg = nsfg.ReadFemPreg()
    live = preg[preg.outcome == 1]
    firsts = live[live.birthord == 1]
    others = live[live.birthord != 1]
    mean_firsts = firsts.totalwgt_lb.mean()
    mean_others = others.totalwgt_lb.mean()
    diff = mean_firsts - mean_others
    var_firsts = firsts.totalwgt_lb.var()
    var_others = others.totalwgt_lb.var()
    n1, n2 = len(firsts), len(others)
    pooled_var = (n1 * var_firsts + n2 * var_others) / (n1 + n2)
    d = diff / math.sqrt(pooled_var)
    print(d)
