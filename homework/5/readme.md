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
```
4)  
```bash
```
