# lub7
from PIL import Image

filename = "mult.jpeg"
with Image.open(filename) as img:
    img.load()


img.show()
width, height = img.size

format = img.format

mode = img.mode

print("Ширина: ", width)
print("Высота:  ", height)
print("Формат: ", format)
print("Цветовая модель: ", mode)


from PIL import Image, ImageFilter

filename = "1.jpg"
with Image.open(filename) as img:
    img.load()

new_img = img.resize((img.width // 3, img.height // 3))

new_img.save("resized_auto.jpg")
new_img =img.rotate(180)
new_img.save('rotate_auto.jpg')

from PIL import Image,ImageFilter

filenames = ["1.jpg", "2.jpg", "3.jpg", "4.jpg", "5.jpg"]

for file in filenames:
    with Image.open(file) as img:
        img.load()
        new_img = img.filter(ImageFilter.EMBOSS)
        new_img.show()
        new_img.save("new_" + file)

from PIL import Image


water = 'watermark.jpg'
with Image.open(water) as img_water:
    img_water.load()


img_water = Image.open(water)
img_water = img_water.resize((img_water.width // 2, img_water.height // 2))


filename = 'mult.jpg'
with Image.open(filename) as img:
    img.load()


img.paste(img_water, (42, 40), img_water)
img.save("watermark_mult.jpg")
