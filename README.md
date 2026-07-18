from tkinter import Tk, Label
from time import strftime

def update_time():
    current_time = strftime('%H:%M:%S')
    current_date = strftime('%A, %d %B %Y')
    time_label.config(text=current_time)
    date_label.config(text=current_date)
    time_label.after(1000, update_time)

# Create window
root = Tk()
root.title('Digital Clock')
root.configure(bg='#1a1a2e')
root.resizable(False, False)

# Time display
time_label = Label(
    root,
    font=('Segoe UI', 80, 'bold'),
    bg='#1a1a2e',
    fg='#00d4ff'
)
time_label.pack(padx=60, pady=(40, 10))

# Date display
date_label = Label(
    root,
    font=('Segoe UI', 20),
    bg='#1a1a2e',
    fg='#ffffff'
)
date_label.pack(pady=(0, 40))

update_time()
root.mainloop()
