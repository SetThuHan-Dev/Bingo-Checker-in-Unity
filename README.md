# Bingo-Checker-in-Unity
Re-usable codes for Bingo Checking in Unity Game Dev

### 3*3 Matrix Bingo Checker
> Note : Constant Integers in MatrixArray are only calculated for 3 * 3 Matrix

```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using System;

/// <summary>
/// Note : Constant Integers in MatrixArray are only calculated for 3 * 3 Matrix
/// </summary>
public class BingoChecker: MonoBehaviour
{
    // replacable
    public CellElements cellElements;

    [SerializeField] int BingoRowIndex;
    [SerializeField] int BingoColumnIndex;
    [SerializeField] int BingoDiagonalIndex;
    [SerializeField] int TotalBingoClear;

    private const int Matrix = 3;  // 3 * 3 Matrix Calculation for Diagonal
    
    public void RowColumnDiagonalChecker()
    {
        BingoRowIndex = 0;
        BingoColumnIndex = 0;

        // replacable int
        // Already calculated for constant integers, not to be same values for each bingo check for 3 * 3 Matrix // eg. 1 to 8 line bingo
        int[,] MatrixArray = {
                        {cellElements.cells[0].ClaimedNum[0], cellElements.cells[1].ClaimedNum[0], cellElements.cells[2].ClaimedNum[0],  0},
                        {cellElements.cells[3].ClaimedNum[0], cellElements.cells[4].ClaimedNum[0], cellElements.cells[5].ClaimedNum[0], -1},
                        {cellElements.cells[6].ClaimedNum[0], cellElements.cells[7].ClaimedNum[0], cellElements.cells[8].ClaimedNum[0],  0},
                        {                                  1,                                   1,                                   0,  1}
                    };

        int Rows = MatrixArray.GetLength(0);
        int Columns = MatrixArray.GetLength(1);

        int SumRow, SumColumn;

        for (int i = 0; i < Rows; i++)
        {
            SumRow = 0;

            for (int j = 0; j < Columns; j++)
            {
                SumRow = SumRow + MatrixArray[i, j];
            }
            Debug.Log("Sum of row: " + i + " = " + SumRow);

            switch (BingoRowIndex)
            {
                case 0:
                    if (SumRow == 6 && BingoRowIndex == 0)
                    {
                        BingoRowIndex += 1;
                    }
                    else if (SumRow == 14 && BingoRowIndex == 0)
                    {
                        BingoRowIndex += 1;
                    }
                    else if (SumRow == 24 && BingoRowIndex == 0)
                    {
                        BingoRowIndex += 1;
                    }
                    break;

                case 1:
                    if (SumRow == 6 && BingoRowIndex == 1)
                    {
                        BingoRowIndex += 1;
                    }
                    else if (SumRow == 14 && BingoRowIndex == 1)
                    {
                        BingoRowIndex += 1;
                    }
                    else if (SumRow == 24 && BingoRowIndex == 1)
                    {
                        BingoRowIndex += 1;
                    }
                    break;

                case 2:
                    if (SumRow == 6 && BingoRowIndex == 2)
                    {
                        BingoRowIndex += 1;
                    }
                    else if (SumRow == 14 && BingoRowIndex == 2)
                    {
                        BingoRowIndex += 1;
                    }
                    else if (SumRow == 24 && BingoRowIndex == 2)
                    {
                        BingoRowIndex += 1;
                    }
                    break;

                case 3:
                    if (SumRow == 6 && BingoRowIndex == 3)
                    {
                        BingoRowIndex += 1;
                    }
                    else if (SumRow == 14 && BingoRowIndex == 3)
                    {
                        BingoRowIndex += 1;
                    }
                    else if (SumRow == 24 && BingoRowIndex == 3)
                    {
                        BingoRowIndex += 1;
                    }
                    break;

                case 4:
                    if (SumRow == 6 && BingoRowIndex == 4)
                    {
                        BingoRowIndex += 1;
                    }
                    else if (SumRow == 14 && BingoRowIndex == 4)
                    {
                        BingoRowIndex += 1;
                    }
                    else if (SumRow == 24 && BingoRowIndex == 4)
                    {
                        BingoRowIndex += 1;
                    }
                    break;

                case 5:
                    if (SumRow == 6 && BingoRowIndex == 5)
                    {
                        BingoRowIndex += 1;
                    }
                    else if (SumRow == 14 && BingoRowIndex == 5)
                    {
                        BingoRowIndex += 1;
                    }
                    else if (SumRow == 24 && BingoRowIndex == 5)
                    {
                        BingoRowIndex += 1;
                    }
                    break;

                default:
                    break;
            }

        }

        for (int i = 0; i < Columns; i++)
        {
            SumColumn = 0;

            for (int j = 0; j < Rows; j++)
            {
                SumColumn = SumColumn + MatrixArray[j, i];
            }
            Debug.Log("Sum of col: " + i + " = " + SumColumn);

            switch (BingoColumnIndex)
            {
                case 0:
                    if (SumColumn == 13 && BingoColumnIndex == 0)
                    {
                        BingoColumnIndex += 1;
                    }
                    else if (SumColumn == 16 && BingoColumnIndex == 0)
                    {
                        BingoColumnIndex += 1;
                    }
                    else if (SumColumn == 18 && BingoColumnIndex == 0)
                    {
                        BingoColumnIndex += 1;
                    }
                    break;

                case 1:
                    if (SumColumn == 13 && BingoColumnIndex == 1)
                    {
                        BingoColumnIndex += 1;
                    }
                    else if (SumColumn == 16 && BingoColumnIndex == 1)
                    {
                        BingoColumnIndex += 1;
                    }
                    else if (SumColumn == 18 && BingoColumnIndex == 1)
                    {
                        BingoColumnIndex += 1;
                    }
                    break;

                case 2:
                    if (SumColumn == 13 && BingoColumnIndex == 2)
                    {
                        BingoColumnIndex += 1;
                    }
                    else if (SumColumn == 16 && BingoColumnIndex == 2)
                    {
                        BingoColumnIndex += 1;
                    }
                    else if (SumColumn == 18 && BingoColumnIndex == 2)
                    {
                        BingoColumnIndex += 1;
                    }
                    break;

                case 3:
                    if (SumColumn == 13 && BingoColumnIndex == 3)
                    {
                        BingoColumnIndex += 1;
                    }
                    else if (SumColumn == 16 && BingoColumnIndex == 3)
                    {
                        BingoColumnIndex += 1;
                    }
                    else if (SumColumn == 18 && BingoColumnIndex == 3)
                    {
                        BingoColumnIndex += 1;
                    }
                    break;

                case 4:
                    if (SumColumn == 13 && BingoColumnIndex == 4)
                    {
                        BingoColumnIndex += 1;
                    }
                    else if (SumColumn == 16 && BingoColumnIndex == 4)
                    {
                        BingoColumnIndex += 1;
                    }
                    else if (SumColumn == 18 && BingoColumnIndex == 4)
                    {
                        BingoColumnIndex += 1;
                    }
                    break;

                case 5:
                    if (SumColumn == 13 && BingoColumnIndex == 5)
                    {
                        BingoColumnIndex += 1;
                    }
                    else if (SumColumn == 16 && BingoColumnIndex == 5)
                    {
                        BingoColumnIndex += 1;
                    }
                    else if (SumColumn == 18 && BingoColumnIndex == 5)
                    {
                        BingoColumnIndex += 1;
                    }
                    break;

            }
        }

        Diagonal_Checker(MatrixArray);
        TotalBingoClear = BingoRowIndex + BingoColumnIndex + BingoDiagonalIndex;
        Debug.LogWarning(TotalBingoClear + " Line Bingo!");

    }

    private void Diagonal_Checker(int[,] MatrixArray)
    {
        int SumOfLeftToRight = 0;
        int SumofRightToLeft = 0;

        BingoDiagonalIndex = 0;

        // Loop from i to MatrixArray-1 for rows
        for (int i = 0; i < Matrix; i++)
        {
            // Loop from j = MatrixArray-1 for columns
            for (int j = 0; j < Matrix; j++)
            {
                // Condition for diagonal Left to Right
                if (i == j)
                {
                    SumOfLeftToRight += MatrixArray[i, j];
                }

            }
        }

        // Print the final LeftToRightSum
        Debug.Log("Sum of DiaLeftToRight: " + SumOfLeftToRight);

        switch (BingoDiagonalIndex)
        {
            case 0:
                if (SumOfLeftToRight == 15 && BingoDiagonalIndex == 0)
                {
                    BingoDiagonalIndex += 1;
                }
                break;

            case 1:
                if (SumOfLeftToRight == 15 && BingoDiagonalIndex == 1)
                {
                    BingoDiagonalIndex += 1;
                }
                break;
            default:
                break;

        }

        // Loop from i to MatrixArray-1 for rows
        for (int i = 0; i < Matrix; i++)
        {
            // Loop from j = MatrixArray-1 for columns
            for (int j = 0; j < Matrix; j++)
            {
                // Condition for diagonal Right to Left
                if ((i + j) == Matrix - 1)
                {
                    SumofRightToLeft += MatrixArray[i, j];
                }

            }
        }

        // Print the final RightToLeft
        Debug.Log("Sum of DiaRightToLeft: " + SumofRightToLeft);

        switch (BingoDiagonalIndex)
        {
            case 0:
                if (SumofRightToLeft == 15 && BingoDiagonalIndex == 0)
                {
                    BingoDiagonalIndex += 1;
                }
                break;

            case 1:
                if (SumofRightToLeft == 15 && BingoDiagonalIndex == 1)
                {
                    BingoDiagonalIndex += 1;
                }
                break;

            default:
                break;

        }

    }
}

[Serializable]
public class CellElements
{
    public Cell[] cells;

}

```

> Preview --- In Scene


