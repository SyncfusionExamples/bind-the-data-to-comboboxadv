# Bind Data to ComboBoxAdv in WPF
## Overview
This guide explains how to bind data to the Syncfusion WPF ComboBoxAdv control. ComboBoxAdv supports data binding, making it easy to display dynamic data in your WPF applications.

## Adding Items via Data Binding
### 1. Create Model and ViewModel

**Model Class**
```C#
public class PopulationInfo
{
    public string Continent { get; set; }
    public string Country { get; set; }
    public double Growth { get; set; }
    public double Population { get; set; }
}
```
**ViewModel Class**
```C#
public class PopulationViewModel
{
    public PopulationViewModel()
    {
        PopulationDetails = new ObservableCollection<PopulationInfo>
        {
            new PopulationInfo { Continent = "Asia", Country = "Indonesia", Growth = 3, Population = 237641326 },
            new PopulationInfo { Continent = "Asia", Country = "Russia", Growth = 2, Population = 152518015 },
            new PopulationInfo { Continent = "Asia", Country = "Malaysia", Growth = 1, Population = 29672000 },
            new PopulationInfo { Continent = "North America", Country = "United States", Growth = 4, Population = 315645000 },
            new PopulationInfo { Continent = "North America", Country = "Mexico", Growth = 2, Population = 112336538 },
            new PopulationInfo { Continent = "North America", Country = "Canada", Growth = 1, Population = 35056064 },
            new PopulationInfo { Continent = "South America", Country = "Colombia", Growth = 1, Population = 47000000 },
            new PopulationInfo { Continent = "South America", Country = "Brazil", Growth = 3, Population = 193946886 },
            new PopulationInfo { Continent = "Africa", Country = "Nigeria", Growth = 2, Population = 170901000 },
            new PopulationInfo { Continent = "Africa", Country = "Egypt", Growth = 1, Population = 83661000 },
            new PopulationInfo { Continent = "Europe", Country = "Germany", Growth = 1, Population = 81993000 },
            new PopulationInfo { Continent = "Europe", Country = "France", Growth = 1, Population = 65605000 },
            new PopulationInfo { Continent = "Europe", Country = "UK", Growth = 1, Population = 63181775 }
        };
    }

    public ObservableCollection<PopulationInfo> PopulationDetails { get; set; }
}
```

### 2. Bind Data in XAML

Set the DataContext and bind the ItemsSource property:

```XAML
<Grid>
    <Grid.DataContext>
        <local:PopulationViewModel/>
    </Grid.DataContext>
    <syncfusion:ComboBoxAdv x:Name="comboBoxAdv"
                             Height="30"
                             Width="200"
                             ItemsSource="{Binding PopulationDetails}"
                             DisplayMemberPath="Country"/>
</Grid>
```


## How to Run This Application
- Clone the bind-the-data-to-comboboxadv repository.
- Open the solution in Visual Studio 2022.
- Build and run the project to view the output.

## Troubleshooting
**Path Too Long Exception**

If you encounter this error:
- Close Visual Studio.
- Rename the repository folder to a shorter name.
- Reopen and build the project.

## Screenshot
![Bind data to ComboBoxAdv](ComboBox/Image/Bind%20data%20ComboBox.png)