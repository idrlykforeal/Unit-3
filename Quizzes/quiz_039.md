# py code
```.py
from kivymd.app import MDApp

class quiz_039(MDApp):
    def __init__(self, **kwargs):
        super().__init__(**kwargs)
        self.count=0
    def build(self):
        return
    def add(self):
        self.count+=1
        self.root.ids.counter_label.text = f"Count: {self.count}"

m= quiz_039()
m.run()
```


# kv code
```.kv
Screen:
    size: 500, 300 #width, height
    MDBoxLayout:
        orientation: 'horizontal'

        size_hint: 0.7, 0.3
        pos_hint: {'center_x': 0.5, 'center_y': 0.5}
        MDLabel:

            size_hint: 0.5, 1
            id: counter_label
            pos_hint: {'center_x': 0.5, 'center_y': 0.25}
            halign: "center"
            text: "Count 0"
            font_size: 34

        MDRaisedButton:
            size_hint: .5, 1
            id: add_1
            text: "Add + 1"
            pos_hint: {'center_x': 0.5, 'center_y': 0.25}
            md_bg_color: 0.3, 0.6, 0.5, 0.5
            on_release:
                app.add()
```

# evidence

<img width="790" alt="Screen Shot 2023-01-26 at 10 36 24 AM" src="https://user-images.githubusercontent.com/100017195/214736725-12700f8d-2a42-4bba-9c5c-33c53a489ada.png">


<img width="790" alt="Screen Shot 2023-01-26 at 10 36 28 AM" src="https://user-images.githubusercontent.com/100017195/214736700-0a4aeda5-38ee-4aeb-843d-e47470a26f33.png">


