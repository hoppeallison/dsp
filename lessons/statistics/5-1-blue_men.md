[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

>> 
# find percentage of male population between 5'10 and 6'1 given mean and sigma of male height and that the height distribution is roughly normal.
def Ch5_Ex1():
    import scipy.stats
    mu = 178
    sigma = 7.7
    dist = scipy.stats.norm(loc=mu, scale=sigma)
    type(dist)
    dist.mean(), dist.std()
    low = dist.cdf(177.8)
    high = dist.cdf(185.4)
    print(high-low)
