Homework 5 Answers  
1)  
```bash
```
2)  
```bash
triggerListURL = 'http://www.shahmoradi.org/ICP2017F/homework/5-problems/triggers.txt';
TriggerList = webread(triggerListURL);
TriggerList = strsplit(TriggerList , '\n'); 
dataDir = './swift/';
mkdir(dataDir);
missingFileCounter = 0;
for i = 1:length(TriggerList)
dataRepos = 'http://www.shahmoradi.org/ICP2017F/homework/5-problems/swift/';
filename = ['GRB',TriggerList{i},'_ep_flu.txt'];
dataURL = [dataRepos,filename];
try
    disp(['Fetching the file number: ', num2str(i)]);
    data = webread(dataURL);
    fid = fopen(filename,'w');
    fprintf(fid,'%s',data);
    fclose(fid);
catch
    missingFileCounter = missingFileCounter + 1;
    disp('The requested file does not exist on the web! Skipping...');
    disp(['Total number of missing files: ', num2str(missingFileCounter)]);
end
end
disp(['Total number of missing files: ', num2str(missingFileCounter)]);
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
