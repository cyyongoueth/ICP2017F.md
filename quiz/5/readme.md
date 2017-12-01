1.
GrowthRate = importdata('chain.txt')
hold off;
figure() 
plot(GrowthRate.data(:,4)),'linewidth',3, 'color','blue'); %%something is wrong with getting just the fourth column
hold on;
title('Finding pi through other means', 'fontsize', 12)
 xlabel('Sample Number', 'fontsize', 13);
 ylabel('Growth Rate', 'fontsize', 13);
 set( gca , 'linewidth' , 'log' );
 saveas(gcf,'GrowthRate');
 pause 

2. function [F] = RobustWebRead(A,'s');
try
    webContent = imread('S')
catch
    disp('The webpage doesnt exist..sorry')
end

3. GCA is refers to the current active plot in the current active figure.
GCF is the current figure handle in MATLAB
