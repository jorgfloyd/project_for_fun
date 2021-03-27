import os
import random
import requests
from bs4 import BeautifulSoup
HEADERS={
    "Accept":"*/*",
    "User-Agent":"Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:87.0) Gecko/20100101 Firefox/87.0"
}
def start():
    global dict
    dict=[]
def get(html):
    soup=BeautifulSoup(html,'html.parser')
    name = soup.find_all ( 'audio', class_='media__audio _g-hidden-input' )
    name2=soup.find_all ( 'div', class_='media__performer' )
    name3 = soup.find_all ( 'div', class_='media__name' )
    name4=soup.find( 'h2', class_='_g-subtitle _md' )
    otvet=[]
    name_folder=name4.get_text()
    os.mkdir(name_folder)
    print(name)
    for i in range(0,len(name)):
        text="["+name2[i].get_text()+"] "+name3[i].get_text()

        try:
            with open (f"{name_folder}/"+text+".mp3", "wb" ) as file:
                file.write ( requests.get ( str(name[i]).split('"')[7] ).content )
        except:
            with open (f"{name_folder}/песенка{random.randint(5666,66577676)}.mp3", "wb" ) as file:
                file.write ( requests.get ( str(name[i]).split('"')[7] ).content )
        print(f"{text} успешно загружен {i+1}/{len(name)}")
    print ( '█─█──████──████──███──██─██' )
    print ( '█─█──█──█──█──█──█─────███' )
    print ( '███──█─────█──█──███────█' )
    print ( '──█──█──█──█──█──█─────███' )
    print ( '███──████──█──█──███──██─██' )
def get_html(url,params=None):
    r=requests.get(url,headers=HEADERS,params=params)
    return r
def parse(url):
    html=get_html(url)
    if html.status_code==200:
        get(html.text)
    else:
        print("этот адрес не подходит")
def main():
    print('')
    print('████──████──████──████──███──████')
    print('█──█──█──█──█──█──█──█──█────█──█')
    print('█──█──████──████──█─────███──████')
    print('█──█──█──█──█─────█──█──█────█')
    print('█──█──█──█──█─────████──███──█')
    print('')
    print('')
    print('█───██─█─█──███───────███──████')
    print('██─███─█─█────█────────█───█──██')
    print('█─█─██─███──███──███───█───████')
    print('█───██───█────█────────█───█──██')
    print('█───██─███──███────────█───████')
    print('')
    print('')
    print('████───████───███───███───█──█──███──███')
    print('█──██──█──██──█─────█─█───█──█───█───█')
    print('████───████───███───█─█───█─██───█───███')
    print('█──██──█──██──█────█████──██─█───█───█')
    print('████───████───███──█───█──█──█───█───███')
    print('')
    print('')
    print('████───███───████──███──████')
    print('█──█───█─█───█──█──█────█──█')
    print('████───█─█───████──███──█')
    print('█──█──█████──█─────█────█──█')
    print('█──█──█───█──█─────███──████')
    print('')
    print('──────────────────██')
    print('████────██──███──█──█────██──█──█──████──███──████')
    print('█──█───█─█──█────█──█───█─█──█──█──█──█───█───█──█')
    print('█──█──█──█──███──█─██──█──█──█─██──█──────█───████')
    print('█──█──█──█──█────██─█──█──█──██─█──█──█───█───█──█')
    print('█──█──█──█──███──█──█──█──█──█──█──████───█───█──█')
    
    url=input('\n\nurl:  ')
    parse(url)
if __name__ == '__main__':
    main()

