# pong game

import turtle

# make screen
screen = turtle.Screen()
screen.title("Pong")
screen.bgcolor("black")
screen.setup(width = 1000, height = 600)

# make left paddle
left_paddle = turtle.Turtle()
left_paddle.speed(0)
left_paddle.shape("square")
left_paddle.color("red")
left_paddle.shapesize(stretch_wid = 5, stretch_len = 1)
left_paddle.penup()
left_paddle.goto(-400, 0)

# make right paddle
right_paddle = turtle.Turtle()
right_paddle.speed(0)
right_paddle.shape("square")
right_paddle.color("blue")
right_paddle.shapesize(stretch_wid = 5, stretch_len = 1)
right_paddle.penup()
right_paddle.goto(400, 0)

# make a ball
ball = turtle.Turtle()
ball.speed(40)
ball.shape("circle")
ball.color("white")
ball.penup()
ball.goto(0, 0)
ball.dx = 5
ball.dy = -5

# scores start at zero
left_player = 0
right_player = 0

# displays the score
score = turtle.Turtle()
score.speed(0)
score.color("white")
score.penup()
score.hideturtle()
score.goto(0, 260)
score.write("Left player : 0   Right player: 0", align = "center", font = ("Courier", 24, "normal"))

# functions that move the paddles
def leftPaddleUp():
    y = left_paddle.ycor()
    y += 20
    left_paddle.sety(y)

def leftPaddleDown():
    y = left_paddle.ycor()
    y -= 20
    left_paddle.sety(y)

def rightPaddleUp():
    y = right_paddle.ycor()
    y += 20
    right_paddle.sety(y)

def rightPaddleDown():
    y = right_paddle.ycor()
    y -= 20
    right_paddle.sety(y)

# keyboard keys that move the paddles
screen.listen()
screen.onkeypress(leftPaddleUp, "w")
screen.onkeypress(leftPaddleDown, "s")
screen.onkeypress(rightPaddleUp, "Up")
screen.onkeypress(rightPaddleDown, "Down")

while True:
    screen.update()
    ball.setx(ball.xcor() + ball.dx)
    ball.sety(ball.ycor() + ball.dy)

    # check borders
    if ball.ycor() > 280:
        ball.sety(280)
        ball.dy *= -1
    
    if ball.ycor() < -280:
        ball.sety(-280)
        ball.dy *= -1
    
    if ball.xcor() > 500:
        ball.goto(0, 0)
        ball.dy *= -1
        left_player += 1
        score.clear()
        score.write("Left player : {}   Right player : {}".format(left_player, right_player), align = "center", font = ("Courier", 24, "normal"))

    if ball.xcor() < -500:
        ball.goto(0, 0)
        ball.dy *= -1
        right_player += 1
        score.clear()
        score.write("Left player : {}   Right player : {}".format(left_player, right_player), align = "center", font = ("Courier", 24, "normal"))

    # paddle ball collision
    if (ball.xcor() > 360 and ball.xcor() < 370) and (ball.ycor() < right_paddle.ycor()+40 and ball.ycor() > right_paddle.ycor()-40) :
        ball.setx(360)
        ball.dx *= -1
    
    if (ball.xcor() < -360 and ball.xcor() > -370) and (ball.ycor() < left_paddle.ycor()+40 and ball.ycor()>left_paddle.ycor()-40) :
        ball.setx(-360)
        ball.dx *= -1
