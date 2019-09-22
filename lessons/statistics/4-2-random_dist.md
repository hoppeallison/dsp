[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

    random_numbers = np.random.random(1000)    
    pmf = thinkstats2.Pmf(random_numbers)
    thinkplot.Pmf(pmf, linewidth=0.1)
    thinkplot.Config(xlabel='Random variate', ylabel='PMF')  
    cdf = thinkstats2.Cdf(random_numbers)
    thinkplot.Cdf(cdf)
    thinkplot.Config(xlabel='Random variate', ylabel='CDF')
    
    Yes, the distribution is uniform because the CDF is a straight line.
