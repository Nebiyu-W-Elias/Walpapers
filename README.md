# Walpapers
import requests
from PIL import Image
from io import BytesIO
import random

def fetch_wallpaper():
    url = "https://source.unsplash.com/featured/?wallpaper,aesthetic"
    response = requests.get(url)
    return response.url

def download_wallpaper(url):
    response = requests.get(url)
    img = Image.open(BytesIO(response.content))
    img.save("aesthetic_wallpaper.jpg")

def main():
    wallpaper_url = fetch_wallpaper()
    download_wallpaper(wallpaper_url)
    print("Aesthetic wallpaper downloaded successfully!")

if __name__ == "__main__":
    main()
