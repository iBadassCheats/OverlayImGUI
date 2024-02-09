## C# IMGUI OVERLAY
- Nvidia Overlay (Thanks zaafar/ClickableTransparentOverlay)
- ImguiUtils (My own, Custom ImGui Draws - Center Text, Tooltip, tabButton)
- Memory (Thanks erfg12/memory.dll)

```
        [StructLayout(LayoutKind.Sequential)]
        public struct RECT
        {
            public int left;
            public int top;
            public int right;
            public int bottom;
        }

        [DllImport("user32.dll", SetLastError = true)]
        static extern bool GetWindowRect(IntPtr hWnd, ref RECT Rect);

        static RECT Rect = new RECT();

        GetWindowRect(Cfg_Settings.process.MainWindowHandle, ref Rect);
        Rect.left += 10;
        Rect.top += 31;
        User32.MoveWindow(Handle, Rect.left, Rect.top, Rect.right - Rect.left - 7, Rect.bottom - Rect.top, true);
```C#
