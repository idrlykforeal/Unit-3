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
from kivymd.app import MDApp

class bit_converter(MDApp):
    def __init__(self, **kwargs):
        super().__init__(**kwargs)
        self.input=0
        self.exchanged_result=0
    def build(self):
        return
    def set_input(self):
        # validation for integer
        if not self.root.ids.output.text.isdigit():
            self.root.ids.show_converted_amount.text = "Please enter a valid number"
        number= int(self.root.ids.input.text)
        self.input = number
    def byte_to_bit(self):
        self.exchanged_result = self.input*8
        self.root.ids.output.text = f" {self.exchanged_result} BITS"
    def bit_to_byte(self):
        self.exchanged_result = self.input/8
        self.root.ids.output.text = f" {self.exchanged_result} BYTES"


converter=bit_converter()
converter.run()
```
### kv
```.kv
Screen:
    size: 500,500
    MDBoxLayout:
        id: main
        orientation: 'vertical'
        size_hint:.8,.8
        pos_hint: {'center_x': .5, 'center_y': .5}

        MDLabel:
            text: 'Bit/Byte Converter'
            halign: 'center'
            font_style: 'H3'
            size_hint: 1, .3
            pos_hint: {'center_x': .5, 'center_y': .5}

        MDTextField:
            id: input
            hint_text: 'input bits/bytes you would like to convert'
            size_hint: 1, .2
            pos_hint: {'center_x': .5, 'center_y': .5}
            on_text: app.set_input()

        MDBoxLayout:
            id: buttons
            orientation: "horizontal"
            size_hint: 1, .2
            pos_hint: {'center_x': .5, 'center_y': .5}

            MDRaisedButton:
                id: bit_to_byte
                text: 'Convert Bits to Bytes'
                size_hint: .5, .8
                pos_hint: {'center_x': .5, 'center_y': .5}
                on_release: app.bit_to_byte()
            MDRaisedButton:
                id: byte_to_bit
                text: 'Convert Bytes to Bits'
                size_hint: .5, .8
                pos_hint: {'center_x': .5, 'center_y': .5}
                on_release: app.byte_to_bit()
        MDLabel:
            id: output
            text: '0'
            font_style: 'H4'
            halign: 'center'
            size_hint: 1, .3
            pos_hint: {'center_x': .5, 'center_y': .5}
```

## Showcase
<img width="912" alt="Screen Shot 2023-01-30 at 8 18 45 AM" src="https://user-images.githubusercontent.com/100017195/215361417-ff108f24-a664-425d-a3c2-a17b3ea5bc29.png">
<img width="912" alt="Screen Shot 2023-01-30 at 8 20 44 AM" src="https://user-images.githubusercontent.com/100017195/215361476-3e79020a-136a-4c37-89d6-ed94ca0bd1b3.png">
<img width="912" alt="Screen Shot 2023-01-30 at 8 20 51 AM" src="https://user-images.githubusercontent.com/100017195/215361479-9761cd10-8ce5-4dcc-96b8-66368ff7291a.png">

