# Test-run
 A test to assert that an API call to Character 583 reveals details about Jon Snow
import requests

ENDPOINT= "https://anapioficeandfire.com/api/characters/583"


def test_can_call_endpoint():
    response=requests.get(ENDPOINT)
    assert response.status_code==200

def test_can_call_name():
    response=requests.get(ENDPOINT)
    name= response.json()["name"]
    print(name)
    assert response.json()["name"]== "Jon Snow"

def test_not_name():
    response=requests.get(ENDPOINT)
    not_name= response.json()["name"]
    if not_name== "Sanza Stark":
        print("Not name")
    assert response.json()["name"]!= "Sanza Stark"

def test_gender():
    response=requests.get(ENDPOINT)
    gender= response.json()["gender"]
    print(gender)
    assert  response.json()["gender"]== "Male"


def test_started_in_six_seasons():
    response=requests.get(ENDPOINT)
    seasons= response.json()["tvSeries"]
    print(seasons)
    assert response.json()["tvSeries"]== ["Season 1","Season 2","Season 3","Season 4","Season 5","Season 6"]



    




