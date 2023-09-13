Context: https://github.com/microsoft/microsoft-ui-xaml/issues/7282#issuecomment-1717060648

This is the Windows App SDK C# template, on top of which I have

- Removed x:Name
- Added a button to open and Activate() a new MainWindow
- Added a button to call Close() on the enclosing MainWindow
- Steps to reproduce this behavior are to

1. Build the Packaging project (both Debug and Release feature the issue)
2. Run the program with the debugger attached, to view memory usage information in VS
   - Alternatively, you can use Task Manager to track memory usage
3. Open one or more new windows
   - Observe that the memory usage increases as each new window is opened
4. Close several windows
   - Observe that the memory associated with the window is not freed
