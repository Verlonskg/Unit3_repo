# The GUI Task

## Example 1
### Python Code
```.py
from kivymd.app import MDApp

class Example_01(MDApp):
  def build(self):
    return

test = Example_01()
test.run()

```

### KV File

```.kv
Screen:
  size: 500, 500

  MDLabel:
    text: "H3LL0 W0RLD"
    halign: "center"
    font_size: "34pt"

```

## Example 2
### Python Code

```.py
from kivymd.app import MDApp

class Example_02(MDApp):
  def build(self):
    return
  def close(self):
    exit()

test = Example_02()
test.run()

```
### KV File

```.kv
Screen:
  size: 500, 500

  MDBoxLayout:
    pos_hint: {"center_x": 0.5}
    size_hint: .7, .7
    md_bg_color: "#8B0000"
    orientation: "vertical"

    MDLabel:
      text: "Hello World"
      halign: "center"
      font_size: "34pt"

    MDRaisedButton:
      text: "Close"
      size_hint: .5, 1
      font_size: "34pt"
      md_bg_color: "#FF0000"
      on_press:
        app.close()

```

## Example 3
### Python Code
```.py
from kivymd.app import MDApp

class Example_03(MDApp):
    def build(self):
        return

    def change_author(self, name):
        self.root.ids.title.text = f"Author {name}"


test = Example_03()
test.run()

```
### KV File
```.kv
Screen:
  size: 500, 500

  MDLabel:
    id: title
    text: ""
    font_style: "H1"
    pos_hint: {center_y: .8}
    halign: "center"

  MDBoxLayout:
    pos_hint: {"center_x": 0.5, "center_y": .5}
    size_hint: .7, .2
    orientation: "horizontal"

    MDChip:
        text: "Author A"
        pos_hint: {"center_y": .5}
        icon_right: "close-circle-outline"
        md_bg_color: "#003049"
        text_color: "#FFFFFF"
        on_press: app.change_author ("A")

    MDChip:
        text: "Author B"
        pos_hint: ("center_y": .5}
        icon_right: "close-circle-outline"
        md_bg_color: "#D62828"
        on_press: app.change_author ("B")
        icon_right: "close-circle-outline"
        md_bg_color: "#D62828"
        on_press: app.change_author ("B")

    MDChip:
        text: "Author C"
        pos_hint: {"center_y": 5}
        icon_right: "close-circle-outline"
        md_bg_color: "#F77F00"
        on_press: app.change_author ("C")

    MDChip:
        text: "Author D"
        pos_hint: {"center_y": .5}
        icon_right: "close-circle-outline"
        md_bg_color: "#FCBF49"
        on_press: app.change_author ("D")

    MDChip:
        text: "Author E"
        pos_hint: {"center_y": 5}
        icon_right: "close-circle-outline"
        md_bg_color: "#EAE2B7"
        icon_left: "map-marker"
        on_press: app.change_author ("E")

```
## Task 1
### Python Code
```.py
from kivymd.app import MDApp


class gui_test(MDApp):
    def __init__(self, **kwargs):
        super().__init__(**kwargs)
        self.count = 0
    def build(self):
        return
    def usdconvert(self):
        number = self.root.ids.currency_input.text
        if number.isdigit():
            self.count = round(int(number) * 0.00022, 2)
            self.root.ids.converted_amount.text = f" {self.count} USD"
        else:
            self.root.ids.converted_amount.text = "Please input an integer"

    def jpyconvert(self):
        number = self.root.ids.currency_input.text
        if number.isdigit():
            self.count = round(int(number) * 0.029, 2)
            self.root.ids.converted_amount.text = f" {self.count} JPY"
        else:
            self.root.ids.converted_amount.text = "Please input an integer"




m = gui_test()
m.run()
```
### KV File


```.kv

Screen:
    size:500,500 #width, height
    md_bg_color: "#a3b18a"

    MDBoxLayout:
        id: main_box
        orientation: "vertical"
        size_hint: .75, .75
        pos_hint: {"center_x": .5, "center_y":.5}

        MDLabel:
            id: title
            font_size: 50
            halign: "center"
            text: "Currency converter"
            size_hint: 1, 0.2
            pos_hint: {"center_x": .5}

        MDTextField:
            id: currency_input
            hint_text: "Enter an amount in Colombian Pesos"
            size_hint: .8, .1
            pos_hint: {"center_x": .5}

        MDBoxLayout:
            id: second_box
            orientation: "horizontal"
            size_hint: 1, 0.4
            pos_hint: {"center_x": .5}

            MDLabel:
                id: click
                text: "Click to convert"
                size_hint: 0.5, 1
                pos_hint: {"center_x": .5, "center_y": .75}
                halign: "center"

            MDBoxLayout:
                id: third_box
                orientation: "vertical"
                size_hint: .5, 1

                MDBoxLayout:
                    id: fourth_box
                    orientation: "horizontal"
                    size_hint: .5,1

                    MDRaisedButton:
                        id: jpy
                        text: "USD"
                        pos_hint: {"center_x": .25, "center_y": .5}
                        md_bg_color: "#02075d"
                        on_press: app.usdconvert()
                        text_color: "#FFFFFF"

                    MDRaisedButton:
                        id: usd
                        text: "JPY"
                        pos_hint: {"center_x": .75, "center_y": .5}
                        md_bg_color: "#FF0000"
                        on_press: app.jpyconvert()

                MDLabel:
                    id: converted_amount
                    halign: "center"
                    size_hint: 0.5, .7
                    text: ""
                    font_size: 50

```

![screenshot](https://github.com/Verlonskg/Unit3_repo/edit/main/Tasks/Reasources/Task_01_01.png)
![screenshot](https://github.com/Verlonskg/Unit3_repo/edit/main/Tasks/Reasources/Task_01_02.png)
![screenshot](https://github.com/Verlonskg/Unit3_repo/edit/main/Tasks/Reasources/Task_01_03.png)
![screenshot](https://github.com/Verlonskg/Unit3_repo/edit/main/Tasks/Reasources/Task_01_04.png)

