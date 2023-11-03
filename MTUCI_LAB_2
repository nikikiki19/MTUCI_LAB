from fastapi import FastAPI
import wikipedia


app = FastAPI()
@app.get('/path/{page_title}')
def get_page_title(page_title: str):
    return wikipedia.search(page_title)

@app.get('/query/{page_title}')
def get_title_num(page_title: str, results_page: int):
    return wikipedia.search(page_title, results = results_page)

from pydantic import BaseModel


class Body_input(BaseModel):
    body : str

@app.post('/')
def get_title(page_title: Body_input):
    return wikipedia.search(page_title.body)
