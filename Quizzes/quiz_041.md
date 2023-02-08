# python code
```.py
# tic tac toe game
from kivymd.app import MDApp

class tictactoe(MDApp):
    def build(self):
        return

    def __init__(self, **kwargs):
        super().__init__(**kwargs)
        self.turn= 1 # True for x, False for o

    def play(self, button_id):
        label= "b"+str(button_id)
        if self.turn==1:
            self.root.ids[label].text= "X"
            self.root.ids[label].md_bg_color="fefae0"
            self.turn=2
            self.root.ids.turn.text="It's O's turn"
        else:
            self.root.ids[label].text="O"
            self.root.ids[label].md_bg_color="283618"
            self.turn=1
            self.root.ids.turn.text="It's X's turn"
        self.root.ids[label].disabled = True

game=tictactoe()
game.run()
```

# kv code
```.kv
Screen:
    size: 500, 500

    MDBoxLayout:

        orientation: 'vertical'
        size_hint: 0.8, 0.8
        pos_hint: {'center_x': 0.5, 'center_y': 0.5}

        MDLabel:
            size_hint: .9, .2
            id: Title
            pos_hint: {'center_x': 0.5, 'center_y': 0.5}
            halign: "center"
            text: "Tic Tac Toe by Kris"
            font_style: "H3"
        MDLabel:
            size_hint: .5 , .1
            id: turn
            pos_hint: {'center_x': 0.5, 'center_y': 0.5}
            halign: "center"
            text: "It's X's turn"

        MDBoxLayout:
            size_hint: .9, .7
            orientation: 'vertical'
            pos_hint: {'center_x': 0.5, 'center_y': 0.5}

            MDBoxLayout:
                orientation: 'horizontal'
                MDRaisedButton:
                    id: b1
                    size_hint: .3,1
                    md_bg_color: "d5bdaf"
                    text: ""
                    on_press: app.play(1)
                MDRaisedButton:
                    id: b2
                    size_hint: .3,1
                    md_bg_color: "d5bdaf"
                    on_press: app.play(2)
                MDRaisedButton:
                    id:b3
                    size_hint: .3,1
                    md_bg_color: "d5bdaf"
                    on_press: app.play(3)

            MDBoxLayout:
                orientation: 'horizontal'
                MDRaisedButton:
                    id:b4
                    size_hint: .3,1
                    md_bg_color: "d5bdaf"
                    on_press: app.play(4)
                MDRaisedButton:
                    id:b5
                    size_hint: .3,1
                    md_bg_color: "d5bdaf"
                    on_press: app.play(5)
                MDRaisedButton:
                    id:b6
                    size_hint: .3,1
                    md_bg_color: "d5bdaf"
                    on_press: app.play(6)

            MDBoxLayout:
                orientation: 'horizontal'
                MDRaisedButton:
                    id:b7
                    size_hint: .3,1
                    md_bg_color: "d5bdaf"
                    on_press: app.play(7)
                MDRaisedButton:
                    id:b8
                    size_hint: .3,1
                    md_bg_color: "d5bdaf"
                    on_press: app.play(8)
                MDRaisedButton:
                    id:b9
                    size_hint: .3,1
                    md_bg_color: "d5bdaf"
                    on_press: app.play(9)
```

# showcase

https://user-images.githubusercontent.com/100017195/217507582-721de7ba-be10-4dae-9b8e-efd659f74134.mov

