from bs4 import BeautifulSoup as bs
import funciones
import re
import lxml

def sopadeLetras():
    html_doc1= funciones.abrirWeb("https://www.meneame.net")
    soup = bs(html_doc1, 'lxml')
    cont=0
    dic={}
    li=soup.find_all("div",class_="news-summary")
    for i in li:
        print("---------------------------------")    
        #print(i)
        titulo=i.h2.a.getText()
        link=i.find(class_="center-content").a.get("href")
        print("---------------------------------")

        for e in i.find_all(title=True):
            print("--------------------")
            print(e)
            print("--------------------")
           
        

sopadeLetras()
