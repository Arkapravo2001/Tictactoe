public class GameModel
{
    public char[,] Board { get; private set; }
    public char CurrentPlayer { get; private set; }

    public GameModel()
    {
        Board = new char[3, 3];
        CurrentPlayer = 'X'; // X starts the game
    }

    public bool MakeMove(int row, int col)
    {
        if (row >= 0 && row < 3 && col >= 0 && col < 3 && Board[row, col] == 0)
        {
            Board[row, col] = CurrentPlayer;
            // Check for win conditions or draw here
            // Update CurrentPlayer for the next turn
            CurrentPlayer = (CurrentPlayer == 'X') ? 'O' : 'X';
            return true; // Valid move
        }
        else
        {
            return false; // Invalid move
        }
    }
}
