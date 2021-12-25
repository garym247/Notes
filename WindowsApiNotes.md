# Window Creation


```Create```

```CreateEx```

```GetWindowLong(...) and SetWindowLongPtr(...)```

```LONG GetWindowLong(...);```


# Window Handles

```CWnd::FromHandle()```


# Safe handles


```GetSafeHwnd()```


# Attaching Handles


```CWnd::Attach()```

```CWnd::SubclassWindow()```



# Windows Co-ordinate System


```MoveWindow(...)```

```SetWindowPos(...)```

```GetWindowRect(...)```      screen co-ordinates



# CFrameWnd vs CFrameWndEx


```CFrameWndEx::AdjustDockingLayout()```
```CFrameWndEx::RecalcLayout()```


# Windows Messaging

For re-routing of command messages (i.e. `WM_COMMAND`) override `MainFrame::OnCmdMsg(....)`

Order of messages when resizing:

