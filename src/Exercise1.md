@startuml

class Circle{
	-radius: double
	Circle(x_origin: Double, y_origin: Double, newradius: Double, name: String, colour: Colour)
	+set_radius(newradius: Double): void
	+get_radius(): Double
	+area(): Double
	+perimeter(): Double
	+volume(): Double
	+toString(): String
}

Circle <|-- "extends" Shape

class Colour{
	-colour: String
	-Colour(s: String)
	-setColour(newColour: String): void
	+toString(): String
}

+class Geometry{
	-shapes: TreeSet<Shape>
	+{static} main(args: String[]): void
}

class Point2{
	-colour: Colour
	-xCoordinate: Double
	-yCoordinate: Double
	+Point(a: Double, b: Double, c: Colour)
	+toString(): String
	+getx(): Double
	+setx(newvalue: Double): void
	+gety(): Double
	+sety(newvalue: Double): void
	+distance(other: Point): double
	+{static} distance(that: Point, other: Point): double
}

class Prism{
	-height: Double
	+Prism(x: Double, y: Double, l: Double, w: Double, h: Double, name: String, colour: Colour)
	+set_height(h: Double): void
	+height(): Double
	+area(): Double
	+perimeter(): Double
	+volume(): Double
	+toString(): String
}

Prism <|-- "extends" Rectangle

class Rectangle{
	#width: Double
	#length: Double
	+Rectangle(x_origin: Double, y_origin: Double, new_length: Double, new_width: Double, name: String, colour: Colour)
	#set_length(newlength: Double): void
	#get_length(): Double
	#area(): Double
	#perimeter(): Double
	#volume(): Double
	+toString(): String
}

Rectangle <|-- "extends" Shape


abstract class Shape{
	#origin: Point
	#name: Text
	{abstract}#area(): Double
	{abstract}#perimeter(): Double
	{abstract}#volume(): Double
	#getOrigin(): Point
	#getName(): String
	#distance(other: Shape): Double
	#distance(a: Shape, b: Shape): Double
	#move(dx: Double, dy: Double): void
	+toString(): String
}

+class Text{
	-text: String
	+Text(text: String)
	+setText(newText: String): void
	+getText(): String
	+toString(): String
}






@enduml