# News-Paper-Reader-using-Python-Tkinter-
The application retrieves live news headlines using a News API (like NewsAPI.org) or by scraping news websites with libraries such as BeautifulSoup or newspaper3k.

import tkinter as tk
from newsapi import NewsApiClient

newsapi = NewsApiClient(api_key='cba79ab9432c43078a85cd2500d65498')

def get_news():
    top_headlines = newsapi.get_top_headlines(language='en')
    text.delete(1.0, tk.END)
    for article in top_headlines['articles']:
        text.insert(tk.END, article['title'] + '\n\n')

root = tk.Tk()
root.title('PyHeadings with You😅')
text = tk.Text(root, height=20, width=100, fg='green', bg='black', font=('Times new roman', 14))
text.pack()
button = tk.Button(root, text='Get News',fg='red',bg='Pink',bd=0, command=get_news)
button.pack()
root.mainloop()
