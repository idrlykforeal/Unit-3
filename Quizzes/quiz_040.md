# Python code
```.py
from kivymd.app import MDApp

class change(MDApp):
    def __init__(self, **kwargs):
        super().__init__(**kwargs)
        self.colors=["black","white"]
    def build(self):
        return
    def change(self):
        if self.root.ids.label.text_color==self.colors[0]:
            self.root.ids.label.text_color=self.colors[1]
            self.root.ids.box.md_bg_color=self.colors[0]
        else:
            self.root.ids.label.text_color=self.colors[0]
            self.root.ids.box.md_bg_color=self.colors[1]



test = change()
test.run()
```

# kv code

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
<img width="912" alt="image" src="https://user-images.githubusercontent.com/100017195/216500421-1799a79c-298f-4c2e-92cd-55924577441e.png">

<img width="912" alt="image" src="https://user-images.githubusercontent.com/100017195/216500352-9a39c823-d7f2-4d81-b195-1e5ba673661c.png">
