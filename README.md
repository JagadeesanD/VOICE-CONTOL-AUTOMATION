# VOICE-CONTOL-AUTOMATION
pip install SpeechRecognition
import speech_recognition as sr

def listen_for_commands():
    recognizer = sr.Recognizer()
    
    with sr.Microphone() as source:
        print("Listening... Say a command.")
        recognizer.adjust_for_ambient_noise(source)
        audio = recognizer.listen(source)

    try:
        command = recognizer.recognize_google(audio).lower()
        print("You said:", command)
        return command
    except sr.UnknownValueError:
        print("Sorry, I didn't understand that.")
    except sr.RequestError:
        print("Could not request results from Google Speech Recognition service.")
    return None

def perform_action(command):
    
    if "turn on the lights" in command:
        print("Turning on the lights...")
       
    elif "turn off the lights" in command:
        print("Turning off the lights...")
    
    elif "play music" in command:
        print("Playing music...")
       
    elif "stop music" in command:
        print("Stopping music...")
   
    else:
        print("Command not recognized.")

def main():
    while True:
        command = listen_for_commands()
        if command:
            perform_action(command)

if __name__ == "__main__":
    main()


#VOICE CONTROL AUTOMATION 
#CODING IN THE PYTHON 
