1.

rng(131313)
nustudents = 99; 
StudentData= readtable(students.csv);
 
Groups=randperm(nustudents);
StudentGroups = cell(3,nustudents/3);
 
for i = 1:nustudents/3
    StudentGroups(:,i) = [StudentData(Groups(i))
                            StudentData(Groups(nustudents/3+i))
                            StudentData(Groups2*nustudents/(3+i))];
 
 
end
xlswrite('nameTriples.xlsx', StudentGroups')

2.

triggerListUrl = 'http://www.shahmoradi.org/ICP2017F/homework/5-problems/triggers.txt';
TriggerList = webread(triggerListUrl);
TriggerList = strsplit(TriggerList,'\n');

dataDir = './swift/';
mkdir(dataDir); %stores files in seperate and local file
missingFileCounter = 0;
for i = 1:length(TriggerList)
dataRepos = 'http://www.shahmoradi.org/ICP2017F/homework/5-problems/swift/';
filename = ['GRB',TriggerList{i},'_ep_flu.txt'];%[] concatenate
dataURL = [dataRepos,filename];
%missingFileCounter = 0;
    try
        disp(['Getting the num of files: ', num2str(i)]);
        data = webread(dataURL);
        fid = fopen(['./swift/',filename],'w');
        fprintf(fid,'%s',data);
        fclose(fid);        
    catch
        missingFileCounter = missingFileCounter + 1;
        disp(['The number of missing files: ',num2str(missingFileCounter)]);
    end %in this case errors are the only exceptions    
end

close all;
% Now read all data files and plot the results
dataDirectory = './swift/';
triggerListDirectory = './';
triggerList = fileread([triggerListDirectory,'fetchDataFromWeb.m']);
triggerList = strsplit(triggerList,'\r\n');
missingFileCounter = 0;

eventCounter = 0;
figure(); hold on; %('color','none','visible','off');
i = 1;length(triggerList)
filename = ['GRB',triggerList{i},'_ep_flu.txt'];
dataFile = [dataDirectory,filename];
if exist(dataFile,'file')
	disp (['Reading data for the event number ',num2str(i)]);
	data = readtable(dataFile);
	data = table2array(data);
	if~isempty(data)
		warning('This file is empty. Skipping...');
	elseif all(data(:,2)<0.0)
		eventCounter = eventCounter + 1;
	scatter(exp(data(:,2)) ...
			,data(:,1) ...
			,1 ...
			,'MarkerFaceColor', 'red' ...
			,'MarkerFaceColor', 'red' ...
			,'MarkerFaceAlpha', .01 ...
			,'MarkerFaceAlpha', .01 ...
			);
	end
else
	disp('There is a missing file. Skipping now...');
end

xlabel('Fluence [ergs/cm^2]',...
		'fontsize',13);
ylabel('E_{peak}',...
		'fontsize',13);
%title('Plot of E_{peak} vs Fluence for ',num2str(eventCounter),'Swift GRB events');
set(gca,'xscale','log','yscale','log');
xlim([1.e-8 1.e-2]);
ylim([1 10000]);
saveas(gcf,'swiftDataPlot.png');

3.

rng('shuffle')
nusample = 10000;
winCounter = 0; 
oddsOfWin = zeros(nusample,1);
doors = [1,2,3];
for isample = 1:nusample
    doorWithCar = randi(3);
    myChoice = randi(3);
    hostChoice = doors(doors~=doorWithCar);
    hostChoice = hostChoice(hostChoice~=myChoice);
    hostChoice = hostChoice(randi(length(hostChoice)));
    newChoice=6-hostChoice-myChoice;
    if newChoice==doorWithCar
        winCounter = winCounter+1;
        oddsOfWin(isample) = winCounter/isample;
    else
        oddsOfWin(isample) = oddsOfWin(isample-1);
    end
    disp(['odds of winning by switching:', num2str(oddsOfWin(isample))])
end
plot(oddsOfWin, 'linewidth',3,'color','red')
set(gca, 'xscale', 'log')

4.
function [F] = Montecarlo(S) %S stands for number of simulations
Ncircle = []; 

Xn = rand(S,1); %S determines the number of rows and the 1 makes one column
Yn = rand(S,1);

for t = 1:S
distance = Xn.^2 + Yn.^2 %Equation of a circle

Nucircle = sum(distance<=1); %If Radius of circle (which equals to one) is less than one then it is in the circle
Ncircle(t)= sum(distance(1:t) <=1);
est_pi=4*Ncircle(1:t)./(1:t);
esti_pi = 4*Nucircle/S;
disp(['Pi is ', num2str(esti_pi)]);
figure() 

plot(est_pi,'color', 'blue','markersize',20);
 title('Finding pi through other means', 'fontsize', 12)
 xlabel('Number of Random Sampled Points', 'fontsize', 13);
 ylabel('Estimate of pi','fontsize', 13);
 set(gca, 'linewidth',3);
 saveas(gcf,'Estimationofpi.png');
end 

COMMAND WINDOW

distance =

    1.1517
    1.4249
    0.2539
    0.6389
    0.9601
    1.7562
    0.0541
    1.3560
    0.6983
    0.9845
    0.3617
    0.5920
    0.6714
    0.9824
    0.4812
    0.6143
    1.1362
    1.2331
    0.5384
    0.5266
    0.1403
    0.6918
    1.2228
    0.1065
    0.9728
    0.8303
    0.3112
    0.5659
    0.4018
    0.5768

Pi is 3.0667

(FIGURES FOR QUESTION 3 & 4 ARE ATTACHED IN HW FOLDER AS SCREENSHOT, I COULDNT GET THE FIG FILE TO UPLOAD USING THE ONLINE MATLAB SYSTEM)

   
