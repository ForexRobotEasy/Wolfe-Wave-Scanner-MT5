# Wolfe Wave Scanner MT5

Developer's site: [forexroboteasy.com](https://forexroboteasy.com)

Development: Forex Robot Easy Team

## Global Variables

- `g_currentSymbolIndex` - Current symbol index
- `g_currentTimeframeIndex` - Current timeframe index

## Initialization Function

```c++
int OnInit()
{
    // Initialize the scanner button
    ButtonCreate(0, 'Scanner Button', 0, 0, 100, 30);

    return(INIT_SUCCEEDED);
}
```

## Deinitialization Function

```c++
void OnDeinit(const int reason)
{
    // Delete the scanner button
    ButtonDelete(0);
}
```

## Button Click Event Handler

```c++
void OnButtonClick(const int button)
{
    // Check if the scanner button was clicked
    if (button == 0)
    {
        // Initiate all-symbol scan across all timeframes
        ScanSymbolsAndTimeframes();
    }
}
```

## Scan Symbols and Timeframes Function

```c++
void ScanSymbolsAndTimeframes()
{
    // Loop through all symbols
    for (int i = 0; i < SymbolsTotal(); i++)
    {
        // Set the current symbol index
        g_currentSymbolIndex = i;

        // Loop through all timeframes
        for (int j = 0; j < PeriodsTotal(); j++)
        {
            // Set the current timeframe index
            g_currentTimeframeIndex = j;

            // Perform scanning and provide detailed overview
            PerformScanning();
        }
    }
}
```

## Perform Scanning Function

```c++
void PerformScanning()
{
    // TODO: Implement the scanning algorithm and provide detailed overview
    // Perform scanning logic here based on the current symbol and timeframe
    // Output the scanning results and detailed overview for informed decision-making
    // ...

    // Example: Output the current symbol and timeframe
    Print('Scanning symbol: ', SymbolName(g_currentSymbolIndex));
    Print('Scanning timeframe: ', PeriodToString(g_currentTimeframeIndex));
}
```

## OnTick Event Handler

```c++
void OnTick()
{
    // Check if the scanner button was clicked
    if (ButtonPressed(0))
    {
        // Initiate all-symbol scan across all timeframes
        ScanSymbolsAndTimeframes();
    }
}
```

Forex Robot Easy is not the official developer of the Wolfe Wave Scanner MT5. This code is provided as a sample that can work as described in the product. To find the official developer of this product, please refer to MQL5. 

For detailed reviews and trading results of this product, visit [forexroboteasy.com](https://forexroboteasy.com/forex-robot-review/wolfe-wave-scanner-mt5-review-one-click-all-symbol-all-timeframe-scan/).
