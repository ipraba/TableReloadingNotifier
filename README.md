# TableReloadingNotifier
A sample project which provides how to notify when the table view has finished loading.


I have created this project as this stackoverflow post was getting lot of views
http://stackoverflow.com/questions/1483581/get-notified-when-uitableview-has-finished-asking-for-data/21581834#21581834

This is just a proof of concept for the answer i have provided in the post.

Solution
========
Though tableview provides a lot of delegates by default there is no delegate to intimate when the tableview has actually finished loading. 
The solution would be to use the GCD after the tableview.reload is called

        self.tableView.reloadData()
        dispatch_async(dispatch_get_main_queue(), { () -> Void in
            print("Reload Finished after cells are crated");
        })

 

Tested Environments
===================

iOS7, iOS8 and iOS9

Screenshots
===========


