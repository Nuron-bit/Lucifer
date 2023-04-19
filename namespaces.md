# LUCIFER V1 - API DOCUMENTATION [NAMESPACES]

## ImGui
ImGui is a bloat-free graphical user interface library for C++. Wrapped to lua by Nuron.

### Functions:
* `Text(label: string)` : Renders a text.
* `Button(label: string) -> boolean` : Renders a button with given label. Returns true if its clicked.
* `Button(label: string, size: ImVec2) -> boolean` : Renders a button with given label and size. Returns true if its clicked.
* `Checkbox(label: string, var: string) -> boolean` : Renders a checkbox with given label. Returns true if pressed.
* `SameLine()` : Sets cursor position y to previous position.
* `SetCursorPos(position: ImVec2)` : Sets cursor position as ImVec2.
* `GetCursorPos() -> ImVec2` : Returns current cursor position as ImVec2.
* `BeginTabBar(label: string) -> boolean` : Creates a tab bar. Returns true if active.
* `EndTabBar()` : Ends a tab bar. **Must be called** if you used BeginTabBar.
* `BeginTabItem(label: string) -> boolean` : Creates a tab item. Returns true if active.
* `EndTabItem(label: string)` : Ends a tab item. **Must be called** if you have used BeginTabItem before!
* `Slider(label: string, min: number, max: number, var: string) -> boolean` : Creates a slider where you can modify your integer value in run-time. Returns true if changed.
* `InputNumber(label: string, var: string) -> boolean` : Creates a input box where you can modify your integer value in run-time. Returns true if changed.
* `InputString(label: string, var: string, max_size: string) -> boolean` : Creates a input box where you can modify your string value in run-time. Returns true if changed.
* `Bullet()` : Creates a imgui bullet.
* `BulletText(label: string)` : Creates a imgui bullet with given label.
### Example Code
```lua

geiger_enabled = false
geiger_speed = 1

function OnRender()
  if ImGui.BeginTabBar("Opinions") then
    if ImGui.BeginTabItem("Geiger Mod") then
      ImGui.Checkbox("Enabled", "geiger_enabled")
      
      if geiger_enabled then -- Render additional widgets if its enabled.
        ImGui.Slider("Geiger Speed", 1, 1000, "geiger_speed")
        ImGui.InputNumber("Geiger Speed", "geiger_speed")
      end
      
      ImGui.Text("Inventory Items")
      for i, item in pairs(GetBot():getInventory().items) do
        ImGui.Bullet(GetInfo(item.id).name)
      end
    end
    ImGui.EndTabBar()
  end
end

AddCallback(CallbackType.render, "OnRender")

-- Your Stuff goes here
while true do
  ...
end
```
