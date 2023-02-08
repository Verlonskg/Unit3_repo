# Quiz 040

## Code
```.py
from kivymd.app import MDApp

class quiz_040(MDApp):

    def __init__(self, **kwargs):
        super().__init__(**kwargs)
        self.count = 0

    def build(self):
        return

    def colorchange(self):
        if self.root.ids.Box.md_bg_color == "#000000":
            self.root.ids.Box.md_bg_color = "#FFFFFF"
        else:
            self.root.ids.Box.md_bg_color = "#000000"


test = quiz_040()
test.run()

```
## KV File 
```.py 
Screen:

    size: 500,500

    MDBoxLayout:
        id: Box
        size_hint: 1,1
        md_bg_color: "#FFFFFF"
        orientation: "vertical"

        MDLabel:
            id:message
            text: "Quiz_040, by Verlon"
            pos_hint: {"center_x": 0.5, "center_y": 0.5}
            halign: "center"
            font_size: 50
            color: "#888888"
            size_hint: .5, 1

        MDRaisedButton:
            id: Colorchange
            text: "Switch Theme"
            size_hint: .1,.1
            pos_hint: {"center_x": 0.05, "center_y": 0.1}
            on_press:
                app.colorchange()

``` 

![Test](https://github.com/Verlonskg/Unit3_repo/blob/main/Quizzes/Reasources/quiz_040_test.jpg)
![Test](https://github.com/Verlonskg/Unit3_repo/blob/main/Quizzes/Reasources/quiz_040_test.2.jpg)
