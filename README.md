# Viethoa
Here are the steps
B1: Download the folder to your computer

B2: Drop the "stream" entry into the folder of qb-core

B3: Go to the folder
# Go to qb-core\client\functions.lua
# Find to

        QBCore.Functions = {}
        
# Add after it with :

       QBCore.RequestId = 0
       QBCore.Font = 0

            Citizen.CreateThread(function()
            RegisterFontFile('arial') 
        QBCore.Font = RegisterFontId('arial font')
            AddTextEntry('STRING', "<FONT FACE='arial font'>~a~</FONT>")
            AddTextEntry('CUSTOM_STRING', "<FONT FACE='arial font'>~a~</FONT>")
           end)

    QBCore.Functions.FloatingNotification = function(msg, x,y,z)
           AddTextEntry('FloatingNotification', "<FONT FACE='arial font'>"..msg.."</FONT>")
            SetFloatingHelpTextWorldPosition(1, x, y, z)
            SetFloatingHelpTextStyle(1, 1, 2, -1, 3, 0)
            BeginTextCommandDisplayHelp('FloatingNotification')
            EndTextCommandDisplayHelp(2, false, false, -1)
          end
