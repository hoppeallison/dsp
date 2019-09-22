[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

# Plot histagram of actual distribution of the number of kids in a family and the biased distribution based on asking kids how many children are in their family. Calculates the mean of each distribution. Due to class size paradox.
def Ch3_Ex1():
    import thinkstats2
    import thinkplot
    resp = nsfg.ReadFemResp()
    pmf = thinkstats2.Pmf(resp.numkdhh, label='numkdhh')
    new_pmf = pmf.Copy()
    for x, p in pmf.Items():
        new_pmf.Mult(x, x)
    new_pmf.Normalize()
    thinkplot.PrePlot(2)
    thinkplot.Pmfs([pmf, new_pmf])
    thinkplot.Config(xlabel='Number of children', ylabel='PMF')
    mean_pmf = pmf.Mean()
    mean_new_pmf = new_pmf.Mean()
    print(mean_pmf)
    print(mean_new_pmf)
