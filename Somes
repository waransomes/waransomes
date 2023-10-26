import RPi.GPIO as GPIO
import time

# Define GPIO pins
MOTION_SENSOR_PIN = 17  # Replace with your actual pin number
PUMP_RELAY_PIN = 18     # Replace with your actual pin number

# Setup GPIO
GPIO.setmode(GPIO.BCM)
GPIO.setup(MOTION_SENSOR_PIN, GPIO.IN)
GPIO.setup(PUMP_RELAY_PIN, GPIO.OUT)

# Function to turn on the pump
def turn_on_pump():
    GPIO.output(PUMP_RELAY_PIN, GPIO.HIGH)
    print("Pump is ON")

# Function to turn off the pump
def turn_off_pump():
    GPIO.output(PUMP_RELAY_PIN, GPIO.LOW)
    print("Pump is OFF")

try:
    while True:
        if GPIO.input(MOTION_SENSOR_PIN):
            turn_on_pump()
            time.sleep(10)  # Run the pump for 10 seconds
            turn_off_pump()
        time.sleep(1)  # Wait for 1 second before checking again

except KeyboardInterrupt:
    print("\nProgram terminated by user")
    GPIO.cleanup()
