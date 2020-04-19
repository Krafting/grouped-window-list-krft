applets.js: 
    435:
from '''    onWindowMonitorChanged(screen, metaWindow, metaWorkspace) {
        if (this.state.monitorWatchList.length !== this.numberOfMonitors) {
            let appList = this.getCurrentAppList();
            appList.windowRemoved(metaWorkspace, metaWindow);
            appList.windowAdded(metaWorkspace, metaWindow);
        }
    }'''
to '''    onWindowMonitorChanged(screen, metaWindow, metaWorkspace) {
        if (true === true) {
            let appList = this.getCurrentAppList();
        }
    }'''
used to prevend adding/removing windows each time we move a windows from one monitor to another

appList.js:
    261:
from '''        if (!app
            || (!isFavoriteApp
                && metaWindow
                && this.state.monitorWatchList.indexOf(metaWindow.get_monitor()) === -1)) {
            return;
        }'''
to '''        if (!app
            || (!isFavoriteApp
                && metaWindow
                && this.state.monitorWatchList.indexOf(metaWindow.get_monitor()) > 1)) {
            return;
        }'''
    226:

    200: 
            if (this.state.settings.showAllWorkspaces) {
            windows = global.display.list_windows(0);
        } else {
            windows = this.metaWorkspace.list_windows();
        }

    499: 
    from '''        if (this.numberOfMonitors === 1) {
            monitorWatchList = [Main.layoutManager.primaryIndex];
        } else if (instances.length > 1 && !onPrimary) {
            monitorWatchList = [this.panel.monitorIndex];
        }'''
    to '''        if (this.numberOfMonitors > 1) {
            monitorWatchList = [Main.layoutManager.primaryIndex];
        } else if (instances.length === 1 && !onPrimary) {
            monitorWatchList = [this.panel.monitorIndex];
        }''' 


this is not accurate tbh






