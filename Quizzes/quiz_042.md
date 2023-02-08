# python code

```.py
from kivymd.app import MDApp
from kivymd.uix.screen import MDScreen


class mystery(MDApp):
    def build(self):
        return

class Home(MDScreen):
    pass
class ScreenA(MDScreen):
    pass
class ScreenB(MDScreen):
    pass

app=mystery()
app.run()
```

# kv file
```.kv
Screen:
    MDBoxLayout:
        id: box
        orientation: 'vertical'
        size_hint: 1,1
        md_bg_color: "black"
        MDLabel:
            id: label
            text: 'Kris'
            #color of text: white
            text_color: "white"
            halign: 'center'
            size_hint: 1,.8
            theme_text_color: 'Custom'
            font_style: 'H1'

        MDRaisedButton:
            text: "Change"
            size_hint: .1,.05
            pos_hint: {"corner_x": 0.5}
            on_release: app.change()
```

# showcase


https://user-images.githubusercontent.com/100017195/217509505-701e3f2d-fadd-4e8a-9d09-210da1ec0dc5.mov

