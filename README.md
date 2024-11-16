# SimpleChess

<!DOCTYPE html>
<html>
<head>
    <title>Chessboard Integration</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/chessboard-js/1.0.0/chessboard-1.0.0.min.css">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/chessboard-js/1.0.0/chessboard-1.0.0.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/chess.js/0.10.3/chess.min.js"></script>
</head>
<body>
    <h1>Chess Game Viewer</h1>
    <div id="board" style="width: 400px"></div>
    <button onclick="loadGame()">Load Game</button>

    <script>
        const board = Chessboard('board', {
            draggable: true,
            dropOffBoard: 'trash',
            sparePieces: true
        });

        function loadGame() {
            // Example PGN of a game
            const pgn = '[Event "F/S Return Match"] [Site "Belgrade, Serbia JUG"] [Date "1992.11.04"] [White "Fischer, Robert J."] [Black "Spassky, Boris V."] [Result "1/2-1/2"]';
            const chess = new Chess();
            chess.load_pgn(pgn);
            board.position(chess.fen());
        }
    </script>
</body>
</html>
