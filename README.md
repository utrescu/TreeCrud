# BlazorServerTree

A simple Server-Side Blazor CRUD app to deal with hierarchical data.

The project has a fake data layer service that allow running it without database backend configuration. We are migrating fake data layer to a real one with SQLGraph for R (Retrieve) and Rest for CUD (Create Update Delete)

The basic functionality is ready:

* Unexpand nodes and expand nodes with Lazy load.
* Select and unselect a node.
* Insert new nodes
* ToDo: Update, Delete
* ToDo: Real data layer and data on database.


### Screenshot ( because all us love screenshots ):

![screenshot](./Screenshots/theCrud.gif)

### Show me the code

```
    <UITreeComponent SourceData=@uiTree
                     SelectChangeDelegate=@OnSelectionChanged
                     LazyLoadNodesAsyncDelegate=@LoadNodes
                     CollapseAsyncDelegate=@OnCollapse
                     ExpandAsyncDelegate=@OnExpand
                     TriggerActionAsyncDelegate=@OnAction>
    </UITreeComponent>  

@functions {

    UITree uiTree = new UITree();
    
    private async Task<bool> OnExpand(int Id)
    {
        System.Console.WriteLine("Expanded " + Id);
        return await Task.FromResult(true);
    }

```

### Can I use `UITreeComponent` on my project?

Use it as your risk. Steps:

* Download the project.
* Add a reference to it from your own project.
* Add the following line in your `_ViewImports.cshtml`:  `@addTagHelper *, BlazorTreeControl` 
* Please, PR your improvements and Issue for comments.

Don't hesitate to contact me for further information :)

