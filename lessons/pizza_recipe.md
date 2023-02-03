# Python
```.py
from kivymd.app import  MDApp
from kivymd.uix.screen import MDScreen

class IntroScreen(MDScreen):
    pass
class PrepareDough(MDScreen):
    pass
class Ingredients(MDScreen):
    def add_flour(self):
        if self.ids.flour.active:
            print("flour was added ")
        else:
            print("Flour was removed")
    def add_oliveoil(self):
        if self.ids.oliveoil.active:
            print("Olive oil was added")
        else:
            print("Olive oil was removed")
class AddIngredients(MDScreen):
    pass
class BakePizza(MDScreen):
    pass
class Enjoy(MDScreen):
    pass
class recipe_pizza(MDApp):
    def build(self):
        return

test = recipe_pizza()
test.run()
```

# kv file
```.kv
ScreenManager:
    id:scr_manager
    IntroScreen:
        name:"IntroScreen"
    PrepareDough:
        name:"PrepareDough"
    Ingredients:
        name:"Ingredients"
    AddIngredients:
        name:"AddIngredients"
    BakePizza:
        name:"BakePizza"
    Enjoy:
        name:"Enjoy"
<IntroScreen>:
    MDCard:
        md_bg_color: "orange"
        size_hint: .7, .9
        pos_hint: {"center_x": .5, "center_y": .5}
        radius: 50,0,50,0
        orientation: "vertical"
        MDLabel:
            text:"My Pizza Recipe"
            size_hint: 1, .1
            halign:"center"
            font_style: "H3"
        FitImage:
            size_hint: 1,.7
            source:"pizza.jpg"
        MDBoxLayout:
            size_hint: 1, .05
            MDLabel:
                size_hint: .8, 1
            MDRaisedButton:
                text: "Next"
                size_hint: .2,1
                md_bg_color: "d62828"
                on_press: root.parent.current = "PrepareDough"



<PrepareDough>
    MDCard:
        md_bg_color: "orange"
        size_hint: .7, .9
        pos_hint: {"center_x": .5, "center_y": .5}
        radius: 50,0,50,0
        orientation: "vertical"
        MDLabel:
            text:"Prepare Dough"
            size_hint: 1, .1
            halign:"center"
            font_style: "H3"
        FitImage:
            size_hint: 1,.7
            source:"dough.jpg"
        MDLabel:
            text:"To make the pizza dough, ..."
            size_hint: 1, .05
            halign:"center"
            font_style: "H5"
        MDBoxLayout:
            size_hint: 1, .05
            MDRaisedButton:
                text: "Previous"
                size_hint: .2,1
                md_bg_color: "003049"
                on_press: root.parent.current = "IntroScreen"
            MDLabel:
                size_hint: .8, 1
            MDRaisedButton:
                text: "Next"
                size_hint: .2,1
                md_bg_color: "d62828"
                on_press: root.parent.current = "Ingredients"
<Ingredients>:
    MDCard:
        md_bg_color: "orange"
        size_hint: .7, .9
        pos_hint: {"center_x":.5, "center_y": .5}
        radius: 30, 0, 30, 0
        orientation: "vertical"

        MDLabel:
            text: "List of ingredients"
            size_hint: 1, .1
            halign:"center"
            font_style: "H3"

        MDBoxLayout:
            orientation: "vertical"
            size_hint: 1, .6
            md_bg_color: "white"
            MDBoxLayout:
                MDCheckbox:
                    id:flour
                    size_hint: None, None
                    size: "48dp", "48dp"
                    text: "Flour 500 gr"
                    pos_hint: {'center_x': .5, 'center_y': .5}
                    on_press: root.add_flour()
                MDLabel:
                    text: "Flour 500gr"
            MDBoxLayout:
                MDCheckbox:
                    id:oliveoil
                    size_hint: None, None
                    size: "48dp", "48dp"
                    text: "Olive oil 200 ml"
                    pos_hint: {'center_x': .5, 'center_y': .5}
                    on_press: root.add_oliveoil()
                MDLabel:
                    text: "Olive Oil 200 ml"
        MDBoxLayout:
            size_hint: 1, .05
            MDRaisedButton:
                text: "Previous"
                size_hint: .2,1
                md_bg_color: "003049"
                on_press: root.parent.current = "PrepareDough"
            MDLabel:
                size_hint: .8, 1
            MDRaisedButton:
                text: "Next"
                size_hint: .2,1
                md_bg_color: "d62828"
                on_press: root.parent.current = "AddIngredients"
<AddIngredients>
    MDCard:
        md_bg_color: "orange"
        size_hint: .7, .9
        pos_hint: {"center_x": .5, "center_y": .5}
        radius: 50,0,50,0
        orientation: "vertical"
        MDLabel:
            text:"Add Toppings"
            size_hint: 1, .1
            halign:"center"
            font_style: "H3"
        FitImage:
            size_hint: 1,.7
            source:"pizza-topping-large.jpg"
        MDLabel:
            text:"Add your preferred toppings"
            size_hint: 1, .05
            halign:"center"
            font_style: "H5"
        MDBoxLayout:
            size_hint: 1, .05
            MDRaisedButton:
                text: "Previous"
                size_hint: .2,1
                md_bg_color: "003049"
                on_press: root.parent.current = "Ingredients"
            MDLabel:
                size_hint: .8, 1
            MDRaisedButton:
                text: "Next"
                size_hint: .2,1
                md_bg_color: "d62828"
                on_press: root.parent.current = "BakePizza"
<BakePizza>
    MDCard:
        md_bg_color: "orange"
        size_hint: .7, .9
        pos_hint: {"center_x": .5, "center_y": .5}
        radius: 50,0,50,0
        orientation: "vertical"
        MDLabel:
            text:"Bake"
            size_hint: 1, .1
            halign:"center"
            font_style: "H3"
        FitImage:
            size_hint: 1,.7
            source:"bake.jpg"
        MDLabel:
            text:"Bake your pizza!"
            size_hint: 1, .05
            halign:"center"
            font_style: "H5"
        MDBoxLayout:
            size_hint: 1, .05
            MDRaisedButton:
                text: "Previous"
                size_hint: .2,1
                md_bg_color: "003049"
                on_press: root.parent.current = "AddIngredients"
            MDLabel:
                size_hint: .8, 1
            MDRaisedButton:
                text: "Next"
                size_hint: .2,1
                md_bg_color: "d62828"
                on_press: root.parent.current = "Enjoy"
<Enjoy>
    MDCard:
        md_bg_color: "orange"
        size_hint: .7, .9
        pos_hint: {"center_x": .5, "center_y": .5}
        radius: 50,0,50,0
        orientation: "vertical"
        MDLabel:
            text:"Done!"
            size_hint: 1, .1
            halign:"center"
            font_style: "H3"
        FitImage:
            size_hint: 1,.7
            source:"pizza.jpg"
        MDLabel:
            text:"Enjoy your pizza!"
            size_hint: 1, .05
            halign:"center"
            font_style: "H5"
        MDBoxLayout:
            size_hint: 1, .05
            MDRaisedButton:
                text: "Previous"
                size_hint: .2,1
                md_bg_color: "003049"
                on_press: root.parent.current = "BakePizza"
            MDLabel:
                size_hint: .8, 1
            MDRaisedButton:
                text: "Make another"
                size_hint: .2,1
                md_bg_color: "d62828"
                on_press: root.parent.current = "IntroScreen"
```

# Showcase

https://user-images.githubusercontent.com/100017195/216504540-9d22da70-c9a2-4e66-a7a4-232e873c8346.mov

