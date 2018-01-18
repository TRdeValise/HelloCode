# HelloCode
MyStudy

public class Main {

	public static void main(String[] args) 
	{
		Scanner in = new Scanner(System.in);
		final int size = in.nextInt();
		int[] [] board = new int [size][size];
		boolean getret = false;		
		int numOfX = 0;
		int numOfO = 0;
		
		for(int i=0;i<board.length;i++)
		{
			for(int j=0;j<board[i].length ;j++)
			{
				board[i][j] = in.nextInt();
			}
		}
		
		for(int i=0;i<board.length;i++)
		{
			numOfX = 0;
			numOfO = 0;
			
			for(int j=0;j<board[i].length ;j++)
			{
				if(board[i][j] == 1)
				{
					numOfX ++;
				}
				else
				{
					numOfO ++;
				}				
			}
			
			if( numOfX == size || numOfO == size )
			{
				getret = true;
				break;
			}
			
		}
		
		if(!getret)
		{
			for(int i=0;i<board.length;i++)
			{
				numOfX = 0;
				numOfO = 0;
				
				for(int j=0;j<board[i].length ;j++)
				{
					if(board[j][i] == 1)
					{
						numOfX ++;
					}
					else
					{
						numOfO ++;
					}				
				}
				
				if( numOfX == size || numOfO == size )
				{
					getret = true;
					break;
				}
			}
		}
		
		if(!getret)
		{
			numOfX = 0;
			numOfO = 0;
			
			for(int i=0;i<board.length;i++)
			{
				if( board[i][i] == 1 )
				{
					numOfX ++;
				}
				else 
				{
					numOfO ++;
				}
			}
			
			if( numOfX == size || numOfO == size )
			{
				getret = true;
			}
			
		}
		
		if(!getret)
		{
			numOfX = 0;
			numOfO = 0;
			
			for(int i=0;i<board.length;i++)
			{
				if( board[i][size-i-1] == 1 )
				{
					numOfX ++;
				}
				else 
				{
					numOfO ++;
				}
			}
			
			if( numOfX == size || numOfO == size )
			{
				getret = true;
			}
			
		}
		
		if(getret)
		{
			if(numOfX == size)
			{
				System.out.println("X");
			}
			else if (numOfO == size)
			{
				System.out.println("O");
			}
		}
		else
		{
			System.out.println("NIL");
		}
		
	}

}
