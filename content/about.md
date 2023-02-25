---
title: "About me"
layout: page
_build:
    list: never
---



This is my about page

{{< highlight kotlin "linenos=table" >}}
fun main() {
    println("hola mundo!!!")
    println("Ni Hao")
    println("Saluton")
}
{{< / highlight >}}


{{< highlight gdscript "linenos=table, hl_lines=3" >}}
@onready var player = get_node("../Player")
export var speed = 100
func _ready():
    move_and_slide()
    pass
{{< / highlight >}}