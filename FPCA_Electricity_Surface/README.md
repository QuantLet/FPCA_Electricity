
[<img src="https://github.com/QuantLet/Styleguide-and-FAQ/blob/master/pictures/banner.png" width="888" alt="Visit QuantNet">](http://quantlet.de/)

## [<img src="https://github.com/QuantLet/Styleguide-and-FAQ/blob/master/pictures/qloqo.png" alt="Visit QuantNet">](http://quantlet.de/) **FPCA_Electricity_Surface** [<img src="https://github.com/QuantLet/Styleguide-and-FAQ/blob/master/pictures/QN2.png" width="60" alt="Visit QuantNet 2.0">](http://quantlet.de/)

```yaml

Name of QuantLet:  FPCA_Electricity_Surface

Published in:      'Forecasting generalized quantiles of electricity demand: A functional data approach'

Description:       'Plots a surface of intradaily electricity load curves over time'

Keywords:          surface, functional data, electricity, demand, time-series

See also:          FPCA_Electricity_Simulation, FPCA_Electricity_Application

Author:            Franziska Schulz, Brenda López Cabrera

Submitted:         05.01.2017

Datafile:          LoadTSO.mat

Input:             FPCA_Electricity_Data.R, FPCA_Electricity_Functions
 
Example:           'Surface plot of electricity load curves'

```

![Picture1](FPCA_Electricity_Surface.png)


### Matlab Code:
```Matlab
clc
clear
load('LoadTSO.mat')

figure1 = figure('PaperType', 'a4letter');
axes1   = axes('Parent', figure1,...
    'ZTickLabel', {'100', '150', '200', '250', '300', '350'},...
    'YTickLabel', {'', '2012', '2011', '2010'},...
    'YTick', [0 365 712 1095],...
    'XTickLabel', {'00:00','06:00','12:00','18:00','24:00'},...
    'XTick', [0 25 50 75 100],...
    'FontSize', 14);
view(axes1, [-37.5 30]);
grid(axes1, 'on');
hold(axes1, 'all');

surf(Loadmat, 'Parent', axes1, 'EdgeColor', 'none');
xlabel('Time of day', 'FontSize', 20);
ylabel('Days', 'FontSize', 20);
zlabel('Load in 100 MW', 'FontSize', 20);

```
