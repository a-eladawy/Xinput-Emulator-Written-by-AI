import tkinter as tk
import vgamepad as vg
import keyboard  # Use the keyboard library for key detection

# Initialize virtual Xbox controller
gamepad = vg.VX360Gamepad()


# Function to map keyboard inputs to controller inputs
def map_keyboard_to_controller():
    # Reset all inputs
    gamepad.reset()

    # Map keyboard keys to controller inputs
    if keyboard.is_pressed('w'):  # Move forward (left stick up)
        gamepad.left_joystick_float(x_value_float=0.0, y_value_float=1.0)
    if keyboard.is_pressed('s'):  # Move backward (left stick down)
        gamepad.left_joystick_float(x_value_float=0.0, y_value_float=-1.0)
    if keyboard.is_pressed('a'):  # Move left (left stick left)
        gamepad.left_joystick_float(x_value_float=-1.0, y_value_float=0.0)
    if keyboard.is_pressed('d'):  # Move right (left stick right)
        gamepad.left_joystick_float(x_value_float=1.0, y_value_float=0.0)

    if keyboard.is_pressed('up'):  # Look up (right stick up)
        gamepad.right_joystick_float(x_value_float=0.0, y_value_float=1.0)
    if keyboard.is_pressed('down'):  # Look down (right stick down)
        gamepad.right_joystick_float(x_value_float=0.0, y_value_float=-1.0)
    if keyboard.is_pressed('left'):  # Look left (right stick left)
        gamepad.right_joystick_float(x_value_float=-1.0, y_value_float=0.0)
    if keyboard.is_pressed('right'):  # Look right (right stick right)
        gamepad.right_joystick_float(x_value_float=1.0, y_value_float=0.0)

    if keyboard.is_pressed('space'):  # A button
        gamepad.press_button(button=vg.XUSB_BUTTON.XUSB_GAMEPAD_A)
    if keyboard.is_pressed('ctrl'):  # B button
        gamepad.press_button(button=vg.XUSB_BUTTON.XUSB_GAMEPAD_B)
    if keyboard.is_pressed('shift'):  # X button
        gamepad.press_button(button=vg.XUSB_BUTTON.XUSB_GAMEPAD_X)
    if keyboard.is_pressed('enter'):  # Y button
        gamepad.press_button(button=vg.XUSB_BUTTON.XUSB_GAMEPAD_Y)

    if keyboard.is_pressed('1'):  # Left bumper
        gamepad.press_button(button=vg.XUSB_BUTTON.XUSB_GAMEPAD_LEFT_SHOULDER)
    if keyboard.is_pressed('2'):  # Right bumper
        gamepad.press_button(button=vg.XUSB_BUTTON.XUSB_GAMEPAD_RIGHT_SHOULDER)

    if keyboard.is_pressed('q'):  # Left trigger
        gamepad.left_trigger_float(value_float=1.0)
    if keyboard.is_pressed('e'):  # Right trigger
        gamepad.right_trigger_float(value_float=1.0)

    # Additional buttons
    if keyboard.is_pressed('v'):  # View button (Back/Select equivalent)
        gamepad.press_button(button=vg.XUSB_BUTTON.XUSB_GAMEPAD_BACK)
    if keyboard.is_pressed('m'):  # Menu button (Start equivalent)
        gamepad.press_button(button=vg.XUSB_BUTTON.XUSB_GAMEPAD_START)
    if keyboard.is_pressed('h'):  # Home button (Xbox button)
        gamepad.press_button(button=vg.XUSB_BUTTON.XUSB_GAMEPAD_GUIDE)
    if keyboard.is_pressed('l'):  # L3 button (Left stick click)
        gamepad.press_button(button=vg.XUSB_BUTTON.XUSB_GAMEPAD_LEFT_THUMB)
    if keyboard.is_pressed('r'):  # R3 button (Right stick click)
        gamepad.press_button(button=vg.XUSB_BUTTON.XUSB_GAMEPAD_RIGHT_THUMB)

    # Update the virtual controller with the new inputs
    gamepad.update()


# GUI Application
class XboxControllerEmulatorApp:
    def __init__(self, master):
        self.master = master
        self.master.title("Xbox Controller Emulator")

        # Label for instructions
        self.label = tk.Label(master, text="Press keys to emulate Xbox controller inputs.")
        self.label.pack()

        # Start the input mapping loop
        self.map_inputs()

    def map_inputs(self):
        map_keyboard_to_controller()
        self.master.after(10, self.map_inputs)  # Call this function every 10ms


# Run the application
if __name__ == "__main__":
    root = tk.Tk()
    app = XboxControllerEmulatorApp(root)
    root.mainloop()
