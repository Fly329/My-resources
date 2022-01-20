#我的资源
EnablePrimaryMouseButtonEvents (true)
Hong = false
step = 5  设置宏力度，值越大，下滑越快
  function OnEvent(event, arg)
	OutputLogMessage("event = %s, arg = %d\n", event, arg)
   if (event == "MOUSE_BUTTON_PRESSED" and arg == 4) then   绑定鼠标按键，4为鼠标侧键
    Hong = not Hong
     if Hong then
      OutputLogMessage("kai \n")   按4宏打开
      else
      OutputLogMessage("guan \n")  再按4宏关闭
     end
   end
 if (event == "MOUSE_BUTTON_RELEASED" and arg == 4) then
 end
    if Hong then
     if (event == "MOUSE_BUTTON_PRESSED" and arg == 1 and Hong) then
    	  repeat
       Sleep(10)  鼠标移动流畅度
       MoveMouseRelative(0,step)  鼠标移动方向  x，y
    	  until not IsMouseButtonPressed(1)
 	 end
   end
end

