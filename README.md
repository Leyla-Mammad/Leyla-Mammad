class Program
{
    static void Main()
    {
        Console.WriteLine("Enter name:");
        string input = Console.ReadLine();

        string reversedNames = ReverseIndividualWords(input);
        Console.WriteLine("Reversed names: " + reversedNames);
    }

    static string ReverseIndividualWords(string inputString)
    {
        string[] words = inputString.Split();
        string[] reversedWords = new string[words.Length];

        for (int i = 0; i < words.Length; i++)
        {
            string word = words[i];
            char[] reversedChars = new char[word.Length];

            for (int j = word.Length - 1, k = 0; j >= 0; j--, k++)
            {
                reversedChars[k] = word[j];
            }

            reversedWords[i] = new string(reversedChars);
        }

        string reversedString = string.Join(" ", reversedWords);

        return reversedString;
    }
}
