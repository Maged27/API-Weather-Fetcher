# API-Weather-Fetcher

import requests

API_KEY = "3994baf9ef1cd48dba5faf3365c1ca25"
BASE_URL = "http://api.openweathermap.org/data/2.5/weather"

city = input("Enter city name: ")
request_url = f"{BASE_URL}?appid={API_KEY}&q={city}&units=metric"
response = requests.get(request_url)

if response.status_code == 200:
    data = response.json()
    weather = data['weather'][0]['description']
    tempreather = data["main"]["temp"]
    print("Weather:", weather)
    print("Tempreather:", tempreather)
else:
    print("An error occured.")
