# DotNetAssignment2
```c#

using System;
using System.Text.RegularExpressions;

class Program
{
    static void Main()
    {
        string inputString = "20230911 asd2324234jghjsd hjsdg sdhk 01072024 idf32432 32423 d34234jh dfh";
        
        
        string pattern = @"\b(\d{2})(\d{2})(\d{4})\b";
        
     
        MatchCollection matches = Regex.Matches(inputString, pattern);

        
        foreach (Match match in matches)
        {
            int month = int.Parse(match.Groups[1].Value);
            int day = int.Parse(match.Groups[2].Value);
            int year = int.Parse(match.Groups[3].Value);

            if (IsValidDate(month, day, year))
            {
                string formattedDate = $"{month:D2}{day:D2}{year:D4}";
                Console.WriteLine("Valid Date Found: " + formattedDate);
            }
        }
    }

    // Function to check if the date is valid
    static bool IsValidDate(int month, int day, int year)
    {
        try
        {
            DateTime date = new DateTime(year, month, day);
            return true;
        }
        catch (ArgumentOutOfRangeException)
        {
            return false;
        }
    }
}
```
![assignment_outputscreen2](https://github.com/chaithanya08-kashyap/DotNetAssignment2/assets/155832480/8fa0ca76-e984-49f8-a479-6f5b0977c713)
