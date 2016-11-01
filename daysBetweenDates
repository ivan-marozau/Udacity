# By Websten from forums
#
# Given your birthday and the current date, calculate your age in days. 
# Account for leap days. 
#
# Assume that the birthday and current date are correct dates (and no 
# time travel). 

import time
start = time.clock()

def isLeapYear(year):
	if year%4 != 0:
		return False
	elif year%100 != 0:
		return True
	elif year%400 != 0:
		return False
	else: return True

def daysBetweenDates(year1, month1, day1, year2, month2, day2):
    daysOfMonths = [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]
    sum = 0
    if year2 == year1:
    	if isLeapYear(year2):
    		daysOfMonths[1] = 29
    	i = month1
    	while i < month2-1:
    		sum+=daysOfMonths[i]
    		i += 1
    	sum+=daysOfMonths[month1-1]-day1 + day2
    else:
    	if isLeapYear(year2): daysOfMonths[1] = 29
    	else: daysOfMonths[1] = 28
    	i=0
    	while i < month2-1:
    		sum+=daysOfMonths[i]
    		i += 1
    	if not isLeapYear(year1): daysOfMonths[1] = 28
    	else: daysOfMonths[1] = 29
    	i = month1
    	while i < 12:
    		sum+=daysOfMonths[i]
    		i += 1
    	sum+= day2 + daysOfMonths[month1-1]-day1
    	y = year1
    	while y < year2-1:
    		if isLeapYear(y):
    			sum+=366
    			y+=1
    		else:
    			sum+=365
    			y+=1
    return sum

# Test routine

def test():
    test_cases = [((2012,1,1,2012,2,28), 58), 
                  ((2012,1,1,2012,3,1), 60),
                  ((2011,6,30,2012,6,30), 366),
                  ((2011,1,1,2012,8,8), 585 ),
                  ((1900,1,1,1999,12,31), 36523)]
    for (args, answer) in test_cases:
        result = daysBetweenDates(*args)
        if result != answer:
            print ("Test with data:", args, "failed")
        else:
            print ("Test case passed!")

test()

end = time.clock()
print ("Running time: %s seconds" % (end - start))
