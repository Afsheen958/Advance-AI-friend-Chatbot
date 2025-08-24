import math
import random

# ----------- Quiz Game -----------
def quiz_game():
    print("\n🎯 Welcome to Mini Quiz Game!")
    questions = [
        {
            "q": "What is the capital of Pakistan?",
            "options": ["1) Karachi", "2) Lahore", "3) Islamabad", "4) Peshawar"],
            "answer": "3"
        },
        {
            "q": "Which planet is known as the Red Planet?",
            "options": ["1) Venus", "2) Mars", "3) Jupiter", "4) Mercury"],
            "answer": "2"
        },
        {
            "q": "Who is known as the Father of Computers?",
            "options": ["1) Charles Babbage", "2) Alan Turing", "3) Bill Gates", "4) Steve Jobs"],
            "answer": "1"
        },
        {
            "q": "Which gas do humans need to survive?",
            "options": ["1) Carbon Dioxide", "2) Nitrogen", "3) Oxygen", "4) Helium"],
            "answer": "3"
        },
        {
            "q": "Which is the largest ocean in the world?",
            "options": ["1) Atlantic Ocean", "2) Pacific Ocean", "3) Indian Ocean", "4) Arctic Ocean"],
            "answer": "2"
        }
    ]

    question = random.choice(questions)
    print("\n" + question["q"])
    for opt in question["options"]:
        print(opt)

    user_ans = input("Enter your answer (1/2/3/4): ")

    if user_ans.strip() == question["answer"]:
        print("✅ Correct! 🎉")
    else:
        print(f"❌ Oops! The correct answer was option {question['answer']}.")

# ----------- Chatbot -----------
def chatbot():
    print("Hi! I am your AI Friend Chatbot.")
    name = input("What's your name? ")
    print(f"Nice to meet you, {name}!")

    color = input("What's your favorite color? ")
    if color.lower() == "pink":
        print("Wow! Pink is so cute and lovely.")
    elif color.lower() == "black":
        print("Black is bold and classy.")
    elif color.lower() == "blue":
        print("Blue feels so calm and peaceful.")
    else:
        print(f"{color.capitalize()} is a beautiful color!")

    hobby = input("What's your favorite hobby? ")
    print(f"That's amazing, {name}! I think {hobby} makes life more fun.")

    study = input("What subject are you studying these days? ")
    if study.lower() in ["math", "mathematics"]:
        print("Numbers are powerful! Math makes your brain sharp.")
    elif study.lower() in ["science", "physics", "chemistry", "biology"]:
        print("Science is amazing! It helps us understand the world better.")
    elif study.lower() in ["computer", "computer science", "cs", "programming"]:
        print("Computer Science is the future. Keep learning and coding!")
    else:
        print(f"{study.capitalize()} sounds interesting! Keep studying hard.")

    mood = input("How are you feeling today? (happy/sad/tired/excited) ")
    if mood.lower() == "happy":
        print("Yay! Stay happy and keep smiling.")
    elif mood.lower() == "sad":
        print("Ohh, don’t worry. Everything will be fine soon.")
    elif mood.lower() == "tired":
        print("Take some rest and drink water.")
    elif mood.lower() == "excited":
        print("Wow! I love your energy. Keep it up!")
    else:
        print("Thanks for sharing your mood!")

    # Fun Features
    choice = input("Do you want to try fun features? (yes/no) ")
    if choice.lower() == "yes":
        feature = input("Choose one: (1) Calculator (2) Quiz (3) Python Facts: ")
        if feature == "1":
            calculator()
        elif feature == "2":
            quiz_game()
        elif feature == "3":
            python_facts()

    print("\n✨ Fun Fact: The first chatbot was created in 1966 and was named ELIZA!")
    print(f"It was really nice talking with you, {name}. Bye! 👋")

# ----------- Calculator (with scientific functions) -----------
def calculator():
    print("\n🧮 Scientific Calculator Mode (type 'exit' to quit)")
    print("Supported operators: +, -, *, /, //, %, **, sqrt, sin, cos, tan, log")
    while True:
        expr = input("Enter calculation: ")
        if expr.lower() == "exit":
            print("Exiting calculator...")
            break
        try:
            parts = expr.split()
            if parts[0].lower() == "sqrt":
                num = float(parts[1])
                print("Result =", math.sqrt(num))
            elif parts[0].lower() == "sin":
                num = float(parts[1])
                print("Result =", math.sin(math.radians(num)))
            elif parts[0].lower() == "cos":
                num = float(parts[1])
                print("Result =", math.cos(math.radians(num)))
            elif parts[0].lower() == "tan":
                num = float(parts[1])
                print("Result =", math.tan(math.radians(num)))
            elif parts[0].lower() == "log":
                num = float(parts[1])
                print("Result =", math.log(num))
            else:
                if len(parts) != 3:
                    print("Format: number operator number (e.g., 12 ** 2)")
                    continue
                a, op, b = parts
                a, b = float(a), float(b)

                if op == '+':
                    result = a + b
                elif op == '-':
                    result = a - b
                elif op == '*':
                    result = a * b
                elif op == '/':
                    result = a / b
                elif op == '//':
                    result = a // b
                elif op == '%':
                    result = a % b
                elif op == '**':
                    result = a ** b
                else:
                    print("Operator not supported.")
                    continue

                print("Result =", result)
        except ZeroDivisionError:
            print("Error: Cannot divide by zero!")
        except Exception:
            print("Error: Invalid input.")

# ----------- Python Facts -----------
def python_facts():
    facts = [
        "🐍 Python was created by Guido van Rossum in 1991.",
        "🔥 The name 'Python' came from 'Monty Python’s Flying Circus', not the snake!",
        "⚡ Python is used by Google, Instagram, Netflix, and NASA.",
        "🤖 Python is one of the most popular languages for Artificial Intelligence.",
        "📚 Python has a huge collection of libraries like NumPy, Pandas, and TensorFlow."
    ]
    print("\n✨ Did you know?")
    print(random.choice(facts))

# Run chatbot
chatbot()
