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

https://user-images.githubusercontent.com/100017195/217510732-a6f232d1-21a3-49df-bc7a-76d699429319.mov


