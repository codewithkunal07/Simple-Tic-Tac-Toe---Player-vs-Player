 **📁 Folder Structure**

```
tic-tac-toe-python/
│── tic_tac_toe.py
│── README.md
│── assets/
    │── preview.gif
    │── screenshot.png


---

## **🎮 tic\_tac\_toe.py** (Game Code)

```python
# 🎯 Simple Tic Tac Toe - Player vs Player

board = [" " for _ in range(9)]

def print_board():
    print(f"\n {board[0]} | {board[1]} | {board[2]} ")
    print("---+---+---")
    print(f" {board[3]} | {board[4]} | {board[5]} ")
    print("---+---+---")
    print(f" {board[6]} | {board[7]} | {board[8]} \n")

def check_winner(player):
    win_conditions = [
        [0,1,2], [3,4,5], [6,7,8], # rows
        [0,3,6], [1,4,7], [2,5,8], # columns
        [0,4,8], [2,4,6]           # diagonals
    ]
    return any(board[a] == board[b] == board[c] == player for a,b,c in win_conditions)

def is_full():
    return " " not in board

def play_game():
    current_player = "X"
    while True:
        print_board()
        try:
            move = int(input(f"Player {current_player}, choose position (1-9): ")) - 1
        except ValueError:
            print("❌ Please enter a valid number (1-9).")
            continue

        if move < 0 or move > 8 or board[move] != " ":
            print("⚠️ Invalid move! Try again.")
            continue

        board[move] = current_player

        if check_winner(current_player):
            print_board()
            print(f"🎉 Player {current_player} wins!")
            break

        if is_full():
            print_board()
            print("🤝 It's a draw!")
            break

        current_player = "O" if current_player == "X" else "X"

if __name__ == "__main__":
    play_game()
```

---

## **📄 README.md** (Premium GitHub Page)

````md
# 🎯 Tic Tac Toe – Python Edition

<p align="center">
  <img src="assets/preview.gif" alt="Tic Tac Toe Preview" width="500"/>
</p>

---

## 📜 About
A simple yet addictive **Tic Tac Toe** game made in Python.  
Play with a friend on the same computer – pure nostalgia, pure fun! 🎮  

---

## ✨ Features
✅ Player vs Player mode  
✅ Instant win detection  
✅ Draw detection  
✅ Lightweight – runs in any terminal  

---

## 🚀 How to Run
```bash
git clone https://github.com/YOUR-USERNAME/tic-tac-toe-python.git
cd tic-tac-toe-python
python tic_tac_toe.py
````

---

## 🖼 Preview

![Screenshot](assets/screenshot.png)

---

## 📌 Tech Used

* Python 3.x 🐍
* No external libraries – pure Python

---

## 📄 License

MIT License – Free to use & modify 🚀

```

---

## **📸 Assets Instructions**
1. **preview.gif** – Record your game using a free screen recorder (like OBS, ShareX) → save as GIF → put in `assets/` folder.  
2. **screenshot.png** – Take a screenshot of your game in the terminal → save in `assets/` folder.  
3. Upload everything to GitHub.


