# Task 1: currency converter

## Code

### Python
```.py
# currency converter
from kivymd.app import MDApp

class currency_converter(MDApp):
    def __init__(self, **kwargs):
        super().__init__(**kwargs)
        self.cny=0
        self.exchanged_result=0
    def build(self):
        return
    def set_cny_amount(self):
        # validation for integer
        if not self.root.ids.input_amount.text.isdigit():
            self.root.ids.show_converted_amount.text = "Please enter a valid number"
        number= int(self.root.ids.input_amount.text)
        self.cny = number
    def convert_to_usd(self):
        self.exchanged_result = self.cny*0.15.__round__(2)
        self.root.ids.show_converted_amount.text = f" {self.exchanged_result} USD"
    def convert_to_jpy(self):
        self.exchanged_result = self.cny*19
        self.root.ids.show_converted_amount.text = f" {self.exchanged_result} JPY"



converter=currency_converter()
converter.run()
```
### kv
```.kv
#GUI Building Task 1 - KivyMD
Screen:
    size: 500,500
    MDBoxLayout:
        id: main
        orientation: 'vertical'
        size_hint:1,.8
        pos_hint: {'center_x': .5, 'center_y': .5}

        MDLabel:
            text:"Currency Converter"
            halign: 'center'
            font_style: 'H3'
            size_hint: 1, .2
            pos_hint: {'center_x': .5}

        MDTextField:
            id: input_amount
            hint_text: "Enter Amount in CNY"
            pos_hint: {'center_x':0.5}
            size_hint: .7, .2
            on_text:

                app.set_cny_amount()

        MDBoxLayout:
            id: exchange_and_results
            orientation: 'horizontal'
            size_hint: 1, .4
            pos_hint: {'center_x':0.5}

            MDLabel:
                id : hint
                text: "CLICK TO CONVERT"
                halign: 'center'
                size_hint: .3, 1
                pos_hint: {'center_x':0.2, 'center_y':0.5}
            MDBoxLayout:
                id: buttons_and_result
                orientation:"vertical"
                size_hint: .3, 1
                MDBoxLayout:
                    id: buttons_box
                    orientation: "horizontal"
                    size_hint: .7, 1
                    pos_hint: {'center_x':0.7, 'center_y':0.9}
                    MDRaisedButton:
                        id: usd
                        text: "USD"
                        pos_hint: {"center_x": 0.25, "center_y": .25}
                        on_release: app.convert_to_usd()
                        md_bg_color:"#002B41"
                    MDRaisedButton:
                        id: jpn
                        text: "JPY"
                        pos_hint: {"center_x": 0.75, "center_y": .25}
                        on_release: app.convert_to_jpy()
                        md_bg_color:"#F20021"
                MDLabel:
                    id: show_converted_amount
                    text: "0"
                    halign: 'center'
                    font_style: 'H5'
                    text_color: "#000000"
                    size_hint: .3, 1
                    pos_hint: {'center_x':0.6}
                    font_size:80
```

## Showcase

<img width="912" alt="Screen Shot 2023-01-29 at 10 17 41 PM" src="https://user-images.githubusercontent.com/100017195/215328838-b59c3c36-093c-43ab-bf4c-525a45c78066.png">
<img width="912" alt="Screen Shot 2023-01-29 at 10 19 03 PM" src="https://user-images.githubusercontent.com/100017195/215328910-c138461f-0c59-42ee-94cb-fcd30b1bc7d8.png">
<img width="912" alt="Screen Shot 2023-01-29 at 10 19 18 PM" src="https://user-images.githubusercontent.com/100017195/215328925-c4b5f39d-ee07-49ae-9efd-8ead63b246d2.png">


# Task 2: Bit-Byte converter

## Code

### Python
```.py

```
### kv
```.kv

```

## Showcase
