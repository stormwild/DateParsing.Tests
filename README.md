# DateParsing Test

Just a simple xunit test to see how to parse dates from a string.

## Test

```csharp
    [Fact]
    public void TestDateParsing()
    {
        // Test data
        string dateString1 = "2020-09-16";
        string dateString2 = "20210309";

        // Parse the first date string
        bool success1 = DateOnly.TryParse(dateString1, out DateOnly date1);

        // Parse the second date string using TryParseExact
        bool success2 = DateOnly.TryParseExact(
            dateString2,
            "yyyyMMdd",
            CultureInfo.InvariantCulture,
            DateTimeStyles.None,
            out DateOnly date2);

        Assert.True(success1, $"Failed to parse date string: {dateString1}");
        _output.WriteLine($"Parsed '{dateString1}' to {date1}");

        Assert.True(success2, $"Failed to parse date string: {dateString2}");
        _output.WriteLine($"Parsed '{dateString2}' to {date2}");
    }
```

Ooutput

```shell
Parsed '2020-09-16' to 16 Sep 2020
Parsed '20210309' to 9 Mar 2021
```
