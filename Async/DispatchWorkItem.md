---
title: DispatchWorkItem
link: https://developer.apple.com/documentation/dispatch/dispatchworkitem
---

DispatchWorkItem: A dispatch work item has a cancel flag. If it is cancelled before running, the dispatch queue won’t execute it and will skip it. If it is cancelled during its execution, the cancel property return True. In that case, we can abort the execution

- CANCELLABLE

```class SearchViewController: UIViewController, UISearchBarDelegate {
    // We keep track of the pending work item as a property
    private var pendingRequestWorkItem: DispatchWorkItem?

    func searchBar(_ searchBar: UISearchBar, textDidChange searchText: String) {
        // Cancel the currently pending item
        pendingRequestWorkItem?.cancel()

        // Wrap our request in a work item
        let requestWorkItem = DispatchWorkItem { [weak self] in
            self?.resultsLoader.loadResults(forQuery: searchText)
        }

        // Save the new work item and execute it after 250 ms
        pendingRequestWorkItem = requestWorkItem
        DispatchQueue.main.asyncAfter(deadline: .now() + .milliseconds(250),
                                      execute: requestWorkItem)
    }
}
```

DispatchWorkItemFlags: A set of behaviors for a work item, such as its quality-of-service class and whether to create a barrier or spawn a new detached thread.

[dispatchWorkItemFlags](https://developer.apple.com/documentation/dispatch/dispatchworkitemflags)
