# -*- coding: utf-8 -*-

"""
wcount.py:count words from an Internet file.

__author__ = "Haocheng Lu"

__pkuid__  = "18000117425"

__email__  = "1800011742@pku.edu.cn"

"""

import string
import sys
from urllib.request import urlopen

def wcount(text,u1):

    """
     count words from lines of text string, then sort by their counts
    in reverse order, output the topn (word count), each in one line. 
    """
    
    text_0=text.split()
    text_1=[]
    loop1=1
    for m in text_0:
        m=m.lower()
        a=''
        for m1 in m:
            if m1 not in string.punctuation:
                a=a+m1
        text_1.append(a)
    counts={}
    count1=[]
    for l in text_1:
        counts[l] = counts.get(l, 0) + 1
    for (k,v) in counts.items():
        count1.append((k,v))
    count1=sorted(count1,reverse=True, key=lambda kv:kv[1])
    for k,v in count1:
        if loop1<=u1:
            print('%-15s' % k,v) 
            loop1+=1

def main():

    web=u0
    doc = urlopen(web)
    docstr = doc.read()
    doc.close()
    jstr = docstr.decode('utf-8')
    wcount(jstr,u1)

    
if __name__=='__main__':
    
    if  len(sys.argv) == 1:
        print('Usage: {} url [topn]'.format(sys.argv[0]))
        print('  url: URL of the txt file to analyze ')
        print('  topn: how many (words count) to output. If not given, will output top 10 words')
        sys.exit(1)
    elif len(sys.argv) == 2:
        print('Usage: {} url [topn]'.format(sys.argv[0]))
        print('  url: URL of the txt file to analyze ')
        print('  topn: how many (words count) to output. If not given, will output top 10 words')
        u1=10
        u0=sys.argv[1]
        main()
    elif len(sys.argv) == 3:
        print('Usage: {} url [topn]'.format(sys.argv[0]))
        print('  url: URL of the txt file to analyze ')
        print('  topn: how many (words count) to output. If not given, will output top 10 words')
        u1=int(sys.argv[2])
        u0=sys.argv[1]
        main()





    
