# Leadzen.ai-assignment4
import nltk
from nltk.chat.util import Chat, reflections

# Define pairs of patterns and responses
pairs = [
    ['hi|hello|hey', ['Hello!', 'Hey there!', 'Hi!']],
    ['how are you?', ['I am doing well, thank you!', 'I am good, thanks for asking. How about you?']],
    ['(what can you do for me?|what can you do?|help)', 
        ["I can answer your questions and engage in conversation. Feel free to ask me anything!"]],
    ['(.*) your name?', ["My name is Chatbot."]],
    ['(.*) (age|old) are you?', ["I am a chatbot. I don't have an age."]],
    ['(.*) (created|made) you?', ["I was created by developers using Python and NLTK."]],
    ['(.*) (goodbye|bye|exit)', ['Goodbye!', 'Bye!', 'See you later!']],
]

# Create a Chat instance
chatbot = Chat(pairs, reflections)

# Define a function to chat with the bot
def chat():
    print("Chatbot: Hello! I am a simple chatbot. You can start a conversation with me. Type 'quit' to exit.")
    while True:
        user_input = input("You: ")
        if user_input.lower() == 'quit':
            print("Chatbot: Goodbye!")
            break
        response = chatbot.respond(user_input)
        print("Chatbot:", response)

if __name__ == "__main__":
    chat()
