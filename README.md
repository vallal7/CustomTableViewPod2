# CustomTableViewPod2
A tableview data source pod with custom cells which can download image icons and provide a nice UI and UX
To install and use the POD, follow the below 7 steps:

 // step 1 - add imports
    #import <TableViewDataSource.h>
    #import <SearchTableViewCell.h>

// step 2 - add property for pod datasource
    @property (nonatomic, retain) TableViewDataSource *dataSource; 

// step 3 - register the table view cell from pod with your tableview (searchTableView)
    [self.searchTableView registerClass:[SearchTableViewCell class] forCellReuseIdentifier:SearchTableCellIdentifier];

// step 4 initiailize and set the datasource
    self.dataSource = [[TableViewDataSource alloc] initWithTableView:self.searchTableView];
    self.searchTableView.dataSource = self.dataSource;
    
// step 5 - provide the dataarray
    self.dataSource.dataArray = self.searchResultsArray;

// step 6 - set the number of sections
    self.dataSource.numberOfSections = 1;
    
// step 7 - provide the datasource the new music results array object
    [weakSelf.dataSource reloadTableDataWithContent:arr];
