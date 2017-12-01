Homework 5 Answers  
1)  
```bash
function output = RandomGroupsof3()
rng(131313);
triples = randperm(99);
fileID = fopen('students.csv');
mytable = readtable('students.csv');
output = cell(33,3);
r = 1;
c = 1;
for i = 1:99
    output{r,c} = cell2mat(mytable{triples(i),2});
    if(r == 33)
        r = 1;
        c = c + 1;
    else
        r = r + 1;
    end
end
fclose(fileID);
xlswrite('groups.xlsx',output);
end
```
2)  
```bash
function fetchDataFromWeb()
data = webread('http://www.shahmoradi.org/ICP2017F/homework/5-problems/triggers.txt');
data = strsplit(data ,'\n'); 
dataDir = '.swift/';
mkdir(dataDir);
missingFileCounter = 0;
for i = 1:length(data)
    try
        dataRepos = 'http://www.shahmoradi.org/ICP2017F/homework/5-problems/swift/';
        filename = ['GRB',data{i},'_ep_flu.txt'];
        dataURL = [dataRepos,filename];
        fileID = fopen([dataDir,filename],'w');
        fprintf(fileID, '%s', webread(dataURL));
        fclose(fileID);
    catch
        missingFileCounter = missingFileCounter + 1;
        disp('The requested file does not exist on the web! Skipping...');
    end
end
disp(['Total number of missing files: ', num2str(missingFileCounter)]);
end
```
```bash
function plotDataFromFile2()

directory = dir('C:\Users\Ashmir\Downloads\swift');
success = 0;
data = [0,0];
    for i = 3:size(directory)
        if(directory(i).bytes > 0)
            currentdata = readtable(['.swift/',directory(i).name]);
            try
                currarr = table2array(currentdata);
                if(all(currarr(:,2)< 0.0)) 
                    data = [data ; table2array(currentdata)];
                    success = success + 1;
                end
             catch
                 disp(['Could not recognize at', directory(i).name]);
             end
         end
    end

scatter(exp(data(:,2)), data(:,1), 1,'red','filled','MarkerFaceAlpha',.1,'MarkerEdgeAlpha',.1);
   
title('Plot of E_p_e_a_k vs Fluence for 650 Swift GRB events');
xlabel('Fluence [ergs/cm^2]');
set(gca,'xscale','log');
xlim([1.0000e-08 1.0000e-02]);
xticks([ 1.0000e-8 1.0000e-6 1.0000e-4 1.0000e-2]);
    
   
ylabel('E_p_e_a_k');
set(gca,'yscale','log');
ylim([1.0000e0 1.0000e04]);
 
disp(num2str(success));
end 
```
3)  
```bash
function montehall()
rng('shuffle');
winCounter = 0; 
nsample = 10000;
data = [0,0];
    for isample = 1:nsample
        doors = [1,2,3];
        doorWithCar = randi(3);
        myChoice = randi(3);
        hostChoice = doors(doors~=doorWithCar);
        hostChoice = hostChoice(hostChoice~=myChoice);
        hostChoice = hostChoice(randi(length(hostChoice))); 
        mynewChoice = 6-hostChoice-myChoice;
        if(mynewChoice == doorWithCar)
           winCounter = winCounter + 1;
           data = [data ; [isample winCounter/isample]];
        end
    end
    scatter((data(:,1)), data(:,2),1);
    disp (['The winning percentage due to switching is ', num2str(winCounter/nsample)]);
```
```bash
>> montehall
The winning percentage due to switching is 0.6592
```
4)  
```bash
ntotal = [1000 2000 3000 4000 5000 6000 7000 8000 9000 10000];
pi = zeros(1,10);
for j = 1:10
    x = rand(1,ntotal(j));
    y = rand(1,ntotal(j));
    counter = 0;
for i = 1:ntotal(j)
   if x(i)^2 + y(i)^2 <= 1
       counter = counter + 1;
   end
end
pi(j) = (4*counter)/ntotal(j);
end
disp(pi);

plot(ntotal,pi);
axis([0 10000 0 3.5])
```
```bash
>> montelhallapprox2
    3.1160    3.1420    3.1480    3.1450    3.1632    3.1287    3.1503    3.1595    3.1444    3.0964
```
