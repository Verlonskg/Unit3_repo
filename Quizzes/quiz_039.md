# Quiz 039

## Code
```.py
from kivymd.app import MDApp

class quiz_039(MDApp):
    def __init__(self, **kwargs):
        super().__init__(**kwargs)
        self.count = 0
    def build(self):
        return
    def increase(self):
        self.count += 1
        self.root.ids.my_label.text = f" Count {self.count}"
test = quiz_039()
test.run()

```
## KV File 
```.py 
Screen:
    size: 500,500

    MDBoxLayout:
        size_hint: 0.7, 0.3 #percentages of the screen
        pos_hint:{"center_x":0.5, "center_y":0.5}
        orientation: "horizontal"

        MDLabel:
            id: my_label
            halign: "center"
            text: "Count"
            size_hint: 0.5,1
            font_size: 34
            pos_hint:{"center_x":0.75, "center_y":0.5}

        MDRaisedButton:
            id: my_button
            text: "Add +1"
            size_hint: 0.5,1
            md_bg_color: 'darkred'
            pos_hint:{"center_x":0.75, "center_y":0.5}
            font_size: 34
            on_release:
                app.increase()

``` 

![Test](https://github.com/Verlonskg/Unit3_repo/blob/main/Quizzes/Reasources/quiz_039_test.jpg)
