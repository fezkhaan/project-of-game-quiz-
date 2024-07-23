# project-of-game-quiz-
This is my first project which is based on simple game quiz 
def get_questions():
    return [
        {
            "question": "What is the capital of France?",
            "options": ["A. Paris", "B. London", "C. Berlin", "D. Madrid"],
            "answer": "A"
        },
        {
            "question": "Which planet is known as the Red Planet?",
            "options": ["A. Earth", "B. Mars", "C. Jupiter", "D. Venus"],
            "answer": "B"
        },
        {
            "question": "Who wrote 'To Kill a Mockingbird'?",
            "options": ["A. Harper Lee", "B. Mark Twain", "C. J.K. Rowling", "D. Ernest Hemingway"],
            "answer": "A"
        }
    ]

def ask_question(question_data):
    print(question_data["question"])
    for option in question_data["options"]:
        print(option)
    
    while True:
        user_answer = input("Your answer (A, B, C, or D): ").upper()
        if user_answer in ['A', 'B', 'C', 'D']:
            break
        else:
            print("Invalid input. Please enter A, B, C, or D.")
    
    return user_answer

def provide_feedback(user_answer, correct_answer):
    if user_answer == correct_answer:
        print("Correct!")
        return True
    else:
        print(f"Incorrect. The correct answer is {correct_answer}.")
        return False

def quiz_game():
    questions = get_questions()
    score = 0
    
    for question_data in questions:
        user_answer = ask_question(question_data)
        if provide_feedback(user_answer, question_data["answer"]):
            score += 1
        print()  # Print a newline for better readability
    
    print(f"Your final score is {score} out of {len(questions)}.")

if __name__ == "__main__":
    quiz_game()

