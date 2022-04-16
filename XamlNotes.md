# XAML

## Template for a Window

```
<Window x:Class="HotelReservations.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:HotelReservations"
        xmlns:views="clr-namespace:HotelReservations.Views"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
    <StackPanel>
        
    </StackPanel>
</Window>
```
Notes:

<table>
    <tr>
        <td><code>xmlns</code></td>
        <td>Defines default namespace by which an XML element name should be resolved.</td>
    </tr>
    <tr>
        <td><code>xmlns:x</code></td>
        <td>Defines a non-default namespace. XML elements can be resolved if they are prefixes with <code>x:</code></td>
    </tr>
    <tr>
        <td><code>xmlns:d</code></td>
        <td>The schemas used to represent the design view of application.</td>
    </tr>
    <tr>
        <td><code>xmlns:mc</code></td>
        <td>Todo</td>
    </tr>
    <tr>
        <td><code>xmlns:local</code></td>
        <td>Todo</td>
    </tr>
    <tr>
        <td><code>xmlns:views</code></td>
        <td>Todo</td>
    </tr>
    <tr>
        <td><code>mc:Ignorable</code></td>
        <td>Specifies which XML namespace prefixes encountered in a markup file may be ignored by a XAML processor.</td>
    </tr>
    <tr>
        <td><code>clr-namespace</code></td>
        <td>The CLR namespace declared within the assembly that contains the public types to expose as elements.</td>
    </tr>
</table>
  

## Template for a Control
```
<UserControl x:Class="HotelReservations.Views.MakeReservationView"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:HotelReservations.Views"
        mc:Ignorable="d"
        d:DesignHeight="450" d:DesignWidth="800">
    <StackPanel>
        
    </StackPanel>
</UserControl>
```
Notes:
<table>
    <tr>
        <td><code>d:DesignHeight="450" d:DesignWidth="800" </code></td>
        <td>Sets the window size for the Visual Studio editor</td>
    </tr>
</table>


```
<Window x:Class="OnvifExplorerUI.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:OnvifExplorerUI"
        xmlns:views="clr-namespace:OnvifExplorerUI.Views"
        mc:Ignorable="d"
        Title="MainWindow" Height="450" Width="800">
    <StackPanel>
        <views:DevicesListView />
    </StackPanel>
</Window>
```

```
<Grid>
    <views:ReservationsListView DataContext="{Binding CurrentViewModel}" />
</Grid>
```
