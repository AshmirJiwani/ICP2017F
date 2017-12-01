Quiz 5 answers)  
1) ```bash
    chainfile = importdata('chain.txt'); 
    data = chainfile.data; 
    y = data(:,4); 
    x = linspace(10^0,10^5,length(data)); 
    plot(x,y,'-r','LineWidth',2); 
    xlim([10^0 10^6]); box on; 
    set(gca,'xscale','log');
    xlabel('Sample Number');
    ylabel('Growth Rate');
   ```
2)  
```bash
    function result = robustWebRead(inputstr)
        disp('Reading data from web adress...');
      try
        result = webread(inputstr);
        disp('...Done');
      catch
        warning('The requested web address does not exist! Gracuefully exiting...');
      end
    end
    ```
   
3) 
```bash
gca and gcf are both used in the set() function in MATLAB but gca will refer to the current axis of the figure.  
gca will allow you to set the scale of the axexs.  
gcf refers to the current figure or graph. This will allow you to refer to the graph and save it or even scale the entire graph with the same result of using gca.
```
