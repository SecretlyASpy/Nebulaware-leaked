if shared.VapeExecuted then
	local VERSION = "4.10"..(shared.VapePrivate and " PRIVATE" or "").." "..readfile("vape/commithash.txt"):sub(1, 6)
	local baseDirectory = (shared.VapePrivate and "vapeprivate/" or "vape/")
	local vapeAssetTable = {
		["vape/assets/AddItem.png"] = "rbxassetid://13350763121",
		["vape/assets/AddRemoveIcon1.png"] = "rbxassetid://13350764147",
		["vape/assets/ArrowIndicator.png"] = "rbxassetid://13350766521",
		["vape/assets/BackIcon.png"] = "rbxassetid://13350767223",
		["vape/assets/BindBackground.png"] = "rbxassetid://13350767577",
		["vape/assets/BlatantIcon.png"] = "rbxassetid://13350767943",
		["vape/assets/CircleListBlacklist.png"] = "rbxassetid://13350768647",
		["vape/assets/CircleListWhitelist.png"] = "rbxassetid://13350769066",
		["vape/assets/ColorSlider1.png"] = "rbxassetid://13350769439",
		["vape/assets/ColorSlider2.png"] = "rbxassetid://13350769842",
		["vape/assets/CombatIcon.png"] = "rbxassetid://13350770192",
		["vape/assets/DownArrow.png"] = "rbxassetid://13350770749",
		["vape/assets/DiscordIcon.png"] = "rbxassetid://13546311177",
		["vape/assets/ExitIcon1.png"] = "rbxassetid://13350771140",
		["vape/assets/FriendsIcon.png"] = "rbxassetid://13350771464",
		["vape/assets/HoverArrow.png"] = "rbxassetid://13350772201",
		["vape/assets/HoverArrow2.png"] = "rbxassetid://13350772588",
		["vape/assets/HoverArrow3.png"] = "rbxassetid://13350773014",
		["vape/assets/HoverArrow4.png"] = "rbxassetid://13350773643",
		["vape/assets/InfoNotification.png"] = "rbxassetid://13350774006",
		["vape/assets/KeybindIcon.png"] = "rbxassetid://13350774323",
		["vape/assets/LegitModeIcon.png"] = "rbxassetid://13436400428",
		["vape/assets/MoreButton1.png"] = "rbxassetid://13350775005",
		["vape/assets/MoreButton2.png"] = "rbxassetid://13350775731",
		["vape/assets/MoreButton3.png"] = "rbxassetid://13350776241",
		["vape/assets/NotificationBackground.png"] = "rbxassetid://13350776706",
		["vape/assets/NotificationBar.png"] = "rbxassetid://13350777235",
		["vape/assets/OnlineProfilesButton.png"] = "rbxassetid://13350777717",
		["vape/assets/PencilIcon.png"] = "rbxassetid://13350778187",
		["vape/assets/PinButton.png"] = "rbxassetid://13350778654",
		["vape/assets/ProfilesIcon.png"] = "rbxassetid://13350779149",
		["vape/assets/RadarIcon1.png"] = "rbxassetid://13350779545",
		["vape/assets/RadarIcon2.png"] = "rbxassetid://13350779992",
		["vape/assets/RainbowIcon1.png"] = "rbxassetid://13350780571",
		["vape/assets/RainbowIcon2.png"] = "rbxassetid://13350780993",
		["vape/assets/RightArrow.png"] = "rbxassetid://13350781908",
		["vape/assets/SearchBarIcon.png"] = "rbxassetid://13350782420",
		["vape/assets/SettingsWheel1.png"] = "rbxassetid://13350782848",
		["vape/assets/SettingsWheel2.png"] = "rbxassetid://13350783258",
		["vape/assets/SliderArrow1.png"] = "rbxassetid://13350783794",
		["vape/assets/SliderArrowSeperator.png"] = "rbxassetid://13350784477",
		["vape/assets/SliderButton1.png"] = "rbxassetid://13350785680",
		["vape/assets/TargetIcon.png"] = "rbxassetid://13350786128",
		["vape/assets/TargetIcon1.png"] = "rbxassetid://13350786776",
		["vape/assets/TargetIcon2.png"] = "rbxassetid://13350787228",
		["vape/assets/TargetIcon3.png"] = "rbxassetid://13350787729",
		["vape/assets/TargetIcon4.png"] = "rbxassetid://13350788379",
		["vape/assets/TargetInfoIcon1.png"] = "rbxassetid://13350788860",
		["vape/assets/TargetInfoIcon2.png"] = "rbxassetid://13350789239",
		["vape/assets/TextBoxBKG.png"] = "rbxassetid://13350789732",
		["vape/assets/TextBoxBKG2.png"] = "rbxassetid://13350790229",
		["vape/assets/TextGUIIcon1.png"] = "rbxassetid://13350790634",
		["vape/assets/TextGUIIcon2.png"] = "rbxassetid://13350791175",
		["vape/assets/TextGUIIcon3.png"] = "rbxassetid://13350791758",
		["vape/assets/TextGUIIcon4.png"] = "rbxassetid://13350792279",
		["vape/assets/ToggleArrow.png"] = "rbxassetid://13350792786",
		["vape/assets/UpArrow.png"] = "rbxassetid://13350793386",
		["vape/assets/UtilityIcon.png"] = "rbxassetid://13350793918",
		["vape/assets/WarningNotification.png"] = "rbxassetid://13350794868",
		["vape/assets/WindowBlur.png"] = "rbxassetid://13350795660",
		["vape/assets/WorldIcon.png"] = "rbxassetid://13350796199",
		["vape/assets/VapeIcon.png"] = "rbxassetid://13350808582",
		["vape/assets/RenderIcon.png"] = "rbxassetid://13350832775",
		["vape/assets/VapeLogo1.png"] = "rbxassetid://13350860863",
		["vape/assets/VapeLogo3.png"] = "rbxassetid://13350872035",
		["vape/assets/VapeLogo2.png"] = "rbxassetid://13350876307",
		["vape/assets/VapeLogo4.png"] = "rbxassetid://13350877564"
	}
	local getcustomasset = getsynasset or getcustomasset or function(location) return vapeAssetTable[location] or "" end
	local customassetcheck = (getsynasset or getcustomasset) and true
	local requestfunc = syn and syn.request or http and http.request or http_request or fluxus and fluxus.request or request or function() end
	local isfile = isfile or function(file)
		local suc, res = pcall(function() return readfile(file) end)
		return suc and res ~= nil
	end
	local loadedsuccessfully = false
	local GuiLibrary = {
		Settings = {},
		Profiles = {
			default = {Keybind = "", Selected = true}
		},
		RainbowSpeed = 0.6,
		GUIKeybind = "RightShift",
		CurrentProfile = "default",
		KeybindCaptured = false,
		PressedKeybindKey = "",
		ToggleNotifications = false,
		Notifications = false,
		ToggleTooltips = false,
		ObjectsThatCanBeSaved = {["Gui ColorSliderColor"] = {Api = {Hue = 0.44, Sat = 1, Value = 1}}},
		MobileButtons = {},
		RainbowSliders = {}
	}
	local runService = game:GetService("RunService")
	local inputService = game:GetService("UserInputService")
	local httpService = game:GetService("HttpService")
	local tweenService = game:GetService("TweenService")
	local guiService = game:GetService("GuiService")
	local textService = game:GetService("TextService")
	local translations = shared.VapeTranslation or {}
	local translatedlogo = false

	GuiLibrary.ColorStepped = runService.RenderStepped:Connect(function()
		local col = (tick() * 0.25 * GuiLibrary.RainbowSpeed) % 1
		for i, v in pairs(GuiLibrary.RainbowSliders) do
			v.SetValue(col)
		end
	end)

	local function randomString()
		local randomlength = math.random(10,100)
		local array = {}

		for i = 1, randomlength do
			array[i] = string.char(math.random(32, 126))
		end

		return table.concat(array)
	end

	local function RelativeXY(GuiObject, location)
		local x, y = location.X - GuiObject.AbsolutePosition.X, location.Y - GuiObject.AbsolutePosition.Y
		local x2 = 0
		local xm, ym = GuiObject.AbsoluteSize.X, GuiObject.AbsoluteSize.Y
		x2 = math.clamp(x, 4, xm - 6)
		x = math.clamp(x, 0, xm)
		y = math.clamp(y, 0, ym)
		return x, y, x/xm, y/ym, x2/xm
	end

	local gui = Instance.new("ScreenGui")
	gui.Name = randomString()
	gui.DisplayOrder = 999
	gui.ZIndexBehavior = Enum.ZIndexBehavior.Global
	gui.OnTopOfCoreBlur = true
	gui.ResetOnSpawn = false
	gui.Parent = game:GetService("Players").LocalPlayer.PlayerGui
	GuiLibrary["MainGui"] = gui

	local vapeCachedAssets = {}
	local function vapeGithubRequest(scripturl)
		if not isfile("vape/"..scripturl) then
			local suc, res = pcall(function() return game:HttpGet("https://raw.githubusercontent.com/7GrandDadPGN/VapeV4ForRoblox/"..readfile("vape/commithash.txt").."/"..scripturl, true) end)
			assert(suc, res)
			assert(res ~= "404: Not Found", res)
			if scripturl:find(".lua") then res = "--This watermark is used to delete the file if its cached, remove it to make the file persist after commits.\n"..res end
			writefile("vape/"..scripturl, res)
		end
		return readfile("vape/"..scripturl)
	end

	local function downloadVapeAsset(path)
		if customassetcheck then
			if not isfile(path) then
				task.spawn(function()
					local textlabel = Instance.new("TextLabel")
					textlabel.Size = UDim2.new(1, 0, 0, 36)
					textlabel.Text = "Downloading "..path
					textlabel.BackgroundTransparency = 1
					textlabel.TextStrokeTransparency = 0
					textlabel.TextSize = 30
					textlabel.Font = Enum.Font.SourceSans
					textlabel.TextColor3 = Color3.new(1, 1, 1)
					textlabel.Position = UDim2.new(0, 0, 0, -36)
					textlabel.Parent = GuiLibrary.MainGui
					repeat task.wait() until isfile(path)
					textlabel:Destroy()
				end)
				local suc, req = pcall(function() return vapeGithubRequest(path:gsub("vape/assets", "assets")) end)
				if suc and req then
					writefile(path, req)
				else
					return ""
				end
			end
		end
		if not vapeCachedAssets[path] then vapeCachedAssets[path] = getcustomasset(path) end
		return vapeCachedAssets[path]
	end

	GuiLibrary["UpdateHudEvent"] = Instance.new("BindableEvent")
	GuiLibrary["SelfDestructEvent"] = Instance.new("BindableEvent")
	GuiLibrary["LoadSettingsEvent"] = Instance.new("BindableEvent")

	local scaledgui = Instance.new("Frame")
	scaledgui.Name = "ScaledGui"
	scaledgui.Size = UDim2.new(1, 0, 1, 0)
	scaledgui.BackgroundTransparency = 1
	scaledgui.Parent = GuiLibrary["MainGui"]
	local clickgui = Instance.new("Frame")
	clickgui.Name = "ClickGui"
	clickgui.Size = UDim2.new(1, 0, 1, 0)
	clickgui.BackgroundTransparency = 1
	clickgui.BorderSizePixel = 0
	clickgui.BackgroundColor3 = Color3.fromRGB(79, 83, 166)
	clickgui.Visible = false
	clickgui.Parent = scaledgui
	local searchbarmain = Instance.new("Frame")
	searchbarmain.Size = UDim2.new(0, 220, 0, 37)
	searchbarmain.Position = UDim2.new(0.5, -110, 0, -23)
	searchbarmain.ClipsDescendants = false
	searchbarmain.ZIndex = 10
	searchbarmain.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
	searchbarmain.Name = "SearchBar"
	searchbarmain.Parent = clickgui
	local searchbarchildren = Instance.new("Frame")
	searchbarchildren.Size = UDim2.new(1, 0, 1, -37)
	searchbarchildren.Position = UDim2.new(0, 0, 0, 37)
	searchbarchildren.BackgroundTransparency = 1
	searchbarchildren.ZIndex = 10
	searchbarchildren.Parent = searchbarmain
	local searchbaricon = Instance.new("ImageLabel")
	searchbaricon.BackgroundTransparency = 1
	searchbaricon.ZIndex = 10
	searchbaricon.Image = downloadVapeAsset("vape/assets/SearchBarIcon.png")
	searchbaricon.Size = UDim2.new(0, 14, 0, 14)
	searchbaricon.Position = UDim2.new(1, -32, 0, 10)
	searchbaricon.Parent = searchbarmain
	local searchbar = Instance.new("TextBox")
	searchbar.PlaceholderText = ""
	searchbar.Text = ""
	searchbar.ZIndex = 10
	searchbar.TextColor3 = Color3.fromRGB(121, 121, 121)
	searchbar.Size = UDim2.new(1, -56, 0, 37)
	searchbar.Font = Enum.Font.Gotham
	searchbar.TextXAlignment = Enum.TextXAlignment.Left
	searchbar.TextSize = 15
	searchbar.Position = UDim2.new(0, 56, 0, 0)
	searchbar.BackgroundTransparency = 1
	searchbar.Parent = searchbarmain
	local searchbarshadow = Instance.new("ImageLabel")
	searchbarshadow.AnchorPoint = Vector2.new(0.5, 0.5)
	searchbarshadow.Position = UDim2.new(0.5, 0, 0.5, 0)
	searchbarshadow.Image = downloadVapeAsset("vape/assets/WindowBlur.png")
	searchbarshadow.BackgroundTransparency = 1
	searchbarshadow.ZIndex = -1
	searchbarshadow.Size = UDim2.new(1, 6, 1, 6)
	searchbarshadow.ImageColor3 = Color3.new(0, 0, 0)
	searchbarshadow.ScaleType = Enum.ScaleType.Slice
	searchbarshadow.SliceCenter = Rect.new(10, 10, 118, 118)
	searchbarshadow.Parent = searchbarmain
	local searchbarround = Instance.new("UICorner")
	searchbarround.CornerRadius = UDim.new(0, 5)
	searchbarround.Parent = searchbarmain
	local searchbaricon2 = Instance.new("ImageButton")
	searchbaricon2.Size = UDim2.new(0, 29, 0, 16)
	searchbaricon2.AutoButtonColor = false
	searchbaricon2.Image = downloadVapeAsset("vape/assets/LegitModeIcon.png")
	searchbaricon2.BackgroundTransparency = 1
	searchbaricon2.Name = "LegitMode"
	searchbaricon2.ZIndex = 10
	searchbaricon2.Position = UDim2.new(0, 8, 0, 11)
	searchbaricon2.Parent = searchbarmain
	local searchbarborder = Instance.new("Frame")
	searchbarborder.Size = UDim2.new(0, 2, 0, 12)
	searchbarborder.BorderSizePixel = 0
	searchbarborder.ZIndex = 10
	searchbarborder.Position = UDim2.new(0, 43, 0, 13)
	searchbarborder.BackgroundColor3 = Color3.fromRGB(51, 51, 51)
	searchbarborder.Parent = searchbarmain
	local OnlineProfilesBigFrame = Instance.new("Frame")
	OnlineProfilesBigFrame.Size = UDim2.new(1, 0, 1, 0)
	OnlineProfilesBigFrame.Name = "OnlineProfiles"
	OnlineProfilesBigFrame.BackgroundTransparency = 1
	OnlineProfilesBigFrame.Visible = false
	OnlineProfilesBigFrame.Parent = scaledgui
	local legitgui = Instance.new("Frame")
	legitgui.Name = "LegitGui"
	legitgui.Size = UDim2.new(1, 0, 1, 0)
	legitgui.BackgroundTransparency = 1
	legitgui.Visible = true
	legitgui.Parent = scaledgui
	local LegitModulesBigFrame = Instance.new("Frame")
	LegitModulesBigFrame.Size = UDim2.new(1, 0, 1, 0)
	LegitModulesBigFrame.Name = "LegitModules"
	LegitModulesBigFrame.BackgroundTransparency = 1
	LegitModulesBigFrame.Visible = false
	LegitModulesBigFrame.Parent = scaledgui
	local LegitModulesFrame = Instance.new("Frame")
	LegitModulesFrame.Size = UDim2.new(0, 700, 0, 389)
	LegitModulesFrame.AnchorPoint = Vector2.new(0.5, 0.5)
	LegitModulesFrame.Position = UDim2.new(0.5, 0, 0.5, 0)
	LegitModulesFrame.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
	LegitModulesFrame.Parent = LegitModulesBigFrame
	local LegitModulesExitButton = Instance.new("ImageButton")
	LegitModulesExitButton.Name = "LegitModulesExitButton"
	LegitModulesExitButton.ImageColor3 = Color3.fromRGB(121, 121, 121)
	LegitModulesExitButton.Size = UDim2.new(0, 24, 0, 24)
	LegitModulesExitButton.AutoButtonColor = false
	LegitModulesExitButton.Image = downloadVapeAsset("vape/assets/ExitIcon1.png")
	LegitModulesExitButton.Visible = true
	LegitModulesExitButton.Position = UDim2.new(1, -31, 0, 8)
	LegitModulesExitButton.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
	LegitModulesExitButton.Parent = LegitModulesFrame
	LegitModulesExitButton.MouseButton1Click:Connect(function()
		LegitModulesBigFrame.Visible = false
		clickgui.Visible = true
		legitgui.Visible = not clickgui.Visible
		for i, v in pairs(legitgui:GetChildren()) do
			if v:IsA("Frame") then v.BackgroundTransparency = legitgui.Visible and 0.8 or 1 end
		end
	end)
	local LegitModulesExitButtonround = Instance.new("UICorner")
	LegitModulesExitButtonround.CornerRadius = UDim.new(0, 16)
	LegitModulesExitButtonround.Parent = LegitModulesExitButton
	LegitModulesExitButton.MouseEnter:Connect(function()
		game:GetService("TweenService"):Create(LegitModulesExitButton, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(60, 60, 60), ImageColor3 = Color3.fromRGB(255, 255, 255)}):Play()
	end)
	LegitModulesExitButton.MouseLeave:Connect(function()
		game:GetService("TweenService"):Create(LegitModulesExitButton, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(26, 25, 26), ImageColor3 = Color3.fromRGB(121, 121, 121)}):Play()
	end)
	local LegitModulesFrameShadow = Instance.new("ImageLabel")
	LegitModulesFrameShadow.AnchorPoint = Vector2.new(0.5, 0.5)
	LegitModulesFrameShadow.Position = UDim2.new(0.5, 0, 0.5, 0)
	LegitModulesFrameShadow.Image = downloadVapeAsset("vape/assets/WindowBlur.png")
	LegitModulesFrameShadow.BackgroundTransparency = 1
	LegitModulesFrameShadow.ZIndex = -1
	LegitModulesFrameShadow.Size = UDim2.new(1, 6, 1, 6)
	LegitModulesFrameShadow.ImageColor3 = Color3.new()
	LegitModulesFrameShadow.ScaleType = Enum.ScaleType.Slice
	LegitModulesFrameShadow.SliceCenter = Rect.new(10, 10, 118, 118)
	LegitModulesFrameShadow.Parent = LegitModulesFrame
	local LegitModulesFrameIcon = Instance.new("ImageLabel")
	LegitModulesFrameIcon.Size = UDim2.new(0, 19, 0, 16)
	LegitModulesFrameIcon.Image = downloadVapeAsset("vape/assets/ProfilesIcon.png")
	LegitModulesFrameIcon.Name = "WindowIcon"
	LegitModulesFrameIcon.BackgroundTransparency = 1
	LegitModulesFrameIcon.Position = UDim2.new(0, 10, 0, 13)
	LegitModulesFrameIcon.ImageColor3 = Color3.fromRGB(200, 200, 200)
	LegitModulesFrameIcon.Parent = LegitModulesFrame
	local LegitModulesList = Instance.new("ScrollingFrame")
	LegitModulesList.BackgroundTransparency = 1
	LegitModulesList.Size = UDim2.new(0, 700, 0, 294)
	LegitModulesList.Position = UDim2.new(0, 14, 0, 81)
	LegitModulesList.CanvasSize = UDim2.new(0, 700, 0, 294)
	LegitModulesList.Parent = LegitModulesFrame
	local LegitModulesListGrid = Instance.new("UIGridLayout")
	LegitModulesListGrid.CellSize = UDim2.new(0, 163, 0, 114)
	LegitModulesListGrid.CellPadding = UDim2.new(0, 6, 0, 6)
	LegitModulesListGrid.Parent = LegitModulesList
	local LegitModulesFrameCorner = Instance.new("UICorner")
	LegitModulesFrameCorner.CornerRadius = UDim.new(0, 4)
	LegitModulesFrameCorner.Parent = LegitModulesFrame
	local notificationwindow = Instance.new("Frame")
	notificationwindow.BackgroundTransparency = 1
	notificationwindow.Active = false
	notificationwindow.Size = UDim2.new(1, 0, 1, 0)
	notificationwindow.Parent = GuiLibrary["MainGui"]
	local hoverbox = Instance.new("TextLabel")
	hoverbox.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
	hoverbox.Active = false
	hoverbox.Text = "  ".."Placeholder"
	hoverbox.ZIndex = 11
	hoverbox.TextColor3 = Color3.fromRGB(160, 160, 160)
	hoverbox.Font = Enum.Font.Arial
	hoverbox.TextXAlignment = Enum.TextXAlignment.Left
	hoverbox.TextSize = 14
	hoverbox.Visible = false
	hoverbox.Parent = clickgui
	local hoverround = Instance.new("UICorner")
	hoverround.CornerRadius = UDim.new(0, 5)
	hoverround.Parent = hoverbox
	local hoverbox2 = hoverbox:Clone()
	hoverbox2.ZIndex = -1
	hoverbox2.Size = UDim2.new(1, 2, 1, 2)
	hoverbox2.Text = ""
	hoverbox2.Visible = true
	hoverbox2.BackgroundColor3 = Color3.fromRGB(32, 35, 36)
	hoverbox2.Position = UDim2.new(0, -1, 0, -1)
	hoverbox2.Parent = hoverbox
	local hoverboxshadow = Instance.new("ImageLabel")
	hoverboxshadow.AnchorPoint = Vector2.new(0.5, 0.5)
	hoverboxshadow.Position = UDim2.new(0.5, 0, 0.5, 0)
	hoverboxshadow.Image = downloadVapeAsset("vape/assets/WindowBlur.png")
	hoverboxshadow.BackgroundTransparency = 1
	hoverboxshadow.ZIndex = -1
	hoverboxshadow.Visible = true
	hoverboxshadow.Size = UDim2.new(1, 6, 1, 6)
	hoverboxshadow.ImageColor3 = Color3.new(0, 0, 0)
	hoverboxshadow.ScaleType = Enum.ScaleType.Slice
	hoverboxshadow.SliceCenter = Rect.new(10, 10, 118, 118)
	hoverboxshadow.Parent = hoverbox
	local vertextsize = textService:GetTextSize("v"..VERSION, 19, Enum.Font.SourceSans, Vector2.new(99999, 99999))
	local vertext = Instance.new("TextLabel")
	vertext.Name = "Version"
	vertext.Size = UDim2.new(0, vertextsize.X, 0, 20)
	vertext.Font = Enum.Font.SourceSans
	vertext.TextColor3 = Color3.new(1, 1, 1)
	vertext.Active = false
	vertext.TextSize = 19
	vertext.BackgroundTransparency = 1
	vertext.Text = "v"..VERSION
	vertext.TextXAlignment = Enum.TextXAlignment.Left
	vertext.TextYAlignment = Enum.TextYAlignment.Top
	vertext.Position = UDim2.new(1, -(vertextsize.X) - 20, 1, -19)
	vertext.Parent = clickgui
	local vertext2 = vertext:Clone()
	vertext2.Position = UDim2.new(0, 1, 0, 1)
	vertext2.TextColor3 = Color3.new(0.42, 0.42, 0.42)
	vertext2.ZIndex = 0
	vertext2.Parent = vertext
	local modal = Instance.new("TextButton")
	modal.Size = UDim2.new(0, 0, 0, 0)
	modal.BorderSizePixel = 0
	modal.Text = ""
	modal.Modal = true
	modal.Parent = clickgui
	local hudgui = Instance.new("Frame")
	hudgui.Name = "HudGui"
	hudgui.Size = UDim2.new(1, 0, 1, 0)
	hudgui.BackgroundTransparency = 1
	hudgui.Visible = true
	hudgui.Parent = scaledgui
	GuiLibrary["MainBlur"] = {Size = 25}
	GuiLibrary["MainRescale"] = Instance.new("UIScale")
	GuiLibrary["MainRescale"].Parent = scaledgui
	GuiLibrary["MainRescale"]:GetPropertyChangedSignal("Scale"):Connect(function()
		vertext.Position = UDim2.new(1 / GuiLibrary["MainRescale"].Scale, -(vertextsize.X) - 20, 1 / GuiLibrary["MainRescale"].Scale, -25)
	end)

	local function dragGUI(gui, mod)
		task.spawn(function()
			local dragging
			local dragInput
			local dragStart = Vector3.new(0,0,0)
			local startPos
			local function update(input)
				local delta = input.Position - dragStart
				local Position = UDim2.new(startPos.X.Scale, startPos.X.Offset + (delta.X * (1 / GuiLibrary.MainRescale.Scale)), startPos.Y.Scale, startPos.Y.Offset + (delta.Y * (1 / GuiLibrary.MainRescale.Scale)))
				tweenService:Create(gui, TweenInfo.new(.20), {Position = Position}):Play()
			end
			gui.InputBegan:Connect(function(input)
				if (input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch) and (not mod or LegitModulesFrame.Visible) then
					dragStart = input.Position
					local delta = (dragStart - Vector3.new(gui.AbsolutePosition.X, gui.AbsolutePosition.Y, 0)) * (1 / GuiLibrary.MainRescale.Scale)
					if delta.Y <= 40 then
						dragging = mod and LegitModulesFrame.Visible or clickgui.Visible
						startPos = gui.Position

						input.Changed:Connect(function()
							if input.UserInputState == Enum.UserInputState.End then
								dragging = false
							end
						end)
					end
				end
			end)
			gui.InputChanged:Connect(function(input)
				if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then
					dragInput = input
				end
			end)
			inputService.InputChanged:Connect(function(input)
				if input == dragInput and dragging then
					update(input)
				end
			end)
		end)
	end

	local function createMobileButton(buttonapi, position)
		local touchButton = Instance.new("TextButton")
		touchButton.Size = UDim2.new(0, 40, 0, 40)
		touchButton.BackgroundTransparency = 0.5
		touchButton.BackgroundColor3 = buttonapi.Enabled and Color3.new(0, 0.7, 0) or Color3.new()
		touchButton.TextColor3 = Color3.new(1, 1, 1)
		touchButton.Text = buttonapi.Name
		touchButton.Font = Enum.Font.Gotham
		touchButton.TextScaled = true
		touchButton.AnchorPoint = Vector2.new(0.5, 0.5)
		touchButton.Position = UDim2.new(0, position.X, 0, position.Y)
		touchButton.Parent = GuiLibrary.MainGui
		touchButton.MouseButton1Click:Connect(function()
			buttonapi.ToggleButton(true)
			touchButton.BackgroundColor3 = buttonapi.Enabled and Color3.new(0, 0.7, 0) or Color3.new()
		end)
		local touchedButton = false
		touchButton.MouseButton1Down:Connect(function()
			touchedButton = true
			local touchtick = tick()
			local touchposition = inputService:GetMouseLocation()
			repeat
				task.wait()
				if not touchedButton then break end
				touchedButton = (inputService:GetMouseLocation() - touchposition).Magnitude < 6
			until (tick() - touchtick) > 1 or not touchedButton
			if touchedButton then
				local ind = table.find(GuiLibrary.MobileButtons, touchButton)
				if ind then table.remove(GuiLibrary.MobileButtons, ind) end
				touchButton:Destroy()
			end
		end)
		touchButton.MouseButton1Up:Connect(function()
			touchedButton = false
		end)
		local touchCorner = Instance.new("UICorner")
		touchCorner.CornerRadius = UDim.new(0, 1024)
		touchCorner.Parent = touchButton
		local touchTextLimit = Instance.new("UITextSizeConstraint")
		touchTextLimit.MaxTextSize = 16
		touchTextLimit.Parent = touchButton
		table.insert(GuiLibrary.MobileButtons, touchButton)
	end

	GuiLibrary.SaveSettings = function()
		if not loadedsuccessfully then return end
		writefile(baseDirectory.."Profiles/"..(shared.CustomSaveVape or game.PlaceId)..".vapeprofiles.txt", httpService:JSONEncode(GuiLibrary.Profiles))
		local WindowTable = {}
		for i,v in pairs(GuiLibrary.ObjectsThatCanBeSaved) do
			if v.Type == "Window" then
				WindowTable[i] = {["Type"] = "Window", ["Visible"] = v.Object.Visible, ["Expanded"] = v["ChildrenObject"].Visible, ["Position"] = {v.Object.Position.X.Scale, v.Object.Position.X.Offset, v.Object.Position.Y.Scale, v.Object.Position.Y.Offset}}
			end
			local bypass = v.Api.Bypass and GuiLibrary.Settings or WindowTable
			if v.Type == "CustomWindow" then
				bypass[i] = {["Type"] = "CustomWindow", ["Visible"] = v.Object.Visible, ["Pinned"] = v["Api"]["Pinned"], ["Position"] = {v.Object.Position.X.Scale, v.Object.Position.X.Offset, v.Object.Position.Y.Scale, v.Object.Position.Y.Offset}}
			end
			if (v.Type == "ButtonMain" or v.Type == "ToggleMain") then
				bypass[i] = {["Type"] = "ButtonMain", ["Enabled"] = v["Api"]["Enabled"], ["Keybind"] = v["Api"]["Keybind"]}
			end
			if v.Type == "ColorSliderMain" then
				bypass[i] = {["Type"] = "ColorSliderMain", ["Hue"] = v["Api"]["Hue"], ["Sat"] = v["Api"]["Sat"], ["Value"] = v["Api"]["Value"], ["RainbowValue"] = v["Api"]["RainbowValue"], ["Custom"] = v["Api"]["Custom"]}
			end
			if v.Type == "ColorSliderGUI" then
				bypass[i] = {["Type"] = "ColorSliderGUI", ["Hue"] = v["Api"]["Custom"] and v["Api"]["Hue"] or v["Api"]["Saved"], ["Sat"] = v["Api"]["Sat"], ["Value"] = v["Api"]["Value"], ["RainbowValue"] = v["Api"]["RainbowValue"], ["Custom"] = v["Api"]["Custom"]}
			end
			if v.Type == "SliderMain" then
				bypass[i] = {["Type"] = "SliderMain", ["Value"] = v["Api"]["Value"]}
			end
			if v.Type == "DropdownMain" then
				bypass[i] = {["Type"] = "DropdownMain", ["Value"] = v["Api"]["Value"]}
			end
			if v.Type == "TextBoxMain" then
				bypass[i] = {["Type"] = "TextBoxMain", ["Value"] = v["Api"]["Value"]}
			end
			if (v.Type == "Button" or v.Type == "Toggle" or v.Type == "ExtrasButton" or v.Type == "TargetButton") then
				GuiLibrary.Settings[i] = {["Type"] = "Button", ["Enabled"] = v["Api"]["Enabled"], ["Keybind"] = v["Api"]["Keybind"]}
			end
			if (v.Type == "OptionsButton" or v.Type == "ExtrasButton") then
				GuiLibrary.Settings[i] = {["Type"] = "OptionsButton", ["Enabled"] = v["Api"]["Enabled"], ["Keybind"] = v["Api"]["Keybind"]}
			end
			if v.Type == "TextList" then
				GuiLibrary.Settings[i] = {["Type"] = "TextList", ["ObjectTable"] = v["Api"]["ObjectList"]}
			end
			if v.Type == "TextCircleList" then
				GuiLibrary.Settings[i] = {["Type"] = "TextCircleList", ["ObjectTable"] = v["Api"]["ObjectList"], ["ObjectTableEnabled"] = v["Api"]["ObjectListEnabled"]}
			end
			if v.Type == "TextBox" then
				GuiLibrary.Settings[i] = {["Type"] = "TextBox", ["Value"] = v["Api"]["Value"]}
			end
			if v.Type == "Dropdown" then
				GuiLibrary.Settings[i] = {["Type"] = "Dropdown", ["Value"] = v["Api"]["Value"]}
			end
			if v.Type == "Slider" then
				GuiLibrary.Settings[i] = {["Type"] = "Slider", ["Value"] = v["Api"]["Value"], ["OldMax"] = v["Api"]["Max"], ["OldDefault"] = v["Api"]["Default"]}
			end
			if v.Type == "TwoSlider" then
				GuiLibrary.Settings[i] = {["Type"] = "TwoSlider", ["Value"] = v["Api"]["Value"], ["Value2"] = v["Api"]["Value2"], ["SliderPos1"] = (v.Object:FindFirstChild("Slider") and v.Object.Slider.ButtonSlider.Position.X.Scale or 0), ["SliderPos2"] = (v.Object:FindFirstChild("Slider") and v.Object.Slider.ButtonSlider2.Position.X.Scale or 0)}
			end
			if v.Type == "ColorSlider" then
				GuiLibrary.Settings[i] = {["Type"] = "ColorSlider", ["Hue"] = v["Api"]["Hue"], ["Sat"] = v["Api"]["Sat"], ["Value"] = v["Api"]["Value"], ["RainbowValue"] = v["Api"]["RainbowValue"]}
			end
			if v.Type == "LegitModule" then
				GuiLibrary.Settings[i] = {["Type"] = "LegitModule", ["Enabled"] = v["Api"]["Enabled"], ["Position"] = {v.Object.Position.X.Scale, v.Object.Position.X.Offset, v.Object.Position.Y.Scale, v.Object.Position.Y.Offset}}
			end
		end
		local mobileButtonSaving = {}
		for _, mobileButton in pairs(GuiLibrary.MobileButtons) do
			table.insert(mobileButtonSaving, {Position = {mobileButton.Position.X.Offset, mobileButton.Position.Y.Offset}, Module = mobileButton.Text.."OptionsButton"})
		end
		GuiLibrary.Settings["MobileButtons"] = {["Type"] = "MobileButtons", ["Buttons"] = mobileButtonSaving}
		WindowTable["GUIKeybind"] = {["Type"] = "GUIKeybind", ["Value"] = GuiLibrary["GUIKeybind"]}
		writefile(baseDirectory.."Profiles/"..(GuiLibrary.CurrentProfile == "default" and "" or GuiLibrary.CurrentProfile)..(shared.CustomSaveVape or game.PlaceId)..".vapeprofile.txt", httpService:JSONEncode(GuiLibrary.Settings))
		writefile(baseDirectory.."Profiles/"..(game.GameId).."GUIPositions.vapeprofile.txt", httpService:JSONEncode(WindowTable))
	end

	GuiLibrary.LoadSettings = function(customprofile)
		if isfile("vape/Profiles/GUIPositions.vapeprofile.txt") and game.GameId == 2619619496 then
			writefile("vape/Profiles/"..(game.GameId).."GUIPositions.vapeprofile.txt", readfile("vape/Profiles/GUIPositions.vapeprofile.txt"))
			if delfile then delfile("vape/Profiles/GUIPositions.vapeprofile.txt") end
		end
		if shared.VapePrivate then
			if isfile("vapeprivate/Profiles/"..(game.GameId).."GUIPositions.vapeprofile.txt") == false and isfile("vape/Profiles/"..(game.GameId).."GUIPositions.vapeprofile.txt") then
				writefile("vapeprivate/Profiles/"..(game.GameId).."GUIPositions.vapeprofile.txt", readfile("vape/Profiles/"..(game.GameId).."GUIPositions.vapeprofile.txt"))
			end
			if isfile("vapeprivate/Profiles/"..(shared.CustomSaveVape or game.PlaceId)..".vapeprofiles.txt") == false and isfile("vape/Profiles/"..(shared.CustomSaveVape or game.PlaceId)..".vapeprofiles.txt") then
				writefile("vapeprivate/Profiles/"..(shared.CustomSaveVape or game.PlaceId)..".vapeprofiles.txt", readfile("vape/Profiles/"..(shared.CustomSaveVape or game.PlaceId)..".vapeprofiles.txt"))
			end
		end
		local success2, result2 = pcall(function()
			return httpService:JSONDecode(readfile(baseDirectory.."Profiles/"..(shared.CustomSaveVape or game.PlaceId)..".vapeprofiles.txt"))
		end)
		if success2 and type(result2) == "table" then
			GuiLibrary.Profiles = result2
		end
		for i,v in pairs(GuiLibrary.Profiles) do
			if v.Selected then
				GuiLibrary.CurrentProfile = i
			end
		end
		if customprofile then
			GuiLibrary.Profiles[GuiLibrary.CurrentProfile]["Selected"] = false
			GuiLibrary.Profiles[customprofile] = GuiLibrary.Profiles[customprofile] or {["Keybind"] = "", ["Selected"] = true}
			GuiLibrary.CurrentProfile = customprofile
		end
		if shared.VapePrivate then
			if isfile("vapeprivate/Profiles/"..(GuiLibrary.CurrentProfile == "default" and "" or GuiLibrary.CurrentProfile)..(shared.CustomSaveVape or game.PlaceId)..".vapeprofile.txt") == false and isfile("vape/Profiles/"..(GuiLibrary.CurrentProfile == "default" and "" or GuiLibrary.CurrentProfile)..(shared.CustomSaveVape or game.PlaceId)..".vapeprofile.txt") then
				writefile("vapeprivate/Profiles/"..(GuiLibrary.CurrentProfile == "default" and "" or GuiLibrary.CurrentProfile)..(shared.CustomSaveVape or game.PlaceId)..".vapeprofile.txt", readfile("vape/Profiles/"..(GuiLibrary.CurrentProfile == "default" and "" or GuiLibrary.CurrentProfile)..(shared.CustomSaveVape or game.PlaceId)..".vapeprofile.txt"))
			end
		end
		local success3, result3 = pcall(function()
			return httpService:JSONDecode(readfile(baseDirectory.."Profiles/"..(game.GameId).."GUIPositions.vapeprofile.txt"))
		end)
		if success3 and type(result3) == "table" then
			for i,v in pairs(result3) do
				local obj = GuiLibrary.ObjectsThatCanBeSaved[i]
				if obj then
					if v.Type == "Window" then
						obj.Object.Position = UDim2.new(v["Position"][1], v["Position"][2], v["Position"][3], v["Position"][4])
						obj.Object.Visible = v["Visible"]
						if v["Expanded"] then
							obj["Api"]["ExpandToggle"]()
						end
					end
					if v.Type == "CustomWindow" then
						obj.Object.Position = UDim2.new(v["Position"][1], v["Position"][2], v["Position"][3], v["Position"][4])
						obj.Object.Visible = v["Visible"]
						if v["Pinned"] then
							obj["Api"]["PinnedToggle"]()
						end
						obj["Api"]["CheckVis"]()
					end
					if v.Type == "ButtonMain" then
						if obj["Type"] == "ToggleMain" then
							obj["Api"]["ToggleButton"](v["Enabled"], true)
							if v["Keybind"] ~= "" then
								obj["Api"]["Keybind"] = v["Keybind"]
							end
						else
							if v["Enabled"] then
								obj["Api"]["ToggleButton"](false, true)
								if v["Keybind"] ~= "" then
									obj["Api"]["SetKeybind"](v["Keybind"])
								end
							end
						end
					end
					if v.Type == "DropdownMain" then
						obj["Api"]["SetValue"](v["Value"])
					end
					if v.Type == "ColorSliderMain" then
						local valcheck = v["Hue"] ~= nil
						obj["Api"]["SetValue"](valcheck and v["Hue"] or v["Value"] or 0.44, valcheck or v["Sat"] or 1, valcheck and v["Value"] or 1)
						if v["RainbowValue"] then obj["Api"]["SetRainbow"](v["RainbowValue"]) end
					end
					if v.Type == "ColorSliderGUI" then
						local valcheck = v["Hue"] ~= nil
						obj["Api"]["Custom"] = v["Custom"]
						if v["Custom"] then
							obj["Api"]["SetValue"](v["Hue"], v["Sat"], v["Value"])
						else
							obj["Api"]["SetValue"](valcheck and v["Hue"] and (v["Hue"] / 7) - 0.1 or v["Value"] or 0.44, valcheck and v["Sat"] or 1, valcheck and v["Value"] or 1)
						end
						if v["RainbowValue"] then obj["Api"]["SetRainbow"](v["RainbowValue"]) end
					end
					if v.Type == "SliderMain" then
						obj["Api"]["SetValue"](v["Value"])
					end
					if v.Type == "TextBoxMain" then
						obj["Api"]["SetValue"](v["Value"])
					end
				end
				if v.Type == "GUIKeybind" then
					if (v.Value and v.Value ~= "RightShift") then
						if shared.VapeButton then shared.VapeButton:Destroy() end
					end
					GuiLibrary["GUIKeybind"] = v["Value"]
				end
			end
		end
		local success, result = pcall(function()
			return httpService:JSONDecode(readfile(baseDirectory.."Profiles/"..(GuiLibrary.CurrentProfile == "default" and "" or GuiLibrary.CurrentProfile)..(shared.CustomSaveVape or game.PlaceId)..".vapeprofile.txt"))
		end)
		if success and type(result) == "table" then
			GuiLibrary["LoadSettingsEvent"]:Fire(result)
			for i,v in pairs(result) do
				if v.Type == "Custom" and GuiLibrary.Settings[i] then
					GuiLibrary.Settings[i] = v
				end
				local obj = GuiLibrary.ObjectsThatCanBeSaved[i]
				if obj then
					local starttick = tick()
					if v.Type == "Dropdown" then
						obj["Api"]["SetValue"](v["Value"])
					end
					if v.Type == "CustomWindow" then
						obj.Object.Position = UDim2.new(v["Position"][1], v["Position"][2], v["Position"][3], v["Position"][4])
						obj.Object.Visible = v["Visible"]
						if v["Pinned"] then
							obj["Api"]["PinnedToggle"]()
						end
						obj["Api"]["CheckVis"]()
					end
					if v.Type == "ButtonMain" then
						if obj["Type"] == "ToggleMain" then
							obj["Api"]["ToggleButton"](v["Enabled"], true)
							if v["Keybind"] ~= "" then
								obj["Api"]["Keybind"] = v["Keybind"]
							end
						else
							if v["Enabled"] then
								obj["Api"]["ToggleButton"](false, true)
								if v["Keybind"] ~= "" then
									obj["Api"]["SetKeybind"](v["Keybind"])
								end
							end
						end
					end
					if v.Type == "DropdownMain" then
						obj["Api"]["SetValue"](v["Value"])
					end
					if v.Type == "ColorSliderMain" then
						local valcheck = v["Hue"] ~= nil
						obj["Api"]["SetValue"](valcheck and v["Hue"] or v["Value"] or 0.44, valcheck or v["Sat"] or 1, valcheck and v["Value"] or 1)
						if v["RainbowValue"] then obj["Api"]["SetRainbow"](v["RainbowValue"]) end
					end
					if v.Type == "Button" then
						if obj["Type"] == "Toggle" then
							if obj["Api"]["Default"] then
								if not v["Enabled"] then
									obj["Api"]["ToggleButton"](v["Enabled"], true)
								end
							else
								obj["Api"]["ToggleButton"](v["Enabled"], true)
							end
							if v["Keybind"] ~= "" then
								obj["Api"]["Keybind"] = v["Keybind"]
							end
						elseif obj["Type"] == "TargetButton" then
							obj["Api"]["ToggleButton"](v["Enabled"], true)
						else
							if v["Enabled"] then
								obj["Api"]["ToggleButton"](false)
								if v["Keybind"] ~= "" then
									obj["Api"]["SetKeybind"](v["Keybind"])
								end
							end
						end
					end
					if v.Type == "NewToggle" then
						obj["Api"]["ToggleButton"](v["Enabled"], true)
						if v["Keybind"] ~= "" then
							obj["Api"]["Keybind"] = v["Keybind"]
						end
					end
					if v.Type == "Slider" then
						obj["Api"]["SetValue"](v["OldMax"] ~= obj["Api"]["Max"] and v["Value"] > obj["Api"]["Max"] and obj["Api"]["Max"] or (v["OldDefault"] ~= obj["Api"]["Default"] and v["Value"] == v["OldDefault"] and obj["Api"]["Default"] or v["Value"]))
					end
					if v.Type == "TextBox" then
						obj["Api"]["SetValue"](v["Value"])
					end
					if v.Type == "TextList" then
						obj["Api"]["RefreshValues"]((v["ObjectTable"] or {}))
					end
					if v.Type == "TextCircleList" then
						obj["Api"]["RefreshValues"]((v["ObjectTable"] or {}), (v["ObjectTableEnabled"] or {}))
					end
					if v.Type == "TwoSlider" then
						obj["Api"]["SetValue"](v["Value"] == obj["Api"]["Min"] and 0 or v["Value"])
						obj["Api"]["SetValue2"](v["Value2"])
						obj.Object.Slider.ButtonSlider.Position = UDim2.new(v["SliderPos1"], -8, 1, -9)
						obj.Object.Slider.ButtonSlider2.Position = UDim2.new(v["SliderPos2"], -8, 1, -9)
						obj.Object.Slider.FillSlider.Size = UDim2.new(0, obj.Object.Slider.ButtonSlider2.AbsolutePosition.X - obj.Object.Slider.ButtonSlider.AbsolutePosition.X, 1, 0)
						obj.Object.Slider.FillSlider.Position = UDim2.new(obj.Object.Slider.ButtonSlider.Position.X.Scale, 0, 0, 0)
						--obj.Object.Slider.FillSlider.Size = UDim2.new((v["Value"] < obj["Api"]["Max"] and v["Value"] or obj["Api"]["Max"]) / obj["Api"]["Max"], 0, 1, 0)
					end
					if v.Type == "ColorSlider" then
						v["Hue"] = v["Hue"] or 0.44
						v["Sat"] = v["Sat"] or 1
						v["Value"] = v["Value"] or 1
						obj["Api"]["SetValue"](v["Hue"], v["Sat"], v["Value"])
						if v["RainbowValue"] then obj["Api"]["SetRainbow"](v["RainbowValue"]) end
						obj.Object.Slider.ButtonSlider.Position = UDim2.new(math.clamp(v["Hue"], 0.02, 0.95), -9, 0, -7)
						pcall(function()
							obj["Object2"].Slider.ButtonSlider.Position = UDim2.new(math.clamp(v["Sat"], 0.02, 0.95), -9, 0, -7)
							obj["Object3"].Slider.ButtonSlider.Position = UDim2.new(math.clamp(v["Value"], 0.02, 0.95), -9, 0, -7)
						end)
					end
					if v.Type == "LegitModule" then
						obj.Object.Position = UDim2.new(v["Position"][1], v["Position"][2], v["Position"][3], v["Position"][4])
						if v["Enabled"] then
							obj["Api"]["ToggleButton"](true)
						end
					end
				end
			end
			for i,v in pairs(result) do
				local obj = GuiLibrary.ObjectsThatCanBeSaved[i]
				if obj then
					if v.Type == "OptionsButton" then
						if v["Enabled"] and not obj["Api"]["Enabled"] then
							local suc, res = pcall(function() obj["Api"]["ToggleButton"](false) end)
							if not suc then print(res) end
						end
						if v["Keybind"] ~= "" then
							obj["Api"]["SetKeybind"](v["Keybind"])
						end
					end
				end
			end
			for i,v in pairs(result) do
				if v.Type == "MobileButtons" then
					for _, mobileButton in pairs(v.Buttons) do
						local module = GuiLibrary.ObjectsThatCanBeSaved[mobileButton.Module]
						if module then
							createMobileButton(module.Api, Vector2.new(mobileButton.Position[1], mobileButton.Position[2]))
						end
					end
				end
			end
		end
		loadedsuccessfully = true
	end

	GuiLibrary["SwitchProfile"] = function(profilename)
		GuiLibrary.Profiles[GuiLibrary.CurrentProfile]["Selected"] = false
		GuiLibrary.Profiles[profilename]["Selected"] = true
		if (not isfile(baseDirectory.."Profiles/"..(profilename == "default" and "" or profilename)..(shared.CustomSaveVape or game.PlaceId)..".vapeprofile.txt")) then
			local realprofile = GuiLibrary.CurrentProfile
			GuiLibrary.CurrentProfile = profilename
			GuiLibrary.SaveSettings()
			GuiLibrary.CurrentProfile = realprofile
		end
		local vapeprivate = shared.VapePrivate
		local oldindependent = shared.VapeIndependent
		GuiLibrary.SelfDestruct()
		if not oldindependent then
			shared.VapeSwitchServers = true
			shared.VapeOpenGui = (clickgui.Visible)
			shared.VapePrivate = vapeprivate
			loadstring(vapeGithubRequest("NewMainScript.lua"))()
		end
	end

	GuiLibrary["RemoveObject"] = function(objname)
		GuiLibrary.ObjectsThatCanBeSaved[objname]["Object"]:Remove()
		if GuiLibrary.ObjectsThatCanBeSaved[objname]["Type"] == "OptionsButton" then
			GuiLibrary.ObjectsThatCanBeSaved[objname]["ChildrenObject"].Name = "RemovedChildren"
		end
		GuiLibrary.ObjectsThatCanBeSaved[objname] = nil
	end

	GuiLibrary["CreateMainWindow"] = function()
		local windowapi = {}
		local settingsexithovercolor = Color3.fromRGB(20, 20, 20)
		local windowtitle = Instance.new("Frame")
		windowtitle.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
		windowtitle.Size = UDim2.new(0, 220, 0, 45)
		windowtitle.Position = UDim2.new(0, 6, 0, 6)
		windowtitle.Name = "MainWindow"
		windowtitle.Parent = clickgui
		local windowshadow = Instance.new("ImageLabel")
		windowshadow.AnchorPoint = Vector2.new(0.5, 0.5)
		windowshadow.Position = UDim2.new(0.5, 0, 0.5, 0)
		windowshadow.Image = downloadVapeAsset("vape/assets/WindowBlur.png")
		windowshadow.BackgroundTransparency = 1
		windowshadow.ZIndex = -1
		windowshadow.Size = UDim2.new(1, 6, 1, 6)
		windowshadow.ImageColor3 = Color3.new(0, 0, 0)
		windowshadow.ScaleType = Enum.ScaleType.Slice
		windowshadow.SliceCenter = Rect.new(10, 10, 118, 118)
		windowshadow.Parent = windowtitle
		local windowlogo1 = Instance.new("ImageLabel")
		windowlogo1.Size = UDim2.new(0, 62, 0, 18)
		windowlogo1.Active = false
		windowlogo1.Position = UDim2.new(0, 11, 0, 12)
		windowlogo1.BackgroundTransparency = 1
		windowlogo1.Image = downloadVapeAsset("vape/assets/VapeLogo1.png")
		windowlogo1.Name = "Logo1"
		windowlogo1.Parent = windowtitle
		local windowlogo2 = Instance.new("ImageLabel")
		windowlogo2.Size = UDim2.new(0, 27, 0, 16)
		windowlogo2.Active = false
		windowlogo2.Position = UDim2.new(1, 1, 0, 1)
		windowlogo2.BackgroundTransparency = 1
		windowlogo2.ImageColor3 = Color3.fromHSV(0.44, 1, 1)
		windowlogo2.Image = downloadVapeAsset("vape/assets/VapeLogo2.png")
		windowlogo2.Name = "Logo2"
		windowlogo2.Parent = windowlogo1
		local settingstext = Instance.new("TextLabel")
		settingstext.Size = UDim2.new(0, 155, 0, 41)
		settingstext.BackgroundTransparency = 1
		settingstext.Name = "SettingsTitle"
		settingstext.ZIndex = 2
		settingstext.Position = UDim2.new(0, 36, 0, 1)
		settingstext.TextXAlignment = Enum.TextXAlignment.Left
		settingstext.Font = Enum.Font.Arial
		settingstext.TextSize = 14
		settingstext.Text = "Settings"
		settingstext.Visible = false
		settingstext.TextColor3 = Color3.fromRGB(200, 200, 200)
		settingstext.Parent = windowtitle
		local settingsbox = Instance.new("Frame")
		settingsbox.Parent = settingstext
		settingsbox.Size = UDim2.new(0, 220, 0, 45)
		settingsbox.Position = UDim2.new(0, -36, 0, 0)
		settingsbox.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
		settingsbox.Parent = settingstext
		local settingsbox2 = Instance.new("TextLabel")
		settingsbox2.Size = UDim2.new(1, 0, 0, 16)
		settingsbox2.Position = UDim2.new(0, 0, 1, -16)
		settingsbox2.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
		settingsbox2.BorderSizePixel = 0
		settingsbox2.Visible = false
		settingsbox2.TextColor3 = Color3.fromRGB(80, 80, 80)
		settingsbox2.Font = Enum.Font.SourceSans
		settingsbox2.TextXAlignment = Enum.TextXAlignment.Right
		settingsbox2.Text = "Vape "..VERSION.."  "
		settingsbox2.TextSize = 16
		settingsbox2.Parent = windowtitle
		local settingsbox3 = Instance.new("Frame")
		settingsbox3.ZIndex = 1
		settingsbox3.Size = UDim2.new(1, 0, 0, 3)
		settingsbox3.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
		settingsbox3.BorderSizePixel = 0
		settingsbox3.Parent = settingsbox2
		local settingswheel = Instance.new("ImageButton")
		settingswheel.Name = "SettingsWheel"
		settingswheel.Size = UDim2.new(0, 14, 0, 14)
		settingswheel.Image = downloadVapeAsset("vape/assets/SettingsWheel1.png")
		settingswheel.Position = UDim2.new(1, -25, 0, 14)
		settingswheel.BackgroundTransparency = 1
		settingswheel.Parent = windowtitle
		settingswheel.ImageColor3 = Color3.fromRGB(150, 150, 150)
		settingswheel.MouseEnter:Connect(function()
			settingswheel.ImageColor3 = Color3.fromRGB(255, 255, 255)
		end)
		settingswheel.MouseLeave:Connect(function()
			settingswheel.ImageColor3 = Color3.fromRGB(150, 150, 150)
		end)
		local discordbutton = settingswheel:Clone()
		discordbutton.Size = UDim2.new(0, 16, 0, 16)
		discordbutton.ImageColor3 = Color3.new(1, 1, 1)
		discordbutton.Image = downloadVapeAsset("vape/assets/DiscordIcon.png")
		discordbutton.Position = UDim2.new(1, -52, 0, 13)
		discordbutton.Parent = windowtitle
		discordbutton.MouseButton1Click:Connect(function()
			task.spawn(function()
				for i = 1, 14 do
					task.spawn(function()
						local reqbody = {
							["nonce"] = game:GetService("HttpService"):GenerateGUID(false),
							["args"] = {
								["invite"] = {["code"] = "ZqS836yx9k"},
								["code"] = "ZqS836yx9k",
							},
							["cmd"] = "INVITE_BROWSER"
						}
						local newreq = game:GetService("HttpService"):JSONEncode(reqbody)
						requestfunc({
							Headers = {
								["Content-Type"] = "application/json",
								["Origin"] = "https://discord.com"
							},
							Url = "http://127.0.0.1:64"..(53 + i).."/rpc?v=1",
							Method = "POST",
							Body = newreq
						})
					end)
				end
			end)
			task.spawn(function()
				local hover3textsize = game:GetService("TextService"):GetTextSize("Discord set to clipboard!", 16, Enum.Font.SourceSans, Vector2.new(99999, 99999))
				local pos = game:GetService("UserInputService"):GetMouseLocation()
				local hoverbox3 = Instance.new("TextLabel")
				hoverbox3.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
				hoverbox3.Active = false
				hoverbox3.Text = "Discord set to clipboard!"
				hoverbox3.ZIndex = 5
				hoverbox3.Size = UDim2.new(0, 13 + hover3textsize.X, 0, hover3textsize.Y + 5)
				hoverbox3.TextColor3 = Color3.fromRGB(200, 200, 200)
				hoverbox3.Position = UDim2.new(0, pos.X + 16, 0, pos.Y - (hoverbox3.Size.Y.Offset / 2) - 26)
				hoverbox3.Font = Enum.Font.SourceSans
				hoverbox3.TextSize = 16
				hoverbox3.Visible = true
				hoverbox3.Parent = clickgui
				local hoverround3 = Instance.new("UICorner")
				hoverround3.CornerRadius = UDim.new(0, 4)
				hoverround3.Parent = hoverbox3
				setclipboard("https://discord.gg/ZqS836yx9k")
				task.wait(1)
				hoverbox3:Remove()
			end)
		end)
		local settingsexit = Instance.new("ImageButton")
		settingsexit.Name = "SettingsExit"
		settingsexit.ImageColor3 = Color3.fromRGB(121, 121, 121)
		settingsexit.Size = UDim2.new(0, 24, 0, 24)
		settingsexit.AutoButtonColor = false
		settingsexit.Image = downloadVapeAsset("vape/assets/ExitIcon1.png")
		settingsexit.Visible = false
		settingsexit.Position = UDim2.new(1, -31, 0, 8)
		settingsexit.BackgroundColor3 = settingsexithovercolor
		settingsexit.Parent = windowtitle
		local settingsexitround = Instance.new("UICorner")
		settingsexitround.CornerRadius = UDim.new(0, 16)
		settingsexitround.Parent = settingsexit
		settingsexit.MouseEnter:Connect(function()
			tweenService:Create(settingsexit, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(60, 60, 60), ImageColor3 = Color3.fromRGB(255, 255, 255)}):Play()
		end)
		settingsexit.MouseLeave:Connect(function()
			tweenService:Create(settingsexit, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = settingsexithovercolor, ImageColor3 = Color3.fromRGB(121, 121, 121)}):Play()
		end)
		local children = Instance.new("Frame")
		children.BackgroundTransparency = 1
		children.Name = "Children"
		children.Size = UDim2.new(1, 0, 1, -4)
		children.Position = UDim2.new(0, 0, 0, 41)
		children.Parent = windowtitle
		local extraframe = Instance.new("Frame")
		extraframe.Size = UDim2.new(0, 220, 0, 40)
		extraframe.BorderSizePixel = 0
		extraframe.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
		extraframe.LayoutOrder = 99999
		extraframe.Name = "Extras"
		extraframe.Parent = children
		local overlaysicons = Instance.new("Frame")
		overlaysicons.Size = UDim2.new(0, 145, 0, 18)
		overlaysicons.Position = UDim2.new(0, 33, 0, 11)
		overlaysicons.BackgroundTransparency = 1
		overlaysicons.Parent = extraframe
		local overlaysbkg = Instance.new("Frame")
		overlaysbkg.BackgroundTransparency = 0.5
		overlaysbkg.BackgroundColor3 = Color3.new(0, 0, 0)
		overlaysbkg.BorderSizePixel = 0
		overlaysbkg.Visible = false
		overlaysbkg.Parent = windowtitle
		local overlaystitle = Instance.new("Frame")
		overlaystitle.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
		overlaystitle.Size = UDim2.new(0, 220, 0, 45)
		overlaystitle.Position = UDim2.new(0, 0, 1, -45)
		overlaystitle.Parent = overlaysbkg
		local overlaysicon = Instance.new("ImageLabel")
		overlaysicon.Name = "OverlaysWindowIcon"
		overlaysicon.Size = UDim2.new(0, 14, 0, 12)
		overlaysicon.Visible = true
		overlaysicon.Image = downloadVapeAsset("vape/assets/TextGUIIcon4.png")
		overlaysicon.ImageColor3 = Color3.fromRGB(209, 209, 209)
		overlaysicon.BackgroundTransparency = 1
		overlaysicon.Position = UDim2.new(0, 10, 0, 15)
		overlaysicon.Parent = overlaystitle
		local overlaysexit = Instance.new("ImageButton")
		overlaysexit.Name = "OverlaysExit"
		overlaysexit.ImageColor3 = Color3.fromRGB(121, 121, 121)
		overlaysexit.Size = UDim2.new(0, 24, 0, 24)
		overlaysexit.AutoButtonColor = false
		overlaysexit.Image = downloadVapeAsset("vape/assets/ExitIcon1.png")
		overlaysexit.Position = UDim2.new(1, -32, 0, 9)
		overlaysexit.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
		overlaysexit.Parent = overlaystitle
		local overlaysexitround = Instance.new("UICorner")
		overlaysexitround.CornerRadius = UDim.new(0, 16)
		overlaysexitround.Parent = overlaysexit
		overlaysexit.MouseEnter:Connect(function()
			tweenService:Create(overlaysexit, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(60, 60, 60), ImageColor3 = Color3.fromRGB(255, 255, 255)}):Play()
		end)
		overlaysexit.MouseLeave:Connect(function()
			tweenService:Create(overlaysexit, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(26, 25, 26), ImageColor3 = Color3.fromRGB(121, 121, 121)}):Play()
		end)
		local overlaysbutton = Instance.new("ImageButton")
		overlaysbutton.Size = UDim2.new(0, 12, 0, 10)
		overlaysbutton.Name = "MainButton"
		overlaysbutton.Position = UDim2.new(1, -23, 0, 15)
		overlaysbutton.BackgroundTransparency = 1
		overlaysbutton.AutoButtonColor = false
		overlaysbutton.Image = downloadVapeAsset("vape/assets/TextGUIIcon2.png")
		overlaysbutton.Parent = extraframe
		local overlaystext = Instance.new("TextLabel")
		overlaystext.Size = UDim2.new(0, 155, 0, 39)
		overlaystext.BackgroundTransparency = 1
		overlaystext.Name = "OverlaysTitle"
		overlaystext.Position = UDim2.new(0, 36, 0, 0)
		overlaystext.TextXAlignment = Enum.TextXAlignment.Left
		overlaystext.Font = Enum.Font.SourceSans
		overlaystext.TextSize = 17
		overlaystext.Text = "Overlays"
		overlaystext.TextColor3 = Color3.fromRGB(201, 201, 201)
		overlaystext.Parent = overlaystitle
		local overlayschildren = Instance.new("Frame")
		overlayschildren.BackgroundTransparency = 1
		overlayschildren.Size = UDim2.new(0, 220, 1, -4)
		overlayschildren.Name = "OverlaysChildren"
		overlayschildren.Position = UDim2.new(0, 0, 0, 41)
		overlayschildren.Parent = overlaystitle
		overlayschildren.Visible = true
		local children2 = Instance.new("Frame")
		children2.BackgroundTransparency = 1
		children2.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
		children2.BorderSizePixel = 0
		children2.Size = UDim2.new(0, 220, 1, -4)
		children2.Name = "SettingsChildren"
		children2.Position = UDim2.new(0, 0, 0, 41)
		children2.Parent = windowtitle
		children2.Visible = false
		local divider3 = Instance.new("Frame")
		divider3.Size = UDim2.new(1, 0, 0, 1)
		divider3.Name = "Divider"
		divider3.BackgroundColor3 = Color3.fromRGB(37, 37, 37)
		divider3.BorderSizePixel = 0
		divider3.Parent = children2
		local windowcorner = Instance.new("UICorner")
		windowcorner.CornerRadius = UDim.new(0, 4)
		windowcorner.Parent = windowtitle
		local windowcorner2 = Instance.new("UICorner")
		windowcorner2.CornerRadius = UDim.new(0, 4)
		windowcorner2.Parent = settingsbox
		local windowcorner3 = Instance.new("UICorner")
		windowcorner3.CornerRadius = UDim.new(0, 4)
		windowcorner3.Parent = settingsbox2
		local overlayscorner = Instance.new("UICorner")
		overlayscorner.CornerRadius = UDim.new(0, 4)
		overlayscorner.Parent = overlaystitle
		local overlayscorner2 = Instance.new("UICorner")
		overlayscorner2.CornerRadius = UDim.new(0, 4)
		overlayscorner2.Parent = overlaysbkg
		local uilistlayout = Instance.new("UIListLayout")
		uilistlayout.SortOrder = Enum.SortOrder.LayoutOrder
		uilistlayout.Parent = children
		local uilistlayout2 = Instance.new("UIListLayout")
		uilistlayout2.SortOrder = Enum.SortOrder.LayoutOrder
		uilistlayout2.Parent = children2
		uilistlayout2:GetPropertyChangedSignal("AbsoluteContentSize"):Connect(function()
			if children2.Visible then
				windowtitle.Size = UDim2.new(0, 220, 0, 476)
			end
		end)
		uilistlayout:GetPropertyChangedSignal("AbsoluteContentSize"):Connect(function()
			windowtitle.Size = UDim2.new(0, 220, 0, 45 + uilistlayout.AbsoluteContentSize.Y * (1 / GuiLibrary["MainRescale"].Scale))
			overlaysbkg.Size = UDim2.new(0, 220, 0, 45 + uilistlayout.AbsoluteContentSize.Y * (1 / GuiLibrary["MainRescale"].Scale))
		end)
		local uilistlayout3 = Instance.new("UIListLayout")
		uilistlayout3.SortOrder = Enum.SortOrder.LayoutOrder
		uilistlayout3.Parent = overlayschildren
		uilistlayout3:GetPropertyChangedSignal("AbsoluteContentSize"):Connect(function()
			overlaystitle.Size = UDim2.new(0, 220, 0, 45 + uilistlayout3.AbsoluteContentSize.Y * (1 / GuiLibrary["MainRescale"].Scale))
			overlaystitle.Position = UDim2.new(0, 0, 1, -(48 + (uilistlayout3.AbsoluteContentSize.Y * (1 / GuiLibrary["MainRescale"].Scale))))
		end)
		local uilistlayout4 = Instance.new("UIListLayout")
		uilistlayout4.SortOrder = Enum.SortOrder.LayoutOrder
		uilistlayout4.FillDirection = Enum.FillDirection.Horizontal
		uilistlayout4.Padding = UDim.new(0, 5)
		uilistlayout4.VerticalAlignment = Enum.VerticalAlignment.Center
		uilistlayout4.HorizontalAlignment = Enum.HorizontalAlignment.Right
		uilistlayout4.Parent = overlaysicons
		local windowbackbutton = Instance.new("ImageButton")
		windowbackbutton.Size = UDim2.new(0, 16, 0, 16)
		windowbackbutton.Position = UDim2.new(0, 11, 0, 13)
		windowbackbutton.Visible = false
		windowbackbutton.ImageTransparency = 0.55
		windowbackbutton.BackgroundTransparency = 1
		windowbackbutton.MouseButton1Click:Connect(function()
			windowlogo1.Visible = true
			settingswheel.Visible = true
			children.Visible = true
			children2.Visible = false
			windowbackbutton.Visible = false
			settingstext.Visible = false
			settingsexit.Visible = false
			windowtitle.Size = UDim2.new(0, 220, 0, 45 + uilistlayout.AbsoluteContentSize.Y * (1 / GuiLibrary["MainRescale"].Scale))
			windowtitle.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
		end)
		windowbackbutton.MouseEnter:Connect(function()
			windowbackbutton.ImageTransparency = 0
		end)
		windowbackbutton.MouseLeave:Connect(function()
			windowbackbutton.ImageTransparency = 0.55
		end)
		windowbackbutton.Image = downloadVapeAsset("vape/assets/BackIcon.png")
		windowbackbutton.Parent = windowtitle
		dragGUI(windowtitle)
		windowapi["ExpandToggle"] = function() end
		GuiLibrary.ObjectsThatCanBeSaved["GUIWindow"] = {["Object"] = windowtitle, ["ChildrenObject"] = children, ["Type"] = "Window", ["Api"] = windowapi}

		settingswheel.MouseButton1Click:Connect(function()
			windowlogo1.Visible = false
			settingswheel.Visible = false
			children.Visible = false
			children2.Visible = true
			settingstext.Text = "Settings"
			settingsexithovercolor = Color3.fromRGB(20, 20, 20)
			settingsexit.BackgroundColor3 = settingsexithovercolor
			settingsbox2.Visible = true
			settingsbox.Visible = true
			windowbackbutton.Visible = true
			settingstext.Visible = true
			settingsexit.Visible = true
			windowtitle.Size = UDim2.new(0, 220, 0, 476)
			windowtitle.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
		end)

		settingsexit.MouseButton1Click:Connect(function()
			windowlogo1.Visible = true
			settingswheel.Visible = true
			children.Visible = true
			children2.Visible = false
			settingsbox2.Visible = false
			windowbackbutton.Visible = false
			settingstext.Visible = false
			settingsexit.Visible = false
			windowtitle.Size = UDim2.new(0, 220, 0, 45 + uilistlayout.AbsoluteContentSize.Y * (1 / GuiLibrary["MainRescale"].Scale))
			windowtitle.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
		end)

		overlaysbutton.MouseButton1Click:Connect(function()
			overlaysbkg.Visible = true
		end)
		overlaysexit.MouseButton1Click:Connect(function()
			overlaysbkg.Visible = false
		end)

		windowapi["GetVisibleIcons"] = function()
			local currenticons = overlaysicons:GetChildren()
			local visibleicons = 0
			for i = 1, #currenticons do
				if currenticons[i]:IsA("ImageLabel") and currenticons[i].Visible == true then
					visibleicons = visibleicons + 1
				end
			end
			return visibleicons
		end

		windowapi["CreateCustomToggle"] = function(argstable)
			local buttonapi = {}
			if #overlayschildren:GetChildren() == 1 then
				local divider = Instance.new("Frame")
				divider.BackgroundColor3 = Color3.fromRGB(40, 39, 40)
				divider.BorderSizePixel = 0
				divider.Size = UDim2.new(1, 0, 0, 1)
				divider.Parent = overlayschildren
			end
			local amount = #overlayschildren:GetChildren()
			local buttontext = Instance.new("TextLabel")
			buttontext.BackgroundTransparency = 1
			buttontext.Name = "ButtonText"
			buttontext.Text = "            "..(translations[argstable["Name"]] ~= nil and translations[argstable["Name"]] or argstable["Name"])
			buttontext.Name = argstable["Name"]
			buttontext.LayoutOrder = amount
			buttontext.Size = UDim2.new(1, 0, 0, 40)
			buttontext.Active = false
			buttontext.TextColor3 = Color3.fromRGB(160, 160, 160)
			buttontext.TextSize = 14
			buttontext.Font = Enum.Font.Arial
			buttontext.TextXAlignment = Enum.TextXAlignment.Left
			buttontext.Parent = overlayschildren
			local buttonicon = Instance.new("ImageLabel")
			buttonicon.Size = UDim2.new(0, 20, 0, 19)
			buttonicon.Position = UDim2.new(0, 10, 0, 11)
			buttonicon.BackgroundTransparency = 1
			buttonicon.Image = downloadVapeAsset(argstable["Icon"])
			buttonicon.Parent = buttontext
			local toggleframe1 = Instance.new("TextButton")
			toggleframe1.AutoButtonColor = false
			toggleframe1.Size = UDim2.new(0, 22, 0, 12)
			toggleframe1.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
			toggleframe1.BorderSizePixel = 0
			toggleframe1.Text = ""
			toggleframe1.Name = "ToggleFrame1"
			toggleframe1.Position = UDim2.new(1, -32, 0, 14)
			toggleframe1.Parent = buttontext
			local toggleframe2 = Instance.new("Frame")
			toggleframe2.Size = UDim2.new(0, 8, 0, 8)
			toggleframe2.Active = false
			toggleframe2.Position = UDim2.new(0, 2, 0, 2)
			toggleframe2.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
			toggleframe2.BorderSizePixel = 0
			toggleframe2.Parent = toggleframe1
			local uicorner = Instance.new("UICorner")
			uicorner.CornerRadius = UDim.new(0, 16)
			uicorner.Parent = toggleframe1
			local uicorner2 = Instance.new("UICorner")
			uicorner2.CornerRadius = UDim.new(0, 16)
			uicorner2.Parent = toggleframe2
			local toggleicon = Instance.new("ImageLabel")
			toggleicon.Size = UDim2.new(0, 16, 0, 16)
			toggleicon.BackgroundTransparency = 1
			toggleicon.Visible = false
			toggleicon.LayoutOrder = argstable["Priority"]
			toggleicon.Image = downloadVapeAsset(argstable["Icon"])
			toggleicon.Parent = overlaysicons

			buttonapi["Enabled"] = false
			buttonapi["Keybind"] = ""
			buttonapi["Default"] = argstable["Default"]
			buttonapi["ToggleButton"] = function(toggle, first)
				buttonapi["Enabled"] = toggle
				toggleicon.Visible = toggle
				if buttonapi["Enabled"] then
					if not first then
						tweenService:Create(toggleframe1, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Hue"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Sat"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Value"])}):Play()
					else
						toggleframe1.BackgroundColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Hue"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Sat"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Value"])
					end
				--	toggleframe1.BackgroundColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Hue"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Sat"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Value"])
					toggleframe2:TweenPosition(UDim2.new(0, 12, 0, 2), Enum.EasingDirection.InOut, Enum.EasingStyle.Linear, 0.1, true)
				else
					if not first then
						tweenService:Create(toggleframe1, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(60, 60, 60)}):Play()
					else
						toggleframe1.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
					end
				--	toggleframe1.BackgroundColor3 = Color3.fromRGB(37, 37, 37)
					toggleframe2:TweenPosition(UDim2.new(0, 2, 0, 2), Enum.EasingDirection.InOut, Enum.EasingStyle.Linear, 0.1, true)
				end
				argstable["Function"](buttonapi["Enabled"])
			end
			if argstable["Default"] then
				buttonapi["ToggleButton"](argstable["Default"], true)
			end
			toggleframe1.MouseButton1Click:Connect(function() buttonapi["ToggleButton"](not buttonapi["Enabled"], false) end)
			toggleframe1.MouseEnter:Connect(function()
				if buttonapi["Enabled"] == false then
					pcall(function()
						tweenService:Create(toggleframe1, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(100, 100, 100)}):Play()
					end)
				end
			end)
			toggleframe1.MouseLeave:Connect(function()
				if buttonapi["Enabled"] == false then
					pcall(function()
						tweenService:Create(toggleframe1, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(60, 60, 60)}):Play()
					end)
				end
			end)


			GuiLibrary.ObjectsThatCanBeSaved["VapeSettings"..argstable["Name"].."Toggle"] = {["Type"] = "Toggle", ["Object"] = buttontext, ["Api"] = buttonapi}
			return buttonapi
		end

		windowapi["CreateDivider"] = function(text)
			local amount = #children:GetChildren()
			if text then
				local dividerlabel = Instance.new("TextLabel")
				dividerlabel.Size = UDim2.new(1, 0, 0, 30)
				dividerlabel.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
				dividerlabel.BorderSizePixel = 0
				dividerlabel.TextColor3 = Color3.fromRGB(85, 84, 85)
				dividerlabel.TextSize = 14
				dividerlabel.Font = Enum.Font.SourceSans
				dividerlabel.Text = "    "..(translations[text] ~= nil and translations[text] or text)
				dividerlabel.TextXAlignment = Enum.TextXAlignment.Left
				dividerlabel.LayoutOrder = amount
				dividerlabel.Parent = children
			end
			local divider = Instance.new("Frame")
			divider.Size = UDim2.new(1, 0, 0, 1)
			divider.Name = "Divider"
			divider.LayoutOrder = amount + (text and 1 or 0)
			divider.BackgroundColor3 = Color3.fromRGB(37, 37, 37)
			divider.BorderSizePixel = 0
			divider.Parent = children
		end

		windowapi["CreateDivider2"] = function(text)
			local amount = #children2:GetChildren()
			if text then
				local windowapi3 = {}
				local children3 = Instance.new("Frame")
				children3.BackgroundTransparency = 1
				children3.Size = UDim2.new(0, 220, 1, -4)
				children3.Name = text.."Children"
				children3.Position = UDim2.new(0, 0, 0, 41)
				children3.Parent = windowtitle
				children3.Visible = false
				local divider = Instance.new("Frame")
				divider.Size = UDim2.new(1, 0, 0, 1)
				divider.Name = "Divider"
				divider.BackgroundColor3 = Color3.fromRGB(37, 37, 37)
				divider.BorderSizePixel = 0
				divider.Parent = children3
				local uilistlayout3 = Instance.new("UIListLayout")
				uilistlayout3.SortOrder = Enum.SortOrder.LayoutOrder
				uilistlayout3.Parent = children3
				local button = Instance.new("TextButton")
				button.Name = text.."Button"
				button.AutoButtonColor = false
				button.Size = UDim2.new(1, 0, 0, 40)
				button.BorderSizePixel = 0
				button.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
				button.Text = ""
				button.LayoutOrder = amount
				button.Parent = children2
				local buttontext = Instance.new("TextLabel")
				buttontext.BackgroundTransparency = 1
				buttontext.Name = "ButtonText"
				buttontext.Text = (translations[text] ~= nil and translations[text] or text)
				buttontext.Size = UDim2.new(0, 120, 0, 38)
				buttontext.Active = false
				buttontext.TextColor3 = Color3.fromRGB(160, 160, 160)
				buttontext.TextSize = 17
				buttontext.Font = Enum.Font.SourceSans
				buttontext.TextXAlignment = Enum.TextXAlignment.Left
				buttontext.Position = UDim2.new(0, 10, 0, 0)
				buttontext.Parent = button
				local arrow = Instance.new("ImageLabel")
				arrow.Size = UDim2.new(0, 4, 0, 8)
				arrow.BackgroundTransparency = 1
				arrow.Name = "RightArrow"
				arrow.Position = UDim2.new(1, -20, 0, 16)
				arrow.Image = downloadVapeAsset("vape/assets/RightArrow.png")
				arrow.Active = false
				arrow.Parent = button
				local windowbackbutton2 = Instance.new("ImageButton")
				windowbackbutton2.Size = UDim2.new(0, 16, 0, 16)
				windowbackbutton2.Position = UDim2.new(0, 11, 0, 13)
				windowbackbutton2.Visible = false
				windowbackbutton2.ImageTransparency = 0.55
				windowbackbutton2.BackgroundTransparency = 1
				windowbackbutton2.MouseButton1Click:Connect(function()
					children3.Visible = false
					children2.Visible = true
					settingstext.Text = "Settings"
					settingsexithovercolor = Color3.fromRGB(20, 20, 20)
					settingsexit.BackgroundColor3 = settingsexithovercolor
					settingsbox2.Visible = true
					settingsbox.Visible = true
					windowbackbutton2.Visible = false
					windowbackbutton.Visible = true
				end)
				windowbackbutton2.MouseEnter:Connect(function()
					windowbackbutton2.ImageTransparency = 0
				end)
				windowbackbutton2.MouseLeave:Connect(function()
					windowbackbutton2.ImageTransparency = 0.55
				end)
				windowbackbutton2.Image = downloadVapeAsset("vape/assets/BackIcon.png")
				windowbackbutton2.Parent = windowtitle
				button.MouseEnter:Connect(function()
					tweenService:Create(button, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(31, 30, 31)}):Play()
					buttontext.TextColor3 = Color3.fromRGB(200, 200, 200)
				end)
				button.MouseLeave:Connect(function()
					tweenService:Create(button, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(26, 25, 26)}):Play()
					buttontext.TextColor3 = Color3.fromRGB(160, 160, 160)
				end)
				button.MouseButton1Click:Connect(function()
					children2.Visible = false
					children3.Visible = true
					windowbackbutton.Visible = false
					windowbackbutton2.Visible = true
					settingstext.Text = text
					settingsexithovercolor = Color3.fromRGB(26, 25, 26)
					settingsexit.BackgroundColor3 = settingsexithovercolor
					settingsbox2.Visible = false
					settingsbox.Visible = false
				end)
				settingsexit.MouseButton1Click:Connect(function()
					children3.Visible = false
					windowbackbutton2.Visible = false
				end)

				windowapi3["CreateToggle"] = function(argstable)
					local buttonapi = {}
					local currentanim
					local amount = #children3:GetChildren()
					local buttontext = Instance.new("TextButton")
					buttontext.AutoButtonColor = false
					buttontext.BackgroundTransparency = 1
					buttontext.Name = "ButtonText"
					buttontext.Text = "          "..(translations[argstable["Name"]] ~= nil and translations[argstable["Name"]] or argstable["Name"])
					buttontext.Name = argstable["Name"]
					buttontext.LayoutOrder = amount
					buttontext.Size = UDim2.new(1, 0, 0, 30)
					buttontext.Active = false
					buttontext.TextColor3 = Color3.fromRGB(160, 160, 160)
					buttontext.TextSize = 14
					buttontext.Font = Enum.Font.Arial
					buttontext.TextXAlignment = Enum.TextXAlignment.Left
					buttontext.Position = UDim2.new(0, (icon and 36 or 10), 0, 0)
					buttontext.Parent = children3
					local buttonarrow = Instance.new("ImageLabel")
					buttonarrow.Size = UDim2.new(1, 0, 0, 4)
					buttonarrow.Position = UDim2.new(0, 0, 1, -4)
					buttonarrow.BackgroundTransparency = 1
					buttonarrow.Name = "ToggleArrow"
					buttonarrow.Image = downloadVapeAsset("vape/assets/ToggleArrow.png")
					buttonarrow.Visible = false
					buttonarrow.Parent = buttontext
					local toggleframe1 = Instance.new("Frame")
					toggleframe1.Size = UDim2.new(0, 22, 0, 12)
					toggleframe1.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
					toggleframe1.BorderSizePixel = 0
					toggleframe1.Name = "ToggleFrame1"
					toggleframe1.Position = UDim2.new(1, -30, 0, 10)
					toggleframe1.Parent = buttontext
					local toggleframe2 = Instance.new("Frame")
					toggleframe2.Size = UDim2.new(0, 8, 0, 8)
					toggleframe2.Active = false
					toggleframe2.Position = UDim2.new(0, 2, 0, 2)
					toggleframe2.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
					toggleframe2.BorderSizePixel = 0
					toggleframe2.Parent = toggleframe1
					local uicorner = Instance.new("UICorner")
					uicorner.CornerRadius = UDim.new(0, 16)
					uicorner.Parent = toggleframe1
					local uicorner2 = Instance.new("UICorner")
					uicorner2.CornerRadius = UDim.new(0, 16)
					uicorner2.Parent = toggleframe2

					buttonapi["Enabled"] = false
					buttonapi["Keybind"] = ""
					buttonapi["Default"] = argstable["Default"]
					buttonapi["Object"] = buttontext
					buttonapi["ToggleButton"] = function(toggle, first)
						buttonapi["Enabled"] = toggle
						if buttonapi["Enabled"] then
							if not first then
								tweenService:Create(toggleframe1, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Hue"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Sat"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Value"])}):Play()
							else
								toggleframe1.BackgroundColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Hue"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Sat"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Value"])
							end
							toggleframe2:TweenPosition(UDim2.new(0, 12, 0, 2), Enum.EasingDirection.InOut, Enum.EasingStyle.Linear, 0.1, true)
						else
							if not first then
								tweenService:Create(toggleframe1, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(60, 60, 60)}):Play()
							else
								toggleframe1.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
							end
							toggleframe2:TweenPosition(UDim2.new(0, 2, 0, 2), Enum.EasingDirection.InOut, Enum.EasingStyle.Linear, 0.1, true)
						end
						argstable["Function"](buttonapi["Enabled"])
					end
					if argstable["Default"] then
						buttonapi["ToggleButton"](argstable["Default"], true)
					end
					buttontext.MouseButton1Click:Connect(function() buttonapi["ToggleButton"](not buttonapi["Enabled"], false) end)
					buttontext.MouseEnter:Connect(function()
						if argstable["HoverText"] and type(argstable["HoverText"]) == "string" then
							hoverbox.Visible = (GuiLibrary["ToggleTooltips"] and hoverbox.TextSize ~= 1)
							local textsize = textService:GetTextSize(argstable["HoverText"], hoverbox.TextSize, hoverbox.Font, Vector2.new(99999, 99999))
							hoverbox.Text = "  "..argstable["HoverText"]:gsub("\n", "\n  ")
							hoverbox.Size = UDim2.new(0, 13 + textsize.X, 0, textsize.Y + 5)
						end
						if buttonapi["Enabled"] == false then
							tweenService:Create(toggleframe1, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(100, 100, 100)}):Play()
						end
					end)
					if argstable["HoverText"] and type(argstable["HoverText"]) == "string" then
						buttontext.MouseMoved:Connect(function(x, y)
							hoverbox.Visible = (GuiLibrary["ToggleTooltips"] and hoverbox.TextSize ~= 1)
							hoverbox.Position = UDim2.new(0, (x + 16) * (1 / GuiLibrary["MainRescale"].Scale), 0,	(y - (hoverbox.Size.Y.Offset / 2) - 26) * (1 / GuiLibrary["MainRescale"].Scale))
						end)
					end
					buttontext.MouseLeave:Connect(function()
						hoverbox.Visible = false
						if buttonapi["Enabled"] == false then
							tweenService:Create(toggleframe1, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(60, 60, 60)}):Play()
						end
					end)

					GuiLibrary.ObjectsThatCanBeSaved[argstable["Name"].."Toggle"] = {["Type"] = "Toggle", ["Object"] = buttontext, ["Api"] = buttonapi}
					return buttonapi
				end

				windowapi3["CreateSlider"] = function(argstable)

					local sliderapi = {}
					local amount2 = #children3:GetChildren()
					local frame = Instance.new("Frame")
					frame.Size = UDim2.new(0, 220, 0, 50)
					frame.BackgroundTransparency = 1
					frame.ClipsDescendants = true
					frame.LayoutOrder = amount2
					frame.Name = argstable["Name"]
					frame.Parent = children3
					local text1 = Instance.new("TextLabel")
					text1.Font = Enum.Font.Arial
					text1.TextXAlignment = Enum.TextXAlignment.Left
					text1.Text = "          "..(translations[argstable["Name"]] ~= nil and translations[argstable["Name"]] or argstable["Name"])
					text1.Size = UDim2.new(1, 0, 0, 25)
					text1.TextColor3 = Color3.fromRGB(160, 160, 160)
					text1.Position = UDim2.new(0, 0, 0, 4)
					text1.BackgroundTransparency = 1
					text1.TextSize = 12
					text1.Parent = frame
					local text2 = Instance.new("TextButton")
					text2.Font = Enum.Font.Arial
					text2.AutoButtonColor = false
					text2.TextXAlignment = Enum.TextXAlignment.Right
					text2.Text = tostring((argstable["Default"] or argstable["Min"])) .. " "..(argstable["Percent"] and "%" or " ").." "
					text2.Size = UDim2.new(0, 40, 0, 25)
					text2.Position = UDim2.new(1, -40, 0, 4)
					text2.TextColor3 = Color3.fromRGB(160, 160, 160)
					text2.BackgroundTransparency = 1
					text2.TextSize = 12
					text2.Parent = frame
					local text3 = Instance.new("TextBox")
					text3.Visible = false
					text3.Font = Enum.Font.Arial
					text3.TextXAlignment = Enum.TextXAlignment.Right
					text3.BackgroundTransparency = 1
					text3.TextColor3 = Color3.fromRGB(160, 160, 160)
					text3.Text = ""
					text3.Position = UDim2.new(1, -40, 0, 4)
					text3.Size = UDim2.new(0, 40, 0, 25)
					text3.TextSize = 12
					text3.Parent = frame
					local textdown = Instance.new("Frame")
					textdown.BackgroundColor3 = Color3.fromRGB(37, 36, 37)
					textdown.Size = UDim2.new(0, 30, 0, 2)
					textdown.Position = UDim2.new(1, -38, 1, -4)
					textdown.Visible = false
					textdown.BorderSizePixel = 0
					textdown.Parent = text2
					local textdown2 = Instance.new("Frame")
					textdown2.BackgroundColor3 = Color3.fromRGB(41, 41, 41)
					textdown2.Size = UDim2.new(0, 30, 0, 2)
					textdown2.Position = UDim2.new(1, -38, 1, -4)
					textdown2.BorderSizePixel = 0
					textdown2.Parent = text3
					local slider1 = Instance.new("Frame")
					slider1.Size = UDim2.new(0, 200, 0, 2)
					slider1.BorderSizePixel = 0
					slider1.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
					slider1.Position = UDim2.new(0, 10, 0, 37)
					slider1.Name = "Slider"
					slider1.Parent = frame
					local slider2 = Instance.new("Frame")
					slider2.BorderSizePixel = 0
					slider2.Size = UDim2.new(math.clamp(((argstable["Default"] or argstable["Min"]) / argstable["Max"]), 0.02, 0.97), 0, 1, 0)
					slider2.BackgroundColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Hue"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Sat"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Value"])
					slider2.Name = "FillSlider"
					slider2.Parent = slider1
					local slider3 = Instance.new("ImageButton")
					slider3.AutoButtonColor = false
					slider3.Size = UDim2.new(0, 24, 0, 16)
					slider3.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
					slider3.BorderSizePixel = 0
					slider3.Image = downloadVapeAsset("vape/assets/SliderButton1.png")
					slider3.Position = UDim2.new(1, -11, 0, -7)
					slider3.Parent = slider2
					slider3.Name = "ButtonSlider"
					sliderapi["Object"] = frame
					sliderapi["Value"] = (argstable["Default"] or argstable["Min"])
					sliderapi["Default"] = (argstable["Default"] or argstable["Min"])
					sliderapi["Min"] = argstable["Min"]
					sliderapi["Max"] = argstable["Max"]
					sliderapi["SetValue"] = function(val)
					--	val = math.clamp(val, argstable["Min"], argstable["Max"])
						sliderapi["Value"] = val
						slider2.Size = UDim2.new(math.clamp((val / argstable["Max"]), 0.02, 0.97), 0, 1, 0)
						text2.Text = sliderapi["Value"] .. ".0 "..(argstable["Percent"] and "%" or " ").." "
						argstable["Function"](val)
					end
					slider3.MouseButton1Down:Connect(function()
						local x,y,xscale,yscale,xscale2 = RelativeXY(slider1, inputService:GetMouseLocation())
						sliderapi["SetValue"](math.floor(argstable["Min"] + ((argstable["Max"] - argstable["Min"]) * xscale)))
						text2.Text = sliderapi["Value"] .. ".0 "..(argstable["Percent"] and "%" or " ").." "
						slider2.Size = UDim2.new(xscale2,0,1,0)
						local move
						local kill
						move = inputService.InputChanged:Connect(function(input)
							if input.UserInputType == Enum.UserInputType.MouseMovement then
								local x,y,xscale,yscale,xscale2 = RelativeXY(slider1, inputService:GetMouseLocation())
								sliderapi["SetValue"](math.floor(argstable["Min"] + ((argstable["Max"] - argstable["Min"]) * xscale)))
								text2.Text = sliderapi["Value"] .. ".0 "..(argstable["Percent"] and "%" or " ").." "
								slider2.Size = UDim2.new(xscale2,0,1,0)
							end
						end)
						kill = inputService.InputEnded:Connect(function(input)
							if input.UserInputType == Enum.UserInputType.MouseButton1 then
								move:Disconnect()
								kill:Disconnect()
							end
						end)
					end)
					text2.MouseEnter:Connect(function()
						textdown.Visible = true
					end)
					text2.MouseLeave:Connect(function()
						textdown.Visible = false
					end)
					text2.MouseButton1Click:Connect(function()
						text3.Visible = true
						text2.Visible = false
						text3:CaptureFocus()
						text3.Text = text2.Text
					end)
					text3.FocusLost:Connect(function(enter)
						text3.Visible = false
						text2.Visible = true
						if enter then
							sliderapi["SetValue"](tonumber(text3.Text))
						end
					end)
					frame.MouseEnter:Connect(function()
						if argstable["HoverText"] and type(argstable["HoverText"]) == "string" then
							hoverbox.Visible = (GuiLibrary["ToggleTooltips"] and hoverbox.TextSize ~= 1)
							local textsize = textService:GetTextSize(argstable["HoverText"], hoverbox.TextSize, hoverbox.Font, Vector2.new(99999, 99999))
							hoverbox.Text = "  "..argstable["HoverText"]:gsub("\n", "\n  ")
							hoverbox.Size = UDim2.new(0, 13 + textsize.X, 0, textsize.Y + 5)
						end
					end)
					if argstable["HoverText"] and type(argstable["HoverText"]) == "string" then
						frame.MouseMoved:Connect(function(x, y)
							hoverbox.Visible = (GuiLibrary["ToggleTooltips"] and hoverbox.TextSize ~= 1)
							hoverbox.Position = UDim2.new(0, (x + 16) * (1 / GuiLibrary["MainRescale"].Scale), 0,	(y - (hoverbox.Size.Y.Offset / 2) - 26) * (1 / GuiLibrary["MainRescale"].Scale))
						end)
					end
					frame.MouseLeave:Connect(function()
						hoverbox.Visible = false
					end)
					GuiLibrary.ObjectsThatCanBeSaved[argstable["Name"].."Slider"] = {["Type"] = "Slider", ["Object"] = frame, ["Api"] = sliderapi}
					return sliderapi
				end

				windowapi3["CreateButton2"] = function(argstable)
					local buttonapi = {}
					local currentanim
					local amount = #children3:GetChildren()
					local buttontext = Instance.new("Frame")
					buttontext.BackgroundTransparency = 1
					buttontext.Name = "ButtonText"
					buttontext.Name = argstable["Name"]
					buttontext.LayoutOrder = amount
					buttontext.Size = UDim2.new(1, 0, 0, 30)
					buttontext.Active = false
					buttontext.Position = UDim2.new(0, (icon and 36 or 10), 0, 0)
					buttontext.Parent = children3
					local toggleframe2 = Instance.new("Frame")
					toggleframe2.Size = UDim2.new(0, 199, 0, 26)
					toggleframe2.Position = UDim2.new(0, 11, 0, 1)
					toggleframe2.BackgroundColor3 = Color3.fromRGB(38, 37, 38)
					toggleframe2.Name = "ToggleFrame2"
					toggleframe2.Parent = buttontext
					local toggleframe1 = Instance.new("TextButton")
					toggleframe1.AutoButtonColor = false
					toggleframe1.Size = UDim2.new(0, 195, 0, 22)
					toggleframe1.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
					toggleframe1.BorderSizePixel = 0
					toggleframe1.Text = (translations[argstable["Name"]] ~= nil and translations[argstable["Name"]] or argstable["Name"]):upper()
					toggleframe1.Font = Enum.Font.SourceSans
					toggleframe1.TextSize = 17
					toggleframe1.TextColor3 = Color3.fromRGB(151, 151, 151)
					toggleframe1.Name = "ToggleFrame1"
					toggleframe1.Position = UDim2.new(0, 2, 0, 2)
					toggleframe1.Parent = toggleframe2
					local uicorner = Instance.new("UICorner")
					uicorner.CornerRadius = UDim.new(0, 3)
					uicorner.Parent = toggleframe1
					local uicorner2 = Instance.new("UICorner")
					uicorner2.CornerRadius = UDim.new(0, 3)
					uicorner2.Parent = toggleframe2

					toggleframe1.MouseButton1Click:Connect(function() argstable["Function"]() end)
					toggleframe1.MouseEnter:Connect(function()
						tweenService:Create(toggleframe1, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(31, 30, 31)}):Play()
					end)
					toggleframe1.MouseLeave:Connect(function()
						tweenService:Create(toggleframe1, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(26, 25, 26)}):Play()
					end)

					return buttonapi
				end

				return windowapi3
			else
				local divider = Instance.new("Frame")
				divider.Size = UDim2.new(1, 0, 0, 1)
				divider.Name = "Divider"
				divider.LayoutOrder = amount
				divider.BackgroundColor3 = Color3.fromRGB(37, 37, 37)
				divider.BorderSizePixel = 0
				divider.Parent = children2
			end
		end

		windowapi["CreateGUIBind"] = function()
			local amount2 = #children2:GetChildren()
			local frame = Instance.new("TextLabel")
			frame.Size = UDim2.new(0, 220, 0, 40)
			frame.BackgroundTransparency = 1
			frame.TextSize = 17
			frame.TextColor3 = Color3.fromRGB(151, 151, 151)
			frame.Font = Enum.Font.SourceSans
			frame.Text = "   Rebind GUI"
			frame.LayoutOrder = amount2
			frame.Name = "Rebind GUI"
			frame.TextXAlignment = Enum.TextXAlignment.Left
			frame.Parent = children2
			local bindbkg = Instance.new("TextButton")
			bindbkg.Text = ""
			bindbkg.AutoButtonColor = false
			bindbkg.Size = UDim2.new(0, 20, 0, 21)
			bindbkg.Position = UDim2.new(1, -50, 0, 10)
			bindbkg.BorderSizePixel = 0
			bindbkg.BackgroundColor3 = Color3.fromRGB(40, 41, 40)
			bindbkg.BackgroundTransparency = 0
			bindbkg.Visible = true
			bindbkg.Parent = frame
			local bindimg = Instance.new("ImageLabel")
			bindimg.Image = downloadVapeAsset("vape/assets/KeybindIcon.png")
			bindimg.BackgroundTransparency = 1
			bindimg.ImageColor3 = Color3.fromRGB(225, 225, 225)
			bindimg.Size = UDim2.new(0, 12, 0, 12)
			bindimg.Position = UDim2.new(0.5, -6, 0, 5)
			bindimg.Active = false
			bindimg.Visible = (GuiLibrary["GUIKeybind"] == "")
			bindimg.Parent = bindbkg
			local bindtext = Instance.new("TextLabel")
			bindtext.Active = false
			bindtext.BackgroundTransparency = 1
			bindtext.TextSize = 16
			bindtext.Parent = bindbkg
			bindtext.Font = Enum.Font.SourceSans
			bindtext.Size = UDim2.new(1, 0, 1, 0)
			bindtext.TextColor3 = Color3.fromRGB(80, 80, 80)
			bindtext.Visible = (GuiLibrary["GUIKeybind"] ~= "")
			local bindtext2 = Instance.new("ImageLabel")
			bindtext2.Size = UDim2.new(0, 154, 0, 41)
			bindtext2.Image = downloadVapeAsset("vape/assets/BindBackground.png")
			bindtext2.BackgroundTransparency = 1
			bindtext2.ScaleType = Enum.ScaleType.Slice
			bindtext2.SliceCenter = Rect.new(0, 0, 140, 41)
			bindtext2.Visible = false
			bindtext2.Parent = frame
			local bindtext3 = Instance.new("TextLabel")
			bindtext3.Text = "  PRESS  KEY TO BIND"
			bindtext3.Size = UDim2.new(0, 150, 0, 33)
			bindtext3.Font = Enum.Font.SourceSans
			bindtext3.TextXAlignment = Enum.TextXAlignment.Left
			bindtext3.TextSize = 17
			bindtext3.TextColor3 = Color3.fromRGB(44, 44, 44)
			bindtext3.BackgroundColor3 = Color3.fromRGB(37, 37, 37)
			bindtext3.BorderSizePixel = 0
			bindtext3.Parent = bindtext2
			local bindround = Instance.new("UICorner")
			bindround.CornerRadius = UDim.new(0, 6)
			bindround.Parent = bindbkg
			bindbkg.MouseButton1Click:Connect(function()
				if GuiLibrary["KeybindCaptured"] == false then
					GuiLibrary["KeybindCaptured"] = true
					task.spawn(function()
						bindtext2.Visible = true
						repeat task.wait() until GuiLibrary["PressedKeybindKey"] ~= ""
						local key = GuiLibrary["PressedKeybindKey"]
						local textsize = textService:GetTextSize(key, 16, bindtext.Font, Vector2.new(99999, 99999))
						newsize = UDim2.new(0, 13 + textsize.X, 0, 21)
						GuiLibrary["GUIKeybind"] = key
						bindbkg.Visible = true
						bindbkg.Size = newsize
						bindbkg.Position = UDim2.new(1, -(10 + newsize.X.Offset), 0, 10)
						bindimg.Visible = false
						bindtext.Visible = true
						bindtext.Text = key
						GuiLibrary["PressedKeybindKey"] = ""
						GuiLibrary["KeybindCaptured"] = false
						bindtext2.Visible = false
					end)
				end
			end)
			bindbkg.MouseEnter:Connect(function()
				bindimg.Image = downloadVapeAsset("vape/assets/PencilIcon.png")
				bindimg.Visible = true
				bindtext.Visible = false
			end)
			bindbkg.MouseLeave:Connect(function()
				bindimg.Image = downloadVapeAsset("vape/assets/KeybindIcon.png")
				if GuiLibrary["GUIKeybind"] ~= "" then
					bindimg.Visible = false
					bindtext.Visible = true
					bindbkg.Size = newsize
					bindbkg.Position = UDim2.new(1, -(10 + newsize.X.Offset), 0, 10)
				end
			end)
			if GuiLibrary["GUIKeybind"] ~= "" then
				bindtext.Text = GuiLibrary["GUIKeybind"]
				local textsize = textService:GetTextSize(GuiLibrary["GUIKeybind"], 16, bindtext.Font, Vector2.new(99999, 99999))
				newsize = UDim2.new(0, 13 + textsize.X, 0, 21)
				bindbkg.Size = newsize
				bindbkg.Position = UDim2.new(1, -(10 + newsize.X.Offset), 0, 10)
			end
			return {
				["Reload"] = function()
					if GuiLibrary["GUIKeybind"] ~= "" then
						bindtext.Text = GuiLibrary["GUIKeybind"]
						local textsize = textService:GetTextSize(GuiLibrary["GUIKeybind"], 16, bindtext.Font, Vector2.new(99999, 99999))
						newsize = UDim2.new(0, 13 + textsize.X, 0, 21)
						bindbkg.Size = newsize
						bindbkg.Position = UDim2.new(1, -(10 + newsize.X.Offset), 0, 10)
					end
				end
			}
		end

		windowapi["CreateColorSlider"] = function(name, temporaryfunction)
			local firstmove = true
			local slidercolors = {Color3.fromRGB(250, 50, 56), Color3.fromRGB(242, 99, 33), Color3.fromRGB(252, 179, 22), Color3.fromRGB(5, 133, 104), Color3.fromRGB(47, 122, 229), Color3.fromRGB(126, 84, 217), Color3.fromRGB(232, 96, 152)}
			local sldiercolorpos = {
				[1] = 4,
				[2] = 33,
				[3] = 62,
				[4] = 90,
				[5] = 119,
				[6] = 148,
				[7] = 177
			}

			local function getclosestcolor(color)
				local singlecolor = (1 / #slidercolors)
				for i = 1, #slidercolors do
					if color <= (singlecolor * i) then
						return i
					end
				end
				return 1
			end

			local min, max = 0, 1
			local def = math.floor((min + max) / 2)
			local defsca = (def - min)/(max - min)
			local sliderapi = {}
			local amount2 = #children2:GetChildren()

			local function createSlider(text, changeType)
				local frame = Instance.new("Frame")
				frame.Size = UDim2.new(0, 220, 0, 50)
				frame.BorderSizePixel = 0
				frame.BackgroundTransparency = 0
				frame.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
				frame.LayoutOrder = amount2 + 1
				frame.Name = text
				frame.Visible = false
				frame.Parent = children2
				local text1 = Instance.new("TextLabel")
				text1.Font = Enum.Font.Arial
				text1.TextXAlignment = Enum.TextXAlignment.Left
				text1.Text = "          "..text
				text1.Size = UDim2.new(1, 0, 0, 27)
				text1.TextColor3 = Color3.fromRGB(160, 160, 160)
				text1.Position = UDim2.new(0, 0, 0, 4)
				text1.BackgroundTransparency = 1
				text1.TextSize = 12
				text1.Parent = frame
				local slider1 = Instance.new("TextButton")
				slider1.AutoButtonColor = false
				slider1.Text = ""
				slider1.Size = UDim2.new(0, 200, 0, 2)
				slider1.BorderSizePixel = 0
				slider1.BackgroundColor3 = Color3.new(1, 1, 1)
				slider1.Position = UDim2.new(0, 10, 0, 32)
				slider1.Name = "Slider"
				slider1.Parent = frame
				local uigradient = Instance.new("UIGradient")
				uigradient.Color = ColorSequence.new({ColorSequenceKeypoint.new(0, Color3.fromHSV(0, 1, 1)), ColorSequenceKeypoint.new(0.2, Color3.fromHSV(0.2, 1, 1)), ColorSequenceKeypoint.new(0.3, Color3.fromHSV(0.3, 1, 1)), ColorSequenceKeypoint.new(0.4, Color3.fromHSV(0.4, 1, 1)), ColorSequenceKeypoint.new(0.5, Color3.fromHSV(0.5, 1, 1)), ColorSequenceKeypoint.new(0.6, Color3.fromHSV(0.6, 1, 1)), ColorSequenceKeypoint.new(0.7, Color3.fromHSV(0.7, 1, 1)), ColorSequenceKeypoint.new(0.8, Color3.fromHSV(0.8, 1, 1)), ColorSequenceKeypoint.new(0.9, Color3.fromHSV(0.9, 1, 1)), ColorSequenceKeypoint.new(1, Color3.fromHSV(1, 1, 1))})
				uigradient.Parent = slider1
				local slider3 = Instance.new("ImageButton")
				slider3.AutoButtonColor = false
				slider3.Size = UDim2.new(0, 24, 0, 16)
				slider3.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
				slider3.BorderSizePixel = 0
				slider3.Image = downloadVapeAsset("vape/assets/SliderButton1.png")
				slider3.Position = UDim2.new(0.44, -11, 0, -7)
				slider3.Parent = slider1
				slider3.Name = "ButtonSlider"

				local clicktick = tick()
				local function slidercode(obj)
					sliderapi["Custom"] = true
					if clicktick > tick() then
						sliderapi["SetRainbow"](not sliderapi["RainbowValue"])
					end
					clicktick = tick() + 0.3
					local x,y,xscale,yscale,xscale2 = RelativeXY(obj, inputService:GetMouseLocation())
					sliderapi["SetValue"]((changeType == "Hue" and (min + ((max - min) * xscale)) or sliderapi["Hue"]), (changeType == "Sat" and (min + ((max - min) * xscale)) or sliderapi["Sat"]), (changeType == "Value" and (min + ((max - min) * xscale)) or sliderapi["Value"]))
					obj.ButtonSlider.Position = UDim2.new(math.clamp(xscale2, 0.02, 0.95), -9, 0, -7)
					local move
					local kill
					move = inputService.InputChanged:Connect(function(input)
						if input.UserInputType == Enum.UserInputType.MouseMovement then
							local x,y,xscale,yscale,xscale2 = RelativeXY(obj, inputService:GetMouseLocation())
							sliderapi["SetValue"]((changeType == "Hue" and (min + ((max - min) * xscale)) or sliderapi["Hue"]), (changeType == "Sat" and (min + ((max - min) * xscale)) or sliderapi["Sat"]), (changeType == "Value" and (min + ((max - min) * xscale)) or sliderapi["Value"]))
							obj.ButtonSlider.Position = UDim2.new(math.clamp(xscale2, 0.02, 0.95), -9, 0, -7)
						end
					end)
					kill = inputService.InputEnded:Connect(function(input)
						if input.UserInputType == Enum.UserInputType.MouseButton1 then
							move:Disconnect()
							kill:Disconnect()
						end
					end)
				end
				slider1.MouseButton1Down:Connect(function()
					slidercode(slider1)
				end)
				slider3.MouseButton1Down:Connect(function()
					slidercode(slider1)
				end)

				return frame
			end

			local frame = Instance.new("Frame")
			frame.Size = UDim2.new(0, 220, 0, 50)
			frame.BackgroundTransparency = 1
			frame.LayoutOrder = amount2
			frame.Name = name
			frame.Parent = children2
			local text1 = Instance.new("TextLabel")
			text1.Font = Enum.Font.Arial
			text1.TextXAlignment = Enum.TextXAlignment.Left
			text1.Text = "          "..name
			text1.Size = UDim2.new(1, 0, 0, 25)
			text1.TextColor3 = Color3.fromRGB(160, 160, 160)
			text1.Position = UDim2.new(0, 0, 0, 4)
			text1.BackgroundTransparency = 1
			text1.TextSize = 12
			text1.Parent = frame
			local text2 = Instance.new("Frame")
			text2.Size = UDim2.new(0, 12, 0, 12)
			text2.Position = UDim2.new(1, -22, 0, 10)
			text2.BackgroundColor3 = Color3.fromRGB(5, 133, 104)
			text2.Parent = frame
			local uicorner4 = Instance.new("UICorner")
			uicorner4.CornerRadius = UDim.new(0, 4)
			uicorner4.Parent = text2
			local slider1 = Instance.new("TextButton")
			slider1.AutoButtonColor = false
			slider1.Text = ""
			slider1.Size = UDim2.new(0, 200, 0, 2)
			slider1.BackgroundTransparency = 1
			slider1.BackgroundColor3 = Color3.fromRGB(5, 133, 104)
			slider1.Position = UDim2.new(0, 10, 0, 32)
			slider1.Name = "Slider"
			slider1.Parent = frame
			local sliderrainbow = Instance.new("ImageButton")
			sliderrainbow.Image = downloadVapeAsset("vape/assets/RainbowIcon1.png")
			sliderrainbow.BackgroundTransparency = 1
			sliderrainbow.Size = UDim2.new(0, 12, 0, 12)
			sliderrainbow.Position = UDim2.new(1, -43, 0, 10)
			sliderrainbow.Parent = frame
			local colornum = 10
			local colorbigger = true
			for i, v in pairs(slidercolors) do
				local colorframe = Instance.new("Frame")
				colorframe.Size = UDim2.new(0, 27 + (colorbigger and 1 or 0), 0, 2)
				colorframe.Position = UDim2.new(0, colornum, 0, 32)
				colorframe.BorderSizePixel = 0
				colorframe.BackgroundColor3 = v
				colorframe.Parent = frame
				colornum = colornum + (colorframe.Size.X.Offset + 1)
				colorbigger = not colorbigger
			end
			local slider3 = Instance.new("ImageButton")
			slider3.AutoButtonColor = false
			slider3.Size = UDim2.new(0, 26, 0, 12)
			slider3.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
			slider3.BorderSizePixel = 0
			slider3.ZIndex = 2
			slider3.Image = downloadVapeAsset("vape/assets/ColorSlider1.png")
			slider3.Position = UDim2.new(0, sldiercolorpos[4] - 3, 0, -5)
			slider3.Parent = slider1
			slider3.Name = "ButtonSlider"
			local hueSlider = createSlider("Custom color", "Hue")
			local satSlider = createSlider("Saturation", "Sat")
			satSlider.Slider.UIGradient.Color = ColorSequence.new({ColorSequenceKeypoint.new(0, Color3.fromHSV(0, 0, 1)), ColorSequenceKeypoint.new(1, Color3.fromHSV(0.4, 1, 1))})
			local valSlider = createSlider("Vibrance", "Value")
			valSlider.Slider.UIGradient.Color = ColorSequence.new({ColorSequenceKeypoint.new(0, Color3.fromHSV(0, 0, 0)), ColorSequenceKeypoint.new(1, Color3.fromHSV(0.4, 1, 1))})
			local sliderexpand = Instance.new("ImageButton")
			sliderexpand.AutoButtonColor = false
			sliderexpand.Size = UDim2.new(0, 15, 0, 15)
			sliderexpand.BackgroundTransparency = 1
			sliderexpand.Position = UDim2.new(0, textService:GetTextSize(text1.Text, text1.TextSize, text1.Font, Vector2.new(10000, 100000)).X + 3, 0, 6)
			sliderexpand.Image = downloadVapeAsset("vape/assets/HoverArrow3.png")
			sliderexpand.Parent = frame
			sliderexpand.MouseEnter:Connect(function()
				sliderexpand.Image = downloadVapeAsset("vape/assets/HoverArrow4.png")
			end)
			sliderexpand.MouseLeave:Connect(function()
				sliderexpand.Image = downloadVapeAsset("vape/assets/HoverArrow3.png")
			end)
			sliderexpand.MouseButton1Click:Connect(function()
				local val = not hueSlider.Visible
				hueSlider.Visible = val
				satSlider.Visible = val
				valSlider.Visible = val
				sliderexpand.Rotation = (val and 180 or 0)
			end)
			local defaulth, defaults, defaultv = slidercolors[4]:ToHSV()
			sliderapi["Hue"] = defaulth
			sliderapi["Sat"] = defaults
			sliderapi["Value"] = defaultv
			sliderapi["Saved"] = 4
			sliderapi["RainbowValue"] = false
			sliderapi["Custom"] = false
			sliderapi["Object"] = frame

			--[[
				sliderapi["Hue"] = (argstable["Default"] or 0.44)
				sliderapi["Sat"] = 1
				sliderapi["Value"] = 1
				sliderapi["Object"] = frame
				sliderapi["RainbowValue"] = false
				sliderapi["SetValue"] = function(hue, sat, val)
					hue = (hue or sliderapi["Hue"])
					sat = (sat or sliderapi["Sat"])
					val = (val or sliderapi["Value"])
					text2.BackgroundColor3 = Color3.fromHSV(hue, sat, val)
					pcall(function()
						slidersat.Slider.UIGradient.Color = ColorSequence.new({ColorSequenceKeypoint.new(0, Color3.fromHSV(0, 0, val)), ColorSequenceKeypoint.new(1, Color3.fromHSV(hue, 1, val))})
						sliderval.Slider.UIGradient.Color = ColorSequence.new({ColorSequenceKeypoint.new(0, Color3.fromHSV(0, 0, 0)), ColorSequenceKeypoint.new(1, Color3.fromHSV(hue, sat, 1))})
					end)
					sliderapi["Hue"] = hue
					sliderapi["Sat"] = sat
					sliderapi["Value"] = val
					slider3.Position = UDim2.new(math.clamp(hue, 0.02, 0.95), -9, 0, -7)
					argstable["Function"](hue, sat, val)
				end
			]]
			sliderapi["SetValue"] = function(hue, sat, val)
				hue = hue or 0.46
				sat = sat or 0.96
				val = val or 0.52
				slider3.Image = ((sliderapi["RainbowValue"] or sliderapi["Custom"]) and downloadVapeAsset("vape/assets/ColorSlider2.png") or downloadVapeAsset("vape/assets/ColorSlider1.png"))
				sliderrainbow.Image = (sliderapi["RainbowValue"] and downloadVapeAsset("vape/assets/RainbowIcon2.png") or downloadVapeAsset("vape/assets/RainbowIcon1.png"))
				if sliderapi["RainbowValue"] or sliderapi["Custom"] then
					val = math.clamp(val, min, max)
					text2.BackgroundColor3 = Color3.fromHSV(hue, 0.7, 0.9)
					slider3.ImageColor3 = Color3.new(1, 1, 1)
					sliderapi["Hue"] = hue
					sliderapi["Sat"] = sat
					sliderapi["Value"] = val
					pcall(function()
						satSlider.Slider.UIGradient.Color = ColorSequence.new({ColorSequenceKeypoint.new(0, Color3.fromHSV(0, 0, val)), ColorSequenceKeypoint.new(1, Color3.fromHSV(hue, 1, val))})
						valSlider.Slider.UIGradient.Color = ColorSequence.new({ColorSequenceKeypoint.new(0, Color3.fromHSV(0, 0, 0)), ColorSequenceKeypoint.new(1, Color3.fromHSV(hue, sat, 1))})
						hueSlider.Slider.ButtonSlider.Position = UDim2.new(math.clamp(hue, 0.02, 0.95), -9, 0, -7)
						satSlider.Slider.ButtonSlider.Position = UDim2.new(math.clamp(sat, 0.02, 0.95), -9, 0, -7)
						valSlider.Slider.ButtonSlider.Position = UDim2.new(math.clamp(val, 0.02, 0.95), -9, 0, -7)
					end)
					slider3.Position = UDim2.new(0, sldiercolorpos[4] - 3, 0, -5)
					temporaryfunction(hue, sat, val)
				else
					local colornum = getclosestcolor(hue)
					sliderapi["Saved"] = colornum
					local h, s, v = slidercolors[colornum]:ToHSV()
					text2.BackgroundColor3 = slidercolors[colornum]
					slider3.ImageColor3 = slidercolors[colornum]
					sliderapi["Hue"] = h
					sliderapi["Sat"] = s
					sliderapi["Value"] = v
					pcall(function()
						satSlider.Slider.UIGradient.Color = ColorSequence.new({ColorSequenceKeypoint.new(0, Color3.fromHSV(0, 0, val)), ColorSequenceKeypoint.new(1, Color3.fromHSV(hue, 1, val))})
						valSlider.Slider.UIGradient.Color = ColorSequence.new({ColorSequenceKeypoint.new(0, Color3.fromHSV(0, 0, 0)), ColorSequenceKeypoint.new(1, Color3.fromHSV(hue, sat, 1))})
						hueSlider.Slider.ButtonSlider.Position = UDim2.new(math.clamp(h, 0.02, 0.95), -9, 0, -7)
						satSlider.Slider.ButtonSlider.Position = UDim2.new(math.clamp(s, 0.02, 0.95), -9, 0, -7)
						valSlider.Slider.ButtonSlider.Position = UDim2.new(math.clamp(v, 0.02, 0.95), -9, 0, -7)
					end)
					slider3.Position = UDim2.new(0, sldiercolorpos[colornum] - 3, 0, -5)
					temporaryfunction(h, s, v)
				end
				firstmove = false
			end
			sliderapi["SetRainbow"] = function(val)
				sliderapi["RainbowValue"] = val
				sliderapi["Custom"] = false
				if sliderapi["RainbowValue"] then
					table.insert(GuiLibrary.RainbowSliders, sliderapi)
				else
					table.remove(GuiLibrary.RainbowSliders, table.find(GuiLibrary.RainbowSliders, sliderapi))
					sliderapi["SetValue"]()
				end
			end
			sliderrainbow.MouseButton1Click:Connect(function()
				sliderapi["SetRainbow"](not sliderapi["RainbowValue"])
				sliderrainbow.Image = (sliderapi["RainbowValue"] and downloadVapeAsset("vape/assets/RainbowIcon2.png") or downloadVapeAsset("vape/assets/RainbowIcon1.png"))
			end)
			slider1.MouseButton1Down:Connect(function()
				sliderapi["Custom"] = false
				local x,y,xscale,yscale,xscale2 = RelativeXY(slider1, inputService:GetMouseLocation())
				sliderapi["SetValue"](min + ((max - min) * xscale))
			--	slider3.Position = UDim2.new(math.clamp(xscale2, 0.02, 0.95), -9, 0, -5)
				local move
				local kill
				move = inputService.InputChanged:Connect(function(input)
					if input.UserInputType == Enum.UserInputType.MouseMovement then
						local x,y,xscale,yscale,xscale2 = RelativeXY(slider1, inputService:GetMouseLocation())
						sliderapi["SetValue"](min + ((max - min) * xscale))
					--	slider3.Position = UDim2.new(math.clamp(xscale2, 0.02, 0.95), -9, 0, -5)
					end
				end)
				kill = inputService.InputEnded:Connect(function(input)
					if input.UserInputType == Enum.UserInputType.MouseButton1 then
						move:Disconnect()
						kill:Disconnect()
					end
				end)
			end)
			local clicktick = tick()
			slider3.MouseButton1Down:Connect(function()
				sliderapi["Custom"] = false
				if clicktick > tick() then
					sliderapi["SetRainbow"](not sliderapi["RainbowValue"])
				end
				clicktick = tick() + 0.3
				local x,y,xscale,yscale,xscale2 = RelativeXY(slider1, inputService:GetMouseLocation())
				sliderapi["SetValue"](min + ((max - min) * xscale), 0.7, 0.9)
				--slider3.Position = UDim2.new(math.clamp(xscale2, 0.02, 0.95), -9, 0, -5)
				local move
				local kill
				move = inputService.InputChanged:Connect(function(input)
					if input.UserInputType == Enum.UserInputType.MouseMovement then
						local x,y,xscale,yscale,xscale2 = RelativeXY(slider1, inputService:GetMouseLocation())
						sliderapi["SetValue"](min + ((max - min) * xscale), 0.7, 0.9)
					--	slider3.Position = UDim2.new(math.clamp(xscale2, 0.02, 0.95), -9, 0, -5)
					end
				end)
				kill = inputService.InputEnded:Connect(function(input)
					if input.UserInputType == Enum.UserInputType.MouseButton1 then
						move:Disconnect()
						kill:Disconnect()
					end
				end)
			end)
			GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"] = {["Type"] = "ColorSliderGUI", ["Object"] = frame, ["Api"] = sliderapi}
			return sliderapi
		end

		windowapi["CreateToggle"] = function(argstable)
			local buttonapi = {}
			local currentanim
			local amount = #children2:GetChildren()
			local buttontext = Instance.new("TextButton")
			buttontext.AutoButtonColor = false
			buttontext.BackgroundTransparency = 1
			buttontext.Name = "ButtonText"
			buttontext.Text = "          "..(translations[argstable["Name"]] ~= nil and translations[argstable["Name"]] or argstable["Name"])
			buttontext.Name = argstable["Name"]
			buttontext.LayoutOrder = amount
			buttontext.Size = UDim2.new(1, 0, 0, 30)
			buttontext.Active = false
			buttontext.TextColor3 = Color3.fromRGB(160, 160, 160)
			buttontext.TextSize = 14
			buttontext.Font = Enum.Font.Arial
			buttontext.TextXAlignment = Enum.TextXAlignment.Left
			buttontext.Position = UDim2.new(0, (icon and 36 or 10), 0, 0)
			buttontext.Parent = children2
			local buttonarrow = Instance.new("ImageLabel")
			buttonarrow.Size = UDim2.new(1, 0, 0, 4)
			buttonarrow.Position = UDim2.new(0, 0, 1, -4)
			buttonarrow.BackgroundTransparency = 1
			buttonarrow.Name = "ToggleArrow"
			buttonarrow.Image = downloadVapeAsset("vape/assets/ToggleArrow.png")
			buttonarrow.Visible = false
			buttonarrow.Parent = buttontext
			local toggleframe1 = Instance.new("Frame")
			toggleframe1.Size = UDim2.new(0, 22, 0, 12)
			toggleframe1.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
			toggleframe1.BorderSizePixel = 0
			toggleframe1.Name = "ToggleFrame1"
			toggleframe1.Position = UDim2.new(1, -30, 0, 10)
			toggleframe1.Parent = buttontext
			local toggleframe2 = Instance.new("Frame")
			toggleframe2.Size = UDim2.new(0, 8, 0, 8)
			toggleframe2.Active = false
			toggleframe2.Position = UDim2.new(0, 2, 0, 2)
			toggleframe2.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
			toggleframe2.BorderSizePixel = 0
			toggleframe2.Parent = toggleframe1
			local uicorner = Instance.new("UICorner")
			uicorner.CornerRadius = UDim.new(0, 16)
			uicorner.Parent = toggleframe1
			local uicorner2 = Instance.new("UICorner")
			uicorner2.CornerRadius = UDim.new(0, 16)
			uicorner2.Parent = toggleframe2

			buttonapi["Enabled"] = false
			buttonapi["Keybind"] = ""
			buttonapi["Default"] = argstable["Default"]
			buttonapi["Object"] = buttontext
			buttonapi["ToggleButton"] = function(toggle, first)
				buttonapi["Enabled"] = toggle
				if buttonapi["Enabled"] then
					if not first then
						tweenService:Create(toggleframe1, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Hue"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Sat"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Value"])}):Play()
					else
						toggleframe1.BackgroundColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Hue"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Sat"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Value"])
					end
					toggleframe2:TweenPosition(UDim2.new(0, 12, 0, 2), Enum.EasingDirection.InOut, Enum.EasingStyle.Linear, 0.1, true)
				else
					if not first then
						tweenService:Create(toggleframe1, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(60, 60, 60)}):Play()
					else
						toggleframe1.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
					end
					toggleframe2:TweenPosition(UDim2.new(0, 2, 0, 2), Enum.EasingDirection.InOut, Enum.EasingStyle.Linear, 0.1, true)
				end
				argstable["Function"](buttonapi["Enabled"])
			end
			if argstable["Default"] then
				buttonapi["ToggleButton"](argstable["Default"], true)
			end
			buttontext.MouseButton1Click:Connect(function() buttonapi["ToggleButton"](not buttonapi["Enabled"], false) end)
			buttontext.MouseEnter:Connect(function()
				if argstable["HoverText"] and type(argstable["HoverText"]) == "string" then
					hoverbox.Visible = (GuiLibrary["ToggleTooltips"] and hoverbox.TextSize ~= 1)
					local textsize = textService:GetTextSize(argstable["HoverText"], hoverbox.TextSize, hoverbox.Font, Vector2.new(99999, 99999))
					hoverbox.Text = " "..argstable["HoverText"]:gsub("\n", "\n ")
					hoverbox.Size = UDim2.new(0, 8 + textsize.X, 0, textsize.Y + 5)
				end
				if buttonapi["Enabled"] == false then
					tweenService:Create(toggleframe1, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(100, 100, 100)}):Play()
				end
			end)
			if argstable["HoverText"] and type(argstable["HoverText"]) == "string" then
				buttontext.MouseMoved:Connect(function(x, y)
					hoverbox.Visible = (GuiLibrary["ToggleTooltips"] and hoverbox.TextSize ~= 1)
					hoverbox.Position = UDim2.new(0, (x + 16) * (1 / GuiLibrary["MainRescale"].Scale), 0,	(y - (hoverbox.Size.Y.Offset / 2) - 26) * (1 / GuiLibrary["MainRescale"].Scale))
				end)
			end
			buttontext.MouseLeave:Connect(function()
				hoverbox.Visible = false
				if buttonapi["Enabled"] == false then
					tweenService:Create(toggleframe1, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(60, 60, 60)}):Play()
				end
			end)

			GuiLibrary.ObjectsThatCanBeSaved[argstable["Name"].."Toggle"] = {["Type"] = "Toggle", ["Object"] = buttontext, ["Api"] = buttonapi}
			return buttonapi
		end

		windowapi["CreateButton"] = function(argstable)
			local buttonapi = {}
			local amount = #children:GetChildren()
			local button = Instance.new("TextButton")
			button.Name = argstable["Name"].."Button"
			button.AutoButtonColor = false
			button.Size = UDim2.new(1, 0, 0, 40)
			button.BorderSizePixel = 0
			button.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
			button.Text = ""
			button.LayoutOrder = amount
			button.Parent = children
			local buttontext = Instance.new("TextLabel")
			buttontext.BackgroundTransparency = 1
			buttontext.Name = "ButtonText"
			buttontext.Text = (translations[argstable["Name"]] ~= nil and translations[argstable["Name"]] or argstable["Name"])
			buttontext.Size = UDim2.new(0, 120, 0, 38)
			buttontext.Active = false
			buttontext.TextColor3 = Color3.fromRGB(160, 160, 160)
			buttontext.TextSize = 14
			buttontext.Font = Enum.Font.Arial
			buttontext.TextXAlignment = Enum.TextXAlignment.Left
			buttontext.Position = UDim2.new(0, (argstable["Icon"] and 33 or 10), 0, 1)
			buttontext.Parent = button
			local arrow = Instance.new("ImageLabel")
			arrow.Size = UDim2.new(0, 4, 0, 8)
			arrow.BackgroundTransparency = 1
			arrow.Name = "RightArrow"
			arrow.Position = UDim2.new(1, -20, 0, 16)
			arrow.Image = downloadVapeAsset("vape/assets/RightArrow.png")
			arrow.Active = false
			arrow.Parent = button
			local buttonicon
			if argstable["Icon"] then
				buttonicon = Instance.new("ImageLabel")
				buttonicon.Active = false
				buttonicon.Size = UDim2.new(0, argstable["IconSize"] - 2, 0, 14)
				buttonicon.BackgroundTransparency = 1
				buttonicon.Position = UDim2.new(0, 10, 0, 13)
				buttonicon.ImageColor3 = Color3.fromRGB(160, 160, 160)
				buttonicon.Image = downloadVapeAsset(argstable["Icon"])
				buttonicon.Name = "ButtonIcon"
				buttonicon.Parent = button
			end
			buttonapi["Enabled"] = false
			buttonapi["Keybind"] = ""
			buttonapi["ToggleButton"] = function(clicked, first)
				if overlaysbkg.Visible == false then
					buttonapi["Enabled"] = not buttonapi["Enabled"]
					if buttonapi["Enabled"] then
						button.BackgroundColor3 = Color3.fromRGB(31, 30, 31)
						buttontext.TextColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Hue"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Sat"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Value"])
						if not first then
							arrow:TweenPosition(UDim2.new(1, -14, 0, 16), Enum.EasingDirection.InOut, Enum.EasingStyle.Quad, 0.2, true)
						end
						if buttonicon then
							buttonicon.ImageColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Hue"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Sat"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Value"])
						end
					else
						button.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
						buttontext.TextColor3 = Color3.fromRGB(160, 160, 160)
						if not first then
							arrow:TweenPosition(UDim2.new(1, -20, 0, 16), Enum.EasingDirection.InOut, Enum.EasingStyle.Quad, 0.2, true)
						end
						if buttonicon then
							buttonicon.ImageColor3 = Color3.fromRGB(200, 200, 200)
						end
					end
					argstable["Function"](buttonapi["Enabled"])
					GuiLibrary["UpdateHudEvent"]:Fire()
				end
			end

			button.MouseButton1Click:Connect(function() buttonapi["ToggleButton"](true) end)
			button.MouseEnter:Connect(function()
				if overlaysbkg.Visible == false then
					if not buttonapi["Enabled"] then
						tweenService:Create(button, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(31, 30, 31)}):Play()
						buttontext.TextColor3 = Color3.fromRGB(200, 200, 200)
						if buttonicon then
							buttonicon.ImageColor3 = Color3.fromRGB(200, 200, 200)
						end
					end
				end
			end)
			button.MouseLeave:Connect(function()
				if overlaysbkg.Visible == false then
					if not buttonapi["Enabled"] then
						tweenService:Create(button, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(26, 25, 26)}):Play()
						buttontext.TextColor3 = Color3.fromRGB(160, 160, 160)
						if buttonicon then
							buttonicon.ImageColor3 = Color3.fromRGB(160, 160, 160)
						end
					end
				end
			end)
			GuiLibrary.ObjectsThatCanBeSaved[argstable["Name"].."Button"] = {["Type"] = "ButtonMain", ["Object"] = button, ["Api"] = buttonapi}

			return buttonapi
		end

		return windowapi
	end

	GuiLibrary["CreateCustomWindow"] = function(argstablemain)
		local windowapi = {}
		local windowtitle = Instance.new("TextButton")
		windowtitle.Text = ""
		windowtitle.AutoButtonColor = false
		windowtitle.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
		windowtitle.Size = UDim2.new(0, 220, 0, 45)
		windowtitle.Position = UDim2.new(0, 223, 0, 6)
		windowtitle.Name = "MainWindow"
		windowtitle.Visible = false
		windowtitle.Name = argstablemain["Name"]
		windowtitle.Parent = hudgui
		local windowshadow = Instance.new("ImageLabel")
		windowshadow.AnchorPoint = Vector2.new(0.5, 0.5)
		windowshadow.Position = UDim2.new(0.5, 0, 0.5, 0)
		windowshadow.Image = downloadVapeAsset("vape/assets/WindowBlur.png")
		windowshadow.BackgroundTransparency = 1
		windowshadow.ZIndex = -1
		windowshadow.Size = UDim2.new(1, 6, 1, 6)
		windowshadow.ImageColor3 = Color3.new(0, 0, 0)
		windowshadow.ScaleType = Enum.ScaleType.Slice
		windowshadow.SliceCenter = Rect.new(10, 10, 118, 118)
		windowshadow.Parent = windowtitle
		local windowicon = Instance.new("ImageLabel")
		windowicon.Size = UDim2.new(0, argstablemain["IconSize"], 0, 16)
		windowicon.Image = downloadVapeAsset(argstablemain["Icon"])
		windowicon.Name = "WindowIcon"
		windowicon.BackgroundTransparency = 1
		windowicon.Position = UDim2.new(0, 12, 0, 12)
		windowicon.Parent = windowtitle
		local windowtext = Instance.new("TextLabel")
		windowtext.Size = UDim2.new(0, 155, 0, 41)
		windowtext.BackgroundTransparency = 1
		windowtext.Name = "WindowTitle"
		windowtext.Position = UDim2.new(0, 36, 0, 1)
		windowtext.TextXAlignment = Enum.TextXAlignment.Left
		windowtext.Font = Enum.Font.Arial
		windowtext.TextSize = 14
		windowtext.Text = (translations[argstablemain["Name"]] ~= nil and translations[argstablemain["Name"]] or argstablemain["Name"])
		windowtext.TextColor3 = Color3.fromRGB(201, 201, 201)
		windowtext.Parent = windowtitle
		local expandbutton = Instance.new("ImageButton")
		expandbutton.AutoButtonColor = false
		expandbutton.Size = UDim2.new(0, 16, 0, 16)
		expandbutton.Image = downloadVapeAsset("vape/assets/PinButton.png")
		expandbutton.ImageColor3 = Color3.fromRGB(84, 84, 84)
		expandbutton.BackgroundTransparency = 1
		expandbutton.Name = "PinButton"
		expandbutton.Position = UDim2.new(1, -47, 0, 13)
		expandbutton.Parent = windowtitle
		local optionsbutton = Instance.new("ImageButton")
		optionsbutton.AutoButtonColor = false
		optionsbutton.Size = UDim2.new(0, 10, 0, 20)
		optionsbutton.Position = UDim2.new(1, -16, 0, 11)
		optionsbutton.Name = "OptionsButton"
		optionsbutton.BackgroundTransparency = 1
		optionsbutton.Image = downloadVapeAsset("vape/assets/MoreButton3.png")
		optionsbutton.Parent = windowtitle
		local children = Instance.new("Frame")
		children.BackgroundTransparency = 1
		children.Size = UDim2.new(0, 220, 0, 300)
		children.Position = UDim2.new(0, 0, 1, 0)
		children.Visible = true
		children.Parent = windowtitle
		local children2 = Instance.new("Frame")
		children2.BackgroundTransparency = 1
		children2.Size = UDim2.new(1, 0, 1, -4)
		children2.Position = UDim2.new(0, 0, 0, 41)
		children2.Visible = false
		children2.Parent = windowtitle
		local windowcorner = Instance.new("UICorner")
		windowcorner.CornerRadius = UDim.new(0, 4)
		windowcorner.Parent = windowtitle
		local uilistlayout = Instance.new("UIListLayout")
		uilistlayout.SortOrder = Enum.SortOrder.LayoutOrder
		uilistlayout.Parent = children2
		uilistlayout:GetPropertyChangedSignal("AbsoluteContentSize"):Connect(function()
			if children2.Visible then
				windowtitle.Size = UDim2.new(0, 220, 0, 45 + uilistlayout.AbsoluteContentSize.Y * (1 / GuiLibrary["MainRescale"].Scale))

			end
		end)
		dragGUI(windowtitle)
		windowapi["Pinned"] = false
		windowapi["RealVis"] = false
		windowapi["Bypass"] = argstablemain["Bypass"]

		windowapi["CheckVis"] = function()
			if windowapi["RealVis"] then
				if clickgui.Visible then
					windowtitle.Visible = true
					windowtext.Visible = true
					windowtitle.Size = UDim2.new(0, 220, 0, 45)
					windowtitle.BackgroundTransparency = 0
					windowicon.Visible = true
					expandbutton.Visible = true
					optionsbutton.Visible = true
				else
					if windowapi["Pinned"] then
						windowtitle.Visible = true
						windowtext.Visible = false
						windowtitle.Size = UDim2.new(0, 220, 0, 0)
						windowtitle.BackgroundTransparency = 1
						windowicon.Visible = false
						expandbutton.Visible = false
						optionsbutton.Visible = false
						children2.Visible = false
						children.Visible = true
					else
						windowtitle.Visible = false
					end
				end
			else
				windowtitle.Visible = false
			end
			windowshadow.Visible = (windowtitle.Size ~= UDim2.new(0, 220, 0, 0))
		end

		windowapi["SetVisible"] = function(value)
			windowapi["RealVis"] = value
			windowapi["CheckVis"]()
		end

		windowapi["ExpandToggle"] = function()
			if children2.Visible then
				children2.Visible = false
				children.Visible = true
				windowtitle.Size = UDim2.new(0, 220, 0, 45)
			else
				children2.Visible = true
				children.Visible = false
				windowtitle.Size = UDim2.new(0, 220, 0, 45 + uilistlayout.AbsoluteContentSize.Y * (1 / GuiLibrary["MainRescale"].Scale))
			end
		end

		windowapi["CreateSlider"] = function(argstable)

			local sliderapi = {}
			local amount2 = #children2:GetChildren()
			local frame = Instance.new("Frame")
			frame.Size = UDim2.new(0, 220, 0, 50)
			frame.BackgroundTransparency = 1
			frame.ClipsDescendants = true
			frame.LayoutOrder = amount2
			frame.Name = argstable["Name"]
			frame.Parent = children2
			local text1 = Instance.new("TextLabel")
			text1.Font = Enum.Font.Arial
			text1.TextXAlignment = Enum.TextXAlignment.Left
			text1.Text = "          "..(translations[argstable["Name"]] ~= nil and translations[argstable["Name"]] or argstable["Name"])
			text1.Size = UDim2.new(1, 0, 0, 25)
			text1.TextColor3 = Color3.fromRGB(160, 160, 160)
			text1.Position = UDim2.new(0, 0, 0, 4)
			text1.BackgroundTransparency = 1
			text1.TextSize = 12
			text1.Parent = frame
			local text2 = Instance.new("TextButton")
			text2.Font = Enum.Font.Arial
			text2.AutoButtonColor = false
			text2.TextXAlignment = Enum.TextXAlignment.Right
			text2.Text = tostring((argstable["Default"] or argstable["Min"])) .. " "..(argstable["Percent"] and "%" or " ").." "
			text2.Size = UDim2.new(0, 40, 0, 25)
			text2.Position = UDim2.new(1, -40, 0, 4)
			text2.TextColor3 = Color3.fromRGB(160, 160, 160)
			text2.BackgroundTransparency = 1
			text2.TextSize = 12
			text2.Parent = frame
			local text3 = Instance.new("TextBox")
			text3.Visible = false
			text3.Font = Enum.Font.Arial
			text3.TextXAlignment = Enum.TextXAlignment.Right
			text3.BackgroundTransparency = 1
			text3.TextColor3 = Color3.fromRGB(160, 160, 160)
			text3.Text = ""
			text3.Position = UDim2.new(1, -40, 0, 4)
			text3.Size = UDim2.new(0, 40, 0, 25)
			text3.TextSize = 12
			text3.Parent = frame
			local textdown = Instance.new("Frame")
			textdown.BackgroundColor3 = Color3.fromRGB(37, 36, 37)
			textdown.Size = UDim2.new(0, 30, 0, 2)
			textdown.Position = UDim2.new(1, -38, 1, -4)
			textdown.Visible = false
			textdown.BorderSizePixel = 0
			textdown.Parent = text2
			local textdown2 = Instance.new("Frame")
			textdown2.BackgroundColor3 = Color3.fromRGB(41, 41, 41)
			textdown2.Size = UDim2.new(0, 30, 0, 2)
			textdown2.Position = UDim2.new(1, -38, 1, -4)
			textdown2.BorderSizePixel = 0
			textdown2.Parent = text3
			local slider1 = Instance.new("Frame")
			slider1.Size = UDim2.new(0, 200, 0, 2)
			slider1.BorderSizePixel = 0
			slider1.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
			slider1.Position = UDim2.new(0, 10, 0, 37)
			slider1.Name = "Slider"
			slider1.Parent = frame
			local slider2 = Instance.new("Frame")
			slider2.BorderSizePixel = 0
			slider2.Size = UDim2.new(math.clamp(((argstable["Default"] or argstable["Min"]) / argstable["Max"]), 0.02, 0.97), 0, 1, 0)
			slider2.BackgroundColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Hue"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Sat"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Value"])
			slider2.Name = "FillSlider"
			slider2.Parent = slider1
			local slider3 = Instance.new("ImageButton")
			slider3.AutoButtonColor = false
			slider3.Size = UDim2.new(0, 24, 0, 16)
			slider3.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
			slider3.BorderSizePixel = 0
			slider3.Image = downloadVapeAsset("vape/assets/SliderButton1.png")
			slider3.Position = UDim2.new(1, -11, 0, -7)
			slider3.Parent = slider2
			slider3.Name = "ButtonSlider"
			sliderapi["Object"] = frame
			sliderapi["Value"] = (argstable["Default"] or argstable["Min"])
			sliderapi["Default"] = (argstable["Default"] or argstable["Min"])
			sliderapi["Min"] = argstable["Min"]
			sliderapi["Max"] = argstable["Max"]
			sliderapi["SetValue"] = function(val)
			--	val = math.clamp(val, argstable["Min"], argstable["Max"])
				sliderapi["Value"] = val
				slider2.Size = UDim2.new(math.clamp((val / argstable["Max"]), 0.02, 0.97), 0, 1, 0)
				text2.Text = sliderapi["Value"] .. ".0 "..(argstable["Percent"] and "%" or " ").." "
				argstable["Function"](val)
			end
			slider3.MouseButton1Down:Connect(function()
				local x,y,xscale,yscale,xscale2 = RelativeXY(slider1, inputService:GetMouseLocation())
				sliderapi["SetValue"](math.floor(argstable["Min"] + ((argstable["Max"] - argstable["Min"]) * xscale)))
				text2.Text = sliderapi["Value"] .. ".0 "..(argstable["Percent"] and "%" or " ").." "
				slider2.Size = UDim2.new(xscale2,0,1,0)
				local move
				local kill
				move = inputService.InputChanged:Connect(function(input)
					if input.UserInputType == Enum.UserInputType.MouseMovement then
						local x,y,xscale,yscale,xscale2 = RelativeXY(slider1, inputService:GetMouseLocation())
						sliderapi["SetValue"](math.floor(argstable["Min"] + ((argstable["Max"] - argstable["Min"]) * xscale)))
						text2.Text = sliderapi["Value"] .. ".0 "..(argstable["Percent"] and "%" or " ").." "
						slider2.Size = UDim2.new(xscale2,0,1,0)
					end
				end)
				kill = inputService.InputEnded:Connect(function(input)
					if input.UserInputType == Enum.UserInputType.MouseButton1 then
						move:Disconnect()
						kill:Disconnect()
					end
				end)
			end)
			text2.MouseEnter:Connect(function()
				textdown.Visible = true
			end)
			text2.MouseLeave:Connect(function()
				textdown.Visible = false
			end)
			text2.MouseButton1Click:Connect(function()
				text3.Visible = true
				text2.Visible = false
				text3:CaptureFocus()
				text3.Text = text2.Text
			end)
			text3.FocusLost:Connect(function(enter)
				text3.Visible = false
				text2.Visible = true
				if enter then
					sliderapi["SetValue"](tonumber(text3.Text))
				end
			end)
			frame.MouseEnter:Connect(function()
				if argstable["HoverText"] and type(argstable["HoverText"]) == "string" then
					hoverbox.Visible = (GuiLibrary["ToggleTooltips"] and hoverbox.TextSize ~= 1)
					local textsize = textService:GetTextSize(argstable["HoverText"], hoverbox.TextSize, hoverbox.Font, Vector2.new(99999, 99999))
					hoverbox.Text = " "..argstable["HoverText"]:gsub("\n", "\n ")
					hoverbox.Size = UDim2.new(0, 8 + textsize.X, 0, textsize.Y + 5)
				end
			end)
			if argstable["HoverText"] and type(argstable["HoverText"]) == "string" then
				frame.MouseMoved:Connect(function(x, y)
					hoverbox.Visible = (GuiLibrary["ToggleTooltips"] and hoverbox.TextSize ~= 1)
					hoverbox.Position = UDim2.new(0, (x + 16) * (1 / GuiLibrary["MainRescale"].Scale), 0,	(y - (hoverbox.Size.Y.Offset / 2) - 26) * (1 / GuiLibrary["MainRescale"].Scale))
				end)
			end
			frame.MouseLeave:Connect(function()
				hoverbox.Visible = false
			end)
			GuiLibrary.ObjectsThatCanBeSaved[argstablemain["Name"]..argstable["Name"].."Slider"] = {["Type"] = "SliderMain", ["Object"] = frame, ["Api"] = sliderapi}
			return sliderapi
		end

		windowapi["CreateTextBox"] = function(argstable)
			local textGuiLibrary = {}
			local amount2 = #children2:GetChildren()
			local frame = Instance.new("Frame")
			frame.Size = UDim2.new(0, 220, 0, 50)
			frame.BackgroundTransparency = 1
			frame.ClipsDescendants = true
			frame.LayoutOrder = amount2
			frame.Name = argstable["Name"]
			frame.Parent = children2
			local frametext = Instance.new("TextLabel")
			frametext.Font = Enum.Font.SourceSans
			frametext.TextSize = 16
			frametext.Size = UDim2.new(1, 0, 0, 18)
			frametext.Position = UDim2.new(0, 0, 0, -3)
			frametext.BackgroundTransparency = 1
			frametext.TextXAlignment = Enum.TextXAlignment.Left
			frametext.TextYAlignment = Enum.TextYAlignment.Top
			frametext.TextColor3 = Color3.fromRGB(180, 180, 180)
			frametext.Text = "   "..argstable["Name"]
			frametext.Parent = frame
			local framebox = Instance.new("TextBox")
			framebox.Size = UDim2.new(0, 200, 0, 29)
			framebox.Position = UDim2.new(0, 10, 0, 16)
			framebox.BackgroundColor3 = Color3.fromRGB(31, 30, 31)
			framebox.Font = Enum.Font.SourceSans
			framebox.PlaceholderText = " Click to set"
			framebox.Text = ""
			framebox.TextColor3 = Color3.new(1, 1, 1)
			framebox.TextXAlignment = Enum.TextXAlignment.Left
			framebox.TextSize = 18
			framebox.PlaceholderColor3 = Color3.fromRGB(180, 180, 180)
			framebox.Parent = frame
			local frameboxcorner = Instance.new("UICorner")
			frameboxcorner.CornerRadius = UDim.new(0, 5)
			frameboxcorner.Parent = framebox
			textGuiLibrary["Object"] = frame
			textGuiLibrary["Value"] = ""
			textGuiLibrary["SetValue"] = function(val, entered)
				textGuiLibrary["Value"] = val
				framebox.Text = val
				if argstable["FocusLost"] and (not entered) then
					argstable["FocusLost"](false)
				end
			end

			framebox.FocusLost:Connect(function(enter)
				textGuiLibrary["SetValue"](framebox.Text, true)
				if argstable["FocusLost"] then
					argstable["FocusLost"](enter)
				end
			end)

			GuiLibrary.ObjectsThatCanBeSaved[argstablemain["Name"]..argstable["Name"].."TextBox"] = {["Type"] = "TextBoxMain", ["Api"] = textGuiLibrary, ["Object"] = frame}

			return textGuiLibrary
		end

		windowapi["CreateCircleWindow"] = function(argstablemain3)
			local buttonapi = {}
			local buttonreturned = {}
			local windowapi3 = {}
			local amount2 = #children2:GetChildren()
			local frame = Instance.new("Frame")
			frame.Size = UDim2.new(0, 220, 0, 49)
			frame.BackgroundTransparency = 1
			frame.LayoutOrder = amount2
			frame.Name = argstablemain["Name"].."TargetFrame"
			frame.Parent = children2
			local drop1 = Instance.new("TextButton")
			drop1.AutoButtonColor = false
			drop1.Size = UDim2.new(0, 198, 0, 39)
			drop1.Position = UDim2.new(0, 11, 0, 5)
			drop1.Parent = frame
			drop1.BorderSizePixel = 0
			drop1.ZIndex = 2
			drop1.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
			drop1.TextSize = 17
			drop1.TextXAlignment = Enum.TextXAlignment.Left
			drop1.Text = ""
			local targeticon = Instance.new("ImageLabel")
			targeticon.Size = UDim2.new(0, 14, 0, 12)
			targeticon.Position = UDim2.new(0, 12, 0, 14)
			targeticon.BackgroundTransparency = 1
			targeticon.Image = downloadVapeAsset("vape/assets/CircleList"..(argstablemain3["Type"] == "Blacklist" and "Blacklist" or "Whitelist")..".png")
			targeticon.ZIndex = 2
			targeticon.Parent = drop1
			local targettext = Instance.new("TextLabel")
			targettext.Size = UDim2.new(0, 190, 1, 0)
			targettext.Position = UDim2.new(0, 29, 0, 0)
			targettext.TextTruncate = Enum.TextTruncate.AtEnd
			targettext.BackgroundTransparency = 1
			targettext.ZIndex = 2
			targettext.TextSize = 17
			targettext.RichText = true
			targettext.TextColor3 = Color3.new(205, 205, 205)
			targettext.Text = "  "..argstablemain3["Name"].." \n "..'<font color="rgb(151, 151, 151)">None</font>'
			targettext.Font = Enum.Font.SourceSans
			targettext.TextXAlignment = Enum.TextXAlignment.Left
			targettext.Parent = drop1
			local thing = Instance.new("Frame")
			thing.Size = UDim2.new(1, 2, 1, 2)
			thing.BorderSizePixel = 0
			thing.Position = UDim2.new(0, -1, 0, -1)
			thing.ZIndex = 1
			thing.BackgroundColor3 = Color3.fromRGB(38, 37, 38)
			thing.Parent = drop1
			local uicorner = Instance.new("UICorner")
			uicorner.CornerRadius = UDim.new(0, 4)
			uicorner.Parent = drop1
			local uicorner2 = Instance.new("UICorner")
			uicorner2.CornerRadius = UDim.new(0, 4)
			uicorner2.Parent = thing
			local windowtitle = Instance.new("TextButton")
			windowtitle.Text = ""
			windowtitle.AutoButtonColor = false
			windowtitle.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
			windowtitle.Size = UDim2.new(0, 220, 0, 41)
			windowtitle.Position = UDim2.new(1, 1, 0, 0)
			windowtitle.Name = "CircleWindow"
			windowtitle.Visible = false
			windowtitle.ZIndex = 3
			windowtitle.Parent = clickgui
			frame:GetPropertyChangedSignal("AbsolutePosition"):Connect(function()
				windowtitle.Position = UDim2.new(0, frame.Size.X.Offset + frame.AbsolutePosition.X + 2, 0, frame.AbsolutePosition.Y)
			end)
			local windowshadow = Instance.new("ImageLabel")
			windowshadow.AnchorPoint = Vector2.new(0.5, 0.5)
			windowshadow.Position = UDim2.new(0.5, 0, 0.5, 0)
			windowshadow.Image = downloadVapeAsset("vape/assets/WindowBlur.png")
			windowshadow.BackgroundTransparency = 1
			windowshadow.ZIndex = -1
			windowshadow.Size = UDim2.new(1, 6, 1, 6)
			windowshadow.ImageColor3 = Color3.new(0, 0, 0)
			windowshadow.ScaleType = Enum.ScaleType.Slice
			windowshadow.SliceCenter = Rect.new(10, 10, 118, 118)
			windowshadow.Parent = windowtitle
			local windowicon = Instance.new("ImageLabel")
			windowicon.Size = UDim2.new(0, 18, 0, 16)
			windowicon.Image = downloadVapeAsset("vape/assets/CircleList"..(argstablemain3["Type"] == "Blacklist" and "Blacklist" or "Whitelist")..".png")
			windowicon.ImageColor3 = Color3.fromRGB(200, 200, 200)
			windowicon.ZIndex = 3
			windowicon.Name = "WindowIcon"
			windowicon.BackgroundTransparency = 1
			windowicon.Position = UDim2.new(0, 10, 0, 13)
			windowicon.Parent = windowtitle
			local windowtext = Instance.new("TextLabel")
			windowtext.Size = UDim2.new(0, 155, 0, 41)
			windowtext.BackgroundTransparency = 1
			windowtext.Name = "WindowTitle"
			windowtext.Position = UDim2.new(0, 36, 0, 0)
			windowtext.ZIndex = 3
			windowtext.TextXAlignment = Enum.TextXAlignment.Left
			windowtext.Font = Enum.Font.SourceSans
			windowtext.TextSize = 17
			windowtext.Text = argstablemain3["Name"]
			windowtext.TextColor3 = Color3.fromRGB(200, 200, 200)
			windowtext.Parent = windowtitle
			local children = Instance.new("Frame")
			children.BackgroundTransparency = 1
			children.Size = UDim2.new(1, 0, 1, -4)
			children.ZIndex = 3
			children.Position = UDim2.new(0, 0, 0, 41)
			children.Visible = true
			children.Parent = windowtitle
			local windowcorner = Instance.new("UICorner")
			windowcorner.CornerRadius = UDim.new(0, 4)
			windowcorner.Parent = windowtitle
			local uilistlayout = Instance.new("UIListLayout")
			uilistlayout.SortOrder = Enum.SortOrder.LayoutOrder
			uilistlayout.Parent = children
			uilistlayout:GetPropertyChangedSignal("AbsoluteContentSize"):Connect(function()
				windowtitle.Size = UDim2.new(0, 220, 0, 45 + uilistlayout.AbsoluteContentSize.Y)
			end)

			windowapi3["UpdateIgnore"] = function()
				local str = ""
				for i,v in pairs(buttonreturned["CircleList"]["ObjectList"]) do
					local enabled = buttonreturned["CircleList"]["ObjectListEnabled"][i]
					if enabled then
						str = (str == "" and v or str..", "..v)
					end
				end
				if str == "" then
					str = "None"
				end
				if argstablemain3["UpdateFunction"] then
					argstablemain3["UpdateFunction"]()
				end
				targettext.Text = "  "..argstablemain3["Name"].." \n "..'<font color="rgb(151, 151, 151)">'..str..'</font>'
			end

			windowapi3["CreateCircleTextList"] = function(argstable)
				local textGuiLibrary = {}
				local amount = #children:GetChildren()
				local frame = Instance.new("Frame")
				frame.Size = UDim2.new(0, 220, 0, 40)
				frame.BackgroundTransparency = 1
				frame.ZIndex = 5
				frame.ClipsDescendants = true
				frame.LayoutOrder = amount
				frame.Name = argstable["Name"]
				frame.Parent = children
				local textboxbkg = Instance.new("ImageLabel")
				textboxbkg.BackgroundTransparency = 1
				textboxbkg.Name = "AddBoxBKG"
				textboxbkg.Size = UDim2.new(0, (argstable["Name"] == "ProfilesList" and 150 or 200), 0, 31)
				textboxbkg.Position = UDim2.new(0, 10, 0, 5)
				textboxbkg.ZIndex = 6
				textboxbkg.ClipsDescendants = true
				textboxbkg.Image = downloadVapeAsset((argstable["Name"] == "ProfilesList" and "vape/assets/TextBoxBKG2.png" or "vape/assets/TextBoxBKG.png"))
				textboxbkg.Parent = frame
				local textbox = Instance.new("TextBox")
				textbox.Size = UDim2.new(0, 159, 1, 0)
				textbox.Position = UDim2.new(0, 11, 0, 0)
				textbox.ZIndex = 6
				textbox.TextXAlignment = Enum.TextXAlignment.Left
				textbox.Name = "AddBox"
				textbox.BackgroundTransparency = 1
				textbox.TextColor3 = Color3.new(1, 1, 1)
				textbox.PlaceholderColor3 = Color3.fromRGB(200, 200, 200)
				textbox.Font = Enum.Font.SourceSans
				textbox.Text = ""
				textbox.PlaceholderText = "Add entry..."
				textbox.TextSize = 17
				textbox.Parent = textboxbkg
				local addbutton = Instance.new("ImageButton")
				addbutton.BorderSizePixel = 0
				addbutton.Name = "AddButton"
				addbutton.ZIndex = 6
				addbutton.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
				addbutton.Position = UDim2.new(0, (argstable["Name"] == "ProfilesList" and 124 or 174), 0, 8)
				addbutton.AutoButtonColor = false
				addbutton.Size = UDim2.new(0, 16, 0, 16)
				addbutton.ImageColor3 = argstable["Color"]
				addbutton.Image = downloadVapeAsset("vape/assets/AddItem.png")
				addbutton.Parent = textboxbkg
				local scrollframebkg = Instance.new("Frame")
				scrollframebkg.ZIndex = 5
				scrollframebkg.Name = "ScrollingFrameBKG"
				scrollframebkg.Size = UDim2.new(0, 220, 0, 3)
				scrollframebkg.BackgroundTransparency = 1
				scrollframebkg.LayoutOrder = amount
				scrollframebkg.Parent = children
				local scrollframe = Instance.new("ScrollingFrame")
				scrollframe.ZIndex = 5
				scrollframe.Size = UDim2.new(0, 200, 0, 3)
				scrollframe.Position = UDim2.new(0, 10, 0, 0)
				scrollframe.BackgroundTransparency = 1
				scrollframe.ScrollBarThickness = 0
				scrollframe.ScrollBarImageColor3 = Color3.new(0, 0, 0)
				scrollframe.LayoutOrder = amount
				scrollframe.Parent = scrollframebkg
				local uilistlayout3 = Instance.new("UIListLayout")
				uilistlayout3.Padding = UDim.new(0, 3)
				uilistlayout3.Parent = scrollframe
				uilistlayout3:GetPropertyChangedSignal("AbsoluteContentSize"):Connect(function()
					scrollframe.CanvasSize = UDim2.new(0, 0, 0, uilistlayout3.AbsoluteContentSize.Y)
					scrollframe.Size = UDim2.new(0, 220, 0, math.clamp(uilistlayout3.AbsoluteContentSize.Y, 1, 105))
					scrollframebkg.Size = UDim2.new(0, 220, 0, math.clamp(uilistlayout3.AbsoluteContentSize.Y, 1, 105) + 3)
				end)

				textGuiLibrary["Object"] = frame
				textGuiLibrary["ScrollingObject"] = scrollframebkg
				textGuiLibrary["ObjectList"] = {}
				textGuiLibrary["ObjectListEnabled"] = {}
				local hoveredover = {}
				textGuiLibrary["RefreshValues"] = function(tab, tab2)
					textGuiLibrary["ObjectList"] = tab
					if tab2 then
						textGuiLibrary["ObjectListEnabled"] = tab2
					end
					windowapi3["UpdateIgnore"]()
					for i2,v2 in pairs(scrollframe:GetChildren()) do
						if v2:IsA("TextButton") then v2:Remove() end
					end
					for i,v in pairs(textGuiLibrary["ObjectList"]) do
						local objenabled = textGuiLibrary["ObjectListEnabled"][i]
						local itemframe = Instance.new("TextButton")
						itemframe.Size = UDim2.new(0, 200, 0, 33)
						itemframe.Text = ""
						itemframe.AutoButtonColor = false
						itemframe.BackgroundColor3 = (hoveredover[i] and Color3.fromRGB(26, 25, 26) or Color3.fromRGB(31, 30, 31))
						itemframe.BorderSizePixel = 0
						itemframe.ZIndex = 5
						itemframe.Parent = scrollframe
						local itemcorner = Instance.new("UICorner")
						itemcorner.CornerRadius = UDim.new(0, 6)
						itemcorner.Parent = itemframe
						local itemtext = Instance.new("TextLabel")
						itemtext.BackgroundTransparency = 1
						itemtext.Size = UDim2.new(0, 157, 0, 33)
						itemtext.Name = "ItemText"
						itemtext.ZIndex = 5
						itemtext.Position = UDim2.new(0, 36, 0, 0)
						itemtext.Font = Enum.Font.SourceSans
						itemtext.TextSize = 17
						itemtext.Text = v
						itemtext.TextXAlignment = Enum.TextXAlignment.Left
						itemtext.TextColor3 = (objenabled and Color3.fromRGB(160, 160, 160) or Color3.fromRGB(90, 90, 90))
						itemtext.Parent = itemframe
						local friendcircle = Instance.new("Frame")
						friendcircle.Size = UDim2.new(0, 10, 0, 10)
						friendcircle.Name = "FriendCircle"
						friendcircle.ZIndex = 5
						friendcircle.BackgroundColor3 = (objenabled and argstable["Color"] or Color3.fromRGB(120, 120, 120))
						friendcircle.BorderSizePixel = 0
						friendcircle.Position = UDim2.new(0, 10, 0, 13)
						friendcircle.Parent = itemframe
						local friendcorner = Instance.new("UICorner")
						friendcorner.CornerRadius = UDim.new(0, 8)
						friendcorner.Parent = friendcircle
						local friendcircle2 = friendcircle:Clone()
						friendcircle2.Size = UDim2.new(0, 8, 0, 8)
						friendcircle2.BackgroundColor3 = Color3.fromRGB(31, 31, 31)
						friendcircle2.Position = UDim2.new(0, 1, 0, 1)
						friendcircle2.Visible = not objenabled
						friendcircle2.Parent = friendcircle
						itemframe:GetPropertyChangedSignal("BackgroundColor3"):Connect(function()
							friendcircle2.BackgroundColor3 = itemframe.BackgroundColor3
						end)
						itemframe.MouseEnter:Connect(function()
							itemframe.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
							hoveredover[i] = true
						end)
						itemframe.MouseLeave:Connect(function()
							itemframe.BackgroundColor3 = Color3.fromRGB(31, 30, 31)
							hoveredover[i] = nil
						end)
						itemframe.MouseButton1Click:Connect(function()
							textGuiLibrary["ObjectListEnabled"][i] = not textGuiLibrary["ObjectListEnabled"][i]
							textGuiLibrary["RefreshValues"](textGuiLibrary["ObjectList"])
						end)
						itemframe.MouseButton2Click:Connect(function()
							textGuiLibrary["ObjectListEnabled"][i] = not textGuiLibrary["ObjectListEnabled"][i]
							textGuiLibrary["RefreshValues"](textGuiLibrary["ObjectList"])
						end)
						local deletebutton = Instance.new("ImageButton")
						deletebutton.Size = UDim2.new(0, 6, 0, 6)
						deletebutton.BackgroundTransparency = 1
						deletebutton.AutoButtonColor = false
						deletebutton.ZIndex = 5
						deletebutton.Image = downloadVapeAsset("vape/assets/AddRemoveIcon1.png")
						deletebutton.Position = UDim2.new(1, -16, 0, 14)
						deletebutton.Parent = itemframe
						deletebutton.MouseButton1Click:Connect(function()
							table.remove(textGuiLibrary["ObjectList"], i)
							textGuiLibrary["ObjectListEnabled"][i] = nil
							textGuiLibrary["RefreshValues"](textGuiLibrary["ObjectList"])
							if argstable["RemoveFunction"] then
								argstable["RemoveFunction"](i, v)
							end
						end)
					end
				end

				GuiLibrary.ObjectsThatCanBeSaved[argstablemain["Name"]..argstable["Name"].."TextCircleList"] = {["Type"] = "TextCircleList", ["Api"] = textGuiLibrary}
				local function AddToList()
					local num = #textGuiLibrary["ObjectList"] + 1
					textGuiLibrary["ObjectList"][num] = textbox.Text
					textGuiLibrary["ObjectListEnabled"][num] = true
					textGuiLibrary["RefreshValues"](textGuiLibrary["ObjectList"])
					if argstable["AddFunction"] then
						argstable["AddFunction"](textbox.Text)
					end
                    textbox.Text = ""
                end
                addbutton.MouseButton1Click:Connect(AddToList)
                textbox.FocusLost:Connect(function(enter)
                    if enter then
                        AddToList()
                        textbox:CaptureFocus()
                    end
                end)
				return textGuiLibrary
			end

			--[[windowapi3["CreateButton"] = function(argstable)
				local buttonapi = {}
				local amount = #children:GetChildren()
				local buttontext = Instance.new("TextButton")
				buttontext.Name = argstablemain["Name"]..argstable["Name"].."TargetButton"
				buttontext.LayoutOrder = amount
				buttontext.AutoButtonColor = false
				buttontext.Size = UDim2.new(0, 45, 0, 29)
				buttontext.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
				buttontext.Active = false
				buttontext.Text = ""
				buttontext.ZIndex = 4
				buttontext.Font = Enum.Font.SourceSans
				buttontext.TextXAlignment = Enum.TextXAlignment.Left
				buttontext.Position = argstable["Position"]
				buttontext.Parent = buttonframeholder
				local buttonbkg = Instance.new("Frame")
				buttonbkg.BackgroundColor3 = Color3.fromRGB(38, 37, 38)
				buttonbkg.Size = UDim2.new(0, 47, 0, 31)
				buttonbkg.Position = argstable["Position"] - UDim2.new(0, 1, 0, 1)
				buttonbkg.ZIndex = 3
				buttonbkg.Parent = buttonframeholder
				local buttonimage = Instance.new("ImageLabel")
				buttonimage.BackgroundTransparency = 1
				buttonimage.Position = UDim2.new(0, 14, 0, 7)
				buttonimage.Size = UDim2.new(0, argstable["IconSize"], 0, 16)
				buttonimage.Image = downloadVapeAsset(argstable["Icon"])
				buttonimage.ImageColor3 = Color3.fromRGB(121, 121, 121)
				buttonimage.ZIndex = 5
				buttonimage.Active = false
				buttonimage.Parent = buttontext
				local buttontexticon = Instance.new("ImageLabel")
				buttontexticon.Size = UDim2.new(0, argstable["IconSize"] - 3, 0, 12)
				buttontexticon.Image = downloadVapeAsset(argstable["Icon"])
				buttontexticon.LayoutOrder = amount
				buttontexticon.ZIndex = 4
				buttontexticon.BackgroundTransparency = 1
				buttontexticon.Visible = false
				buttontexticon.Parent = targetframe
				local buttonround1 = Instance.new("UICorner")
				buttonround1.CornerRadius = UDim.new(0, 5)
				buttonround1.Parent = buttontext
				local buttonround2 = Instance.new("UICorner")
				buttonround2.CornerRadius = UDim.new(0, 5)
				buttonround2.Parent = buttonbkg
				buttonapi["Enabled"] = false
				buttonapi["Default"] = argstable["Default"]

				buttonapi["ToggleButton"] = function(toggle, frist)
					buttonapi["Enabled"] = toggle
					buttontexticon.Visible = toggle
					if buttonapi["Enabled"] then
						if not first then
							tweenService:Create(buttontext, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Hue"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Sat"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Value"])}):Play()
						else
							buttontext.BackgroundColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Hue"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Sat"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Value"])
						end
					else
						if not first then
							tweenService:Create(buttontext, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(26, 25, 26)}):Play()
						else
							buttontext.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
						end
					end
					buttonimage.ImageColor3 = (buttonapi["Enabled"] and Color3.new(1, 1, 1) or Color3.fromRGB(121, 121, 121))
					argstable["Function"](buttonapi["Enabled"])
				end

				if argstable["Default"] then
					buttonapi["ToggleButton"](argstable["Default"], true)
				end
				buttontext.MouseButton1Click:Connect(function() buttonapi["ToggleButton"](not buttonapi["Enabled"], false) end)
				GuiLibrary.ObjectsThatCanBeSaved[argstablemain["Name"]..argstable["Name"].."TargetButton"] = {["Type"] = "TargetButton", ["Object"] = buttontext, ["Api"] = buttonapi}
				return buttonapi
			end]]
			buttonreturned["Object"] = frame
			buttonreturned["CircleList"] = windowapi3.CreateCircleTextList({
				Name = "CircleList",
				Color = (argstablemain3["Type"] == "Blacklist" and Color3.fromRGB(250, 50, 56) or Color3.fromRGB(5, 134, 105))
			})

			drop1.MouseButton1Click:Connect(function()
				windowtitle.Visible = not windowtitle.Visible
				if not windowtitle.Visible then
					tweenService:Create(thing, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(107, 107, 107)}):Play()
				end
			end)
			drop1.MouseEnter:Connect(function()
				if not windowtitle.Visible then
					tweenService:Create(thing, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(107, 107, 107)}):Play()
				end
			end)
			drop1.MouseLeave:Connect(function()
				if not windowtitle.Visible then
					tweenService:Create(thing, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(38, 37, 38)}):Play()
				end
			end)

			GuiLibrary.ObjectsThatCanBeSaved[argstablemain["Name"].."CircleListFrame"] = {["Type"] = "CircleListFrame", ["Object"] = frame, ["Object2"] = windowtitle, ["Api"] = buttonreturned}

			return buttonreturned
		end

		windowapi["CreateDropdown"] = function(argstable)
			local dropGuiLibrary = {}
			local list = argstable["List"]
			local amount2 = #children2:GetChildren()
			local frame = Instance.new("Frame")
			frame.Size = UDim2.new(0, 220, 0, 40)
			frame.BackgroundTransparency = 1
			frame.LayoutOrder = amount2
			frame.Name = argstable["Name"]
			frame.Parent = children2
			local drop1 = Instance.new("TextButton")
			drop1.AutoButtonColor = false
			drop1.Size = UDim2.new(0, 198, 0, 29)
			drop1.Position = UDim2.new(0, 11, 0, 5)
			drop1.Parent = frame
			drop1.BorderSizePixel = 0
			drop1.ZIndex = 2
			drop1.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
			drop1.TextSize = 14
			drop1.TextXAlignment = Enum.TextXAlignment.Left
			drop1.TextColor3 = Color3.fromRGB(160, 160, 160)
			drop1.Text = "         "..(translations[argstable["Name"]] ~= nil and translations[argstable["Name"]] or argstable["Name"]).." - "..(list ~= {} and list[1] or "")
			drop1.TextTruncate = Enum.TextTruncate.AtEnd
			drop1.Font = Enum.Font.Arial
			local expandbutton2 = Instance.new("ImageLabel")
			expandbutton2.Active = false
			expandbutton2.Size = UDim2.new(0, 9, 0, 4)
			expandbutton2.Image = downloadVapeAsset("vape/assets/DownArrow.png")
			expandbutton2.ZIndex = 5
			expandbutton2.Position = UDim2.new(1, -19, 1, -16)
			expandbutton2.Name = "ExpandButton2"
			expandbutton2.BackgroundTransparency = 0
			expandbutton2.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
			expandbutton2.BorderSizePixel = 0
			expandbutton2.Parent = drop1
			local drop2 = drop1:Clone()
			drop2.Name = "MainButton"
			drop2.Position = UDim2.new(0, 0, 0, 0)
			drop2.ZIndex = 4
			drop2.BackgroundTransparency = 1
			drop1:GetPropertyChangedSignal("Text"):Connect(function()
				drop2.Text = drop1.Text
			end)
			drop2.ExpandButton2.Image = downloadVapeAsset("vape/assets/UpArrow.png")
			local thing = Instance.new("Frame")
			thing.Size = UDim2.new(1, 2, 1, 2)
			thing.BorderSizePixel = 0
			thing.Position = UDim2.new(0, -1, 0, -1)
			thing.ZIndex = 1
			thing.BackgroundColor3 = Color3.fromRGB(34, 34, 34)
			thing.Parent = drop1
			local uicorner = Instance.new("UICorner")
			uicorner.CornerRadius = UDim.new(0, 6)
			uicorner.Parent = drop1
			local uicorner2 = Instance.new("UICorner")
			uicorner2.CornerRadius = UDim.new(0, 6)
			uicorner2.Parent = thing
			local dropframe = Instance.new("Frame")
			dropframe.ZIndex = 3
			dropframe.Parent = drop1
			dropframe.Active = true
			dropframe.Position = UDim2.new(0, 0, 0, 0)
			dropframe.Size = UDim2.new(1, 0, 0, 0)
			dropframe.BackgroundTransparency = 0
			dropframe.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
			dropframe.Visible = false
			local uicorner3 = Instance.new("UICorner")
			uicorner3.CornerRadius = UDim.new(0, 6)
			uicorner3.Parent = dropframe
			local thing2 = thing:Clone()
			thing2.BackgroundColor3 = Color3.fromRGB(53, 52, 53)
			thing2.Parent = dropframe
			drop2.Parent = dropframe
			drop2.MouseButton1Click:Connect(function()
				dropframe.Visible = not dropframe.Visible
				hoverbox.TextSize = (dropframe.Visible and 0 or 15)
				--children.CanvasSize = UDim2.new(0, 0, 0, uilistlayout2.AbsoluteContentSize.Y + (dropframe.Visible and #dropframe:GetChildren() * 12 or 0) + 10)
			end)
			drop1.MouseButton1Click:Connect(function()
				dropframe.Visible = not dropframe.Visible
				hoverbox.TextSize = (dropframe.Visible and 0 or 15)
				--children.CanvasSize = UDim2.new(0, 0, 0, uilistlayout2.AbsoluteContentSize.Y + (dropframe.Visible and #dropframe:GetChildren() * 12 or 0) + 10)
			end)
			drop1.MouseEnter:Connect(function()
				thing.BackgroundColor3 = Color3.fromRGB(49, 48, 49)
			end)
			drop1.MouseLeave:Connect(function()
				thing.BackgroundColor3 = Color3.fromRGB(34, 34, 34)
			end)
			frame.MouseEnter:Connect(function()
				if argstable["HoverText"] and type(argstable["HoverText"]) == "string" then
					hoverbox.Visible = (GuiLibrary["ToggleTooltips"] and hoverbox.TextSize ~= 1)
					local textsize = textService:GetTextSize(argstable["HoverText"], hoverbox.TextSize, hoverbox.Font, Vector2.new(99999, 99999))
					hoverbox.Text = " "..argstable["HoverText"]:gsub("\n", "\n ")
					hoverbox.Size = UDim2.new(0, 8 + textsize.X, 0, textsize.Y + 5)
				end
			end)
			if argstable["HoverText"] and type(argstable["HoverText"]) == "string" then
				frame.MouseMoved:Connect(function(x, y)
					hoverbox.Visible = (GuiLibrary["ToggleTooltips"] and hoverbox.TextSize ~= 1)
					hoverbox.Position = UDim2.new(0, (x + 16) * (1 / GuiLibrary["MainRescale"].Scale), 0,	(y - (hoverbox.Size.Y.Offset / 2) - 26) * (1 / GuiLibrary["MainRescale"].Scale))
				end)
			end
			frame.MouseLeave:Connect(function()
				hoverbox.Visible = false
			end)
			local placeholder = 0
			dropGuiLibrary["Value"] = (list ~= {} and list[1] or "")
			dropGuiLibrary["Default"] = dropGuiLibrary["Value"]
			dropGuiLibrary["Object"] = frame
			dropGuiLibrary["List"] = list
			dropGuiLibrary["UpdateList"] = function(val)
				placeholder = 25
				list = val
				dropGuiLibrary["List"] = val
				if not table.find(list, dropGuiLibrary["Value"]) then
					dropGuiLibrary["Value"] = list[1]
					drop1.Text = "         "..(translations[argstable["Name"]] ~= nil and translations[argstable["Name"]] or argstable["Name"]).." - "..list[1]
					dropframe.Visible = false
					argstable["Function"](list[1])
				end
				for del1, del2 in pairs(dropframe:GetChildren()) do if del2:IsA("TextButton") and del2.Name ~= "MainButton" then del2:Remove() end end
				for numbe, listobj in pairs(val) do
					if listobj == dropGuiLibrary["Value"] then continue end
					local drop2 = Instance.new("TextButton")
					dropframe.Size = UDim2.new(0, 198, 0, placeholder + 23)
					drop2.Text = "   "..listobj
					drop2.LayoutOrder = numbe
					drop2.TextColor3 = Color3.fromRGB(160, 160, 160)
					drop2.AutoButtonColor = false
					drop2.TextXAlignment = Enum.TextXAlignment.Left
					drop2.TextYAlignment = Enum.TextYAlignment.Top
					drop2.Size = UDim2.new(0, 198, 0, 19)
					drop2.Position = UDim2.new(0, 0, 0, placeholder)
					drop2.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
					drop2.Font = Enum.Font.SourceSans
					drop2.TextSize = 17
					drop2.ZIndex = 4
					drop2.BorderSizePixel = 0
					drop2.Name = listobj
					drop2.Parent = dropframe
					drop2.MouseButton1Click:Connect(function()
						hoverbox.TextSize = 15
						dropGuiLibrary["Value"] = listobj
						drop1.Text = "         "..(translations[argstable["Name"]] ~= nil and translations[argstable["Name"]] or argstable["Name"]).." - "..listobj
						dropframe.Visible = false
						--children.CanvasSize = UDim2.new(0, 0, 0, uilistlayout2.AbsoluteContentSize.Y + (dropframe.Visible and #dropframe:GetChildren() * 12 or 0) + 10)
						argstable["Function"](listobj)
						dropGuiLibrary["UpdateList"](list)
						GuiLibrary["UpdateHudEvent"]:Fire()
					end)
					drop2.MouseEnter:Connect(function()
						drop2.BackgroundColor3 = Color3.fromRGB(31, 30, 31)
					end)
					drop2.MouseLeave:Connect(function()
						drop2.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
					end)
					placeholder = placeholder + 19
				end
			end
			dropGuiLibrary["SetValue"] = function(listobj)
				dropGuiLibrary["Value"] = listobj
				drop1.Text = "         "..(translations[argstable["Name"]] ~= nil and translations[argstable["Name"]] or argstable["Name"]).." - "..listobj
				dropframe.Visible = false
				argstable["Function"](listobj)
				dropGuiLibrary["UpdateList"](list)
			end
			dropGuiLibrary["UpdateList"](list)
			GuiLibrary.ObjectsThatCanBeSaved[argstablemain["Name"]..argstable["Name"].."Dropdown"] = {["Type"] = "DropdownMain", ["Object"] = frame, ["Api"] = dropGuiLibrary}

			return dropGuiLibrary
		end

		windowapi["CreateColorSlider"] = function(argstable)
			local min, max = 0, 1
			local def = math.floor((min + max) / 2)
			local defsca = (def - min)/(max - min)
			local sliderapi = {}
			local amount2 = #children2:GetChildren()
			local frame = Instance.new("Frame")
			frame.Size = UDim2.new(0, 220, 0, 50)
			frame.BackgroundTransparency = 1
			frame.LayoutOrder = amount2
			frame.Name = argstable["Name"]
			frame.Parent = children2
			local text1 = Instance.new("TextLabel")
			text1.Font = Enum.Font.Arial
			text1.TextXAlignment = Enum.TextXAlignment.Left
			text1.Text = "          "..(translations[argstable["Name"]] ~= nil and translations[argstable["Name"]] or argstable["Name"])
			text1.Size = UDim2.new(1, 0, 0, 25)
			text1.TextColor3 = Color3.fromRGB(160, 160, 160)
			text1.Position = UDim2.new(0, 0, 0, 4)
			text1.BackgroundTransparency = 1
			text1.TextSize = 12
			text1.Parent = frame
			local text2 = Instance.new("Frame")
			text2.Size = UDim2.new(0, 12, 0, 12)
			text2.Position = UDim2.new(1, -22, 0, 9)
			text2.BackgroundColor3 = Color3.fromHSV(0.44, 1, 1)
			text2.Parent = frame
			local uicorner4 = Instance.new("UICorner")
			uicorner4.CornerRadius = UDim.new(0, 4)
			uicorner4.Parent = text2
			local slider1 = Instance.new("TextButton")
			slider1.AutoButtonColor = false
			slider1.Text = ""
			slider1.Size = UDim2.new(0, 200, 0, 2)
			slider1.BorderSizePixel = 0
			slider1.BackgroundColor3 = Color3.new(1, 1, 1)
			slider1.Position = UDim2.new(0, 10, 0, 32)
			slider1.Name = "Slider"
			slider1.Parent = frame
			local uigradient = Instance.new("UIGradient")
			uigradient.Color = ColorSequence.new({ColorSequenceKeypoint.new(0, Color3.fromHSV(0, 1, 1)), ColorSequenceKeypoint.new(0.1, Color3.fromHSV(0.1, 1, 1)), ColorSequenceKeypoint.new(0.2, Color3.fromHSV(0.2, 1, 1)), ColorSequenceKeypoint.new(0.3, Color3.fromHSV(0.3, 1, 1)), ColorSequenceKeypoint.new(0.4, Color3.fromHSV(0.4, 1, 1)), ColorSequenceKeypoint.new(0.5, Color3.fromHSV(0.5, 1, 1)), ColorSequenceKeypoint.new(0.6, Color3.fromHSV(0.6, 1, 1)), ColorSequenceKeypoint.new(0.7, Color3.fromHSV(0.7, 1, 1)), ColorSequenceKeypoint.new(0.8, Color3.fromHSV(0.8, 1, 1)), ColorSequenceKeypoint.new(0.9, Color3.fromHSV(0.9, 1, 1)), ColorSequenceKeypoint.new(1, Color3.fromHSV(1, 1, 1))})
			uigradient.Parent = slider1
			local slider3 = Instance.new("ImageButton")
			slider3.AutoButtonColor = false
			slider3.Size = UDim2.new(0, 24, 0, 16)
			slider3.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
			slider3.BorderSizePixel = 0
			slider3.Image = downloadVapeAsset("vape/assets/SliderButton1.png")
			slider3.Position = UDim2.new(0.44, -11, 0, -7)
			slider3.Parent = slider1
			slider3.Name = "ButtonSlider"
			sliderapi["Value"] = 0.44
			sliderapi["RainbowValue"] = false
			sliderapi["Object"] = frame
			sliderapi["SetValue"] = function(val)
				val = math.clamp(val, min, max)
				text2.BackgroundColor3 = Color3.fromHSV(val, 1, 1)
				sliderapi["Value"] = val
				slider3.Position = UDim2.new(math.clamp(val, 0.02, 0.95), -9, 0, -7)
				argstable["Function"](val)
			end
			sliderapi["SetRainbow"] = function(val)
				sliderapi["RainbowValue"] = val
				if sliderapi["RainbowValue"] then
					table.insert(GuiLibrary.RainbowSliders, sliderapi)
				else
					table.remove(GuiLibrary.RainbowSliders, table.find(GuiLibrary.RainbowSliders, sliderapi))
				end
			end
			slider1.MouseButton1Down:Connect(function()
				task.spawn(function()
					click = true
					task.wait(0.3)
					click = false
				end)
				if click then
					sliderapi["SetRainbow"](not sliderapi["RainbowValue"])
				end
				local x,y,xscale,yscale,xscale2 = RelativeXY(slider1, inputService:GetMouseLocation())
				sliderapi["SetValue"](min + ((max - min) * xscale))
				slider3.Position = UDim2.new(math.clamp(xscale2, 0.02, 0.95), -9, 0, -7)
				local move
				local kill
				move = inputService.InputChanged:Connect(function(input)
					if input.UserInputType == Enum.UserInputType.MouseMovement then
						local x,y,xscale,yscale,xscale2 = RelativeXY(slider1, inputService:GetMouseLocation())
						sliderapi["SetValue"](min + ((max - min) * xscale))
						slider3.Position = UDim2.new(math.clamp(xscale2, 0.02, 0.95), -9, 0, -7)
					end
				end)
				kill = inputService.InputEnded:Connect(function(input)
					if input.UserInputType == Enum.UserInputType.MouseButton1 then
						move:Disconnect()
						kill:Disconnect()
					end
				end)
			end)
			local clicktick = tick()
			slider3.MouseButton1Down:Connect(function()
				if clicktick > tick() then
					sliderapi["SetRainbow"](not sliderapi["RainbowValue"])
				end
				clicktick = tick() + 0.3
				local x,y,xscale,yscale,xscale2 = RelativeXY(slider1, inputService:GetMouseLocation())
				sliderapi["SetValue"](min + ((max - min) * xscale))
				slider3.Position = UDim2.new(math.clamp(xscale2, 0.02, 0.95), -9, 0, -7)
				local move
				local kill
				move = inputService.InputChanged:Connect(function(input)
					if input.UserInputType == Enum.UserInputType.MouseMovement then
						local x,y,xscale,yscale,xscale2 = RelativeXY(slider1, inputService:GetMouseLocation())
						sliderapi["SetValue"](min + ((max - min) * xscale))
						slider3.Position = UDim2.new(math.clamp(xscale2, 0.02, 0.95), -9, 0, -7)
					end
				end)
				kill = inputService.InputEnded:Connect(function(input)
					if input.UserInputType == Enum.UserInputType.MouseButton1 then
						move:Disconnect()
						kill:Disconnect()
					end
				end)
			end)
			frame.MouseEnter:Connect(function()
				if argstable["HoverText"] and type(argstable["HoverText"]) == "string" then
					hoverbox.Visible = (GuiLibrary["ToggleTooltips"] and hoverbox.TextSize ~= 1)
					local textsize = textService:GetTextSize(argstable["HoverText"], hoverbox.TextSize, hoverbox.Font, Vector2.new(99999, 99999))
					hoverbox.Text = " "..argstable["HoverText"]:gsub("\n", "\n ")
					hoverbox.Size = UDim2.new(0, 8 + textsize.X, 0, textsize.Y + 5)
				end
			end)
			if argstable["HoverText"] and type(argstable["HoverText"]) == "string" then
				frame.MouseMoved:Connect(function(x, y)
					hoverbox.Visible = (GuiLibrary["ToggleTooltips"] and hoverbox.TextSize ~= 1)
					hoverbox.Position = UDim2.new(0, (x + 16) * (1 / GuiLibrary["MainRescale"].Scale), 0,	(y - (hoverbox.Size.Y.Offset / 2) - 26) * (1 / GuiLibrary["MainRescale"].Scale))
				end)
			end
			frame.MouseLeave:Connect(function()
				hoverbox.Visible = false
			end)
			GuiLibrary.ObjectsThatCanBeSaved[argstablemain["Name"]..argstable["Name"].."SliderColor"] = {["Type"] = "ColorSliderMain", ["Object"] = frame, ["Api"] = sliderapi}
			return sliderapi
		end

		windowapi["CreateToggle"] = function(argstable)
			local buttonapi = {}
			local currentanim
			local amount = #children2:GetChildren()
			local buttontext = Instance.new("TextButton")
			buttontext.AutoButtonColor = false
			buttontext.BackgroundTransparency = 1
			buttontext.Name = "ButtonText"
			buttontext.Text = "          "..(translations[argstable["Name"]] ~= nil and translations[argstable["Name"]] or argstable["Name"])
			buttontext.Name = argstable["Name"]
			buttontext.LayoutOrder = amount
			buttontext.Size = UDim2.new(1, 0, 0, 30)
			buttontext.Active = false
			buttontext.TextColor3 = Color3.fromRGB(160, 160, 160)
			buttontext.TextSize = 14
			buttontext.Font = Enum.Font.Arial
			buttontext.TextXAlignment = Enum.TextXAlignment.Left
			buttontext.Position = UDim2.new(0, (icon and 36 or 10), 0, 0)
			buttontext.Parent = children2
			local buttonarrow = Instance.new("ImageLabel")
			buttonarrow.Size = UDim2.new(1, 0, 0, 4)
			buttonarrow.Position = UDim2.new(0, 0, 1, -4)
			buttonarrow.BackgroundTransparency = 1
			buttonarrow.Name = "ToggleArrow"
			buttonarrow.Image = downloadVapeAsset("vape/assets/ToggleArrow.png")
			buttonarrow.Visible = false
			buttonarrow.Parent = buttontext
			local toggleframe1 = Instance.new("Frame")
			toggleframe1.Size = UDim2.new(0, 22, 0, 12)
			toggleframe1.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
			toggleframe1.BorderSizePixel = 0
			toggleframe1.Name = "ToggleFrame1"
			toggleframe1.Position = UDim2.new(1, -30, 0, 10)
			toggleframe1.Parent = buttontext
			local toggleframe2 = Instance.new("Frame")
			toggleframe2.Size = UDim2.new(0, 8, 0, 8)
			toggleframe2.Active = false
			toggleframe2.Position = UDim2.new(0, 2, 0, 2)
			toggleframe2.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
			toggleframe2.BorderSizePixel = 0
			toggleframe2.Parent = toggleframe1
			local uicorner = Instance.new("UICorner")
			uicorner.CornerRadius = UDim.new(0, 16)
			uicorner.Parent = toggleframe1
			local uicorner2 = Instance.new("UICorner")
			uicorner2.CornerRadius = UDim.new(0, 16)
			uicorner2.Parent = toggleframe2

			buttonapi["Enabled"] = false
			buttonapi["Keybind"] = ""
			buttonapi["Default"] = argstable["Default"]
			buttonapi["Object"] = buttontext
			buttonapi["ToggleButton"] = function(toggle, first)
				buttonapi["Enabled"] = toggle
				if buttonapi["Enabled"] then
					if not first then
						tweenService:Create(toggleframe1, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Hue"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Sat"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Value"])}):Play()
					else
						toggleframe1.BackgroundColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Hue"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Sat"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Value"])
					end
					toggleframe2:TweenPosition(UDim2.new(0, 12, 0, 2), Enum.EasingDirection.InOut, Enum.EasingStyle.Linear, 0.1, true)
				else
					if not first then
						tweenService:Create(toggleframe1, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(60, 60, 60)}):Play()
					else
						toggleframe1.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
					end
					toggleframe2:TweenPosition(UDim2.new(0, 2, 0, 2), Enum.EasingDirection.InOut, Enum.EasingStyle.Linear, 0.1, true)
				end
				argstable["Function"](buttonapi["Enabled"])
			end
			if argstable["Default"] then
				buttonapi["ToggleButton"](argstable["Default"], true)
			end
			buttontext.MouseButton1Click:Connect(function() buttonapi["ToggleButton"](not buttonapi["Enabled"], false) end)
			buttontext.MouseEnter:Connect(function()
				if argstable["HoverText"] and type(argstable["HoverText"]) == "string" then
					hoverbox.Visible = (GuiLibrary["ToggleTooltips"] and hoverbox.TextSize ~= 1)
					local textsize = textService:GetTextSize(argstable["HoverText"], hoverbox.TextSize, hoverbox.Font, Vector2.new(99999, 99999))
					hoverbox.Text = " "..argstable["HoverText"]:gsub("\n", "\n ")
					hoverbox.Size = UDim2.new(0, 8 + textsize.X, 0, textsize.Y + 5)
				end
				if buttonapi["Enabled"] == false then
					tweenService:Create(toggleframe1, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(100, 100, 100)}):Play()
				end
			end)
			if argstable["HoverText"] and type(argstable["HoverText"]) == "string" then
				buttontext.MouseMoved:Connect(function(x, y)
					hoverbox.Visible = (GuiLibrary["ToggleTooltips"] and hoverbox.TextSize ~= 1)
					hoverbox.Position = UDim2.new(0, (x + 16) * (1 / GuiLibrary["MainRescale"].Scale), 0,	(y - (hoverbox.Size.Y.Offset / 2) - 26) * (1 / GuiLibrary["MainRescale"].Scale))
				end)
			end
			buttontext.MouseLeave:Connect(function()
				hoverbox.Visible = false
				if buttonapi["Enabled"] == false then
					tweenService:Create(toggleframe1, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(60, 60, 60)}):Play()
				end
			end)

			GuiLibrary.ObjectsThatCanBeSaved[argstablemain["Name"]..argstable["Name"].."Toggle"] = {["Type"] = "ToggleMain", ["Object"] = buttontext, ["Api"] = buttonapi}
			return buttonapi
		end

		windowapi["PinnedToggle"] = function()
			windowapi["Pinned"] = not windowapi["Pinned"]
			if windowapi["Pinned"] then
				expandbutton.ImageColor3 = Color3.fromRGB(200, 200, 200)
			else
				expandbutton.ImageColor3 = Color3.fromRGB(84, 84, 84)
			end
		end

		clickgui:GetPropertyChangedSignal("Visible"):Connect(windowapi["CheckVis"])
		windowapi["CheckVis"]()

		windowapi["GetCustomChildren"] = function()
			return children
		end

		expandbutton.MouseButton1Click:Connect(windowapi["PinnedToggle"])
		windowtitle.MouseButton2Click:Connect(windowapi["ExpandToggle"])
		optionsbutton.MouseButton1Click:Connect(windowapi["ExpandToggle"])
		GuiLibrary.ObjectsThatCanBeSaved[argstablemain["Name"].."CustomWindow"] = {["Object"] = windowtitle, ["ChildrenObject"] = children, ["Type"] = "CustomWindow", ["Api"] = windowapi}

		return windowapi
	end

	GuiLibrary["CreateWindow"] = function(argstablemain2)
		local currentexpandedbutton = nil
		local windowapi = {}
		local windowtitle = Instance.new("TextButton")
		windowtitle.Text = ""
		windowtitle.AutoButtonColor = false
		windowtitle.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
		windowtitle.Size = UDim2.new(0, 220, 0, 41)
		windowtitle.Position = UDim2.new(0, 223, 0, 6)
		windowtitle.Name = "MainWindow"
		windowtitle.Visible = false
		windowtitle.Name = argstablemain2["Name"]
		windowtitle.Parent = clickgui
		local windowshadow = Instance.new("ImageLabel")
		windowshadow.AnchorPoint = Vector2.new(0.5, 0.5)
		windowshadow.Position = UDim2.new(0.5, 0, 0.5, 0)
		windowshadow.Image = downloadVapeAsset("vape/assets/WindowBlur.png")
		windowshadow.BackgroundTransparency = 1
		windowshadow.ZIndex = -1
		windowshadow.Size = UDim2.new(1, 6, 1, 6)
		windowshadow.ImageColor3 = Color3.new(0, 0, 0)
		windowshadow.ScaleType = Enum.ScaleType.Slice
		windowshadow.SliceCenter = Rect.new(10, 10, 118, 118)
		windowshadow.Parent = windowtitle
		local windowicon = Instance.new("ImageLabel")
		windowicon.Size = UDim2.new(0, argstablemain2["IconSize"], 0, 16)
		windowicon.Image = downloadVapeAsset(argstablemain2["Icon"])
		windowicon.Name = "WindowIcon"
		windowicon.BackgroundTransparency = 1
		windowicon.Position = UDim2.new(0, 12, 0, 12)
		windowicon.ImageColor3 = Color3.fromRGB(200, 200, 200)
		windowicon.Parent = windowtitle
		local windowbackbutton = Instance.new("ImageButton")
		windowbackbutton.Size = UDim2.new(0, 16, 0, 16)
		windowbackbutton.Position = UDim2.new(0, 15, 0, 13)
		windowbackbutton.Visible = false
		windowbackbutton.BackgroundTransparency = 1
		windowbackbutton.MouseButton1Click:Connect(function()
			if currentexpandedbutton then
				currentexpandedbutton["ExpandToggle"]()
			end
		end)
		windowbackbutton.Image = downloadVapeAsset("vape/assets/BackIcon.png")
		windowbackbutton.Parent = windowtitle
		local windowtext = Instance.new("TextLabel")
		windowtext.Size = UDim2.new(0, 155, 0, 41)
		windowtext.BackgroundTransparency = 1
		windowtext.Name = "WindowTitle"
		windowtext.Position = UDim2.new(0, 36, 0, 1)
		windowtext.TextXAlignment = Enum.TextXAlignment.Left
		windowtext.Font = Enum.Font.Arial
		windowtext.TextSize = 14
		windowtext.Text = (translations[argstablemain2["Name"]] ~= nil and translations[argstablemain2["Name"]] or argstablemain2["Name"])
		windowtext.TextColor3 = Color3.fromRGB(200, 200, 200)
		windowtext.Parent = windowtitle
		local expandbutton = Instance.new("TextButton")
		expandbutton.Text = ""
		expandbutton.BackgroundTransparency = 1
		expandbutton.BorderSizePixel = 0
		expandbutton.BackgroundColor3 = Color3.new(1, 1, 1)
		expandbutton.Name = "ExpandButton"
		expandbutton.Size = UDim2.new(0, 24, 0, 16)
		expandbutton.Position = UDim2.new(1, -28, 0, 13)
		expandbutton.Parent = windowtitle
		local expandbutton2 = Instance.new("ImageLabel")
		expandbutton2.Active = false
		expandbutton2.Size = UDim2.new(0, 9, 0, 4)
		expandbutton2.Image = downloadVapeAsset("vape/assets/UpArrow.png")
		expandbutton2.Position = UDim2.new(0, 8, 0, 6)
		expandbutton2.Name = "ExpandButton2"
		expandbutton2.BackgroundTransparency = 1
		expandbutton2.Parent = expandbutton
		local children = Instance.new("ScrollingFrame")
		children.BackgroundTransparency = 1
		children.BorderSizePixel = 0
		children.ScrollBarThickness = 3
		children.ScrollBarImageTransparency = 0.8
		children.Size = UDim2.new(1, 0, 1, -45)
		children.ClipsDescendants = true
		children.Position = UDim2.new(0, 0, 0, 41)
		children.Visible = false
		children.Parent = windowtitle
		local windowcorner = Instance.new("UICorner")
		windowcorner.CornerRadius = UDim.new(0, 4)
		windowcorner.Parent = windowtitle
		local uilistlayout = Instance.new("UIListLayout")
		uilistlayout.SortOrder = Enum.SortOrder.LayoutOrder
		uilistlayout.Parent = children
		uilistlayout:GetPropertyChangedSignal("AbsoluteContentSize"):Connect(function()
			if children.Visible then
				windowtitle.Size = UDim2.new(0, 220, 0, math.clamp(45 + uilistlayout.AbsoluteContentSize.Y * (1 / GuiLibrary["MainRescale"].Scale), 0, 605))
				children.CanvasSize = UDim2.new(0, 0, 0, uilistlayout.AbsoluteContentSize.Y * (1 / GuiLibrary["MainRescale"].Scale))
				--560
			end
		end)
		local noexpand = false
		dragGUI(windowtitle)
		GuiLibrary.ObjectsThatCanBeSaved[argstablemain2["Name"].."Window"] = {["Object"] = windowtitle, ["ChildrenObject"] = children, ["Type"] = "Window", ["Api"] = windowapi, ["SortOrder"] = 0}

		windowapi["SetVisible"] = function(value)
			windowtitle.Visible = value
		end

		windowapi["ExpandToggle"] = function()
			if noexpand == false then
				children.Visible = not children.Visible
				if children.Visible then
					expandbutton2.Image = downloadVapeAsset("vape/assets/DownArrow.png")
					windowtitle.Size = UDim2.new(0, 220, 0, math.clamp(45 + uilistlayout.AbsoluteContentSize.Y * (1 / GuiLibrary["MainRescale"].Scale), 0, 605))
					children.CanvasSize = UDim2.new(0, 0, 0, uilistlayout.AbsoluteContentSize.Y * (1 / GuiLibrary["MainRescale"].Scale))
				else
					expandbutton2.Image = downloadVapeAsset("vape/assets/UpArrow.png")
					windowtitle.Size = UDim2.new(0, 220, 0, 41)
				end
			end
		end

		windowtitle.MouseButton2Click:Connect(windowapi["ExpandToggle"])
		expandbutton.MouseButton1Click:Connect(windowapi["ExpandToggle"])
		expandbutton.MouseButton2Click:Connect(windowapi["ExpandToggle"])

		windowapi["CreateOptionsButton"] = function(argstablemain)
			local buttonapi = {}
			local amount = #children:GetChildren()
			local button = Instance.new("TextButton")
			local currenttween = tweenService:Create(button, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(31, 30, 31)})
			button.Name = argstablemain["Name"].."Button"
			button.AutoButtonColor = false
			button.Size = UDim2.new(1, 0, 0, 40)
			button.BorderSizePixel = 0
			button.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
			button.Text = ""
			--button.LayoutOrder = amount
			button.Parent = children
			local buttonactiveborder = Instance.new("Frame")
			buttonactiveborder.BackgroundTransparency = 0.75
			buttonactiveborder.BackgroundColor3 = Color3.new(0, 0, 0)
			buttonactiveborder.BorderSizePixel = 0
			buttonactiveborder.Size = UDim2.new(1, 0, 0, 1)
			buttonactiveborder.Position = UDim2.new(0, 0, 1, -1)
			buttonactiveborder.Visible = false
			buttonactiveborder.Parent = button
			local button2 = Instance.new("ImageButton")
			button2.BackgroundTransparency = 1
			button2.Size = UDim2.new(0, 10, 0, 20)
			button2.Position = UDim2.new(1, -24, 0, 10)
			button2.Name = "OptionsButton"
			button2.Image = downloadVapeAsset("vape/assets/MoreButton1.png")
			button2.Parent = button
			local buttontext = Instance.new("TextLabel")
			buttontext.BackgroundTransparency = 1
			buttontext.Name = "ButtonText"
			buttontext.Text = (translations[argstablemain["Name"]] ~= nil and translations[argstablemain["Name"]] or argstablemain["Name"])
			buttontext.Size = UDim2.new(0, 118, 0, 39)
			buttontext.Active = false
			buttontext.TextColor3 = Color3.fromRGB(160, 160, 160)
			buttontext.TextSize = 14
			buttontext.Font = Enum.Font.Arial
			buttontext.TextXAlignment = Enum.TextXAlignment.Left
			buttontext.Position = UDim2.new(0, 12, 0, 1)
			buttontext.Parent = button
			local children2 = Instance.new("Frame")
			children2.Size = UDim2.new(1, 0, 0, 0)
			children2.BorderSizePixel = 0
			children2.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
		--	children2.LayoutOrder = amount
			children2.Visible = false
			children2.Name = argstablemain["Name"].."Children"
			children2.Parent = children
			local uilistlayout2 = Instance.new("UIListLayout")
			uilistlayout2.SortOrder = Enum.SortOrder.LayoutOrder
			uilistlayout2.Parent = children2
			uilistlayout2:GetPropertyChangedSignal("AbsoluteContentSize"):Connect(function()
				children2.Size = UDim2.new(0, 220, 0, uilistlayout2.AbsoluteContentSize.Y * (1 / GuiLibrary["MainRescale"].Scale))
				--if children2.Visible then
					--windowtitle.Size = UDim2.new(0, 220, 0, math.clamp(85 + (uilistlayout2.AbsoluteContentSize.Y * (1 / GuiLibrary["MainRescale"].Scale)), 0, 605))
					--children.CanvasSize = UDim2.new(0, 0, 0, (uilistlayout2.AbsoluteContentSize.Y + (40 * GuiLibrary["MainRescale"].Scale)) * (1 / GuiLibrary["MainRescale"].Scale))
				--end
			end)
			local bindbkg = Instance.new("TextButton")
			bindbkg.Text = ""
			bindbkg.AutoButtonColor = false
			bindbkg.Size = UDim2.new(0, 20, 0, 21)
			bindbkg.Position = UDim2.new(1, -56, 0, 9)
			bindbkg.BorderSizePixel = 0
			bindbkg.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
			bindbkg.BackgroundTransparency = 0.95
			bindbkg.Visible = false
			bindbkg.Parent = button
			local bindbkg2 = bindbkg:Clone()
			bindbkg2.BackgroundTransparency = 1
			bindbkg2.ZIndex = 2
			bindbkg2.Text = "x"
			bindbkg2.TextColor3 = Color3.fromRGB(88, 88, 88)
			bindbkg2.Parent = button
			local bindimg = Instance.new("ImageLabel")
			bindimg.Image = downloadVapeAsset("vape/assets/KeybindIcon.png")
			bindimg.BackgroundTransparency = 1
			bindimg.ImageColor3 = Color3.fromRGB(88, 88, 88)
			bindimg.Size = UDim2.new(0, 12, 0, 12)
			bindimg.Position = UDim2.new(0, 4, 0, 5)
			bindimg.Active = false
			bindimg.Parent = bindbkg
			local bindtext = Instance.new("TextLabel")
			bindtext.Active = false
			bindtext.BackgroundTransparency = 1
			bindtext.Text = ""
			bindtext.TextSize = 14
			bindtext.Parent = bindbkg
			bindtext.Font = Enum.Font.Arial
			bindtext.Size = UDim2.new(1, 0, 1, 0)
			bindtext.TextColor3 = Color3.fromRGB(85, 85, 85)
			bindtext.Visible = false
			local bindtext2 = Instance.new("ImageLabel")
			bindtext2.Size = UDim2.new(0, 156, 0, 39)
			bindtext2.Image = downloadVapeAsset("vape/assets/BindBackground.png")
			bindtext2.BackgroundTransparency = 1
			bindtext2.ScaleType = Enum.ScaleType.Slice
			bindtext2.SliceCenter = Rect.new(0, 0, 140, 40)
			bindtext2.Visible = false
			bindtext2.Parent = button
			local bindtext3 = Instance.new("TextLabel")
			bindtext3.Text = "   PRESS  KEY TO BIND"
			bindtext3.Size = UDim2.new(1, 0, 1, 0)
			bindtext3.Font = Enum.Font.Arial
			bindtext3.TextXAlignment = Enum.TextXAlignment.Left
			bindtext3.TextSize = 14
			bindtext3.TextColor3 = Color3.fromRGB(44, 44, 44)
			bindtext3.BackgroundTransparency = 1
			bindtext3.BorderSizePixel = 0
			bindtext3.Parent = bindtext2
			local bindround = Instance.new("UICorner")
			bindround.CornerRadius = UDim.new(0, 6)
			bindround.Parent = bindbkg
			if argstablemain["HoverText"] and type(argstablemain["HoverText"]) == "string" then
				button.MouseEnter:Connect(function()
					hoverbox.Visible = (GuiLibrary["ToggleTooltips"] and hoverbox.TextSize ~= 1)
					local textsize = textService:GetTextSize(argstablemain["HoverText"], hoverbox.TextSize, hoverbox.Font, Vector2.new(99999, 99999))
					hoverbox.Text = " "..argstablemain["HoverText"]:gsub("\n", "\n ")
					hoverbox.Size = UDim2.new(0, 8 + textsize.X, 0, textsize.Y + 5)
				end)
				button.MouseMoved:Connect(function(x, y)
					hoverbox.Visible = (GuiLibrary["ToggleTooltips"] and hoverbox.TextSize ~= 1)
					hoverbox.Position = UDim2.new(0, (x + 16) * (1 / GuiLibrary["MainRescale"].Scale), 0,	(y - (hoverbox.Size.Y.Offset / 2) - 26) * (1 / GuiLibrary["MainRescale"].Scale))
				end)
			end
			buttonapi["Enabled"] = false
			buttonapi["Keybind"] = ""
			buttonapi["HoverText"] = argstablemain["HoverText"]
			buttonapi["Children"] = children2
			buttonapi["Name"] = argstablemain["Name"]
			buttonapi["HasExtraText"] = type(argstablemain["ExtraText"]) == "function"
			buttonapi["GetExtraText"] = (buttonapi["HasExtraText"] and argstablemain["ExtraText"] or function() return "" end)
			buttonapi.Connections = {}
			local newsize = UDim2.new(0, 20, 0, 21)

			buttonapi["SetKeybind"] = function(key)
				if key == "" then
					buttonapi["Keybind"] = key
					newsize = UDim2.new(0, 20, 0, 21)
					bindbkg.Size = newsize
					bindbkg.Visible = true
					bindbkg.Position = UDim2.new(1, -(36 + newsize.X.Offset), 0, 9)
					bindimg.Visible = true
					bindtext.Visible = false
					bindtext.Text = key
				else
					local textsize = textService:GetTextSize(key, 16, bindtext.Font, Vector2.new(99999, 99999))
					newsize = UDim2.new(0, 11 + textsize.X, 0, 21)
					buttonapi["Keybind"] = key
					bindbkg.Visible = true
					bindbkg.Size = newsize
					bindbkg.Position = UDim2.new(1, -(36 + newsize.X.Offset), 0, 9)
					bindimg.Visible = false
					bindtext.Visible = true
					bindtext.Text = key
				end
			end

			buttonapi["ToggleButton"] = function(clicked, toggle)
				buttonapi["Enabled"] = (toggle or not buttonapi["Enabled"])
				if buttonapi["Enabled"] then
					button.BackgroundColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Hue"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Sat"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Value"])
					currenttween:Cancel()
					buttonactiveborder.Visible = true
					button2.Image = downloadVapeAsset("vape/assets/MoreButton2.png")
					buttontext.TextColor3 = Color3.new(0, 0, 0)
					bindbkg.BackgroundTransparency = 0.9
					bindtext.TextColor3 = Color3.fromRGB(45, 45, 45)
					bindimg.ImageColor3 = Color3.fromRGB(45, 45, 45)
				else
					for i, v in pairs(buttonapi.Connections) do
						if v.Disconnect then pcall(function() v:Disconnect() end) continue end
						if v.disconnect then pcall(function() v:disconnect() end) continue end
					end
					table.clear(buttonapi.Connections)
					button.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
					buttonactiveborder.Visible = false
					button2.Image = downloadVapeAsset("vape/assets/MoreButton1.png")
					buttontext.TextColor3 = Color3.fromRGB(160, 160, 160)
					bindbkg.BackgroundTransparency = 0.95
					bindtext.TextColor3 = Color3.fromRGB(88, 88, 88)
					bindimg.ImageColor3 = Color3.fromRGB(88, 88, 88)
				end
				argstablemain["Function"](buttonapi["Enabled"])
				GuiLibrary["UpdateHudEvent"]:Fire()
			end

			buttonapi["ExpandToggle"] = function()
				children2.Visible = not children2.Visible
				--[[
				if children2.Visible then
					for i,v in pairs(children:GetChildren()) do
						if v:IsA("TextButton") then
							v.Visible = true
						end
					end
					windowicon.Visible = true
					windowbackbutton.Visible = false
					children2.Visible = false
					noexpand = false
					windowtitle.Size = UDim2.new(0, 220, 0, math.clamp(45 + uilistlayout.AbsoluteContentSize.Y * (1 / GuiLibrary["MainRescale"].Scale), 0, 605))
					children.CanvasSize = UDim2.new(0, 0, 0, uilistlayout.AbsoluteContentSize.Y * (1 / GuiLibrary["MainRescale"].Scale))
				else
					for i,v in pairs(children:GetChildren()) do
						if v:IsA("TextButton") then
							v.Visible = false
						end
					end
					windowicon.Visible = false
					windowbackbutton.Visible = true
					button.Visible = true
					children2.Visible = true
					noexpand = true
					--windowtitle.Size = UDim2.new(0, 220, 0, 85 + uilistlayout2.AbsoluteContentSize.Y * (1 / GuiLibrary["MainRescale"].Scale))
					windowtitle.Size = UDim2.new(0, 220, 0, math.clamp(85 + (uilistlayout2.AbsoluteContentSize.Y * (1 / GuiLibrary["MainRescale"].Scale)), 0, 605))
					children.CanvasSize = UDim2.new(0, 0, 0, (uilistlayout2.AbsoluteContentSize.Y + (40 * GuiLibrary["MainRescale"].Scale)) * (1 / GuiLibrary["MainRescale"].Scale))
					currentexpandedbutton = buttonapi
				end]]
			end

			buttonapi["CreateTextList"] = function(argstable)
				local textGuiLibrary = {}
				local amount = #children2:GetChildren()
				local frame = Instance.new("Frame")
				frame.Size = UDim2.new(0, 220, 0, 40)
				frame.BackgroundTransparency = 1
				frame.ClipsDescendants = true
				frame.LayoutOrder = amount
				frame.Name = argstable["Name"]
				frame.Parent = children2
				local textboxbkg = Instance.new("ImageLabel")
				textboxbkg.BackgroundTransparency = 1
				textboxbkg.Name = "AddBoxBKG"
				textboxbkg.Size = UDim2.new(0, 200, 0, 31)
				textboxbkg.Position = UDim2.new(0, 10, 0, 5)
				textboxbkg.ClipsDescendants = true
				textboxbkg.Image = downloadVapeAsset("vape/assets/TextBoxBKG.png")
				textboxbkg.Parent = frame
				local textbox = Instance.new("TextBox")
				textbox.Size = UDim2.new(0, 159, 1, 0)
				textbox.Position = UDim2.new(0, 11, 0, 0)
				textbox.TextXAlignment = Enum.TextXAlignment.Left
				textbox.Name = "AddBox"
				textbox.BackgroundTransparency = 1
				textbox.TextColor3 = Color3.new(1, 1, 1)
				textbox.PlaceholderColor3 = Color3.fromRGB(200, 200, 200)
				textbox.Font = Enum.Font.SourceSans
				textbox.Text = ""
				textbox.PlaceholderText = argstable["TempText"]
				textbox.TextSize = 17
				textbox.Parent = textboxbkg
				local addbutton = Instance.new("ImageButton")
				addbutton.BorderSizePixel = 0
				addbutton.Name = "AddButton"
				addbutton.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
				addbutton.Position = UDim2.new(0, 174, 0, 8)
				addbutton.AutoButtonColor = false
				addbutton.Size = UDim2.new(0, 16, 0, 16)
				addbutton.ImageColor3 = Color3.fromHSV(0.44, 1, 1)
				addbutton.Image = downloadVapeAsset("vape/assets/AddItem.png")
				addbutton.Parent = textboxbkg
				local scrollframebkg = Instance.new("Frame")
				scrollframebkg.ZIndex = 2
				scrollframebkg.Name = "ScrollingFrameBKG"
				scrollframebkg.Size = UDim2.new(0, 220, 0, 3)
				scrollframebkg.BackgroundTransparency = 1
				scrollframebkg.LayoutOrder = amount
				scrollframebkg.Parent = children2
				local scrollframe = Instance.new("ScrollingFrame")
				scrollframe.ZIndex = 2
				scrollframe.Size = UDim2.new(0, 200, 0, 3)
				scrollframe.Position = UDim2.new(0, 10, 0, 0)
				scrollframe.BackgroundTransparency = 1
				scrollframe.ScrollBarThickness = 0
				scrollframe.ScrollBarImageColor3 = Color3.new(0, 0, 0)
				scrollframe.LayoutOrder = amount
				scrollframe.Parent = scrollframebkg
				local uilistlayout3 = Instance.new("UIListLayout")
				uilistlayout3.Padding = UDim.new(0, 3)
				uilistlayout3.Parent = scrollframe
				uilistlayout3:GetPropertyChangedSignal("AbsoluteContentSize"):Connect(function()
					scrollframe.CanvasSize = UDim2.new(0, 0, 0, uilistlayout3.AbsoluteContentSize.Y)
					scrollframe.Size = UDim2.new(0, 220, 0, math.clamp(uilistlayout3.AbsoluteContentSize.Y, 1, 105))
					scrollframebkg.Size = UDim2.new(0, 220, 0, math.clamp(uilistlayout3.AbsoluteContentSize.Y, 1, 105) + 3)
				end)

				textGuiLibrary["Object"] = frame
				textGuiLibrary["ScrollingObject"] = scrollframebkg
				textGuiLibrary["ObjectList"] = {}
				textGuiLibrary["RefreshValues"] = function(tab)
					textGuiLibrary["ObjectList"] = tab
					if argstable["SortFunction"] then
						table.sort(textGuiLibrary["ObjectList"], argstable["SortFunction"])
					end
					for i2,v2 in pairs(scrollframe:GetChildren()) do
						if v2:IsA("TextButton") then v2:Remove() end
					end
					for i,v in pairs(textGuiLibrary["ObjectList"]) do
						local itemframe = Instance.new("TextButton")
						itemframe.Size = UDim2.new(0, 200, 0, 33)
						itemframe.BackgroundColor3 = Color3.fromRGB(31, 30, 31)
						itemframe.BorderSizePixel = 0
						itemframe.Text = ""
						itemframe.AutoButtonColor = false
						itemframe.Parent = scrollframe
						local itemcorner = Instance.new("UICorner")
						itemcorner.CornerRadius = UDim.new(0, 6)
						itemcorner.Parent = itemframe
						local itemtext = Instance.new("TextLabel")
						itemtext.BackgroundTransparency = 1
						itemtext.Size = UDim2.new(0, 193, 0, 33)
						itemtext.Name = "ItemText"
						itemtext.Position = UDim2.new(0, 8, 0, 0)
						itemtext.Font = Enum.Font.SourceSans
						itemtext.TextSize = 17
						itemtext.Text = v
						itemtext.TextXAlignment = Enum.TextXAlignment.Left
						itemtext.TextColor3 = Color3.fromRGB(86, 85, 86)
						itemtext.Parent = itemframe
						local deletebutton = Instance.new("ImageButton")
						deletebutton.Size = UDim2.new(0, 6, 0, 6)
						deletebutton.BackgroundTransparency = 1
						deletebutton.AutoButtonColor = false
						deletebutton.ZIndex = 1
						deletebutton.Image = downloadVapeAsset("vape/assets/AddRemoveIcon1.png")
						deletebutton.Position = UDim2.new(1, -16, 0, 14)
						deletebutton.Parent = itemframe
						deletebutton.MouseButton1Click:Connect(function()
							table.remove(textGuiLibrary["ObjectList"], table.find(textGuiLibrary["ObjectList"], v))
							textGuiLibrary["RefreshValues"](textGuiLibrary["ObjectList"])
							if argstable["RemoveFunction"] then
								argstable["RemoveFunction"](i, v)
							end
						end)
						if argstable["CustomFunction"] then
							argstable["CustomFunction"](itemframe)
						end
					end
				end

                local function AddToList()
					table.insert(textGuiLibrary["ObjectList"], textbox.Text)
					textGuiLibrary["RefreshValues"](textGuiLibrary["ObjectList"])
					if argstable["AddFunction"] then
						argstable["AddFunction"](textbox.Text)
					end
                    textbox.Text = ""
				end

				addbutton.MouseButton1Click:Connect(AddToList)
                textbox.FocusLost:Connect(function(enter)
                    if enter then
                        AddToList()
                        textbox:CaptureFocus()
                    end
                end)

				GuiLibrary.ObjectsThatCanBeSaved[argstablemain["Name"]..argstable["Name"].."TextList"] = {["Type"] = "TextList", ["Api"] = textGuiLibrary}
				return textGuiLibrary
			end

			buttonapi["CreateTextBox"] = function(argstable)
				local textGuiLibrary = {}
				local amount = #children2:GetChildren()
				local frame = Instance.new("Frame")
				frame.Size = UDim2.new(0, 220, 0, 40)
				frame.BackgroundTransparency = 1
				frame.ClipsDescendants = true
				frame.LayoutOrder = amount
				frame.Name = argstable["Name"]
				frame.Parent = children2
				local textboxbkg = Instance.new("ImageLabel")
				textboxbkg.BackgroundTransparency = 1
				textboxbkg.Name = "AddBoxBKG"
				textboxbkg.Size = UDim2.new(0, 200, 0, 31)
				textboxbkg.Position = UDim2.new(0, 10, 0, 5)
				textboxbkg.ClipsDescendants = true
				textboxbkg.Image = downloadVapeAsset("vape/assets/TextBoxBKG.png")
				textboxbkg.Parent = frame
				local textbox = Instance.new("TextBox")
				textbox.Size = UDim2.new(0, 159, 1, 0)
				textbox.Position = UDim2.new(0, 11, 0, 0)
				textbox.TextXAlignment = Enum.TextXAlignment.Left
				textbox.Name = "AddBox"
				textbox.ClearTextOnFocus = false
				textbox.BackgroundTransparency = 1
				textbox.TextColor3 = Color3.new(1, 1, 1)
				textbox.PlaceholderColor3 = Color3.fromRGB(200, 200, 200)
				textbox.Font = Enum.Font.SourceSans
				textbox.Text = ""
				textbox.PlaceholderText = argstable["TempText"]
				textbox.TextSize = 17
				textbox.Parent = textboxbkg

				textGuiLibrary["Object"] = frame
				textGuiLibrary["Value"] = ""
				textGuiLibrary["SetValue"] = function(val, entered)
					textGuiLibrary["Value"] = val
					textbox.Text = val
					if argstable["FocusLost"] and (not entered) then
						argstable["FocusLost"](false)
					end
				end

				textbox.FocusLost:Connect(function(enter)
					textGuiLibrary["SetValue"](textbox.Text, true)
					if argstable["FocusLost"] then
						argstable["FocusLost"](enter)
					end
				end)

				GuiLibrary.ObjectsThatCanBeSaved[argstablemain["Name"]..argstable["Name"].."TextBox"] = {["Type"] = "TextBox", ["Api"] = textGuiLibrary, ["Object"] = frame}
				return textGuiLibrary
			end

			buttonapi["CreateTargetWindow"] = function(argstablemain3)
				local buttonapi = {}
				local buttonreturned = {}
				local windowapi = {}
				local amount2 = #children2:GetChildren()
				local frame = Instance.new("Frame")
				frame.Size = UDim2.new(0, 220, 0, 49)
				frame.BackgroundTransparency = 1
				frame.LayoutOrder = amount2
				frame.Name = argstablemain["Name"].."TargetFrame"
				frame.Parent = children2
				local drop1 = Instance.new("TextButton")
				drop1.AutoButtonColor = false
				drop1.Size = UDim2.new(0, 198, 0, 39)
				drop1.Position = UDim2.new(0, 11, 0, 5)
				drop1.Parent = frame
				drop1.BorderSizePixel = 0
				drop1.ZIndex = 2
				drop1.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
				drop1.TextSize = 17
				drop1.TextXAlignment = Enum.TextXAlignment.Left
				drop1.Text = ""
				local targettext = Instance.new("TextLabel")
				targettext.Size = UDim2.new(1, 0, 1, 0)
				targettext.Position = UDim2.new(0, 0, 0, 0)
				targettext.BackgroundTransparency = 1
				targettext.ZIndex = 2
				targettext.TextSize = 17
				targettext.RichText = true
				targettext.TextColor3 = Color3.new(205, 205, 205)
				targettext.Text = "  Target : \n "..'<font color="rgb(151, 151, 151)">Ignore none</font>'
				targettext.Font = Enum.Font.SourceSans
				targettext.TextXAlignment = Enum.TextXAlignment.Left
				targettext.Parent = drop1
				local targetframe = Instance.new("Frame")
				targetframe.Size = UDim2.new(0, 100, 0, 12)
				targetframe.BackgroundTransparency = 1
				targetframe.Position = UDim2.new(0, 53, 0, 6)
				targetframe.ZIndex = 3
				targetframe.Parent = targettext
				local targetlistlayout = Instance.new("UIListLayout")
				targetlistlayout.FillDirection = Enum.FillDirection.Horizontal
				targetlistlayout.SortOrder = Enum.SortOrder.LayoutOrder
				targetlistlayout.Padding = UDim.new(0, 4)
				targetlistlayout.Parent = targetframe
				local thing = Instance.new("Frame")
				thing.Size = UDim2.new(1, 2, 1, 2)
				thing.BorderSizePixel = 0
				thing.Position = UDim2.new(0, -1, 0, -1)
				thing.ZIndex = 1
				thing.BackgroundColor3 = Color3.fromRGB(38, 37, 38)
				thing.Parent = drop1
				local uicorner = Instance.new("UICorner")
				uicorner.CornerRadius = UDim.new(0, 4)
				uicorner.Parent = drop1
				local uicorner2 = Instance.new("UICorner")
				uicorner2.CornerRadius = UDim.new(0, 4)
				uicorner2.Parent = thing
				local windowtitle = Instance.new("TextButton")
				windowtitle.Text = ""
				windowtitle.AutoButtonColor = false
				windowtitle.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
				windowtitle.Size = UDim2.new(0, 220, 0, 41)
				windowtitle.Position = UDim2.new(1, 1, 0, 0)
				windowtitle.Name = argstablemain["Name"].."TargetWindow"
				windowtitle.Visible = false
				windowtitle.ZIndex = 3
				windowtitle.Parent = clickgui
				frame:GetPropertyChangedSignal("AbsolutePosition"):Connect(function()
					windowtitle.Position = UDim2.new(0, frame.Size.X.Offset + frame.AbsolutePosition.X + 2, 0, frame.AbsolutePosition.Y)
				end)
				local windowshadow = Instance.new("ImageLabel")
				windowshadow.AnchorPoint = Vector2.new(0.5, 0.5)
				windowshadow.Position = UDim2.new(0.5, 0, 0.5, 0)
				windowshadow.Image = downloadVapeAsset("vape/assets/WindowBlur.png")
				windowshadow.BackgroundTransparency = 1
				windowshadow.ZIndex = -1
				windowshadow.Size = UDim2.new(1, 6, 1, 6)
				windowshadow.ImageColor3 = Color3.new(0, 0, 0)
				windowshadow.ScaleType = Enum.ScaleType.Slice
				windowshadow.SliceCenter = Rect.new(10, 10, 118, 118)
				windowshadow.Parent = windowtitle
				local windowicon = Instance.new("ImageLabel")
				windowicon.Size = UDim2.new(0, 18, 0, 16)
				windowicon.Image = downloadVapeAsset("vape/assets/TargetIcon.png")
				windowicon.ImageColor3 = Color3.fromRGB(200, 200, 200)
				windowicon.ZIndex = 3
				windowicon.Name = "WindowIcon"
				windowicon.BackgroundTransparency = 1
				windowicon.Position = UDim2.new(0, 12, 0, 12)
				windowicon.Parent = windowtitle
				local windowtext = Instance.new("TextLabel")
				windowtext.Size = UDim2.new(0, 155, 0, 41)
				windowtext.BackgroundTransparency = 1
				windowtext.Name = "WindowTitle"
				windowtext.Position = UDim2.new(0, 36, 0, 1)
				windowtext.ZIndex = 3
				windowtext.TextXAlignment = Enum.TextXAlignment.Left
				windowtext.Font = Enum.Font.Arial
				windowtext.TextSize = 14
				windowtext.Text = "Target settings"
				windowtext.TextColor3 = Color3.fromRGB(200, 200, 200)
				windowtext.Parent = windowtitle
				local children = Instance.new("Frame")
				children.BackgroundTransparency = 1
				children.Size = UDim2.new(1, 0, 1, -4)
				children.ZIndex = 3
				children.Position = UDim2.new(0, 0, 0, 41)
				children.Visible = true
				children.Parent = windowtitle
				local buttonframeholder = Instance.new("Frame")
				buttonframeholder.BackgroundTransparency = 1
				buttonframeholder.Size = UDim2.new(1, 0, 0, 40)
				buttonframeholder.LayoutOrder = 0
				buttonframeholder.Parent = children
				local windowcorner = Instance.new("UICorner")
				windowcorner.CornerRadius = UDim.new(0, 4)
				windowcorner.Parent = windowtitle
				local uilistlayout = Instance.new("UIListLayout")
				uilistlayout.SortOrder = Enum.SortOrder.LayoutOrder
				uilistlayout.Parent = children
				uilistlayout:GetPropertyChangedSignal("AbsoluteContentSize"):Connect(function()
					windowtitle.Size = UDim2.new(0, 220, 0, 45 + uilistlayout.AbsoluteContentSize.Y)
				end)

				buttonreturned["Invisible"] = {["Enabled"] = false}
				buttonreturned["Naked"] = {["Enabled"] = false}
				buttonreturned["Walls"] = {["Enabled"] = false}

				windowapi["UpdateIgnore"] = function()
					if argstablemain3["UpdateFunction"] then
						argstablemain3["UpdateFunction"]()
					end
					targettext.Text = "  Target : \n "..'<font size="'..(buttonreturned["Invisible"]["Enabled"] and buttonreturned["Naked"]["Enabled"] and buttonreturned["Walls"]["Enabled"] and 14 or 17)..'" color="rgb(151, 151, 151)">'.."Ignore "..((buttonreturned["Invisible"]["Enabled"] or buttonreturned["Naked"]["Enabled"] or buttonreturned["Walls"]["Enabled"]) and "" or "none")..(buttonreturned["Invisible"]["Enabled"] and "invisible" or "")..(buttonreturned["Naked"]["Enabled"] and ((buttonreturned["Invisible"]["Enabled"]) and ", " or "").."naked" or "")..(buttonreturned["Walls"]["Enabled"] and ((buttonreturned["Invisible"]["Enabled"] or buttonreturned["Naked"]["Enabled"]) and ", " or "").."behind walls" or "")..'</font>'
				end

				windowapi["CreateToggle"] = function(argstable)
					local buttonapi = {}
					local currentanim
					local amount = #children2:GetChildren()
					local buttontext = Instance.new("TextButton")
					buttontext.AutoButtonColor = false
					buttontext.BackgroundTransparency = 1
					buttontext.Name = "ButtonText"
					buttontext.Text = "          "..(translations[argstable["Name"]] ~= nil and translations[argstable["Name"]] or argstable["Name"])
					buttontext.Name = argstable["Name"]
					buttontext.LayoutOrder = amount
					buttontext.Size = UDim2.new(1, 0, 0, 30)
					buttontext.Active = false
					buttontext.TextColor3 = Color3.fromRGB(160, 160, 160)
					buttontext.TextSize = 14
					buttontext.ZIndex = 3
					buttontext.Font = Enum.Font.Arial
					buttontext.TextXAlignment = Enum.TextXAlignment.Left
					buttontext.Position = UDim2.new(0, (icon and 36 or 10), 0, 0)
					buttontext.Parent = children
					local buttonarrow = Instance.new("ImageLabel")
					buttonarrow.Size = UDim2.new(1, 0, 0, 4)
					buttonarrow.Position = UDim2.new(0, 0, 1, -4)
					buttonarrow.BackgroundTransparency = 1
					buttonarrow.Name = "ToggleArrow"
					buttonarrow.ZIndex = 3
					buttonarrow.Image = downloadVapeAsset("vape/assets/ToggleArrow.png")
					buttonarrow.Visible = false
					buttonarrow.Parent = buttontext
					local toggleframe1 = Instance.new("Frame")
					toggleframe1.Size = UDim2.new(0, 22, 0, 12)
					toggleframe1.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
					toggleframe1.BorderSizePixel = 0
					toggleframe1.ZIndex = 3
					toggleframe1.Name = "ToggleFrame1"
					toggleframe1.Position = UDim2.new(1, -30, 0, 10)
					toggleframe1.Parent = buttontext
					local toggleframe2 = Instance.new("Frame")
					toggleframe2.Size = UDim2.new(0, 8, 0, 8)
					toggleframe2.Active = false
					toggleframe2.ZIndex = 3
					toggleframe2.Position = UDim2.new(0, 2, 0, 2)
					toggleframe2.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
					toggleframe2.BorderSizePixel = 0
					toggleframe2.Parent = toggleframe1
					local uicorner = Instance.new("UICorner")
					uicorner.CornerRadius = UDim.new(0, 16)
					uicorner.Parent = toggleframe1
					local uicorner2 = Instance.new("UICorner")
					uicorner2.CornerRadius = UDim.new(0, 16)
					uicorner2.Parent = toggleframe2

					buttonapi["Enabled"] = false
					buttonapi["Keybind"] = ""
					buttonapi["Default"] = argstable["Default"]
					buttonapi["Object"] = buttontext
					buttonapi["ToggleButton"] = function(toggle, first)
						buttonapi["Enabled"] = toggle
						if buttonapi["Enabled"] then
							if not first then
								tweenService:Create(toggleframe1, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Hue"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Sat"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Value"])}):Play()
							else
								toggleframe1.BackgroundColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Hue"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Sat"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Value"])
							end
							toggleframe2:TweenPosition(UDim2.new(0, 12, 0, 2), Enum.EasingDirection.InOut, Enum.EasingStyle.Linear, 0.1, true)
						else
							if not first then
								tweenService:Create(toggleframe1, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(60, 60, 60)}):Play()
							else
								toggleframe1.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
							end
							toggleframe2:TweenPosition(UDim2.new(0, 2, 0, 2), Enum.EasingDirection.InOut, Enum.EasingStyle.Linear, 0.1, true)
						end
						argstable["Function"](buttonapi["Enabled"])
					end
					if argstable["Default"] then
						buttonapi["ToggleButton"](argstable["Default"], true)
					end
					buttontext.MouseButton1Click:Connect(function() buttonapi["ToggleButton"](not buttonapi["Enabled"], false) end)
					buttontext.MouseEnter:Connect(function()
						if argstable["HoverText"] and type(argstable["HoverText"]) == "string" then
							hoverbox.Visible = (GuiLibrary["ToggleTooltips"] and hoverbox.TextSize ~= 1)
							local textsize = textService:GetTextSize(argstable["HoverText"], hoverbox.TextSize, hoverbox.Font, Vector2.new(99999, 99999))
							hoverbox.Text = "  "..argstable["HoverText"]:gsub("\n", "\n  ")
							hoverbox.Size = UDim2.new(0, 13 + textsize.X, 0, textsize.Y + 5)
						end
						if buttonapi["Enabled"] == false then
							tweenService:Create(toggleframe1, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(100, 100, 100)}):Play()
						end
					end)
					if argstable["HoverText"] and type(argstable["HoverText"]) == "string" then
						buttontext.MouseMoved:Connect(function(x, y)
							hoverbox.Visible = (GuiLibrary["ToggleTooltips"] and hoverbox.TextSize ~= 1)
							hoverbox.Position = UDim2.new(0, (x + 16) * (1 / GuiLibrary["MainRescale"].Scale), 0,	(y - (hoverbox.Size.Y.Offset / 2) - 26) * (1 / GuiLibrary["MainRescale"].Scale))
						end)
					end
					buttontext.MouseLeave:Connect(function()
						hoverbox.Visible = false
						if buttonapi["Enabled"] == false then
							tweenService:Create(toggleframe1, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(60, 60, 60)}):Play()
						end
					end)

					GuiLibrary.ObjectsThatCanBeSaved[argstablemain["Name"]..argstable["Name"].."TargetToggle"] = {["Type"] = "Toggle", ["Object"] = buttontext, ["Api"] = buttonapi}
					return buttonapi
				end

				windowapi["CreateButton"] = function(argstable)
					local buttonapi = {}
					local amount = #children:GetChildren()
					local buttontext = Instance.new("TextButton")
					buttontext.Name = argstablemain["Name"]..argstable["Name"].."TargetButton"
					buttontext.LayoutOrder = amount
					buttontext.AutoButtonColor = false
					buttontext.Size = UDim2.new(0, 45, 0, 29)
					buttontext.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
					buttontext.Active = false
					buttontext.Text = ""
					buttontext.ZIndex = 4
					buttontext.Font = Enum.Font.SourceSans
					buttontext.TextXAlignment = Enum.TextXAlignment.Left
					buttontext.Position = argstable["Position"]
					buttontext.Parent = buttonframeholder
					local buttonbkg = Instance.new("Frame")
					buttonbkg.BackgroundColor3 = Color3.fromRGB(38, 37, 38)
					buttonbkg.Size = UDim2.new(0, 47, 0, 31)
					buttonbkg.Position = argstable["Position"] - UDim2.new(0, 1, 0, 1)
					buttonbkg.ZIndex = 3
					buttonbkg.Parent = buttonframeholder
					local buttonimage = Instance.new("ImageLabel")
					buttonimage.BackgroundTransparency = 1
					buttonimage.Position = UDim2.new(0, 14, 0, 7)
					buttonimage.Size = UDim2.new(0, argstable["IconSize"], 0, 16)
					buttonimage.Image = downloadVapeAsset(argstable["Icon"])
					buttonimage.ImageColor3 = Color3.fromRGB(121, 121, 121)
					buttonimage.ZIndex = 5
					buttonimage.Active = false
					buttonimage.Parent = buttontext
					local buttontexticon = Instance.new("ImageLabel")
					buttontexticon.Size = UDim2.new(0, argstable["IconSize"] - 3, 0, 12)
					buttontexticon.Image = downloadVapeAsset(argstable["Icon"])
					buttontexticon.LayoutOrder = amount
					buttontexticon.ZIndex = 4
					buttontexticon.BackgroundTransparency = 1
					buttontexticon.Visible = false
					buttontexticon.Parent = targetframe
					local buttonround1 = Instance.new("UICorner")
					buttonround1.CornerRadius = UDim.new(0, 5)
					buttonround1.Parent = buttontext
					local buttonround2 = Instance.new("UICorner")
					buttonround2.CornerRadius = UDim.new(0, 5)
					buttonround2.Parent = buttonbkg
					buttonapi["Enabled"] = false
					buttonapi["Default"] = argstable["Default"]

					buttonapi["ToggleButton"] = function(toggle, frist)
						buttonapi["Enabled"] = toggle
						buttontexticon.Visible = toggle
						if buttonapi["Enabled"] then
							if not first then
								tweenService:Create(buttontext, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Hue"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Sat"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Value"])}):Play()
							else
								buttontext.BackgroundColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Hue"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Sat"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Value"])
							end
						else
							if not first then
								tweenService:Create(buttontext, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(26, 25, 26)}):Play()
							else
								buttontext.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
							end
						end
						buttonimage.ImageColor3 = (buttonapi["Enabled"] and Color3.new(1, 1, 1) or Color3.fromRGB(121, 121, 121))
						argstable["Function"](buttonapi["Enabled"])
					end

					if argstable["Default"] then
						buttonapi["ToggleButton"](argstable["Default"], true)
					end
					buttontext.MouseButton1Click:Connect(function() buttonapi["ToggleButton"](not buttonapi["Enabled"], false) end)
					GuiLibrary.ObjectsThatCanBeSaved[argstablemain["Name"]..argstable["Name"].."TargetButton"] = {["Type"] = "TargetButton", ["Object"] = buttontext, ["Api"] = buttonapi}
					return buttonapi
				end

				buttonreturned["Players"] = windowapi["CreateButton"]({
					["Name"] = "PlayersIcon",
					["Position"] = UDim2.new(0, 11, 0, 6),
					["Icon"] = "vape/assets/TargetIcon1.png",
					["IconSize"] = 15,
					["Function"] = function() end,
					["Default"] = true
				})
				buttonreturned["NPCs"] = windowapi["CreateButton"]({
					["Name"] = "NPCsIcon",
					["Position"] = UDim2.new(0, 62, 0, 6),
					["Icon"] = "vape/assets/TargetIcon2.png",
					["IconSize"] = 12,
					["Function"] = function() end,
					["Default"] = false
				})
				buttonreturned["Peaceful"] = windowapi["CreateButton"]({
					["Name"] = "PeacefulIcon",
					["Position"] = UDim2.new(0, 113, 0, 6),
					["Icon"] = "vape/assets/TargetIcon3.png",
					["IconSize"] = 16,
					["Function"] = function() end,
					["Default"] = false
				})
				buttonreturned["Neutral"] = windowapi["CreateButton"]({
					["Name"] = "NeutralIcon",
					["Position"] = UDim2.new(0, 164, 0, 6),
					["Icon"] = "vape/assets/TargetIcon4.png",
					["IconSize"] = 19,
					["Function"] = function() end,
					["Default"] = false
				})

				buttonreturned["Invisible"] = windowapi["CreateToggle"]({
					["Name"] = "Ignore invisible",
					["Function"] = function() windowapi["UpdateIgnore"]() end,
					["Default"] = (argstablemain3["Default1"] or false)
				})
				buttonreturned["Naked"] = windowapi["CreateToggle"]({
					["Name"] = "Ignore naked",
					["Function"] = function() windowapi["UpdateIgnore"]() end,
					["Default"] = (argstablemain3["Default2"] or false)
				})
				buttonreturned["Walls"] = windowapi["CreateToggle"]({
					["Name"] = "Ignore behind walls",
					["Function"] = function() windowapi["UpdateIgnore"]() end,
					["Default"] = (argstablemain3["Default3"] or false)
				})

				drop1.MouseButton1Click:Connect(function()
					windowtitle.Visible = not windowtitle.Visible
					if not windowtitle.Visible then
						tweenService:Create(thing, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(107, 107, 107)}):Play()
					end
				end)
				drop1.MouseEnter:Connect(function()
					if not windowtitle.Visible then
						tweenService:Create(thing, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(107, 107, 107)}):Play()
					end
				end)
				drop1.MouseLeave:Connect(function()
					if not windowtitle.Visible then
						tweenService:Create(thing, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(38, 37, 38)}):Play()
					end
				end)

				GuiLibrary.ObjectsThatCanBeSaved[argstablemain["Name"].."TargetFrame"] = {["Type"] = "TargetFrame", ["Object"] = frame, ["Object2"] = windowtitle, ["Api"] = buttonreturned}

				return buttonreturned
			end

			buttonapi["CreateCircleWindow"] = function(argstablemain3)
				local buttonapi = {}
				local buttonreturned = {}
				local windowapi = {}
				local amount2 = #children2:GetChildren()
				local frame = Instance.new("Frame")
				frame.Size = UDim2.new(0, 220, 0, 49)
				frame.BackgroundTransparency = 1
				frame.LayoutOrder = amount2
				frame.Name = argstablemain["Name"].."TargetFrame"
				frame.Parent = children2
				local drop1 = Instance.new("TextButton")
				drop1.AutoButtonColor = false
				drop1.Size = UDim2.new(0, 198, 0, 39)
				drop1.Position = UDim2.new(0, 11, 0, 5)
				drop1.Parent = frame
				drop1.BorderSizePixel = 0
				drop1.ZIndex = 2
				drop1.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
				drop1.TextSize = 17
				drop1.TextXAlignment = Enum.TextXAlignment.Left
				drop1.Text = ""
				local targeticon = Instance.new("ImageLabel")
				targeticon.Size = UDim2.new(0, 14, 0, 12)
				targeticon.Position = UDim2.new(0, 12, 0, 14)
				targeticon.BackgroundTransparency = 1
				targeticon.Image = downloadVapeAsset("vape/assets/CircleList"..(argstablemain3["Type"] == "Blacklist" and "Blacklist" or "Whitelist")..".png")
				targeticon.ZIndex = 2
				targeticon.Parent = drop1
				local targettext = Instance.new("TextLabel")
				targettext.Size = UDim2.new(0, 190, 1, 0)
				targettext.Position = UDim2.new(0, 29, 0, 0)
				targettext.TextTruncate = Enum.TextTruncate.AtEnd
				targettext.BackgroundTransparency = 1
				targettext.ZIndex = 2
				targettext.TextSize = 17
				targettext.RichText = true
				targettext.TextColor3 = Color3.new(205, 205, 205)
				targettext.Text = "  "..argstablemain3["Name"].." \n "..'<font color="rgb(151, 151, 151)">None</font>'
				targettext.Font = Enum.Font.SourceSans
				targettext.TextXAlignment = Enum.TextXAlignment.Left
				targettext.Parent = drop1
				local thing = Instance.new("Frame")
				thing.Size = UDim2.new(1, 2, 1, 2)
				thing.BorderSizePixel = 0
				thing.Position = UDim2.new(0, -1, 0, -1)
				thing.ZIndex = 1
				thing.BackgroundColor3 = Color3.fromRGB(38, 37, 38)
				thing.Parent = drop1
				local uicorner = Instance.new("UICorner")
				uicorner.CornerRadius = UDim.new(0, 4)
				uicorner.Parent = drop1
				local uicorner2 = Instance.new("UICorner")
				uicorner2.CornerRadius = UDim.new(0, 4)
				uicorner2.Parent = thing
				local windowtitle = Instance.new("TextButton")
				windowtitle.Text = ""
				windowtitle.AutoButtonColor = false
				windowtitle.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
				windowtitle.Size = UDim2.new(0, 220, 0, 41)
				windowtitle.Position = UDim2.new(1, 1, 0, 0)
				windowtitle.Name = "CircleWindow"
				windowtitle.Visible = false
				windowtitle.ZIndex = 3
				windowtitle.Parent = clickgui
				frame:GetPropertyChangedSignal("AbsolutePosition"):Connect(function()
					windowtitle.Position = UDim2.new(0, frame.Size.X.Offset + frame.AbsolutePosition.X + 2, 0, frame.AbsolutePosition.Y)
				end)
				local windowshadow = Instance.new("ImageLabel")
				windowshadow.AnchorPoint = Vector2.new(0.5, 0.5)
				windowshadow.Position = UDim2.new(0.5, 0, 0.5, 0)
				windowshadow.Image = downloadVapeAsset("vape/assets/WindowBlur.png")
				windowshadow.BackgroundTransparency = 1
				windowshadow.ZIndex = -1
				windowshadow.Size = UDim2.new(1, 6, 1, 6)
				windowshadow.ImageColor3 = Color3.new(0, 0, 0)
				windowshadow.ScaleType = Enum.ScaleType.Slice
				windowshadow.SliceCenter = Rect.new(10, 10, 118, 118)
				windowshadow.Parent = windowtitle
				local windowicon = Instance.new("ImageLabel")
				windowicon.Size = UDim2.new(0, 18, 0, 16)
				windowicon.Image = downloadVapeAsset("vape/assets/CircleList"..(argstablemain3["Type"] == "Blacklist" and "Blacklist" or "Whitelist")..".png")
				windowicon.ImageColor3 = Color3.fromRGB(200, 200, 200)
				windowicon.ZIndex = 3
				windowicon.Name = "WindowIcon"
				windowicon.BackgroundTransparency = 1
				windowicon.Position = UDim2.new(0, 12, 0, 12)
				windowicon.Parent = windowtitle
				local windowtext = Instance.new("TextLabel")
				windowtext.Size = UDim2.new(0, 155, 0, 41)
				windowtext.BackgroundTransparency = 1
				windowtext.Name = "WindowTitle"
				windowtext.Position = UDim2.new(0, 36, 0, 1)
				windowtext.ZIndex = 3
				windowtext.TextXAlignment = Enum.TextXAlignment.Left
				windowtext.Font = Enum.Font.Arial
				windowtext.TextSize = 14
				windowtext.Text = (translations[argstablemain3["Name"]] ~= nil and translations[argstablemain3["Name"]] or argstablemain3["Name"])
				windowtext.TextColor3 = Color3.fromRGB(200, 200, 200)
				windowtext.Parent = windowtitle
				local children = Instance.new("Frame")
				children.BackgroundTransparency = 1
				children.Size = UDim2.new(1, 0, 1, -4)
				children.ZIndex = 3
				children.Position = UDim2.new(0, 0, 0, 41)
				children.Visible = true
				children.Parent = windowtitle
				local windowcorner = Instance.new("UICorner")
				windowcorner.CornerRadius = UDim.new(0, 4)
				windowcorner.Parent = windowtitle
				local uilistlayout = Instance.new("UIListLayout")
				uilistlayout.SortOrder = Enum.SortOrder.LayoutOrder
				uilistlayout.Parent = children
				uilistlayout:GetPropertyChangedSignal("AbsoluteContentSize"):Connect(function()
					windowtitle.Size = UDim2.new(0, 220, 0, 45 + uilistlayout.AbsoluteContentSize.Y)
				end)

				windowapi["UpdateIgnore"] = function()
					local str = ""
					for i,v in pairs(buttonreturned["CircleList"]["ObjectList"]) do
						local enabled = buttonreturned["CircleList"]["ObjectListEnabled"][i]
						if enabled then
							str = (str == "" and v or str..", "..v)
						end
					end
					if str == "" then
						str = "None"
					end
					if argstablemain3["UpdateFunction"] then
						argstablemain3["UpdateFunction"]()
					end
					targettext.Text = "  "..argstablemain3["Name"].." \n "..'<font color="rgb(151, 151, 151)">'..str..'</font>'
				end

				windowapi["CreateCircleTextList"] = function(argstable)
					local textGuiLibrary = {}
					local amount = #children:GetChildren()
					local frame = Instance.new("Frame")
					frame.Size = UDim2.new(0, 220, 0, 40)
					frame.BackgroundTransparency = 1
					frame.ZIndex = 5
					frame.ClipsDescendants = true
					frame.LayoutOrder = amount
					frame.Name = argstable["Name"]
					frame.Parent = children
					local textboxbkg = Instance.new("ImageLabel")
					textboxbkg.BackgroundTransparency = 1
					textboxbkg.Name = "AddBoxBKG"
					textboxbkg.Size = UDim2.new(0, (argstable["Name"] == "ProfilesList" and 150 or 200), 0, 31)
					textboxbkg.Position = UDim2.new(0, 10, 0, 5)
					textboxbkg.ZIndex = 6
					textboxbkg.ClipsDescendants = true
					textboxbkg.Image = downloadVapeAsset((argstable["Name"] == "ProfilesList" and "vape/assets/TextBoxBKG2.png" or "vape/assets/TextBoxBKG.png"))
					textboxbkg.Parent = frame
					local textbox = Instance.new("TextBox")
					textbox.Size = UDim2.new(0, 159, 1, 0)
					textbox.Position = UDim2.new(0, 11, 0, 0)
					textbox.ZIndex = 6
					textbox.TextXAlignment = Enum.TextXAlignment.Left
					textbox.Name = "AddBox"
					textbox.BackgroundTransparency = 1
					textbox.TextColor3 = Color3.new(1, 1, 1)
					textbox.PlaceholderColor3 = Color3.fromRGB(200, 200, 200)
					textbox.Font = Enum.Font.SourceSans
					textbox.Text = ""
					textbox.PlaceholderText = "Add entry..."
					textbox.TextSize = 17
					textbox.Parent = textboxbkg
					local addbutton = Instance.new("ImageButton")
					addbutton.BorderSizePixel = 0
					addbutton.Name = "AddButton"
					addbutton.ZIndex = 6
					addbutton.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
					addbutton.Position = UDim2.new(0, (argstable["Name"] == "ProfilesList" and 124 or 174), 0, 8)
					addbutton.AutoButtonColor = false
					addbutton.Size = UDim2.new(0, 16, 0, 16)
					addbutton.ImageColor3 = argstable["Color"]
					addbutton.Image = downloadVapeAsset("vape/assets/AddItem.png")
					addbutton.Parent = textboxbkg
					local scrollframebkg = Instance.new("Frame")
					scrollframebkg.ZIndex = 5
					scrollframebkg.Name = "ScrollingFrameBKG"
					scrollframebkg.Size = UDim2.new(0, 220, 0, 3)
					scrollframebkg.BackgroundTransparency = 1
					scrollframebkg.LayoutOrder = amount
					scrollframebkg.Parent = children
					local scrollframe = Instance.new("ScrollingFrame")
					scrollframe.ZIndex = 5
					scrollframe.Size = UDim2.new(0, 200, 0, 3)
					scrollframe.Position = UDim2.new(0, 10, 0, 0)
					scrollframe.BackgroundTransparency = 1
					scrollframe.ScrollBarThickness = 0
					scrollframe.ScrollBarImageColor3 = Color3.new(0, 0, 0)
					scrollframe.LayoutOrder = amount
					scrollframe.Parent = scrollframebkg
					local uilistlayout3 = Instance.new("UIListLayout")
					uilistlayout3.Padding = UDim.new(0, 3)
					uilistlayout3.Parent = scrollframe
					uilistlayout3:GetPropertyChangedSignal("AbsoluteContentSize"):Connect(function()
						scrollframe.CanvasSize = UDim2.new(0, 0, 0, uilistlayout3.AbsoluteContentSize.Y)
						scrollframe.Size = UDim2.new(0, 220, 0, math.clamp(uilistlayout3.AbsoluteContentSize.Y, 1, 105))
						scrollframebkg.Size = UDim2.new(0, 220, 0, math.clamp(uilistlayout3.AbsoluteContentSize.Y, 1, 105) + 3)
					end)

					textGuiLibrary["Object"] = frame
					textGuiLibrary["ScrollingObject"] = scrollframebkg
					textGuiLibrary["ObjectList"] = {}
					textGuiLibrary["ObjectListEnabled"] = {}
					local hoveredover = {}
					textGuiLibrary["RefreshValues"] = function(tab, tab2)
						textGuiLibrary["ObjectList"] = tab
						if tab2 then
							textGuiLibrary["ObjectListEnabled"] = tab2
						end
						windowapi["UpdateIgnore"]()
						for i2,v2 in pairs(scrollframe:GetChildren()) do
							if v2:IsA("TextButton") then v2:Remove() end
						end
						for i,v in pairs(textGuiLibrary["ObjectList"]) do
							local objenabled = textGuiLibrary["ObjectListEnabled"][i]
							local itemframe = Instance.new("TextButton")
							itemframe.Size = UDim2.new(0, 200, 0, 33)
							itemframe.Text = ""
							itemframe.AutoButtonColor = false
							itemframe.BackgroundColor3 = (hoveredover[i] and Color3.fromRGB(26, 25, 26) or Color3.fromRGB(31, 30, 31))
							itemframe.BorderSizePixel = 0
							itemframe.ZIndex = 5
							itemframe.Parent = scrollframe
							local itemcorner = Instance.new("UICorner")
							itemcorner.CornerRadius = UDim.new(0, 6)
							itemcorner.Parent = itemframe
							local itemtext = Instance.new("TextLabel")
							itemtext.BackgroundTransparency = 1
							itemtext.Size = UDim2.new(0, 157, 0, 33)
							itemtext.Name = "ItemText"
							itemtext.ZIndex = 5
							itemtext.Position = UDim2.new(0, 36, 0, 0)
							itemtext.Font = Enum.Font.SourceSans
							itemtext.TextSize = 17
							itemtext.Text = v
							itemtext.TextXAlignment = Enum.TextXAlignment.Left
							itemtext.TextColor3 = (objenabled and Color3.fromRGB(160, 160, 160) or Color3.fromRGB(90, 90, 90))
							itemtext.Parent = itemframe
							local friendcircle = Instance.new("Frame")
							friendcircle.Size = UDim2.new(0, 10, 0, 10)
							friendcircle.Name = "FriendCircle"
							friendcircle.ZIndex = 5
							friendcircle.BackgroundColor3 = (objenabled and argstable["Color"] or Color3.fromRGB(120, 120, 120))
							friendcircle.BorderSizePixel = 0
							friendcircle.Position = UDim2.new(0, 10, 0, 13)
							friendcircle.Parent = itemframe
							local friendcorner = Instance.new("UICorner")
							friendcorner.CornerRadius = UDim.new(0, 8)
							friendcorner.Parent = friendcircle
							local friendcircle2 = friendcircle:Clone()
							friendcircle2.Size = UDim2.new(0, 8, 0, 8)
							friendcircle2.BackgroundColor3 = Color3.fromRGB(31, 31, 31)
							friendcircle2.Position = UDim2.new(0, 1, 0, 1)
							friendcircle2.Visible = not objenabled
							friendcircle2.Parent = friendcircle
							itemframe:GetPropertyChangedSignal("BackgroundColor3"):Connect(function()
								friendcircle2.BackgroundColor3 = itemframe.BackgroundColor3
							end)
							itemframe.MouseEnter:Connect(function()
								itemframe.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
								hoveredover[i] = true
							end)
							itemframe.MouseLeave:Connect(function()
								itemframe.BackgroundColor3 = Color3.fromRGB(31, 30, 31)
								hoveredover[i] = nil
							end)
							itemframe.MouseButton1Click:Connect(function()
								textGuiLibrary["ObjectListEnabled"][i] = not textGuiLibrary["ObjectListEnabled"][i]
								textGuiLibrary["RefreshValues"](textGuiLibrary["ObjectList"])
							end)
							itemframe.MouseButton2Click:Connect(function()
								textGuiLibrary["ObjectListEnabled"][i] = not textGuiLibrary["ObjectListEnabled"][i]
								textGuiLibrary["RefreshValues"](textGuiLibrary["ObjectList"])
							end)
							local deletebutton = Instance.new("ImageButton")
							deletebutton.Size = UDim2.new(0, 6, 0, 6)
							deletebutton.BackgroundTransparency = 1
							deletebutton.AutoButtonColor = false
							deletebutton.ZIndex = 5
							deletebutton.Image = downloadVapeAsset("vape/assets/AddRemoveIcon1.png")
							deletebutton.Position = UDim2.new(1, -16, 0, 14)
							deletebutton.Parent = itemframe
							deletebutton.MouseButton1Click:Connect(function()
								table.remove(textGuiLibrary["ObjectList"], i)
								textGuiLibrary["ObjectListEnabled"][i] = nil
								textGuiLibrary["RefreshValues"](textGuiLibrary["ObjectList"])
								if argstable["RemoveFunction"] then
									argstable["RemoveFunction"](i, v)
								end
							end)
						end
					end

					GuiLibrary.ObjectsThatCanBeSaved[argstablemain["Name"]..argstable["Name"].."TextCircleList"] = {["Type"] = "TextCircleList", ["Api"] = textGuiLibrary}
					local function AddToList()
                        local num = #textGuiLibrary["ObjectList"] + 1
                        textGuiLibrary["ObjectList"][num] = textbox.Text
                        textGuiLibrary["ObjectListEnabled"][num] = true
                        textGuiLibrary["RefreshValues"](textGuiLibrary["ObjectList"])
                        if argstable["AddFunction"] then
                            argstable["AddFunction"](textbox.Text)
                        end
                        textbox.Text = ""
                    end
                    addbutton.MouseButton1Click:Connect(AddToList)
                    textbox.FocusLost:Connect(function(enter)
                        if enter then
                            AddToList()
                            textbox:CaptureFocus()
                        end
                    end)
					return textGuiLibrary
				end

				--[[windowapi["CreateButton"] = function(argstable)
					local buttonapi = {}
					local amount = #children:GetChildren()
					local buttontext = Instance.new("TextButton")
					buttontext.Name = argstablemain["Name"]..argstable["Name"].."TargetButton"
					buttontext.LayoutOrder = amount
					buttontext.AutoButtonColor = false
					buttontext.Size = UDim2.new(0, 45, 0, 29)
					buttontext.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
					buttontext.Active = false
					buttontext.Text = ""
					buttontext.ZIndex = 4
					buttontext.Font = Enum.Font.SourceSans
					buttontext.TextXAlignment = Enum.TextXAlignment.Left
					buttontext.Position = argstable["Position"]
					buttontext.Parent = buttonframeholder
					local buttonbkg = Instance.new("Frame")
					buttonbkg.BackgroundColor3 = Color3.fromRGB(38, 37, 38)
					buttonbkg.Size = UDim2.new(0, 47, 0, 31)
					buttonbkg.Position = argstable["Position"] - UDim2.new(0, 1, 0, 1)
					buttonbkg.ZIndex = 3
					buttonbkg.Parent = buttonframeholder
					local buttonimage = Instance.new("ImageLabel")
					buttonimage.BackgroundTransparency = 1
					buttonimage.Position = UDim2.new(0, 14, 0, 7)
					buttonimage.Size = UDim2.new(0, argstable["IconSize"], 0, 16)
					buttonimage.Image = downloadVapeAsset(argstable["Icon"])
					buttonimage.ImageColor3 = Color3.fromRGB(121, 121, 121)
					buttonimage.ZIndex = 5
					buttonimage.Active = false
					buttonimage.Parent = buttontext
					local buttontexticon = Instance.new("ImageLabel")
					buttontexticon.Size = UDim2.new(0, argstable["IconSize"] - 3, 0, 12)
					buttontexticon.Image = downloadVapeAsset(argstable["Icon"])
					buttontexticon.LayoutOrder = amount
					buttontexticon.ZIndex = 4
					buttontexticon.BackgroundTransparency = 1
					buttontexticon.Visible = false
					buttontexticon.Parent = targetframe
					local buttonround1 = Instance.new("UICorner")
					buttonround1.CornerRadius = UDim.new(0, 5)
					buttonround1.Parent = buttontext
					local buttonround2 = Instance.new("UICorner")
					buttonround2.CornerRadius = UDim.new(0, 5)
					buttonround2.Parent = buttonbkg
					buttonapi["Enabled"] = false
					buttonapi["Default"] = argstable["Default"]

					buttonapi["ToggleButton"] = function(toggle, frist)
						buttonapi["Enabled"] = toggle
						buttontexticon.Visible = toggle
						if buttonapi["Enabled"] then
							if not first then
								tweenService:Create(buttontext, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Hue"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Sat"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Value"])}):Play()
							else
								buttontext.BackgroundColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Hue"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Sat"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Value"])
							end
						else
							if not first then
								tweenService:Create(buttontext, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(26, 25, 26)}):Play()
							else
								buttontext.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
							end
						end
						buttonimage.ImageColor3 = (buttonapi["Enabled"] and Color3.new(1, 1, 1) or Color3.fromRGB(121, 121, 121))
						argstable["Function"](buttonapi["Enabled"])
					end

					if argstable["Default"] then
						buttonapi["ToggleButton"](argstable["Default"], true)
					end
					buttontext.MouseButton1Click:Connect(function() buttonapi["ToggleButton"](not buttonapi["Enabled"], false) end)
					GuiLibrary.ObjectsThatCanBeSaved[argstablemain["Name"]..argstable["Name"].."TargetButton"] = {["Type"] = "TargetButton", ["Object"] = buttontext, ["Api"] = buttonapi}
					return buttonapi
				end]]

				buttonreturned["CircleList"] = windowapi.CreateCircleTextList({
					Name = "CircleList",
					Color = (argstablemain3["Type"] == "Blacklist" and Color3.fromRGB(250, 50, 56) or Color3.fromRGB(5, 134, 105))
				})

				drop1.MouseButton1Click:Connect(function()
					windowtitle.Visible = not windowtitle.Visible
					if not windowtitle.Visible then
						tweenService:Create(thing, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(107, 107, 107)}):Play()
					end
				end)
				drop1.MouseEnter:Connect(function()
					if not windowtitle.Visible then
						tweenService:Create(thing, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(107, 107, 107)}):Play()
					end
				end)
				drop1.MouseLeave:Connect(function()
					if not windowtitle.Visible then
						tweenService:Create(thing, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(38, 37, 38)}):Play()
					end
				end)

				GuiLibrary.ObjectsThatCanBeSaved[argstablemain["Name"].."CircleListFrame"] = {["Type"] = "CircleListFrame", ["Object"] = frame, ["Object2"] = windowtitle, ["Api"] = buttonreturned}

				return buttonreturned
			end

			buttonapi["CreateDropdown"] = function(argstable)
				local dropGuiLibrary = {}
				local list = argstable["List"]
				local amount2 = #children2:GetChildren()
				local frame = Instance.new("Frame")
				frame.Size = UDim2.new(0, 220, 0, 40)
				frame.BackgroundTransparency = 1
				frame.LayoutOrder = amount2
				frame.Name = argstable["Name"]
				frame.Parent = children2
				local drop1 = Instance.new("TextButton")
				drop1.AutoButtonColor = false
				drop1.Size = UDim2.new(0, 198, 0, 29)
				drop1.Position = UDim2.new(0, 11, 0, 5)
				drop1.Parent = frame
				drop1.BorderSizePixel = 0
				drop1.ZIndex = 2
				drop1.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
				drop1.TextSize = 14
				drop1.TextXAlignment = Enum.TextXAlignment.Left
				drop1.TextColor3 = Color3.fromRGB(160, 160, 160)
				drop1.Text = "           "..(translations[argstable["Name"]] ~= nil and translations[argstable["Name"]] or argstable["Name"]).." - "..(list ~= {} and list[1] or "")
				drop1.TextTruncate = Enum.TextTruncate.AtEnd
				drop1.Font = Enum.Font.Arial
				local expandbutton2 = Instance.new("ImageLabel")
				expandbutton2.Active = false
				expandbutton2.Size = UDim2.new(0, 9, 0, 4)
				expandbutton2.Image = downloadVapeAsset("vape/assets/DownArrow.png")
				expandbutton2.ZIndex = 5
				expandbutton2.Position = UDim2.new(1, -19, 1, -16)
				expandbutton2.Name = "ExpandButton2"
				expandbutton2.BackgroundTransparency = 0
				expandbutton2.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
				expandbutton2.BorderSizePixel = 0
				expandbutton2.Parent = drop1
				local drop2 = drop1:Clone()
				drop2.Name = "MainButton"
				drop2.Position = UDim2.new(0, 0, 0, 0)
				drop2.ZIndex = 9
				drop2.BackgroundTransparency = 1
				drop1:GetPropertyChangedSignal("Text"):Connect(function()
					drop2.Text = drop1.Text
				end)
				drop2.ExpandButton2.Image = downloadVapeAsset("vape/assets/UpArrow.png")
				drop2.ExpandButton2.ZIndex = 10
				local thing = Instance.new("Frame")
				thing.Size = UDim2.new(1, 2, 1, 2)
				thing.BorderSizePixel = 0
				thing.Position = UDim2.new(0, -1, 0, -1)
				thing.ZIndex = 1
				thing.BackgroundColor3 = Color3.fromRGB(34, 34, 34)
				thing.Parent = drop1
				local uicorner = Instance.new("UICorner")
				uicorner.CornerRadius = UDim.new(0, 6)
				uicorner.Parent = drop1
				local uicorner2 = Instance.new("UICorner")
				uicorner2.CornerRadius = UDim.new(0, 6)
				uicorner2.Parent = thing
				local dropframe = Instance.new("Frame")
				dropframe.ZIndex = 7
				dropframe.Parent = drop1
				dropframe.Position = UDim2.new(0, 0, 0, 0)
				dropframe.Size = UDim2.new(1, 0, 0, 0)
				dropframe.BackgroundTransparency = 0
				dropframe.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
				dropframe.Visible = false
				local uicorner3 = Instance.new("UICorner")
				uicorner3.CornerRadius = UDim.new(0, 6)
				uicorner3.Parent = dropframe
				local thing2 = thing:Clone()
				thing2.ZIndex = 2
				thing2.BackgroundColor3 = Color3.fromRGB(53, 52, 53)
				thing2.Parent = dropframe
				drop2.Parent = dropframe
				drop2.MouseButton1Click:Connect(function()
					dropframe.Visible = not dropframe.Visible
					local num = (dropframe.Visible and 10 or 0) + (uilistlayout2.AbsoluteContentSize.Y + (dropframe.Visible and #dropframe:GetChildren() * (dropframe.Visible and 13 or 9) * (GuiLibrary["MainRescale"].Scale) or 0) + (40 * GuiLibrary["MainRescale"].Scale)) * (1 / GuiLibrary["MainRescale"].Scale)
					frame.Size = UDim2.new(0, 220, 0, 40)
					--	children.CanvasSize = UDim2.new(0, 0, 0, num)
				--	windowtitle.Size = UDim2.new(0, 220, 0, math.clamp(45 + num, 0, 605))
				end)
				drop1.MouseButton1Click:Connect(function()
					dropframe.Visible = not dropframe.Visible
					local num = (dropframe.Visible and 40 or 0) + (uilistlayout2.AbsoluteContentSize.Y + (dropframe.Visible and #dropframe:GetChildren() * (dropframe.Visible and 13 or 9) * (GuiLibrary["MainRescale"].Scale) or 0) + (40 * GuiLibrary["MainRescale"].Scale)) * (1 / GuiLibrary["MainRescale"].Scale)
					frame.Size = UDim2.new(0, 220, 0, dropframe.Size.Y.Offset + 10)
					--	children.CanvasSize = UDim2.new(0, 0, 0, num)
				--	windowtitle.Size = UDim2.new(0, 220, 0, math.clamp(45 + num, 0, 605))
				end)
				drop1.MouseEnter:Connect(function()
					thing.BackgroundColor3 = Color3.fromRGB(49, 48, 49)
				end)
				drop1.MouseLeave:Connect(function()
					thing.BackgroundColor3 = Color3.fromRGB(34, 34, 34)
				end)
				frame.MouseEnter:Connect(function()
					if argstable["HoverText"] and type(argstable["HoverText"]) == "string" then
						hoverbox.Visible = (GuiLibrary["ToggleTooltips"] and hoverbox.TextSize ~= 1)
						local textsize = textService:GetTextSize(argstable["HoverText"], hoverbox.TextSize, hoverbox.Font, Vector2.new(99999, 99999))
						hoverbox.Text = "  "..argstable["HoverText"]:gsub("\n", "\n  ")
						hoverbox.Size = UDim2.new(0, 13 + textsize.X, 0, textsize.Y + 5)
					end
				end)
				if argstable["HoverText"] and type(argstable["HoverText"]) == "string" then
					frame.MouseMoved:Connect(function(x, y)
						hoverbox.Visible = (GuiLibrary["ToggleTooltips"] and hoverbox.TextSize ~= 1)
						hoverbox.Position = UDim2.new(0, (x + 16) * (1 / GuiLibrary["MainRescale"].Scale), 0,	(y - (hoverbox.Size.Y.Offset / 2) - 26) * (1 / GuiLibrary["MainRescale"].Scale))
					end)
				end
				frame.MouseLeave:Connect(function()
					hoverbox.Visible = false
					if buttonapi["Enabled"] == false then
						pcall(function()
							tweenService:Create(toggleframe1, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(60, 60, 60)}):Play()
						end)
					end
				end)
				local placeholder = 0
				dropGuiLibrary["Value"] = (list ~= {} and list[1] or "")
				dropGuiLibrary["Default"] = dropGuiLibrary["Value"]
				dropGuiLibrary["Object"] = frame
				dropGuiLibrary["List"] = list
				dropGuiLibrary["UpdateList"] = function(val)
					placeholder = 25
					list = val
					dropGuiLibrary["List"] = val
					if not table.find(list, dropGuiLibrary["Value"]) then
						dropGuiLibrary["Value"] = list[1]
						drop1.Text = "         "..(translations[argstable["Name"]] ~= nil and translations[argstable["Name"]] or argstable["Name"]).." - "..list[1]
						dropframe.Visible = false
						argstable["Function"](list[1])
					end
					for del1, del2 in pairs(dropframe:GetChildren()) do if del2:IsA("TextButton") and del2.Name ~= "MainButton" then del2:Remove() end end
					for numbe, listobj in pairs(val) do
						if listobj == dropGuiLibrary["Value"] then continue end
						local drop2 = Instance.new("TextButton")
						dropframe.Size = UDim2.new(0, 198, 0, placeholder + 21)
						drop2.Text = "       "..listobj
						drop2.LayoutOrder = numbe
						drop2.TextColor3 = Color3.fromRGB(160, 160, 160)
						drop2.AutoButtonColor = false
						drop2.BackgroundTransparency = 1
						drop2.TextXAlignment = Enum.TextXAlignment.Left
						drop2.Size = UDim2.new(0, 198, 0, 21)
						drop2.Position = UDim2.new(0, 2, 0, placeholder - 4)
						drop2.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
						drop2.Font = Enum.Font.Arial
						drop2.TextSize = 14
						drop2.ZIndex = 8
						drop2.BorderSizePixel = 0
						drop2.Name = listobj
						drop2.Parent = dropframe
						drop2.MouseButton1Click:Connect(function()
							dropGuiLibrary["Value"] = listobj
							drop1.Text = "         "..(translations[argstable["Name"]] ~= nil and translations[argstable["Name"]] or argstable["Name"]).." - "..listobj
							dropframe.Visible = false
							local num = (uilistlayout2.AbsoluteContentSize.Y + (dropframe.Visible and #dropframe:GetChildren() * 9 or 0) + (40 * GuiLibrary["MainRescale"].Scale)) * (1 / GuiLibrary["MainRescale"].Scale)
							frame.Size = UDim2.new(0, 220, 0, 40)
							--children.CanvasSize = UDim2.new(0, 0, 0, num)
							--windowtitle.Size = UDim2.new(0, 220, 0, math.clamp(45 + num, 0, 605))
							argstable["Function"](listobj)
							dropGuiLibrary["UpdateList"](list)
							GuiLibrary["UpdateHudEvent"]:Fire()
						end)
						placeholder = placeholder + 21
					end
				end
				dropGuiLibrary["SetValue"] = function(listobj)
					dropGuiLibrary["Value"] = listobj
					drop1.Text = "         "..(translations[argstable["Name"]] ~= nil and translations[argstable["Name"]] or argstable["Name"]).." - "..listobj
					dropframe.Visible = false
					argstable["Function"](listobj)
					dropGuiLibrary["UpdateList"](list)
				end
				dropGuiLibrary["UpdateList"](list)
				if buttonapi["HasExtraText"] then
					GuiLibrary["UpdateHudEvent"]:Fire()
				end
				GuiLibrary.ObjectsThatCanBeSaved[argstablemain["Name"]..argstable["Name"].."Dropdown"] = {["Type"] = "Dropdown", ["Object"] = frame, ["Api"] = dropGuiLibrary}

				return dropGuiLibrary
			end

			buttonapi["CreateColorSlider"] = function(argstable)
				local min, max = 0, 1
				local sliderapi = {}
				local amount2 = #children2:GetChildren()
				local frame = Instance.new("Frame")
				frame.Size = UDim2.new(0, 220, 0, 50)
				frame.BorderSizePixel = 0
				frame.BackgroundTransparency = 1
				frame.LayoutOrder = amount2
				frame.Name = argstable["Name"]
				frame.Parent = children2
				local text1 = Instance.new("TextLabel")
				text1.Font = Enum.Font.Arial
				text1.TextXAlignment = Enum.TextXAlignment.Left
				text1.Text = "          "..(translations[argstable["Name"]] ~= nil and translations[argstable["Name"]] or argstable["Name"])
				text1.Size = UDim2.new(1, 0, 0, 27)
				text1.TextColor3 = Color3.fromRGB(160, 160, 160)
				text1.BackgroundTransparency = 1
				text1.TextSize = 12
				text1.Parent = frame
				local text2 = Instance.new("Frame")
				text2.Size = UDim2.new(0, 12, 0, 12)
				text2.Position = UDim2.new(1, -22, 0, 9)
				text2.BackgroundColor3 = Color3.fromHSV(0.44, 1, 1)
				text2.Parent = frame
				local uicorner4 = Instance.new("UICorner")
				uicorner4.CornerRadius = UDim.new(0, 4)
				uicorner4.Parent = text2
				local slider1 = Instance.new("TextButton")
				slider1.AutoButtonColor = false
				slider1.Text = ""
				slider1.Size = UDim2.new(0, 200, 0, 2)
				slider1.BorderSizePixel = 0
				slider1.BackgroundColor3 = Color3.new(1, 1, 1)
				slider1.Position = UDim2.new(0, 10, 0, 32)
				slider1.Name = "Slider"
				slider1.Parent = frame
				local uigradient = Instance.new("UIGradient")
				uigradient.Color = ColorSequence.new({ColorSequenceKeypoint.new(0, Color3.fromHSV(0, 1, 1)), ColorSequenceKeypoint.new(0.2, Color3.fromHSV(0.2, 1, 1)), ColorSequenceKeypoint.new(0.3, Color3.fromHSV(0.3, 1, 1)), ColorSequenceKeypoint.new(0.4, Color3.fromHSV(0.4, 1, 1)), ColorSequenceKeypoint.new(0.5, Color3.fromHSV(0.5, 1, 1)), ColorSequenceKeypoint.new(0.6, Color3.fromHSV(0.6, 1, 1)), ColorSequenceKeypoint.new(0.7, Color3.fromHSV(0.7, 1, 1)), ColorSequenceKeypoint.new(0.8, Color3.fromHSV(0.8, 1, 1)), ColorSequenceKeypoint.new(0.9, Color3.fromHSV(0.9, 1, 1)), ColorSequenceKeypoint.new(1, Color3.fromHSV(1, 1, 1))})
				uigradient.Parent = slider1
				local slider3 = Instance.new("ImageButton")
				slider3.AutoButtonColor = false
				slider3.Size = UDim2.new(0, 24, 0, 16)
				slider3.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
				slider3.BorderSizePixel = 0
				slider3.Image = downloadVapeAsset("vape/assets/SliderButton1.png")
				slider3.Position = UDim2.new(0.44, -11, 0, -7)
				slider3.Parent = slider1
				slider3.Name = "ButtonSlider"
				local slidersat = frame:Clone()
				slidersat.TextLabel.Text = "    Saturation"
				slidersat.Name = frame.Name.."Saturation"
				slidersat.BackgroundTransparency = 0
				slidersat.Visible = false
				slidersat.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
				slidersat.Slider.UIGradient.Color = ColorSequence.new({ColorSequenceKeypoint.new(0, Color3.fromHSV(0, 0, 1)), ColorSequenceKeypoint.new(1, Color3.fromHSV(0.4, 1, 1))})
				slidersat.Slider.ButtonSlider.Position = UDim2.new(0.95, -11, 0, -7)
				slidersat.Slider.ButtonSlider.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
				slidersat.Frame:Remove()
				slidersat.Parent = children2
				local sliderval = frame:Clone()
				sliderval.TextLabel.Text = "    Vibrance"
				sliderval.Name = frame.Name.."Vibrance"
				sliderval.BackgroundTransparency = 0
				sliderval.Visible = false
				sliderval.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
				sliderval.Slider.UIGradient.Color = ColorSequence.new({ColorSequenceKeypoint.new(0, Color3.fromHSV(0, 0, 0)), ColorSequenceKeypoint.new(1, Color3.fromHSV(0.4, 1, 1))})
				sliderval.Slider.ButtonSlider.Position = UDim2.new(0.95, -11, 0, -7)
				sliderval.Slider.ButtonSlider.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
				sliderval.Frame:Remove()
				sliderval.Parent = children2
				local sliderexpand = Instance.new("ImageButton")
				sliderexpand.AutoButtonColor = false
				sliderexpand.Size = UDim2.new(0, 15, 0, 15)
				sliderexpand.BackgroundTransparency = 1
				sliderexpand.Position = UDim2.new(0, textService:GetTextSize(text1.Text, text1.TextSize, text1.Font, Vector2.new(10000, 100000)).X + 3, 0, 6)
				sliderexpand.Image = downloadVapeAsset("vape/assets/HoverArrow3.png")
				sliderexpand.Parent = frame
				sliderexpand.MouseEnter:Connect(function()
					sliderexpand.Image = downloadVapeAsset("vape/assets/HoverArrow4.png")
				end)
				sliderexpand.MouseLeave:Connect(function()
					sliderexpand.Image = downloadVapeAsset("vape/assets/HoverArrow3.png")
				end)
				sliderexpand.MouseButton1Click:Connect(function()
					local val = not slidersat.Visible
					slidersat.Visible = val
					sliderval.Visible = val
					sliderexpand.Rotation = (val and 180 or 0)
				end)
				sliderapi["Hue"] = (argstable["Default"] or 0.44)
				sliderapi["Sat"] = 1
				sliderapi["Value"] = 1
				sliderapi["Object"] = frame
				sliderapi["RainbowValue"] = false
				sliderapi["SetValue"] = function(hue, sat, val)
					hue = (hue or sliderapi["Hue"])
					sat = (sat or sliderapi["Sat"])
					val = (val or sliderapi["Value"])
					text2.BackgroundColor3 = Color3.fromHSV(hue, sat, val)
					pcall(function()
						slidersat.Slider.UIGradient.Color = ColorSequence.new({ColorSequenceKeypoint.new(0, Color3.fromHSV(0, 0, val)), ColorSequenceKeypoint.new(1, Color3.fromHSV(hue, 1, val))})
						sliderval.Slider.UIGradient.Color = ColorSequence.new({ColorSequenceKeypoint.new(0, Color3.fromHSV(0, 0, 0)), ColorSequenceKeypoint.new(1, Color3.fromHSV(hue, sat, 1))})
						slidersat.Slider.ButtonSlider.Position = UDim2.new(math.clamp(sat, 0.02, 0.95), -9, 0, -7)
						sliderval.Slider.ButtonSlider.Position = UDim2.new(math.clamp(val, 0.02, 0.95), -9, 0, -7)
					end)
					sliderapi["Hue"] = hue
					sliderapi["Sat"] = sat
					sliderapi["Value"] = val
					slider3.Position = UDim2.new(math.clamp(hue, 0.02, 0.95), -9, 0, -7)
					argstable["Function"](hue, sat, val)
				end
				sliderapi["SetRainbow"] = function(val)
					sliderapi["RainbowValue"] = val
					if sliderapi["RainbowValue"] then
						table.insert(GuiLibrary.RainbowSliders, sliderapi)
					else
						table.remove(GuiLibrary.RainbowSliders, table.find(GuiLibrary.RainbowSliders, sliderapi))
					end
				end
				local clicktick = tick()
				local function slidercode(obj, valtochange)
					if clicktick > tick() then
						sliderapi["SetRainbow"](not sliderapi["RainbowValue"])
					end
					clicktick = tick() + 0.3
					local x,y,xscale,yscale,xscale2 = RelativeXY(obj, inputService:GetMouseLocation())
					sliderapi["SetValue"]((valtochange == "Hue" and (min + ((max - min) * xscale)) or false), (valtochange == "Sat" and (min + ((max - min) * xscale)) or false), (valtochange == "Value" and (min + ((max - min) * xscale)) or false))
					obj.ButtonSlider.Position = UDim2.new(math.clamp(xscale2, 0.02, 0.95), -9, 0, -7)
					local move
					local kill
					move = inputService.InputChanged:Connect(function(input)
						if input.UserInputType == Enum.UserInputType.MouseMovement then
							local x,y,xscale,yscale,xscale2 = RelativeXY(obj, inputService:GetMouseLocation())
							sliderapi["SetValue"]((valtochange == "Hue" and (min + ((max - min) * xscale)) or false), (valtochange == "Sat" and (min + ((max - min) * xscale)) or false), (valtochange == "Value" and (min + ((max - min) * xscale)) or false))
							obj.ButtonSlider.Position = UDim2.new(math.clamp(xscale2, 0.02, 0.95), -9, 0, -7)
						end
					end)
					kill = inputService.InputEnded:Connect(function(input)
						if input.UserInputType == Enum.UserInputType.MouseButton1 then
							move:Disconnect()
							kill:Disconnect()
						end
					end)
				end
				slider1.MouseButton1Down:Connect(function()
					slidercode(slider1, "Hue")
				end)
				slider3.MouseButton1Down:Connect(function()
					slidercode(slider1, "Hue")
				end)
				slidersat.Slider.MouseButton1Down:Connect(function()
					slidercode(slidersat.Slider, "Sat")
				end)
				slidersat.Slider.ButtonSlider.MouseButton1Down:Connect(function()
					slidercode(slidersat.Slider, "Sat")
				end)
				sliderval.Slider.MouseButton1Down:Connect(function()
					slidercode(sliderval.Slider, "Value")
				end)
				sliderval.Slider.ButtonSlider.MouseButton1Down:Connect(function()
					slidercode(sliderval.Slider, "Value")
				end)

				frame.MouseEnter:Connect(function()
					if argstable["HoverText"] and type(argstable["HoverText"]) == "string" then
						hoverbox.Visible = (GuiLibrary["ToggleTooltips"] and hoverbox.TextSize ~= 1)
						local textsize = textService:GetTextSize(argstable["HoverText"], hoverbox.TextSize, hoverbox.Font, Vector2.new(99999, 99999))
						hoverbox.Text = "  "..argstable["HoverText"]:gsub("\n", "\n  ")
						hoverbox.Size = UDim2.new(0, 13 + textsize.X, 0, textsize.Y + 5)
					end
				end)
				if argstable["HoverText"] and type(argstable["HoverText"]) == "string" then
					frame.MouseMoved:Connect(function(x, y)
						hoverbox.Visible = (GuiLibrary["ToggleTooltips"] and hoverbox.TextSize ~= 1)
						hoverbox.Position = UDim2.new(0, (x + 16) * (1 / GuiLibrary["MainRescale"].Scale), 0,	(y - (hoverbox.Size.Y.Offset / 2) - 26) * (1 / GuiLibrary["MainRescale"].Scale))
					end)
				end
				frame.MouseLeave:Connect(function()
					hoverbox.Visible = false
					if buttonapi["Enabled"] == false then
						pcall(function()
							tweenService:Create(toggleframe1, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(60, 60, 60)}):Play()
						end)
					end
				end)
				GuiLibrary.ObjectsThatCanBeSaved[argstablemain["Name"]..argstable["Name"].."SliderColor"] = {["Type"] = "ColorSlider", ["Object"] = frame, ["Object2"] = slidersat, ["Object3"] = sliderval, ["Api"] = sliderapi}
				return sliderapi
			end

			buttonapi["CreateSlider"] = function(argstable)
				local sliderapi = {}
				local amount2 = #children2:GetChildren()
				local frame = Instance.new("Frame")
				frame.Size = UDim2.new(0, 220, 0, 50)
				frame.BackgroundTransparency = 1
				frame.ClipsDescendants = true
				frame.LayoutOrder = amount2
				frame.Name = argstable["Name"]
				frame.Parent = children2
				local text1 = Instance.new("TextLabel")
				text1.Font = Enum.Font.Arial
				text1.TextXAlignment = Enum.TextXAlignment.Left
				text1.Text = "          "..(translations[argstable["Name"]] ~= nil and translations[argstable["Name"]] or argstable["Name"])
				text1.Size = UDim2.new(1, 0, 0, 25)
				text1.TextColor3 = Color3.fromRGB(160, 160, 160)
				text1.Position = UDim2.new(0, 0, 0, 4)
				text1.BackgroundTransparency = 1
				text1.TextSize = 12
				text1.Parent = frame
				local text2 = Instance.new("TextButton")
				text2.Font = Enum.Font.Arial
				text2.AutoButtonColor = false
				text2.TextXAlignment = Enum.TextXAlignment.Right
				text2.Text = tostring((argstable["Default"] or argstable["Min"])) .. " "..(argstable["Percent"] and "%" or " ").." "
				text2.Size = UDim2.new(0, 40, 0, 25)
				text2.Position = UDim2.new(1, -40, 0, 4)
				text2.TextColor3 = Color3.fromRGB(160, 160, 160)
				text2.BackgroundTransparency = 1
				text2.TextSize = 12
				text2.Parent = frame
				local text3 = Instance.new("TextBox")
				text3.Visible = false
				text3.Font = Enum.Font.Arial
				text3.TextXAlignment = Enum.TextXAlignment.Right
				text3.BackgroundTransparency = 1
				text3.TextColor3 = Color3.fromRGB(160, 160, 160)
				text3.Text = ""
				text3.Position = UDim2.new(1, -40, 0, 4)
				text3.Size = UDim2.new(0, 40, 0, 25)
				text3.TextSize = 12
				text3.Parent = frame
				local textdown = Instance.new("Frame")
				textdown.BackgroundColor3 = Color3.fromRGB(37, 36, 37)
				textdown.Size = UDim2.new(0, 30, 0, 2)
				textdown.Position = UDim2.new(1, -38, 1, -4)
				textdown.Visible = false
				textdown.BorderSizePixel = 0
				textdown.Parent = text2
				local textdown2 = Instance.new("Frame")
				textdown2.BackgroundColor3 = Color3.fromRGB(41, 41, 41)
				textdown2.Size = UDim2.new(0, 30, 0, 2)
				textdown2.Position = UDim2.new(1, -38, 1, -4)
				textdown2.BorderSizePixel = 0
				textdown2.Parent = text3
				local slider1 = Instance.new("Frame")
				slider1.Size = UDim2.new(0, 200, 0, 2)
				slider1.BorderSizePixel = 0
				slider1.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
				slider1.Position = UDim2.new(0, 10, 0, 37)
				slider1.Name = "Slider"
				slider1.Parent = frame
				local slider2 = Instance.new("Frame")
				slider2.BorderSizePixel = 0
				slider2.Size = UDim2.new(math.clamp(((argstable["Default"] or argstable["Min"]) / argstable["Max"]), 0.02, 0.97), 0, 1, 0)
				slider2.BackgroundColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Hue"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Sat"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Value"])
				slider2.Name = "FillSlider"
				slider2.Parent = slider1
				local slider3 = Instance.new("ImageButton")
				slider3.AutoButtonColor = false
				slider3.Size = UDim2.new(0, 24, 0, 16)
				slider3.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
				slider3.BorderSizePixel = 0
				slider3.Image = downloadVapeAsset("vape/assets/SliderButton1.png")
				slider3.Position = UDim2.new(1, -11, 0, -7)
				slider3.Parent = slider2
				slider3.Name = "ButtonSlider"
				sliderapi["Object"] = frame
				sliderapi["Value"] = (argstable["Default"] or argstable["Min"])
				sliderapi["Default"] = (argstable["Default"] or argstable["Min"])
				sliderapi["Min"] = argstable["Min"]
				sliderapi["Max"] = argstable["Max"]
				sliderapi["SetValue"] = function(val)
				--	val = math.clamp(val, argstable["Min"], argstable["Max"])
					sliderapi["Value"] = val
					slider2.Size = UDim2.new(math.clamp((val / argstable["Max"]), 0.02, 0.97), 0, 1, 0)
					local doublecheck = argstable["Double"] and (sliderapi["Value"] / argstable["Double"]) or sliderapi["Value"]
					text2.Text = doublecheck .. " "..(argstable["Percent"] and "%  " or " ").." "
					argstable["Function"](val)
				end
				slider3.MouseButton1Down:Connect(function()
					local x,y,xscale,yscale,xscale2 = RelativeXY(slider1, inputService:GetMouseLocation())
					sliderapi["SetValue"](math.floor(argstable["Min"] + ((argstable["Max"] - argstable["Min"]) * xscale)))
					local doublecheck = argstable["Double"] and (sliderapi["Value"] / argstable["Double"]) or sliderapi["Value"]
					text2.Text = doublecheck .. " "..(argstable["Percent"] and "%  " or " ").." "
					slider2.Size = UDim2.new(xscale2,0,1,0)
					local move
					local kill
					move = inputService.InputChanged:Connect(function(input)
						if input.UserInputType == Enum.UserInputType.MouseMovement then
							local x,y,xscale,yscale,xscale2 = RelativeXY(slider1, inputService:GetMouseLocation())
							sliderapi["SetValue"](math.floor(argstable["Min"] + ((argstable["Max"] - argstable["Min"]) * xscale)))
							local doublecheck = argstable["Double"] and (sliderapi["Value"] / argstable["Double"]) or sliderapi["Value"]
							text2.Text = doublecheck .. " "..(argstable["Percent"] and "%  " or " ").." "
							slider2.Size = UDim2.new(xscale2,0,1,0)
						end
					end)
					kill = inputService.InputEnded:Connect(function(input)
						if input.UserInputType == Enum.UserInputType.MouseButton1 then
							move:Disconnect()
							kill:Disconnect()
						end
					end)
				end)
				text2.MouseEnter:Connect(function()
					textdown.Visible = true
				end)
				text2.MouseLeave:Connect(function()
					textdown.Visible = false
				end)
				text2.MouseButton1Click:Connect(function()
					text3.Visible = true
					text2.Visible = false
					text3:CaptureFocus()
					text3.Text = text2.Text
				end)
				text3.FocusLost:Connect(function(enter)
					text3.Visible = false
					text2.Visible = true
					if enter then
						sliderapi["SetValue"](tonumber(text3.Text) * (argstable["Double"] or 1))
					end
				end)
				frame.MouseEnter:Connect(function()
					if argstable["HoverText"] and type(argstable["HoverText"]) == "string" then
						hoverbox.Visible = (GuiLibrary["ToggleTooltips"] and hoverbox.TextSize ~= 1)
						local textsize = textService:GetTextSize(argstable["HoverText"], hoverbox.TextSize, hoverbox.Font, Vector2.new(99999, 99999))
						hoverbox.Text = "  "..argstable["HoverText"]:gsub("\n", "\n  ")
						hoverbox.Size = UDim2.new(0, 13 + textsize.X, 0, textsize.Y + 5)
					end
				end)
				if argstable["HoverText"] and type(argstable["HoverText"]) == "string" then
					frame.MouseMoved:Connect(function(x, y)
						hoverbox.Visible = (GuiLibrary["ToggleTooltips"] and hoverbox.TextSize ~= 1)
						hoverbox.Position = UDim2.new(0, (x + 16) * (1 / GuiLibrary["MainRescale"].Scale), 0,	(y - (hoverbox.Size.Y.Offset / 2) - 26) * (1 / GuiLibrary["MainRescale"].Scale))
					end)
				end
				frame.MouseLeave:Connect(function()
					hoverbox.Visible = false
				end)
				GuiLibrary.ObjectsThatCanBeSaved[argstablemain["Name"]..argstable["Name"].."Slider"] = {["Type"] = "Slider", ["Object"] = frame, ["Api"] = sliderapi}
				return sliderapi
			end

			buttonapi["CreateTwoSlider"] = function(argstable)

				local sliderapi = {}
				local amount2 = #children2:GetChildren()
				local frame = Instance.new("Frame")
				frame.Size = UDim2.new(0, 220, 0, 50)
				frame.BackgroundTransparency = 1
				frame.ClipsDescendants = true
				frame.LayoutOrder = amount2
				frame.Name = argstable["Name"]
				frame.Parent = children2
				local text1 = Instance.new("TextLabel")
				text1.Font = Enum.Font.SourceSans
				text1.TextXAlignment = Enum.TextXAlignment.Left
				text1.Text = "   "..(translations[argstable["Name"]] ~= nil and translations[argstable["Name"]] or argstable["Name"])
				text1.Size = UDim2.new(1, 0, 0, 25)
				text1.TextColor3 = Color3.fromRGB(160, 160, 160)
				text1.BackgroundTransparency = 1
				text1.TextSize = 17
				text1.Parent = frame
				local text2 = Instance.new("TextLabel")
				text2.Font = Enum.Font.SourceSans
				text2.TextXAlignment = Enum.TextXAlignment.Right
				local text2string = tostring((argstable["Default2"] or argstable["Max"]) / 10)
				text2.Text = (argstable["Decimal"] and (text2string:len() > 1 and text2string or text2string..".0   ") or (argstable["Default2"] or argstable["Max"]) .. ".0   ")
				text2.Size = UDim2.new(1, 0, 0, 25)
				text2.TextColor3 = Color3.fromRGB(160, 160, 160)
				text2.BackgroundTransparency = 1
				text2.TextSize = 17
				text2.Parent = frame
				local text3 = Instance.new("TextLabel")
				text3.Font = Enum.Font.SourceSans
				text3.TextColor3 = Color3.fromRGB(160, 160, 160)
				text3.BackgroundTransparency = 1
				text3.TextXAlignment = Enum.TextXAlignment.Right
				text3.Size = UDim2.new(1, -77, 0, 25)
				text3.TextSize = 17
				local text3string = tostring((argstable["Default"] or argstable["Min"]) / 10)
				text3.Text = (argstable["Decimal"] and (text3string:len() > 1 and text3string or text3string..".0") or (argstable["Default"] or argstable["Min"]) .. ".0")
				text3.Parent = frame
				local text4 = Instance.new("ImageLabel")
				text4.Size = UDim2.new(0, 12, 0, 6)
				text4.Image = downloadVapeAsset("vape/assets/SliderArrowSeperator.png")
				text4.BackgroundTransparency = 1
				text4.Position = UDim2.new(0, 154, 0, 10)
				text4.Parent = frame
				local slider1 = Instance.new("Frame")
				slider1.Size = UDim2.new(0, 200, 0, 2)
				slider1.BorderSizePixel = 0
				slider1.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
				slider1.Position = UDim2.new(0, 10, 0, 32)
				slider1.Name = "Slider"
				slider1.Parent = frame
				local slider2 = Instance.new("Frame")
				slider2.Size = UDim2.new(1, 0, 1, 0)
				slider2.BorderSizePixel = 0
				slider2.BackgroundColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Hue"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Sat"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Value"])
				slider2.Name = "FillSlider"
				slider2.Parent = slider1
				local slider3 = Instance.new("ImageButton")
				slider3.AutoButtonColor = false
				slider3.Size = UDim2.new(0, 15, 0, 16)
				slider3.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
				slider3.BorderSizePixel = 0
				slider3.Image = downloadVapeAsset("vape/assets/SliderArrow1.png")
				slider3.Position = UDim2.new(1, -7, 1, -9)
				slider3.Parent = slider1
				slider3.Name = "ButtonSlider"
				local slider4 = slider3:Clone()
				slider4.Rotation = 180
				slider4.Name = "ButtonSlider2"
				slider4.Parent = slider1
				slider3:GetPropertyChangedSignal("Position"):Connect(function()
					slider2.Size = UDim2.new(0, slider4.AbsolutePosition.X - slider3.AbsolutePosition.X, 1, 0)
					slider2.Position = UDim2.new(slider3.Position.X.Scale, 0, 0, 0)
				end)
				slider4:GetPropertyChangedSignal("Position"):Connect(function()
					slider2.Size = UDim2.new(0, slider4.AbsolutePosition.X - slider3.AbsolutePosition.X, 1, 0)
					slider2.Position = UDim2.new(slider3.Position.X.Scale, 0, 0, 0)
				end)
				slider3.Position = UDim2.new((argstable["Default"] and (argstable["Default"] == argstable["Min"] and 0 or argstable["Default"]/argstable["Max"]) or 0), -8, 1, -9)
				slider4.Position = UDim2.new((argstable["Default2"] and (argstable["Default2"] == argstable["Max"] and 1 or argstable["Default2"]/argstable["Max"]) or 1), -8, 1, -9)
				slider2.Size = UDim2.new(0, slider4.AbsolutePosition.X - slider3.AbsolutePosition.X, 1, 0)
				slider2.Position = UDim2.new(slider3.Position.X.Scale, 0, 0, 0)
				sliderapi["Object"] = frame
				sliderapi["Value"] = (argstable["Default"] or argstable["Min"])
				sliderapi["Value2"] = (argstable["Default2"] or argstable["Max"])
				sliderapi["Max"] = argstable["Max"]
				sliderapi["SetValue"] = function(val)
					val = math.clamp(val, argstable["Min"], argstable["Max"])
					sliderapi["Value"] = val
					--slider2.Size = UDim2.new(math.clamp((val / max), 0.02, 0.97), 0, 1, 0)
					--slider3.Position = UDim2.new((val / max), -8, 1, -9)
					slider3:TweenPosition(UDim2.new((val / argstable["Max"]), -8, 1, -9), Enum.EasingDirection.InOut, Enum.EasingStyle.Quad, 0.05, true)
					local stringthing = tostring(sliderapi["Value"] / 10)
					text3.Text = (argstable["Decimal"] and (stringthing:len() > 1 and stringthing or stringthing..".0") or sliderapi["Value"] .. ".0")
				end
				sliderapi["SetValue2"] = function(val)
					val = math.clamp(val, argstable["Min"], argstable["Max"])
					sliderapi["Value2"] = val
					--slider2.Size = UDim2.new(math.clamp((val / max), 0.02, 0.97), 0, 1, 0)
					--slider4.Position = UDim2.new((val / max), -8, 1, -9)
					local stringthing = tostring(sliderapi["Value2"] / 10)
					text2.Text = (argstable["Decimal"] and (stringthing:len() > 1 and stringthing or stringthing..".0").."   " or sliderapi["Value2"] .. ".0   ")
				end
				sliderapi["GetRandomValue"] = function()
					return Random.new().NextNumber(Random.new(), sliderapi["Value"], sliderapi["Value2"])
				end
				slider3.MouseButton1Down:Connect(function()
					local x,y,xscale,yscale,xscale2 = RelativeXY(slider1, inputService:GetMouseLocation())
					sliderapi["SetValue"](math.floor(argstable["Min"] + ((argstable["Max"] - argstable["Min"]) * xscale)))
					slider3.Position = UDim2.new(xscale2, -8, 1, -9)
					local move
					local kill
					move = inputService.InputChanged:Connect(function(input)
						if input.UserInputType == Enum.UserInputType.MouseMovement then
							local x,y,xscale,yscale,xscale2 = RelativeXY(slider1, inputService:GetMouseLocation())
							sliderapi["SetValue"](math.floor(argstable["Min"] + ((argstable["Max"] - argstable["Min"]) * xscale)))
						--	slider3.Position = UDim2.new(xscale2, -8, 1, -9)
							slider3:TweenPosition(UDim2.new(xscale2, -8, 1, -9), Enum.EasingDirection.InOut, Enum.EasingStyle.Quad, 0.05, true)
						end
					end)
					kill = inputService.InputEnded:Connect(function(input)
						if input.UserInputType == Enum.UserInputType.MouseButton1 then
							move:Disconnect()
							kill:Disconnect()
						end
					end)
				end)
				slider4.MouseButton1Down:Connect(function()
					local x,y,xscale,yscale,xscale2 = RelativeXY(slider1, inputService:GetMouseLocation())
					sliderapi["SetValue2"](math.floor(argstable["Min"] + ((argstable["Max"] - argstable["Min"]) * xscale)))
					slider4.Position = UDim2.new(xscale2, -8, 1, -9)
					local move
					local kill
					move = inputService.InputChanged:Connect(function(input)
						if input.UserInputType == Enum.UserInputType.MouseMovement then
							local x,y,xscale,yscale,xscale2 = RelativeXY(slider1, inputService:GetMouseLocation())
							sliderapi["SetValue2"](math.floor(argstable["Min"] + ((argstable["Max"] - argstable["Min"]) * xscale)))
							--slider4.Position = UDim2.new(xscale2, -8, 1, -9)
							slider4:TweenPosition(UDim2.new(xscale2, -8, 1, -9), Enum.EasingDirection.InOut, Enum.EasingStyle.Quad, 0.05, true)
						end
					end)
					kill = inputService.InputEnded:Connect(function(input)
						if input.UserInputType == Enum.UserInputType.MouseButton1 then
							move:Disconnect()
							kill:Disconnect()
						end
					end)
				end)
				GuiLibrary.ObjectsThatCanBeSaved[argstablemain["Name"]..argstable["Name"].."TwoSlider"] = {["Type"] = "TwoSlider", ["Object"] = frame, ["Api"] = sliderapi}
				return sliderapi
			end

			buttonapi["CreateToggle"] = function(argstable)
				local buttonapi = {}
				local currentanim
				local amount = #children2:GetChildren()
				local buttontext = Instance.new("TextButton")
				buttontext.AutoButtonColor = false
				buttontext.BackgroundTransparency = 1
				buttontext.Name = "ButtonText"
				buttontext.Text = "          "..(translations[argstable["Name"]] ~= nil and translations[argstable["Name"]] or argstable["Name"])
				buttontext.Name = argstable["Name"]
				buttontext.LayoutOrder = amount
				buttontext.Size = UDim2.new(1, 0, 0, 30)
				buttontext.Active = false
				buttontext.TextColor3 = Color3.fromRGB(160, 160, 160)
				buttontext.TextSize = 14
				buttontext.Font = Enum.Font.Arial
				buttontext.TextXAlignment = Enum.TextXAlignment.Left
				buttontext.Position = UDim2.new(0, (icon and 36 or 10), 0, 0)
				buttontext.Parent = children2
				local buttonarrow = Instance.new("ImageLabel")
				buttonarrow.Size = UDim2.new(1, 0, 0, 0)
				buttonarrow.Position = UDim2.new(0, 0, 1, -4)
				buttonarrow.BackgroundTransparency = 1
				buttonarrow.Name = "ToggleArrow"
				buttonarrow.Image = downloadVapeAsset("vape/assets/ToggleArrow.png")
				buttonarrow.Visible = false
				buttonarrow.Parent = buttontext
				local toggleframe1 = Instance.new("Frame")
				toggleframe1.Size = UDim2.new(0, 22, 0, 12)
				toggleframe1.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
				toggleframe1.BorderSizePixel = 0
				toggleframe1.Name = "ToggleFrame1"
				toggleframe1.Position = UDim2.new(1, -30, 0, 10)
				toggleframe1.Parent = buttontext
				local toggleframe2 = Instance.new("Frame")
				toggleframe2.Size = UDim2.new(0, 8, 0, 8)
				toggleframe2.Active = false
				toggleframe2.Position = UDim2.new(0, 2, 0, 2)
				toggleframe2.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
				toggleframe2.BorderSizePixel = 0
				toggleframe2.Parent = toggleframe1
				local uicorner = Instance.new("UICorner")
				uicorner.CornerRadius = UDim.new(0, 16)
				uicorner.Parent = toggleframe1
				local uicorner2 = Instance.new("UICorner")
				uicorner2.CornerRadius = UDim.new(0, 16)
				uicorner2.Parent = toggleframe2

				buttonapi["Enabled"] = false
				buttonapi["Keybind"] = ""
				buttonapi["Default"] = argstable["Default"]
				buttonapi["Object"] = buttontext
				buttonapi.Connections = {}
				buttonapi["ToggleButton"] = function(toggle, first)
					buttonapi["Enabled"] = toggle
					if buttonapi["Enabled"] then
						if not first then
							tweenService:Create(toggleframe1, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Hue"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Sat"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Value"])}):Play()
						else
							toggleframe1.BackgroundColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Hue"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Sat"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Value"])
						end
						toggleframe2:TweenPosition(UDim2.new(0, 12, 0, 2), Enum.EasingDirection.InOut, Enum.EasingStyle.Linear, 0.1, true)
					else
						for i, v in pairs(buttonapi.Connections) do
							if v.Disconnect then pcall(function() v:Disconnect() end) continue end
							if v.disconnect then pcall(function() v:disconnect() end) continue end
						end
						table.clear(buttonapi.Connections)
						if not first then
							tweenService:Create(toggleframe1, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(60, 60, 60)}):Play()
						else
							toggleframe1.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
						end
						toggleframe2:TweenPosition(UDim2.new(0, 2, 0, 2), Enum.EasingDirection.InOut, Enum.EasingStyle.Linear, 0.1, true)
					end
					argstable["Function"](buttonapi["Enabled"])
				end
				if argstable["Default"] then
					buttonapi["ToggleButton"](argstable["Default"], true)
				end
				buttontext.MouseButton1Click:Connect(function() buttonapi["ToggleButton"](not buttonapi["Enabled"], false) end)
				buttontext.MouseEnter:Connect(function()
					if argstable["HoverText"] and type(argstable["HoverText"]) == "string" then
						hoverbox.Visible = (GuiLibrary["ToggleTooltips"] and hoverbox.TextSize ~= 1)
						local textsize = textService:GetTextSize(argstable["HoverText"], hoverbox.TextSize, hoverbox.Font, Vector2.new(99999, 99999))
						hoverbox.Text = "  "..argstable["HoverText"]:gsub("\n", "\n  ")
						hoverbox.Size = UDim2.new(0, 13 + textsize.X, 0, textsize.Y + 5)
					end
					if buttonapi["Enabled"] == false then
						tweenService:Create(toggleframe1, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(100, 100, 100)}):Play()
					end
				end)
				if argstable["HoverText"] and type(argstable["HoverText"]) == "string" then
					buttontext.MouseMoved:Connect(function(x, y)
						hoverbox.Visible = (GuiLibrary["ToggleTooltips"] and hoverbox.TextSize ~= 1)
						hoverbox.Position = UDim2.new(0, (x + 16) * (1 / GuiLibrary["MainRescale"].Scale), 0,	(y - (hoverbox.Size.Y.Offset / 2) - 26) * (1 / GuiLibrary["MainRescale"].Scale))
					end)
				end
				buttontext.MouseLeave:Connect(function()
					hoverbox.Visible = false
					if buttonapi["Enabled"] == false then
						tweenService:Create(toggleframe1, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(60, 60, 60)}):Play()
					end
				end)

				GuiLibrary.ObjectsThatCanBeSaved[argstablemain["Name"]..argstable["Name"].."Toggle"] = {["Type"] = "Toggle", ["Object"] = buttontext, ["Api"] = buttonapi}
				return buttonapi
			end

			if argstablemain["Default"] then
				buttonapi["ToggleButton"](false, true)
			end
			button.MouseButton1Click:Connect(function()
				buttonapi["ToggleButton"](true)
			end)
			if inputService.TouchEnabled then
				local touchedButton = false
				button.MouseButton1Down:Connect(function()
					touchedButton = true
					local touchtick = tick()
					local touchposition = inputService:GetMouseLocation()
					repeat
						task.wait()
						if not touchedButton then break end
						touchedButton = (inputService:GetMouseLocation() - touchposition).Magnitude < 6
					until (tick() - touchtick) > 1 or not touchedButton or not clickgui.Visible
					if touchedButton and clickgui.Visible then
						clickgui.Visible = false
						--runService:SetRobloxGuiFocused(guiService:GetErrorType() ~= Enum.ConnectionError.OK)
						for _, mobileButton in pairs(GuiLibrary.MobileButtons) do mobileButton.Visible = not clickgui.Visible end
						local touchconnection
						touchconnection = inputService.InputBegan:Connect(function(inputType)
							if inputType.UserInputType == Enum.UserInputType.Touch then
								createMobileButton(buttonapi, inputType.Position + Vector3.new(0, guiService:GetGuiInset().Y, 0))
								clickgui.Visible = true
								--runService:SetRobloxGuiFocused((clickgui.Visible or guiService:GetErrorType() ~= Enum.ConnectionError.OK) and mainapi.Blur.Enabled)
								for _, mobileButton in pairs(GuiLibrary.MobileButtons) do mobileButton.Visible = not clickgui.Visible end
								touchconnection:Disconnect()
							end
						end)
					end
				end)
				button.MouseButton1Up:Connect(function()
					touchedButton = false
				end)
			end
			button.MouseEnter:Connect(function()
				bindbkg.Visible = true
				if not buttonapi["Enabled"] then
					currenttween = tweenService:Create(button, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(31, 30, 31)})
					currenttween:Play()
				end
			end)
			button.MouseLeave:Connect(function()
				hoverbox.Visible = false
				if buttonapi["Keybind"] == "" then
					bindbkg.Visible = false
				end
				if not buttonapi["Enabled"] then
					currenttween = tweenService:Create(button, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(26, 25, 26)})
					currenttween:Play()
				end
			end)
			bindbkg2.MouseButton1Click:Connect(function()
				GuiLibrary["PressedKeybindKey"] = buttonapi["Keybind"]
				if buttonapi["Keybind"] == "" then
					GuiLibrary["KeybindCaptured"] = false
					GuiLibrary["PressedKeybindKey"] = "A"
				end
				bindbkg2.Visible = false
			end)
			bindbkg.MouseButton1Click:Connect(function()
				if GuiLibrary["KeybindCaptured"] == false then
					GuiLibrary["KeybindCaptured"] = true
					task.spawn(function()
						bindimg.Visible = false
						bindbkg2.Visible = true
						bindtext2.Visible = true
						bindtext3.Text = "   PRESS A KEY TO BIND"
						bindtext2.Size = UDim2.new(0, 154, 0, 40)
						repeat task.wait() bindtext2.Visible = true until GuiLibrary["PressedKeybindKey"] ~= ""
						if GuiLibrary["KeybindCaptured"] then
							buttonapi["SetKeybind"]((GuiLibrary["PressedKeybindKey"] == buttonapi["Keybind"] and "" or GuiLibrary["PressedKeybindKey"]))
						end
						GuiLibrary["PressedKeybindKey"] = ""
						GuiLibrary["KeybindCaptured"] = false
						bindbkg2.Visible = false
						bindtext3.Text = (buttonapi["Keybind"] == "" and "   BIND REMOVED" or "   BOUND TO "..buttonapi["Keybind"]:upper())
						bindtext2.Size = UDim2.new(0, textService:GetTextSize(bindtext3.Text, bindtext3.TextSize, bindtext3.Font, Vector2.new(10000, 100000)).X + 20, 0, 40)
						task.wait(1)
						bindtext2.Visible = false
					end)
				end
			end)
			bindbkg.MouseEnter:Connect(function()
				bindimg.Image = downloadVapeAsset("vape/assets/PencilIcon.png")
				bindimg.Visible = true
				bindtext.Visible = false
				bindbkg.Size = UDim2.new(0, 20, 0, 21)
				bindbkg.Position = UDim2.new(1, -56, 0, 9)
			end)
			bindbkg.MouseLeave:Connect(function()
				bindimg.Image = downloadVapeAsset("vape/assets/KeybindIcon.png")
				if buttonapi["Keybind"] ~= "" then
					bindimg.Visible = false
					bindtext.Visible = true
					bindbkg.Size = newsize
					bindbkg.Position = UDim2.new(1, -(36 + newsize.X.Offset), 0, 9)
				end
			end)
			button.MouseButton2Click:Connect(buttonapi["ExpandToggle"])
			button2.MouseButton1Click:Connect(buttonapi["ExpandToggle"])
			GuiLibrary.ObjectsThatCanBeSaved[argstablemain["Name"].."OptionsButton"] = {["Type"] = "OptionsButton", ["Object"] = button, ["ChildrenObject"] = children2, ["Api"] = buttonapi, ["SortOrder"] = 0}

			local sorttable1 = {}
			for i,v in pairs(children:GetChildren()) do
				if v:IsA("TextButton") then
					table.insert(sorttable1, v.Name)
				end
			end
			table.sort(sorttable1)
			for i2,v2 in pairs(sorttable1) do
				if v2:find("Button") then
					local findstr = v2:gsub("Button", "Children")
					local sortnum = i2
					local findstr2 = v2:gsub("Button", "OptionsButton")
					if GuiLibrary.ObjectsThatCanBeSaved[findstr2] then
						GuiLibrary.ObjectsThatCanBeSaved[findstr2]["SortOrder"] = sortnum
					end
					children[v2].LayoutOrder = sortnum
					if children:FindFirstChild(findstr) then
						children[findstr].LayoutOrder = sortnum
					end
				else
					children[v2].LayoutOrder = i2
				end
			end
			GuiLibrary.ObjectsThatCanBeSaved[argstablemain2["Name"].."Window"]["SortOrder"] = #sorttable1

			return buttonapi
		end

		return windowapi
	end

	GuiLibrary["CreateWindow2"] = function(argstablemain)
		local windowapi = {}
		local windowtitle = Instance.new("TextButton")
		windowtitle.Text = ""
		windowtitle.AutoButtonColor = false
		windowtitle.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
		windowtitle.Size = UDim2.new(0, 220, 0, 41)
		windowtitle.Position = UDim2.new(0, 223, 0, 6)
		windowtitle.Name = "MainWindow"
		windowtitle.Visible = false
		windowtitle.Name = argstablemain["Name"]
		windowtitle.Parent = clickgui
		local windowshadow = Instance.new("ImageLabel")
		windowshadow.AnchorPoint = Vector2.new(0.5, 0.5)
		windowshadow.Position = UDim2.new(0.5, 0, 0.5, 0)
		windowshadow.Image = downloadVapeAsset("vape/assets/WindowBlur.png")
		windowshadow.BackgroundTransparency = 1
		windowshadow.ZIndex = -1
		windowshadow.Size = UDim2.new(1, 6, 1, 6)
		windowshadow.ImageColor3 = Color3.new(0, 0, 0)
		windowshadow.ScaleType = Enum.ScaleType.Slice
		windowshadow.SliceCenter = Rect.new(10, 10, 118, 118)
		windowshadow.Parent = windowtitle
		local windowicon = Instance.new("ImageLabel")
		windowicon.Size = UDim2.new(0, argstablemain["IconSize"], 0, 16)
		windowicon.Image = downloadVapeAsset(argstablemain["Icon"])
		windowicon.ImageColor3 = Color3.fromRGB(200, 200, 200)
		windowicon.Name = "WindowIcon"
		windowicon.BackgroundTransparency = 1
		windowicon.Position = UDim2.new(0, 12, 0, 12)
		windowicon.Parent = windowtitle
		local windowtext = Instance.new("TextLabel")
		windowtext.Size = UDim2.new(0, 155, 0, 41)
		windowtext.BackgroundTransparency = 1
		windowtext.Name = "WindowTitle"
		windowtext.Position = UDim2.new(0, 36, 0, 1)
		windowtext.TextXAlignment = Enum.TextXAlignment.Left
		windowtext.Font = Enum.Font.Arial
		windowtext.TextSize = 14
		windowtext.Text = (translations[argstablemain["Name"]] ~= nil and translations[argstablemain["Name"]] or argstablemain["Name"])
		windowtext.TextColor3 = Color3.fromRGB(200, 200, 200)
		windowtext.Parent = windowtitle
		local expandbutton = Instance.new("TextButton")
		expandbutton.Text = ""
		expandbutton.BackgroundTransparency = 1
		expandbutton.BorderSizePixel = 0
		expandbutton.BackgroundColor3 = Color3.new(1, 1, 1)
		expandbutton.Name = "ExpandButton"
		expandbutton.Size = UDim2.new(0, 24, 0, 16)
		expandbutton.Position = UDim2.new(1, -28, 0, 13)
		expandbutton.Parent = windowtitle
		local expandbutton2 = Instance.new("ImageLabel")
		expandbutton2.Active = false
		expandbutton2.Size = UDim2.new(0, 9, 0, 4)
		expandbutton2.Image = downloadVapeAsset("vape/assets/UpArrow.png")
		expandbutton2.Position = UDim2.new(0, 8, 0, 6)
		expandbutton2.Name = "ExpandButton2"
		expandbutton2.BackgroundTransparency = 1
		expandbutton2.Parent = expandbutton
		local settingsbutton = Instance.new("ImageButton")
		settingsbutton.Active = true
		settingsbutton.Size = UDim2.new(0, 16, 0, 16)
		settingsbutton.Image = downloadVapeAsset("vape/assets/SettingsWheel2.png")
		settingsbutton.Position = UDim2.new(1, -53, 0, 13)
		settingsbutton.Name = "OptionsButton"
		settingsbutton.BackgroundTransparency = 1
		settingsbutton.Rotation = 180
		settingsbutton.Parent = windowtitle
		local children = Instance.new("Frame")
		children.BackgroundTransparency = 1
		children.Size = UDim2.new(1, 0, 1, -4)
		children.Position = UDim2.new(0, 0, 0, 41)
		children.Visible = false
		children.Parent = windowtitle
		local children2 = Instance.new("Frame")
		children2.BackgroundTransparency = 1
		children2.Size = UDim2.new(0, 220, 1, -4)
		children2.Name = "SettingsChildren"
		children2.Position = UDim2.new(0, 0, 0, 41)
		children2.Parent = windowtitle
		children2.Visible = false
		local windowcorner = Instance.new("UICorner")
		windowcorner.CornerRadius = UDim.new(0, 4)
		windowcorner.Parent = windowtitle
		local uilistlayout = Instance.new("UIListLayout")
		uilistlayout.SortOrder = Enum.SortOrder.LayoutOrder
		uilistlayout.Parent = children
		local uilistlayout2 = Instance.new("UIListLayout")
		uilistlayout2.SortOrder = Enum.SortOrder.LayoutOrder
		uilistlayout2.Parent = children2
		uilistlayout:GetPropertyChangedSignal("AbsoluteContentSize"):Connect(function()
			if children.Visible then
				windowtitle.Size = UDim2.new(0, 220, 0, 45 + uilistlayout.AbsoluteContentSize.Y * (1 / GuiLibrary["MainRescale"].Scale))
				--560
			end
		end)
		local noexpand = false
		dragGUI(windowtitle)
		GuiLibrary.ObjectsThatCanBeSaved[argstablemain["Name"].."Window"] = {["Object"] = windowtitle, ["ChildrenObject"] = children, ["Type"] = "Window", ["Api"] = windowapi}

		windowapi["SetVisible"] = function(value)
			windowtitle.Visible = value
		end

		windowapi["ExpandToggle"] = function()
			if noexpand == false then
				children.Visible = not children.Visible
				children2.Visible = false
				if children.Visible then
					expandbutton2.Image = downloadVapeAsset("vape/assets/DownArrow.png")
					windowtitle.Size = UDim2.new(0, 220, 0, 45 + uilistlayout.AbsoluteContentSize.Y)
				else
					expandbutton2.Image = downloadVapeAsset("vape/assets/UpArrow.png")
					windowtitle.Size = UDim2.new(0, 220, 0, 41)
				end
			end
		end

		uilistlayout2:GetPropertyChangedSignal("AbsoluteContentSize"):Connect(function()
			if children2.Visible then
				windowtitle.Size = UDim2.new(0, 220, 0, 45 + uilistlayout2.AbsoluteContentSize.Y)
			end
		end)
		settingsbutton.MouseButton1Click:Connect(function()
			if children.Visible then
				children.Visible = false
				children2.Visible = true
				windowtitle.Size = UDim2.new(0, 220, 0, 45 + uilistlayout2.AbsoluteContentSize.Y)
			else
				children.Visible = true
				children2.Visible = false
				windowtitle.Size = UDim2.new(0, 220, 0, 45 + uilistlayout.AbsoluteContentSize.Y)
			end
		end)
		windowtitle.MouseButton2Click:Connect(windowapi["ExpandToggle"])
		expandbutton.MouseButton1Click:Connect(windowapi["ExpandToggle"])
		expandbutton.MouseButton2Click:Connect(windowapi["ExpandToggle"])

		windowapi["CreateColorSlider"] = function(argstable)
			local min, max = 0, 1
			local sliderapi = {}
			local amount2 = #children2:GetChildren()
			local frame = Instance.new("Frame")
			frame.Size = UDim2.new(0, 220, 0, 50)
			frame.BorderSizePixel = 0
			frame.BackgroundTransparency = 1
			frame.LayoutOrder = amount2
			frame.Name = argstable["Name"]
			frame.Parent = children2
			local text1 = Instance.new("TextLabel")
			text1.Font = Enum.Font.Arial
			text1.TextXAlignment = Enum.TextXAlignment.Left
			text1.Text = "          "..(translations[argstable["Name"]] ~= nil and translations[argstable["Name"]] or argstable["Name"])
			text1.Size = UDim2.new(1, 0, 0, 27)
			text1.TextColor3 = Color3.fromRGB(160, 160, 160)
			text1.Position = UDim2.new(0, 0, 0, 4)
			text1.BackgroundTransparency = 1
			text1.TextSize = 12
			text1.Parent = frame
			local text2 = Instance.new("Frame")
			text2.Size = UDim2.new(0, 12, 0, 12)
			text2.Position = UDim2.new(1, -22, 0, 9)
			text2.BackgroundColor3 = Color3.fromHSV(0.44, 1, 1)
			text2.Parent = frame
			local uicorner4 = Instance.new("UICorner")
			uicorner4.CornerRadius = UDim.new(0, 4)
			uicorner4.Parent = text2
			local slider1 = Instance.new("TextButton")
			slider1.AutoButtonColor = false
			slider1.Text = ""
			slider1.Size = UDim2.new(0, 200, 0, 2)
			slider1.BorderSizePixel = 0
			slider1.BackgroundColor3 = Color3.new(1, 1, 1)
			slider1.Position = UDim2.new(0, 10, 0, 32)
			slider1.Name = "Slider"
			slider1.Parent = frame
			local uigradient = Instance.new("UIGradient")
			uigradient.Color = ColorSequence.new({ColorSequenceKeypoint.new(0, Color3.fromHSV(0, 1, 1)), ColorSequenceKeypoint.new(0.2, Color3.fromHSV(0.2, 1, 1)), ColorSequenceKeypoint.new(0.3, Color3.fromHSV(0.3, 1, 1)), ColorSequenceKeypoint.new(0.4, Color3.fromHSV(0.4, 1, 1)), ColorSequenceKeypoint.new(0.5, Color3.fromHSV(0.5, 1, 1)), ColorSequenceKeypoint.new(0.6, Color3.fromHSV(0.6, 1, 1)), ColorSequenceKeypoint.new(0.7, Color3.fromHSV(0.7, 1, 1)), ColorSequenceKeypoint.new(0.8, Color3.fromHSV(0.8, 1, 1)), ColorSequenceKeypoint.new(0.9, Color3.fromHSV(0.9, 1, 1)), ColorSequenceKeypoint.new(1, Color3.fromHSV(1, 1, 1))})
			uigradient.Parent = slider1
			local slider3 = Instance.new("ImageButton")
			slider3.AutoButtonColor = false
			slider3.Size = UDim2.new(0, 24, 0, 16)
			slider3.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
			slider3.BorderSizePixel = 0
			slider3.Image = downloadVapeAsset("vape/assets/SliderButton1.png")
			slider3.Position = UDim2.new(0.44, -11, 0, -7)
			slider3.Parent = slider1
			slider3.Name = "ButtonSlider"
			local slidersat = frame:Clone()
			slidersat.TextLabel.Text = "    Saturation"
			slidersat.Name = frame.Name.."Saturation"
			slidersat.BackgroundTransparency = 0
			slidersat.Visible = false
			slidersat.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
			slidersat.Slider.UIGradient.Color = ColorSequence.new({ColorSequenceKeypoint.new(0, Color3.fromHSV(0, 0, 1)), ColorSequenceKeypoint.new(1, Color3.fromHSV(0.4, 1, 1))})
			slidersat.Slider.ButtonSlider.Position = UDim2.new(0.95, -11, 0, -7)
			slidersat.Slider.ButtonSlider.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
			slidersat.Frame:Remove()
			slidersat.Parent = children2
			local sliderval = frame:Clone()
			sliderval.TextLabel.Text = "    Vibrance"
			sliderval.Name = frame.Name.."Vibrance"
			sliderval.BackgroundTransparency = 0
			sliderval.Visible = false
			sliderval.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
			sliderval.Slider.UIGradient.Color = ColorSequence.new({ColorSequenceKeypoint.new(0, Color3.fromHSV(0, 0, 0)), ColorSequenceKeypoint.new(1, Color3.fromHSV(0.4, 1, 1))})
			sliderval.Slider.ButtonSlider.Position = UDim2.new(0.95, -11, 0, -7)
			sliderval.Slider.ButtonSlider.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
			sliderval.Frame:Remove()
			sliderval.Parent = children2
			local sliderexpand = Instance.new("ImageButton")
			sliderexpand.AutoButtonColor = false
			sliderexpand.Size = UDim2.new(0, 15, 0, 15)
			sliderexpand.BackgroundTransparency = 1
			sliderexpand.Position = UDim2.new(0, textService:GetTextSize(text1.Text, text1.TextSize, text1.Font, Vector2.new(10000, 100000)).X + 3, 0, 6)
			sliderexpand.Image = downloadVapeAsset("vape/assets/HoverArrow.png")
			sliderexpand.Parent = frame
			sliderexpand.MouseEnter:Connect(function()
				sliderexpand.Image = downloadVapeAsset("vape/assets/HoverArrow2.png")
			end)
			sliderexpand.MouseLeave:Connect(function()
				sliderexpand.Image = downloadVapeAsset("vape/assets/HoverArrow.png")
			end)
			sliderexpand.MouseButton1Click:Connect(function()
				local val = not slidersat.Visible
				slidersat.Visible = val
				sliderval.Visible = val
				sliderexpand.Rotation = (val and 180 or 0)
			end)
			sliderapi["Hue"] = 0.44
			sliderapi["Sat"] = 1
			sliderapi["Value"] = 1
			sliderapi["Object"] = frame
			sliderapi["RainbowValue"] = false
			sliderapi["SetValue"] = function(hue, sat, val)
				hue = (hue or sliderapi["Hue"])
				sat = (sat or sliderapi["Sat"])
				val = (val or sliderapi["Value"])
				text2.BackgroundColor3 = Color3.fromHSV(hue, sat, val)
				pcall(function()
					slidersat.Slider.UIGradient.Color = ColorSequence.new({ColorSequenceKeypoint.new(0, Color3.fromHSV(0, 0, val)), ColorSequenceKeypoint.new(1, Color3.fromHSV(hue, 1, val))})
					sliderval.Slider.UIGradient.Color = ColorSequence.new({ColorSequenceKeypoint.new(0, Color3.fromHSV(0, 0, 0)), ColorSequenceKeypoint.new(1, Color3.fromHSV(hue, sat, 1))})
				end)
				sliderapi["Hue"] = hue
				sliderapi["Sat"] = sat
				sliderapi["Value"] = val
				slider3.Position = UDim2.new(math.clamp(hue, 0.02, 0.95), -9, 0, -7)
				argstable["Function"](hue, sat, val)
			end
			sliderapi["SetRainbow"] = function(val)
				sliderapi["RainbowValue"] = val
				if sliderapi["RainbowValue"] then
					table.insert(GuiLibrary.RainbowSliders, sliderapi)
				else
					table.remove(GuiLibrary.RainbowSliders, table.find(GuiLibrary.RainbowSliders, sliderapi))
				end
			end
			local clicktick = tick()
			local function slidercode(obj, valtochange)
				if clicktick > tick() then
					sliderapi["SetRainbow"](not sliderapi["RainbowValue"])
				end
				clicktick = tick() + 0.3
				local x,y,xscale,yscale,xscale2 = RelativeXY(obj, inputService:GetMouseLocation())
				sliderapi["SetValue"]((valtochange == "Hue" and (min + ((max - min) * xscale)) or false), (valtochange == "Sat" and (min + ((max - min) * xscale)) or false), (valtochange == "Value" and (min + ((max - min) * xscale)) or false))
				obj.ButtonSlider.Position = UDim2.new(math.clamp(xscale2, 0.02, 0.95), -9, 0, -7)
				local move
				local kill
				move = inputService.InputChanged:Connect(function(input)
					if input.UserInputType == Enum.UserInputType.MouseMovement then
						local x,y,xscale,yscale,xscale2 = RelativeXY(obj, inputService:GetMouseLocation())
						sliderapi["SetValue"]((valtochange == "Hue" and (min + ((max - min) * xscale)) or false), (valtochange == "Sat" and (min + ((max - min) * xscale)) or false), (valtochange == "Value" and (min + ((max - min) * xscale)) or false))
						obj.ButtonSlider.Position = UDim2.new(math.clamp(xscale2, 0.02, 0.95), -9, 0, -7)
					end
				end)
				kill = inputService.InputEnded:Connect(function(input)
					if input.UserInputType == Enum.UserInputType.MouseButton1 then
						move:Disconnect()
						kill:Disconnect()
					end
				end)
			end
			slider1.MouseButton1Down:Connect(function()
				slidercode(slider1, "Hue")
			end)
			slider3.MouseButton1Down:Connect(function()
				slidercode(slider1, "Hue")
			end)
			slidersat.Slider.MouseButton1Down:Connect(function()
				slidercode(slidersat.Slider, "Sat")
			end)
			slidersat.Slider.ButtonSlider.MouseButton1Down:Connect(function()
				slidercode(slidersat.Slider, "Sat")
			end)
			sliderval.Slider.MouseButton1Down:Connect(function()
				slidercode(sliderval.Slider, "Value")
			end)
			sliderval.Slider.ButtonSlider.MouseButton1Down:Connect(function()
				slidercode(sliderval.Slider, "Value")
			end)

			frame.MouseEnter:Connect(function()
				if argstable["HoverText"] and type(argstable["HoverText"]) == "string" then
					hoverbox.Visible = (GuiLibrary["ToggleTooltips"] and hoverbox.TextSize ~= 1)
					local textsize = textService:GetTextSize(argstable["HoverText"], hoverbox.TextSize, hoverbox.Font, Vector2.new(99999, 99999))
					hoverbox.Text = " "..argstable["HoverText"]:gsub("\n", "\n ")
					hoverbox.Size = UDim2.new(0, 8 + textsize.X, 0, textsize.Y + 5)
				end
			end)
			if argstable["HoverText"] and type(argstable["HoverText"]) == "string" then
				frame.MouseMoved:Connect(function(x, y)
					hoverbox.Visible = (GuiLibrary["ToggleTooltips"] and hoverbox.TextSize ~= 1)
					hoverbox.Position = UDim2.new(0, (x + 16) * (1 / GuiLibrary["MainRescale"].Scale), 0,	(y - (hoverbox.Size.Y.Offset / 2) - 26) * (1 / GuiLibrary["MainRescale"].Scale))
				end)
			end
			frame.MouseLeave:Connect(function()
				hoverbox.Visible = false
				if buttonapi and buttonapi["Enabled"] == false then
					tweenService:Create(toggleframe1, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(60, 60, 60)}):Play()
				end
			end)
			GuiLibrary.ObjectsThatCanBeSaved[argstable["Name"].."SliderColor"] = {["Type"] = "ColorSlider", ["Object"] = frame, ["Object2"] = slidersat, ["Object3"] = sliderval, ["Api"] = sliderapi}
			return sliderapi
		end

		windowapi["CreateToggle"] = function(argstable)
			local buttonapi = {}
			local currentanim
			local amount = #children2:GetChildren()
			local buttontext = Instance.new("TextButton")
			buttontext.AutoButtonColor = false
			buttontext.BackgroundTransparency = 1
			buttontext.Name = "ButtonText"
			buttontext.Text = "          "..(translations[argstable["Name"]] ~= nil and translations[argstable["Name"]] or argstable["Name"])
			buttontext.Name = argstable["Name"]
			buttontext.LayoutOrder = amount
			buttontext.Size = UDim2.new(1, 0, 0, 30)
			buttontext.Active = false
			buttontext.TextColor3 = Color3.fromRGB(160, 160, 160)
			buttontext.TextSize = 14
			buttontext.Font = Enum.Font.Arial
			buttontext.TextXAlignment = Enum.TextXAlignment.Left
			buttontext.Position = UDim2.new(0, (icon and 36 or 10), 0, 0)
			buttontext.Parent = children2
			local buttonarrow = Instance.new("ImageLabel")
			buttonarrow.Size = UDim2.new(1, 0, 0, 4)
			buttonarrow.Position = UDim2.new(0, 0, 1, -4)
			buttonarrow.BackgroundTransparency = 1
			buttonarrow.Name = "ToggleArrow"
			buttonarrow.Image = downloadVapeAsset("vape/assets/ToggleArrow.png")
			buttonarrow.Visible = false
			buttonarrow.Parent = buttontext
			local toggleframe1 = Instance.new("Frame")
			toggleframe1.Size = UDim2.new(0, 22, 0, 12)
			toggleframe1.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
			toggleframe1.BorderSizePixel = 0
			toggleframe1.Name = "ToggleFrame1"
			toggleframe1.Position = UDim2.new(1, -30, 0, 10)
			toggleframe1.Parent = buttontext
			local toggleframe2 = Instance.new("Frame")
			toggleframe2.Size = UDim2.new(0, 8, 0, 8)
			toggleframe2.Active = false
			toggleframe2.Position = UDim2.new(0, 2, 0, 2)
			toggleframe2.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
			toggleframe2.BorderSizePixel = 0
			toggleframe2.Parent = toggleframe1
			local uicorner = Instance.new("UICorner")
			uicorner.CornerRadius = UDim.new(0, 16)
			uicorner.Parent = toggleframe1
			local uicorner2 = Instance.new("UICorner")
			uicorner2.CornerRadius = UDim.new(0, 16)
			uicorner2.Parent = toggleframe2

			buttonapi["Enabled"] = false
			buttonapi["Keybind"] = ""
			buttonapi["Default"] = argstable["Default"]
			buttonapi["Object"] = buttontext
			buttonapi["ToggleButton"] = function(toggle, first)
				buttonapi["Enabled"] = toggle
				if buttonapi["Enabled"] then
					if not first then
						tweenService:Create(toggleframe1, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Hue"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Sat"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Value"])}):Play()
					else
						toggleframe1.BackgroundColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Hue"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Sat"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Value"])
					end
					toggleframe2:TweenPosition(UDim2.new(0, 12, 0, 2), Enum.EasingDirection.InOut, Enum.EasingStyle.Linear, 0.1, true)
				else
					if not first then
						tweenService:Create(toggleframe1, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(60, 60, 60)}):Play()
					else
						toggleframe1.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
					end
					toggleframe2:TweenPosition(UDim2.new(0, 2, 0, 2), Enum.EasingDirection.InOut, Enum.EasingStyle.Linear, 0.1, true)
				end
				argstable["Function"](buttonapi["Enabled"])
			end
			if argstable["Default"] then
				buttonapi["ToggleButton"](argstable["Default"], true)
			end
			buttontext.MouseButton1Click:Connect(function() buttonapi["ToggleButton"](not buttonapi["Enabled"], false) end)
			buttontext.MouseEnter:Connect(function()
				if argstable["HoverText"] and type(argstable["HoverText"]) == "string" then
					hoverbox.Visible = (GuiLibrary["ToggleTooltips"] and hoverbox.TextSize ~= 1)
					local textsize = textService:GetTextSize(argstable["HoverText"], hoverbox.TextSize, hoverbox.Font, Vector2.new(99999, 99999))
					hoverbox.Text = " "..argstable["HoverText"]:gsub("\n", "\n ")
					hoverbox.Size = UDim2.new(0, 8 + textsize.X, 0, textsize.Y + 5)
				end
				if buttonapi["Enabled"] == false then
					tweenService:Create(toggleframe1, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(100, 100, 100)}):Play()
				end
			end)
			if argstable["HoverText"] and type(argstable["HoverText"]) == "string" then
				buttontext.MouseMoved:Connect(function(x, y)
					hoverbox.Visible = (GuiLibrary["ToggleTooltips"] and hoverbox.TextSize ~= 1)
					hoverbox.Position = UDim2.new(0, (x + 16) * (1 / GuiLibrary["MainRescale"].Scale), 0,	(y - (hoverbox.Size.Y.Offset / 2) - 26) * (1 / GuiLibrary["MainRescale"].Scale))
				end)
			end
			buttontext.MouseLeave:Connect(function()
				hoverbox.Visible = false
				if buttonapi["Enabled"] == false then
					tweenService:Create(toggleframe1, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(60, 60, 60)}):Play()
				end
			end)

			GuiLibrary.ObjectsThatCanBeSaved[argstable["Name"].."Toggle"] = {["Type"] = "Toggle", ["Object"] = buttontext, ["Api"] = buttonapi}
			return buttonapi
		end

		windowapi["CreateTextList"] = function(argstable)
			local textGuiLibrary = {}
			local amount = #children:GetChildren()
			local frame = Instance.new("Frame")
			frame.Size = UDim2.new(0, 220, 0, 40)
			frame.BackgroundTransparency = 1
			frame.ClipsDescendants = true
			frame.LayoutOrder = amount
			frame.Name = argstable["Name"]
			frame.Parent = children
			local textboxbkg = Instance.new("ImageLabel")
			textboxbkg.BackgroundTransparency = 1
			textboxbkg.Name = "AddBoxBKG"
			textboxbkg.Size = UDim2.new(0, (argstable["Name"] == "ProfilesList" and 150 or 200), 0, 31)
			textboxbkg.Position = UDim2.new(0, 10, 0, 5)
			textboxbkg.ClipsDescendants = true
			textboxbkg.Image = downloadVapeAsset((argstable["Name"] == "ProfilesList" and "vape/assets/TextBoxBKG2.png" or "vape/assets/TextBoxBKG.png"))
			textboxbkg.Parent = frame
			local textbox = Instance.new("TextBox")
			textbox.Size = UDim2.new(0, 159, 1, 0)
			textbox.Position = UDim2.new(0, 11, 0, 0)
			textbox.TextXAlignment = Enum.TextXAlignment.Left
			textbox.Name = "AddBox"
			textbox.BackgroundTransparency = 1
			textbox.TextColor3 = Color3.new(1, 1, 1)
			textbox.PlaceholderColor3 = Color3.fromRGB(200, 200, 200)
			textbox.Font = Enum.Font.SourceSans
			textbox.Text = ""
			textbox.PlaceholderText = argstable["TempText"]
			textbox.TextSize = 17
			textbox.Parent = textboxbkg
			local addbutton = Instance.new("ImageButton")
			addbutton.BorderSizePixel = 0
			addbutton.Name = "AddButton"
			addbutton.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
			addbutton.Position = UDim2.new(0, (argstable["Name"] == "ProfilesList" and 124 or 174), 0, 8)
			addbutton.AutoButtonColor = false
			addbutton.Size = UDim2.new(0, 16, 0, 16)
			addbutton.ImageColor3 = Color3.fromHSV(0.44, 1, 1)
			addbutton.Image = downloadVapeAsset("vape/assets/AddItem.png")
			addbutton.Parent = textboxbkg
			local scrollframebkg = Instance.new("Frame")
			scrollframebkg.ZIndex = 2
			scrollframebkg.Name = "ScrollingFrameBKG"
			scrollframebkg.Size = UDim2.new(0, 220, 0, 3)
			scrollframebkg.BackgroundTransparency = 1
			scrollframebkg.LayoutOrder = amount
			scrollframebkg.Parent = children
			local scrollframe = Instance.new("ScrollingFrame")
			scrollframe.ZIndex = 2
			scrollframe.Size = UDim2.new(0, 200, 0, 3)
			scrollframe.Position = UDim2.new(0, 10, 0, 0)
			scrollframe.BackgroundTransparency = 1
			scrollframe.ScrollBarThickness = 0
			scrollframe.BorderSizePixel = 0
			scrollframe.ScrollBarImageColor3 = Color3.new(0, 0, 0)
			scrollframe.LayoutOrder = amount
			scrollframe.Parent = scrollframebkg
			local uilistlayout3 = Instance.new("UIListLayout")
			uilistlayout3.Padding = UDim.new(0, 3)
			uilistlayout3.Parent = scrollframe
			uilistlayout3:GetPropertyChangedSignal("AbsoluteContentSize"):Connect(function()
				scrollframe.CanvasSize = UDim2.new(0, 0, 0, uilistlayout3.AbsoluteContentSize.Y * (1 / GuiLibrary["MainRescale"].Scale))
				scrollframe.Size = UDim2.new(0, 220, 0, math.clamp(uilistlayout3.AbsoluteContentSize.Y * (1 / GuiLibrary["MainRescale"].Scale), 1, 105))
				scrollframebkg.Size = UDim2.new(0, 220, 0, math.clamp(uilistlayout3.AbsoluteContentSize.Y * (1 / GuiLibrary["MainRescale"].Scale), 1, 105))
			end)

			textGuiLibrary["Object"] = frame
			textGuiLibrary["ScrollingObject"] = scrollframebkg
			textGuiLibrary["ObjectList"] = {}
			textGuiLibrary["RefreshValues"] = function(tab)
				textGuiLibrary["ObjectList"] = tab
				for i2,v2 in pairs(scrollframe:GetChildren()) do
					if v2:IsA("TextButton") then v2:Remove() end
				end
				for i,v in pairs(textGuiLibrary["ObjectList"]) do
					local itemframe = Instance.new("TextButton")
					itemframe.Size = UDim2.new(0, 200, 0, 33)
					itemframe.Text = ""
					itemframe.AutoButtonColor = false
					itemframe.BackgroundColor3 = Color3.fromRGB(31, 30, 31)
					itemframe.BorderSizePixel = 0
					itemframe.Parent = scrollframe
					local itemcorner = Instance.new("UICorner")
					itemcorner.CornerRadius = UDim.new(0, 6)
					itemcorner.Parent = itemframe
					local itemtext = Instance.new("TextLabel")
					itemtext.BackgroundTransparency = 1
					itemtext.Size = UDim2.new(0, 193, 0, 33)
					itemtext.Name = "ItemText"
					itemtext.Position = UDim2.new(0, 8, 0, 0)
					itemtext.Font = Enum.Font.SourceSans
					itemtext.TextSize = 17
					itemtext.Text = v
					itemtext.TextXAlignment = Enum.TextXAlignment.Left
					itemtext.TextColor3 = Color3.fromRGB(86, 85, 86)
					itemtext.Parent = itemframe
					local deletebutton = Instance.new("ImageButton")
					deletebutton.Size = UDim2.new(0, 6, 0, 6)
					deletebutton.BackgroundTransparency = 1
					deletebutton.AutoButtonColor = false
					deletebutton.ZIndex = 1
					deletebutton.Image = downloadVapeAsset("vape/assets/AddRemoveIcon1.png")
					deletebutton.Position = UDim2.new(1, -16, 0, 14)
					deletebutton.Parent = itemframe
					deletebutton.MouseButton1Click:Connect(function()
						table.remove(textGuiLibrary["ObjectList"], i)
						textGuiLibrary["RefreshValues"](textGuiLibrary["ObjectList"])
						if argstable["RemoveFunction"] then
							argstable["RemoveFunction"](i, v)
						end
					end)
					if argstable["CustomFunction"] then
						argstable["CustomFunction"](itemframe, v)
					end
				end
			end
			if not argstable["NoSave"] then
				GuiLibrary.ObjectsThatCanBeSaved[argstable["Name"].."TextList"] = {["Type"] = "TextList", ["Api"] = textGuiLibrary}
			end

			local function AddToList()
                table.insert(textGuiLibrary["ObjectList"], textbox.Text)
                textGuiLibrary["RefreshValues"](textGuiLibrary["ObjectList"])
                if argstable["AddFunction"] then
                    argstable["AddFunction"](textbox.Text)
                end
                textbox.Text = ""
            end

            addbutton.MouseButton1Click:Connect(AddToList)
            textbox.FocusLost:Connect(function(enter)
                if enter then
                    AddToList()
                    textbox:CaptureFocus()
                end
            end)
			return textGuiLibrary
		end

		windowapi["CreateCircleTextList"] = function(argstable)
			local textGuiLibrary = {}
			local amount = #children:GetChildren()
			local frame = Instance.new("Frame")
			frame.Size = UDim2.new(0, 220, 0, 40)
			frame.BackgroundTransparency = 1
			frame.ClipsDescendants = true
			frame.LayoutOrder = amount
			frame.Name = argstable["Name"]
			frame.Parent = children
			local textboxbkg = Instance.new("ImageLabel")
			textboxbkg.BackgroundTransparency = 1
			textboxbkg.Name = "AddBoxBKG"
			textboxbkg.Size = UDim2.new(0, (argstable["Name"] == "ProfilesList" and 150 or 200), 0, 31)
			textboxbkg.Position = UDim2.new(0, 10, 0, 5)
			textboxbkg.ClipsDescendants = true
			textboxbkg.Image = downloadVapeAsset((argstable["Name"] == "ProfilesList" and "vape/assets/TextBoxBKG2.png" or "vape/assets/TextBoxBKG.png"))
			textboxbkg.Parent = frame
			local textbox = Instance.new("TextBox")
			textbox.Size = UDim2.new(0, 159, 1, 0)
			textbox.Position = UDim2.new(0, 11, 0, 0)
			textbox.TextXAlignment = Enum.TextXAlignment.Left
			textbox.Name = "AddBox"
			textbox.BackgroundTransparency = 1
			textbox.TextColor3 = Color3.new(1, 1, 1)
			textbox.PlaceholderColor3 = Color3.fromRGB(200, 200, 200)
			textbox.Font = Enum.Font.SourceSans
			textbox.Text = ""
			textbox.PlaceholderText = argstable["TempText"]
			textbox.TextSize = 17
			textbox.Parent = textboxbkg
			local addbutton = Instance.new("ImageButton")
			addbutton.BorderSizePixel = 0
			addbutton.Name = "AddButton"
			addbutton.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
			addbutton.Position = UDim2.new(0, (argstable["Name"] == "ProfilesList" and 124 or 174), 0, 8)
			addbutton.AutoButtonColor = false
			addbutton.Size = UDim2.new(0, 16, 0, 16)
			addbutton.ImageColor3 = argstable["Color"]
			addbutton.Image = downloadVapeAsset("vape/assets/AddItem.png")
			addbutton.Parent = textboxbkg
			local scrollframebkg = Instance.new("Frame")
			scrollframebkg.ZIndex = 2
			scrollframebkg.Name = "ScrollingFrameBKG"
			scrollframebkg.Size = UDim2.new(0, 220, 0, 3)
			scrollframebkg.BackgroundTransparency = 1
			scrollframebkg.LayoutOrder = amount
			scrollframebkg.Parent = children
			local scrollframe = Instance.new("ScrollingFrame")
			scrollframe.ZIndex = 2
			scrollframe.Size = UDim2.new(0, 200, 0, 3)
			scrollframe.Position = UDim2.new(0, 10, 0, 0)
			scrollframe.BackgroundTransparency = 1
			scrollframe.ScrollBarThickness = 0
			scrollframe.ScrollBarImageColor3 = Color3.new(0, 0, 0)
			scrollframe.LayoutOrder = amount
			scrollframe.Parent = scrollframebkg
			local uilistlayout3 = Instance.new("UIListLayout")
			uilistlayout3.Padding = UDim.new(0, 3)
			uilistlayout3.Parent = scrollframe
			uilistlayout3:GetPropertyChangedSignal("AbsoluteContentSize"):Connect(function()
				scrollframe.CanvasSize = UDim2.new(0, 0, 0, uilistlayout3.AbsoluteContentSize.Y * (1 / GuiLibrary["MainRescale"].Scale))
				scrollframe.Size = UDim2.new(0, 220, 0, math.clamp(uilistlayout3.AbsoluteContentSize.Y * (1 / GuiLibrary["MainRescale"].Scale), 1, 105))
				scrollframebkg.Size = UDim2.new(0, 220, 0, math.clamp(uilistlayout3.AbsoluteContentSize.Y * (1 / GuiLibrary["MainRescale"].Scale), 1, 105) + 3)
			end)

			textGuiLibrary["Object"] = frame
			textGuiLibrary["ScrollingObject"] = scrollframebkg
			textGuiLibrary["ObjectList"] = {}
			textGuiLibrary["ObjectListEnabled"] = {}
			local hoveredover = {}
			textGuiLibrary["RefreshValues"] = function(tab, tab2)
				textGuiLibrary["ObjectList"] = tab
				if tab2 then
					textGuiLibrary["ObjectListEnabled"] = tab2
				end
				for i2,v2 in pairs(scrollframe:GetChildren()) do
					if v2:IsA("TextButton") then v2:Remove() end
				end
				for i,v in pairs(textGuiLibrary["ObjectList"]) do
					local objenabled = textGuiLibrary["ObjectListEnabled"][i]
					local itemframe = Instance.new("TextButton")
					itemframe.Size = UDim2.new(0, 200, 0, 33)
					itemframe.Text = ""
					itemframe.AutoButtonColor = false
					itemframe.BackgroundColor3 = (hoveredover[i] and Color3.fromRGB(26, 25, 26) or Color3.fromRGB(31, 30, 31))
					itemframe.BorderSizePixel = 0
					itemframe.Parent = scrollframe
					local itemcorner = Instance.new("UICorner")
					itemcorner.CornerRadius = UDim.new(0, 6)
					itemcorner.Parent = itemframe
					local itemtext = Instance.new("TextLabel")
					itemtext.BackgroundTransparency = 1
					itemtext.Size = UDim2.new(0, 157, 0, 33)
					itemtext.Name = "ItemText"
					itemtext.Position = UDim2.new(0, 36, 0, 0)
					itemtext.Font = Enum.Font.SourceSans
					itemtext.TextSize = 17
					itemtext.Text = v
					itemtext.TextXAlignment = Enum.TextXAlignment.Left
					itemtext.TextColor3 = (objenabled and Color3.fromRGB(160, 160, 160) or Color3.fromRGB(90, 90, 90))
					itemtext.Parent = itemframe
					local friendcircle = Instance.new("Frame")
					friendcircle.Size = UDim2.new(0, 10, 0, 10)
					friendcircle.Name = "FriendCircle"
					friendcircle.BackgroundColor3 = (objenabled and argstable["Color"] or Color3.fromRGB(120, 120, 120))
					friendcircle.BorderSizePixel = 0
					friendcircle.Position = UDim2.new(0, 10, 0, 13)
					friendcircle.Parent = itemframe
					local friendcorner = Instance.new("UICorner")
					friendcorner.CornerRadius = UDim.new(0, 8)
					friendcorner.Parent = friendcircle
					local friendcircle2 = friendcircle:Clone()
					friendcircle2.Size = UDim2.new(0, 8, 0, 8)
					friendcircle2.BackgroundColor3 = Color3.fromRGB(31, 31, 31)
					friendcircle2.Position = UDim2.new(0, 1, 0, 1)
					friendcircle2.Visible = not objenabled
					friendcircle2.Parent = friendcircle
					itemframe:GetPropertyChangedSignal("BackgroundColor3"):Connect(function()
						friendcircle2.BackgroundColor3 = itemframe.BackgroundColor3
					end)
					itemframe.MouseEnter:Connect(function()
						itemframe.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
						hoveredover[i] = true
					end)
					itemframe.MouseLeave:Connect(function()
						itemframe.BackgroundColor3 = Color3.fromRGB(31, 30, 31)
						hoveredover[i] = nil
					end)
					itemframe.MouseButton1Click:Connect(function()
						textGuiLibrary["ObjectListEnabled"][i] = not textGuiLibrary["ObjectListEnabled"][i]
						textGuiLibrary["RefreshValues"](textGuiLibrary["ObjectList"])
					end)
					itemframe.MouseButton2Click:Connect(function()
						textGuiLibrary["ObjectListEnabled"][i] = not textGuiLibrary["ObjectListEnabled"][i]
						textGuiLibrary["RefreshValues"](textGuiLibrary["ObjectList"])
					end)
					local deletebutton = Instance.new("ImageButton")
					deletebutton.Size = UDim2.new(0, 6, 0, 6)
					deletebutton.BackgroundTransparency = 1
					deletebutton.AutoButtonColor = false
					deletebutton.ZIndex = 2
					deletebutton.Image = downloadVapeAsset("vape/assets/AddRemoveIcon1.png")
					deletebutton.Position = UDim2.new(1, -16, 0, 14)
					deletebutton.Parent = itemframe
					deletebutton.MouseButton1Click:Connect(function()
						table.remove(textGuiLibrary["ObjectList"], i)
						textGuiLibrary["ObjectListEnabled"][i] = nil
						textGuiLibrary["RefreshValues"](textGuiLibrary["ObjectList"])
						if argstable["RemoveFunction"] then
							argstable["RemoveFunction"](i, v)
						end
					end)
				end
			end

			GuiLibrary.ObjectsThatCanBeSaved[argstable["Name"].."TextCircleList"] = {["Type"] = "TextCircleList", ["Api"] = textGuiLibrary}
			local function AddToList()
                local num = #textGuiLibrary["ObjectList"] + 1
                textGuiLibrary["ObjectList"][num] = textbox.Text
                textGuiLibrary["ObjectListEnabled"][num] = true
                textGuiLibrary["RefreshValues"](textGuiLibrary["ObjectList"])
                if argstable["AddFunction"] then
                    argstable["AddFunction"](textbox.Text)
                end
                textbox.Text = ""
            end
            addbutton.MouseButton1Click:Connect(AddToList)
            textbox.FocusLost:Connect(function(enter)
                if enter then
                    AddToList()
                    textbox:CaptureFocus()
                end
            end)
			return textGuiLibrary
		end


		return windowapi
	end

	GuiLibrary["CreateLegitModule"] = function(legittable)
		local legitapi = {}
		local customlegit = Instance.new("Frame")
		customlegit.Size = UDim2.new(0, 40, 0, 40)
		customlegit.BackgroundTransparency = 1
		customlegit.BackgroundColor3 = Color3.new(0, 1, 0)
		customlegit.BorderSizePixel = 0
		customlegit.Visible = false
		customlegit.Parent = legitgui
		local legitframe = Instance.new("TextButton")
		legitframe.AutoButtonColor = false
		legitframe.Text = ""
		legitframe.BackgroundColor3 = Color3.fromRGB(31, 30, 31)
		legitframe.Size = UDim2.new(0, 163, 0, 114)
		legitframe.Parent = LegitModulesList
		local legitframecorner = Instance.new("UICorner")
		legitframecorner.CornerRadius = UDim.new(0, 5)
		legitframecorner.Parent = legitframe
		local legitframetext = Instance.new("TextLabel")
		legitframetext.Font = Enum.Font.Gotham
		legitframetext.TextSize = 15
		legitframetext.BackgroundTransparency = 1
		legitframetext.TextXAlignment = Enum.TextXAlignment.Left
		legitframetext.TextYAlignment = Enum.TextYAlignment.Top
		legitframetext.TextColor3 = Color3.fromRGB(160, 160, 160)
		legitframetext.Size = UDim2.new(1, -16, 0, 22)
		legitframetext.Position = UDim2.new(0, 16, 0, 83)
		legitframetext.Text = legittable.Name
		legitframetext.Parent = legitframe
		local toggleframe1 = Instance.new("Frame")
		toggleframe1.Size = UDim2.new(0, 22, 0, 12)
		toggleframe1.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
		toggleframe1.BorderSizePixel = 0
		toggleframe1.Name = "ToggleFrame1"
		toggleframe1.Position = UDim2.new(1, -57, 0, 14)
		toggleframe1.Parent = legitframe
		local toggleframe2 = Instance.new("Frame")
		toggleframe2.Size = UDim2.new(0, 8, 0, 8)
		toggleframe2.Active = false
		toggleframe2.Position = UDim2.new(0, 2, 0, 2)
		toggleframe2.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
		toggleframe2.BorderSizePixel = 0
		toggleframe2.Parent = toggleframe1
		local uicorner = Instance.new("UICorner")
		uicorner.CornerRadius = UDim.new(0, 16)
		uicorner.Parent = toggleframe1
		local uicorner2 = Instance.new("UICorner")
		uicorner2.CornerRadius = UDim.new(0, 16)
		uicorner2.Parent = toggleframe2
		dragGUI(customlegit, true)
		legitapi.Enabled = false

		legitapi.ToggleButton = function(first)
			legitapi.Enabled = not legitapi.Enabled
			customlegit.Visible = legitapi.Enabled
			if legitapi.Enabled then
				legitframe.BackgroundColor3 = Color3.fromRGB(40, 39, 40)
				legitframetext.TextColor3 = Color3.fromRGB(228, 228, 228)
				if not first then
					tweenService:Create(toggleframe1, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Hue"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Sat"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Value"])}):Play()
				else
					toggleframe1.BackgroundColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Hue"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Sat"], GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"]["Api"]["Value"])
				end
				toggleframe2:TweenPosition(UDim2.new(0, 12, 0, 2), Enum.EasingDirection.InOut, Enum.EasingStyle.Linear, 0.1, true)
			else
				legitframe.BackgroundColor3 = Color3.fromRGB(31, 30, 31)
				legitframetext.TextColor3 = Color3.fromRGB(160, 160, 160)
				if not first then
					tweenService:Create(toggleframe1, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(60, 60, 60)}):Play()
				else
					toggleframe1.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
				end
				toggleframe2:TweenPosition(UDim2.new(0, 2, 0, 2), Enum.EasingDirection.InOut, Enum.EasingStyle.Linear, 0.1, true)
			end
			legittable.Function(legitapi.Enabled)
		end
		legitframe.MouseButton1Click:Connect(function() legitapi["ToggleButton"](not legitapi["Enabled"], false) end)

		legitapi["GetCustomChildren"] = function()
			return customlegit
		end

		GuiLibrary.ObjectsThatCanBeSaved[legittable.Name.."LegitModule"] = {Api = legitapi, Type = "LegitModule", Object = customlegit, Toggle = toggleframe1}
		return legitapi
	end

	local function bettertween(obj, newpos, dir, style, tim, override)
		task.spawn(function()
			local frame = Instance.new("Frame")
			frame.Visible = false
			frame.Position = obj.Position
			frame.Parent = GuiLibrary["MainGui"]
			frame:GetPropertyChangedSignal("Position"):Connect(function()
				obj.Position = UDim2.new(obj.Position.X.Scale, obj.Position.X.Offset, frame.Position.Y.Scale, frame.Position.Y.Offset)
			end)
			pcall(function()
				frame:TweenPosition(newpos, dir, style, tim, override)
			end)
			frame.Parent = nil
			task.wait(tim)
			frame:Remove()
		end)
	end

	local function bettertween2(obj, newpos, dir, style, tim, override)
		task.spawn(function()
			local frame = Instance.new("Frame")
			frame.Visible = false
			frame.Position = obj.Position
			frame.Parent = GuiLibrary["MainGui"]
			frame:GetPropertyChangedSignal("Position"):Connect(function()
				obj.Position = UDim2.new(frame.Position.X.Scale, frame.Position.X.Offset, obj.Position.Y.Scale, obj.Position.Y.Offset)
			end)
			pcall(function()
				frame:TweenPosition(newpos, dir, style, tim, override)
			end)
			frame.Parent = nil
			task.wait(tim)
			frame:Remove()
		end)
	end

	notificationwindow.ChildRemoved:Connect(function()
		for i,v in pairs(notificationwindow:GetChildren()) do
			bettertween(v, UDim2.new(1, v.Position.X.Offset, 1, -(150 + 80 * (i - 1))), Enum.EasingDirection.In, Enum.EasingStyle.Sine, 0.15, true)
		end
	end)

	local function removeTags(str)
        str = str:gsub("<br%s*/>", "\n")
        return (str:gsub("<[^<>]->", ""))
    end

	GuiLibrary["CreateNotification"] = function(top, bottom, duration, customicon)
		local size = math.max( textService:GetTextSize(removeTags(bottom), 13, Enum.Font.Gotham, Vector2.new(99999, 99999)).X + 60, 266)
		local offset = #notificationwindow:GetChildren()
		local frame = Instance.new("Frame")
		frame.Size = UDim2.new(0, size, 0, 75)
		frame.Position = UDim2.new(1, 0, 1, -(150 + 80 * offset))
		frame.BackgroundTransparency = 1
		frame.BackgroundColor3 = Color3.new(0, 0,0)
		frame.BorderSizePixel = 0
		frame.Parent = notificationwindow
		frame.Visible = GuiLibrary["Notifications"]
		frame.ClipsDescendants = false
		local image = Instance.new("ImageLabel")
		image.SliceCenter = Rect.new(67, 59, 323, 120)
		image.Position = UDim2.new(0, -61, 0, -50)
		image.BackgroundTransparency = 1
		image.Name = "Frame"
		image.ScaleType = Enum.ScaleType.Slice
		image.Image = downloadVapeAsset("vape/assets/NotificationBackground.png")
		image.Size = UDim2.new(1, 61, 0, 159)
		image.Parent = frame
		local uicorner = Instance.new("UICorner")
		uicorner.CornerRadius = UDim.new(0, 6)
		uicorner.Parent = frame
		local frame2 = Instance.new("ImageLabel")
		frame2.BackgroundColor3 = Color3.new(1, 1, 1)
		frame2.Name = "Frame"
		frame2:GetPropertyChangedSignal("BackgroundColor3"):Connect(function()
			frame2.ImageColor3 = frame2.BackgroundColor3
		end)
		frame2.BackgroundTransparency = 1
		frame2.SliceCenter = Rect.new(2, 0, 224, 2)
		frame2.Size = UDim2.new(1, -61, 0, 2)
		frame2.ScaleType = Enum.ScaleType.Slice
		frame2.Position = UDim2.new(0, 63, 1, -36)
		frame2.ZIndex = 2
		frame2.Image = downloadVapeAsset("vape/assets/NotificationBar.png")
		frame2.BorderSizePixel = 0
		frame2.Parent = image
		local icon = Instance.new("ImageLabel")
		icon.Name = "IconLabel"
		icon.Image = downloadVapeAsset(customicon and "vape/"..customicon or "vape/assets/InfoNotification.png")
		icon.BackgroundTransparency = 1
		icon.Position = UDim2.new(0, -6, 0, -6)
		icon.Size = UDim2.new(0, 60, 0, 60)
		icon.Parent = frame
		local icon2 = icon:Clone()
		icon2.ImageColor3 = Color3.new(0, 0, 0)
		icon2.ZIndex = -1
		icon2.Position = UDim2.new(0, 1, 0, 1)
		icon2.ImageTransparency = 0.5
		icon2.Parent = icon
		local textlabel1 = Instance.new("TextLabel")
		textlabel1.Font = Enum.Font.Arial
		textlabel1.TextSize = 14
		textlabel1.RichText = true
		textlabel1.TextTransparency = 0.1
		textlabel1.TextColor3 = Color3.new(1, 1, 1)
		textlabel1.BackgroundTransparency = 1
		textlabel1.Position = UDim2.new(0, 46, 0, 17)
		textlabel1.TextXAlignment = Enum.TextXAlignment.Left
		textlabel1.TextYAlignment = Enum.TextYAlignment.Top
		textlabel1.Text = (translations[top] ~= nil and translations[top] or top)
		textlabel1.Parent = frame
		local textlabel2 = textlabel1:Clone()
		textlabel2.Position = UDim2.new(0, 46, 0, 44)
		textlabel2.Font = Enum.Font.Arial
		textlabel2.TextTransparency = 0
		textlabel2.TextColor3 = Color3.fromRGB(170, 170, 170)
		textlabel2.RichText = true
		textlabel2.Text = bottom
		textlabel2.Parent = frame
		task.spawn(function()
			pcall(function()
				bettertween2(frame, UDim2.new(1, -(size - 4), 1, -(150 + 80 * offset)), Enum.EasingDirection.In, Enum.EasingStyle.Sine, 0.15, true)
				task.wait(0.15)
				frame2:TweenSize(UDim2.new(0, 0, 0, 2), Enum.EasingDirection.In, Enum.EasingStyle.Linear, duration, true)
				task.wait(duration)
				bettertween2(frame, UDim2.new(1, 0, 1, frame.Position.Y.Offset), Enum.EasingDirection.In, Enum.EasingStyle.Sine, 0.15, true)
				task.wait(0.15)
				frame:Remove()
			end)
		end)
		return frame
	end

	GuiLibrary["LoadedAnimation"] = function(enabled)
		if enabled then
			--no cache but its ran 1 time so idc
			GuiLibrary.CreateNotification("Finished Loading", inputService.TouchEnabled and GuiLibrary["GUIKeybind"] == "RightShift" and "Press the button in the top right to open GUI" or "Press "..string.upper(GuiLibrary["GUIKeybind"]).." to open GUI", 5)
		end
	end

	local holdingalt = false
	local uninjected = false

	if inputService.TouchEnabled then
		local button = Instance.new("TextButton")
		button.Position = UDim2.new(1, -30, 0, 0)
		button.Text = "Vape"
		button.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
		button.TextColor3 = Color3.new(1, 1, 1)
		button.Size = UDim2.new(0, 30, 0, 20)
		button.BorderSizePixel = 0
		button.BackgroundTransparency = 0.5
		button.Parent = GuiLibrary.MainGui
		button.MouseButton1Click:Connect(function()
			clickgui.Visible = not clickgui.Visible
			legitgui.Visible = not clickgui.Visible
			inputService.OverrideMouseIconBehavior = (clickgui.Visible and Enum.OverrideMouseIconBehavior.ForceShow or game:GetService("VRService").VREnabled and Enum.OverrideMouseIconBehavior.ForceHide or Enum.OverrideMouseIconBehavior.None)
			--game:GetService("RunService"):SetRobloxGuiFocused(clickgui.Visible and GuiLibrary["MainBlur"].Size ~= 0 or guiService:GetErrorType() ~= Enum.ConnectionError.OK)
			for _, mobileButton in pairs(GuiLibrary.MobileButtons) do mobileButton.Visible = not clickgui.Visible end
			if OnlineProfilesBigFrame.Visible then
				OnlineProfilesBigFrame.Visible = false
			end
			if LegitModulesBigFrame.Visible then
				LegitModulesBigFrame.Visible = false
				legitgui.Visible = not clickgui.Visible
				for i, v in pairs(legitgui:GetChildren()) do
					if v:IsA("Frame") then v.BackgroundTransparency = legitgui.Visible and 0.8 or 1 end
				end
			end
		end)
		shared.VapeButton = button
	end

	GuiLibrary["KeyInputHandler"] = inputService.InputBegan:Connect(function(input1)
		if inputService:GetFocusedTextBox() == nil then
			if input1.KeyCode == Enum.KeyCode[GuiLibrary["GUIKeybind"]] and GuiLibrary["KeybindCaptured"] == false then
				clickgui.Visible = not clickgui.Visible
				legitgui.Visible = not clickgui.Visible
				inputService.OverrideMouseIconBehavior = (clickgui.Visible and Enum.OverrideMouseIconBehavior.ForceShow or game:GetService("VRService").VREnabled and Enum.OverrideMouseIconBehavior.ForceHide or Enum.OverrideMouseIconBehavior.None)
				--game:GetService("RunService"):SetRobloxGuiFocused(clickgui.Visible and GuiLibrary["MainBlur"].Size ~= 0 or guiService:GetErrorType() ~= Enum.ConnectionError.OK)
				for _, mobileButton in pairs(GuiLibrary.MobileButtons) do mobileButton.Visible = not clickgui.Visible end
				if OnlineProfilesBigFrame.Visible then
					OnlineProfilesBigFrame.Visible = false
				end
				if LegitModulesBigFrame.Visible then
					LegitModulesBigFrame.Visible = false
					legitgui.Visible = not clickgui.Visible
					for i, v in pairs(legitgui:GetChildren()) do
						if v:IsA("Frame") then v.BackgroundTransparency = legitgui.Visible and 0.8 or 1 end
					end
				end
			end
			if input1.KeyCode == Enum.KeyCode.RightAlt then
				holdingalt = true
			end
			if input1.KeyCode == Enum.KeyCode.Home and holdingalt and (not uninjected) then
				GuiLibrary["SelfDestruct"]()
				uninjected = true
			end
			if GuiLibrary["KeybindCaptured"] and input1.KeyCode ~= Enum.KeyCode.LeftShift then
				local hah = string.gsub(tostring(input1.KeyCode), "Enum.KeyCode.", "")
				GuiLibrary["PressedKeybindKey"] = (hah ~= "Unknown" and hah or "")
			end
			for modules,aGuiLibrary in pairs(GuiLibrary.ObjectsThatCanBeSaved) do
				if (aGuiLibrary["Type"] == "OptionsButton" or aGuiLibrary["Type"] == "Button") and (aGuiLibrary["Api"]["Keybind"] ~= nil and aGuiLibrary["Api"]["Keybind"] ~= "") and GuiLibrary["KeybindCaptured"] == false then
					if input1.KeyCode == Enum.KeyCode[aGuiLibrary["Api"]["Keybind"]] and aGuiLibrary["Api"]["Keybind"] ~= GuiLibrary["GUIKeybind"] then
						aGuiLibrary["Api"]["ToggleButton"](false)
						if GuiLibrary["ToggleNotifications"] then
							GuiLibrary["CreateNotification"]("Module Toggled", aGuiLibrary["Api"]["Name"]..' <font color="#FFFFFF">has been</font> <font color="'..(aGuiLibrary["Api"]["Enabled"] and '#32CD32' or '#FF6464')..'">'..(aGuiLibrary["Api"]["Enabled"] and "Enabled" or "Disabled")..'</font><font color="#FFFFFF">!</font>', 1)
						end
					end
				end
			end
			for profilenametext, profiletab in pairs(GuiLibrary.Profiles) do
				if (profiletab["Keybind"] ~= nil and profiletab["Keybind"] ~= "") and GuiLibrary["KeybindCaptured"] == false and profilenametext ~= GuiLibrary.CurrentProfile then
					if input1.KeyCode == Enum.KeyCode[profiletab["Keybind"]] then
						GuiLibrary["SwitchProfile"](profilenametext)
					end
				end
			end
		end
	end)

	GuiLibrary["KeyInputHandler2"] = inputService.InputEnded:Connect(function(input1)
		if input1.KeyCode == Enum.KeyCode.RightAlt then
			holdingalt = false
		end
	end)

	searchbar:GetPropertyChangedSignal("Text"):Connect(function()
		searchbarchildren:ClearAllChildren()
		if searchbar.Text == "" then
			searchbarmain.Size = UDim2.new(0, 220, 0, 37)
		else
			local optionbuttons = {}
			for i,v in pairs(GuiLibrary.ObjectsThatCanBeSaved) do
				if i:find("OptionsButton") and i:sub(1, searchbar.Text:len()):lower() == searchbar.Text:lower() then
					local button = Instance.new("TextButton")
					button.Name = v.Object.Name
					button.AutoButtonColor = false
					button.Active = true
					button.Size = UDim2.new(1, 0, 0, 40)
					button.BorderSizePixel = 0
					button.Position = UDim2.new(0, 0, 0, 40 * #optionbuttons)
					button.ZIndex = 10
					button.BackgroundColor3 = v.Object.BackgroundColor3
					button.Text = ""
					button.LayoutOrder = amount
					button.Parent = searchbarchildren
					v.Object:GetPropertyChangedSignal("BackgroundColor3"):Connect(function()
						button.BackgroundColor3 = v.Object.BackgroundColor3
					end)
					local buttonactiveborder = Instance.new("Frame")
					buttonactiveborder.BackgroundTransparency = 0.75
					buttonactiveborder.BackgroundColor3 = Color3.new(0, 0, 0)
					buttonactiveborder.BorderSizePixel = 0
					buttonactiveborder.Size = UDim2.new(1, 0, 0, 1)
					buttonactiveborder.Position = UDim2.new(0, 0, 1, -1)
					buttonactiveborder.ZIndex = 10
					buttonactiveborder.Visible = false
					buttonactiveborder.Parent = button
					local button2 = Instance.new("ImageButton")
					button2.BackgroundTransparency = 1
					button2.Size = UDim2.new(0, 10, 0, 20)
					button2.Position = UDim2.new(1, -24, 0, 10)
					button2.Name = "OptionsButton"
					button2.ZIndex = 10
					button2.Image = v.Object.OptionsButton.Image
					button2.Parent = button
					v.Object.OptionsButton:GetPropertyChangedSignal("Image"):Connect(function()
						button2.Image = v.Object.OptionsButton.Image
					end)
					local buttontext = Instance.new("TextLabel")
					buttontext.BackgroundTransparency = 1
					buttontext.Name = "ButtonText"
					buttontext.Text = (translations[v.Object.Name:gsub("Button", "")] ~= nil and translations[v.Object.Name:gsub("Button", "")] or v.Object.Name:gsub("Button", ""))
					buttontext.Size = UDim2.new(0, 118, 0, 39)
					buttontext.Active = false
					buttontext.ZIndex = 10
					buttontext.TextColor3 = v.Object.ButtonText.TextColor3
					v.Object.ButtonText:GetPropertyChangedSignal("TextColor3"):Connect(function()
						buttontext.TextColor3 = v.Object.ButtonText.TextColor3
					end)
					buttontext.TextSize = 17
					buttontext.Font = Enum.Font.SourceSans
					buttontext.TextXAlignment = Enum.TextXAlignment.Left
					buttontext.Position = UDim2.new(0, 12, 0, 0)
					buttontext.Parent = button
					button.MouseButton1Click:Connect(function()
						v["Api"]["ToggleButton"](false)
					end)
					table.insert(optionbuttons, v)
				end
			end
			searchbarmain.Size = UDim2.new(0, 220, 0, 39 + (40 * #optionbuttons))
		end
	end)
	GuiLibrary["MainRescale"]:GetPropertyChangedSignal("Scale"):Connect(function()
		searchbarmain.Position = UDim2.new(0.5 / GuiLibrary["MainRescale"].Scale, -110, 0, -23)
	end)

	searchbaricon2.MouseButton1Click:Connect(function()
		LegitModulesBigFrame.Visible = true
		clickgui.Visible = false
		legitgui.Visible = not clickgui.Visible
		for i, v in pairs(legitgui:GetChildren()) do
			if v:IsA("Frame") then v.BackgroundTransparency = legitgui.Visible and 0.8 or 1 end
		end
	end)

	return GuiLibrary
end
repeat task.wait() until game:IsLoaded()
local GuiLibrary
local baseDirectory = (shared.VapePrivate and "vapeprivate/" or "vape/")
local vapeInjected = true
local oldRainbow = false
local errorPopupShown = false
local redownloadedAssets = false
local profilesLoaded = false
local teleportedServers = false
local gameCamera = workspace.CurrentCamera
local textService = game:GetService("TextService")
local playersService = game:GetService("Players")
local inputService = game:GetService("UserInputService")
local isfile = isfile or function(file)
	local suc, res = pcall(function() return readfile(file) end)
	return suc and res ~= nil
end
local setidentity = syn and syn.set_thread_identity or set_thread_identity or setidentity or setthreadidentity or function() end
local getidentity = syn and syn.get_thread_identity or get_thread_identity or getidentity or getthreadidentity or function() return 0 end
local vapeAssetTable = {
	["vape/assets/AddItem.png"] = "rbxassetid://13350763121",
	["vape/assets/AddRemoveIcon1.png"] = "rbxassetid://13350764147",
	["vape/assets/ArrowIndicator.png"] = "rbxassetid://13350766521",
	["vape/assets/BackIcon.png"] = "rbxassetid://13350767223",
	["vape/assets/BindBackground.png"] = "rbxassetid://13350767577",
	["vape/assets/BlatantIcon.png"] = "rbxassetid://13350767943",
	["vape/assets/CircleListBlacklist.png"] = "rbxassetid://13350768647",
	["vape/assets/CircleListWhitelist.png"] = "rbxassetid://13350769066",
	["vape/assets/ColorSlider1.png"] = "rbxassetid://13350769439",
	["vape/assets/ColorSlider2.png"] = "rbxassetid://13350769842",
	["vape/assets/CombatIcon.png"] = "rbxassetid://13350770192",
	["vape/assets/DownArrow.png"] = "rbxassetid://13350770749",
	["vape/assets/ExitIcon1.png"] = "rbxassetid://13350771140",
	["vape/assets/FriendsIcon.png"] = "rbxassetid://13350771464",
	["vape/assets/HoverArrow.png"] = "rbxassetid://13350772201",
	["vape/assets/HoverArrow2.png"] = "rbxassetid://13350772588",
	["vape/assets/HoverArrow3.png"] = "rbxassetid://13350773014",
	["vape/assets/HoverArrow4.png"] = "rbxassetid://13350773643",
	["vape/assets/InfoNotification.png"] = "rbxassetid://13350774006",
	["vape/assets/KeybindIcon.png"] = "rbxassetid://13350774323",
	["vape/assets/LegitModeIcon.png"] = "rbxassetid://13436400428",
	["vape/assets/MoreButton1.png"] = "rbxassetid://13350775005",
	["vape/assets/MoreButton2.png"] = "rbxassetid://13350775731",
	["vape/assets/MoreButton3.png"] = "rbxassetid://13350776241",
	["vape/assets/NotificationBackground.png"] = "rbxassetid://13350776706",
	["vape/assets/NotificationBar.png"] = "rbxassetid://13350777235",
	["vape/assets/OnlineProfilesButton.png"] = "rbxassetid://13350777717",
	["vape/assets/PencilIcon.png"] = "rbxassetid://13350778187",
	["vape/assets/PinButton.png"] = "rbxassetid://13350778654",
	["vape/assets/ProfilesIcon.png"] = "rbxassetid://13350779149",
	["vape/assets/RadarIcon1.png"] = "rbxassetid://13350779545",
	["vape/assets/RadarIcon2.png"] = "rbxassetid://13350779992",
	["vape/assets/RainbowIcon1.png"] = "rbxassetid://13350780571",
	["vape/assets/RainbowIcon2.png"] = "rbxassetid://13350780993",
	["vape/assets/RightArrow.png"] = "rbxassetid://13350781908",
	["vape/assets/SearchBarIcon.png"] = "rbxassetid://13350782420",
	["vape/assets/SettingsWheel1.png"] = "rbxassetid://13350782848",
	["vape/assets/SettingsWheel2.png"] = "rbxassetid://13350783258",
	["vape/assets/SliderArrow1.png"] = "rbxassetid://13350783794",
	["vape/assets/SliderArrowSeperator.png"] = "rbxassetid://13350784477",
	["vape/assets/SliderButton1.png"] = "rbxassetid://13350785680",
	["vape/assets/TargetIcon.png"] = "rbxassetid://13350786128",
	["vape/assets/TargetIcon1.png"] = "rbxassetid://13350786776",
	["vape/assets/TargetIcon2.png"] = "rbxassetid://13350787228",
	["vape/assets/TargetIcon3.png"] = "rbxassetid://13350787729",
	["vape/assets/TargetIcon4.png"] = "rbxassetid://13350788379",
	["vape/assets/TargetInfoIcon1.png"] = "rbxassetid://13350788860",
	["vape/assets/TargetInfoIcon2.png"] = "rbxassetid://13350789239",
	["vape/assets/TextBoxBKG.png"] = "rbxassetid://13350789732",
	["vape/assets/TextBoxBKG2.png"] = "rbxassetid://13350790229",
	["vape/assets/TextGUIIcon1.png"] = "rbxassetid://13350790634",
	["vape/assets/TextGUIIcon2.png"] = "rbxassetid://13350791175",
	["vape/assets/TextGUIIcon3.png"] = "rbxassetid://13350791758",
	["vape/assets/TextGUIIcon4.png"] = "rbxassetid://13350792279",
	["vape/assets/ToggleArrow.png"] = "rbxassetid://13350792786",
	["vape/assets/UpArrow.png"] = "rbxassetid://13350793386",
	["vape/assets/UtilityIcon.png"] = "rbxassetid://13350793918",
	["vape/assets/WarningNotification.png"] = "rbxassetid://13350794868",
	["vape/assets/WindowBlur.png"] = "rbxassetid://13350795660",
	["vape/assets/WorldIcon.png"] = "rbxassetid://13350796199",
	["vape/assets/VapeIcon.png"] = "rbxassetid://13350808582",
	["vape/assets/RenderIcon.png"] = "rbxassetid://13350832775",
	["vape/assets/VapeLogo1.png"] = "rbxassetid://13350860863",
	["vape/assets/VapeLogo3.png"] = "rbxassetid://13350872035",
	["vape/assets/VapeLogo2.png"] = "rbxassetid://13350876307",
	["vape/assets/VapeLogo4.png"] = "rbxassetid://13350877564"
}
if inputService:GetPlatform() ~= Enum.Platform.Windows then 
	--mobile exploit fix
	getgenv().getsynasset = nil
	getgenv().getcustomasset = nil
	-- why is this needed
	getsynasset = nil
	getcustomasset = nil
end
local getcustomasset = getsynasset or getcustomasset or function(location) return vapeAssetTable[location] or "" end
local customassetcheck = (getsynasset or getcustomasset) and true
local queueonteleport = syn and syn.queue_on_teleport or queue_on_teleport or function() end
local delfile = delfile or function(file) writefile(file, "") end

local function displayErrorPopup(text, funclist)
	local oldidentity = getidentity()
	setidentity(8)
	local ErrorPrompt = getrenv().require(game:GetService("CoreGui").RobloxGui.Modules.ErrorPrompt)
	local prompt = ErrorPrompt.new("Default")
	prompt._hideErrorCode = true
	local gui = Instance.new("ScreenGui", game:GetService("CoreGui"))
	prompt:setErrorTitle("Vape")
	local funcs
	if funclist then 
		funcs = {}
		local num = 0
		for i,v in pairs(funclist) do 
			num = num + 1
			table.insert(funcs, {
				Text = i,
				Callback = function() 
					prompt:_close() 
					v()
				end,
				Primary = num == #funclist
			})
		end
	end
	prompt:updateButtons(funcs or {{
		Text = "OK",
		Callback = function() 
			prompt:_close() 
		end,
		Primary = true
	}}, 'Default')
	prompt:setParent(gui)
	prompt:_open(text)
	setidentity(oldidentity)
end

local function vapeGithubRequest(scripturl)
	if not isfile("vape/"..scripturl) then
		local suc, res
		task.delay(15, function()
			if not res and not errorPopupShown then 
				errorPopupShown = true
				displayErrorPopup("The connection to github is taking a while, Please be patient.")
			end
		end)
		suc, res = pcall(function() return game:HttpGet("https://raw.githubusercontent.com/7GrandDadPGN/VapeV4ForRoblox/"..readfile("vape/commithash.txt").."/"..scripturl, true) end)
		if not suc or res == "404: Not Found" then
			displayErrorPopup("Failed to connect to github : vape/"..scripturl.." : "..res)
			error(res)
		end
		if scripturl:find(".lua") then res = "--This watermark is used to delete the file if its cached, remove it to make the file persist after commits.\n"..res end
		writefile("vape/"..scripturl, res)
	end
	return readfile("vape/"..scripturl)
end

local function downloadVapeAsset(path)
	if customassetcheck then
		if not isfile(path) then
			task.spawn(function()
				local textlabel = Instance.new("TextLabel")
				textlabel.Size = UDim2.new(1, 0, 0, 36)
				textlabel.Text = "Downloading "..path
				textlabel.BackgroundTransparency = 1
				textlabel.TextStrokeTransparency = 0
				textlabel.TextSize = 30
				textlabel.Font = Enum.Font.SourceSans
				textlabel.TextColor3 = Color3.new(1, 1, 1)
				textlabel.Position = UDim2.new(0, 0, 0, -36)
				textlabel.Parent = GuiLibrary.MainGui
				repeat task.wait() until isfile(path)
				textlabel:Destroy()
			end)
			local suc, req = pcall(function() return vapeGithubRequest(path:gsub("vape/assets", "assets")) end)
			if suc and req then
				writefile(path, req)
			else
				return ""
			end
		end
	end
	return getcustomasset(path) 
end

assert(not shared.VapeExecuted, "Vape Already Injected")
shared.VapeExecuted = true

for i,v in pairs({baseDirectory:gsub("/", ""), "vape", "vape/Libraries", "vape/CustomModules", "vape/Profiles", baseDirectory.."Profiles", "vape/assets"}) do 
	if not isfolder(v) then makefolder(v) end
end
task.spawn(function()
	local success, assetver = pcall(function() return vapeGithubRequest("assetsversion.txt") end)
	if not isfile("vape/assetsversion.txt") then writefile("vape/assetsversion.txt", "0") end
	if success and assetver > readfile("vape/assetsversion.txt") then
		redownloadedAssets = true
		if isfolder("vape/assets") and not shared.VapeDeveloper then
			if delfolder then
				delfolder("vape/assets")
				makefolder("vape/assets")
			end
		end
		writefile("vape/assetsversion.txt", assetver)
	end
end)
if not isfile("vape/CustomModules/cachechecked.txt") then
	local isNotCached = false
	for i,v in pairs({"vape/Universal.lua", "vape/MainScript.lua", "vape/GuiLibrary.lua"}) do 
		if isfile(v) and not readfile(v):find("--This watermark is used to delete the file if its cached, remove it to make the file persist after commits.") then
			isNotCached = true
		end 
	end
	if isfolder("vape/CustomModules") then 
		for i,v in pairs(listfiles("vape/CustomModules")) do 
			if isfile(v) and not readfile(v):find("--This watermark is used to delete the file if its cached, remove it to make the file persist after commits.") then
				isNotCached = true
			end 
		end
	end
	if isNotCached and not shared.VapeDeveloper then
		displayErrorPopup("Vape has detected uncached files, If you have CustomModules click no, else click yes.", {No = function() end, Yes = function()
			for i,v in pairs({"vape/Universal.lua", "vape/MainScript.lua", "vape/GuiLibrary.lua"}) do 
				if isfile(v) and not readfile(v):find("--This watermark is used to delete the file if its cached, remove it to make the file persist after commits.") then
					delfile(v)
				end 
			end
			for i,v in pairs(listfiles("vape/CustomModules")) do 
				if isfile(v) and not readfile(v):find("--This watermark is used to delete the file if its cached, remove it to make the file persist after commits.") then
					local last = v:split('\\')
					last = last[#last]
					local suc, publicrepo = pcall(function() return game:HttpGet("https://raw.githubusercontent.com/7GrandDadPGN/VapeV4ForRoblox/"..readfile("vape/commithash.txt").."/CustomModules/"..last) end)
					if suc and publicrepo and publicrepo ~= "404: Not Found" then
						writefile("vape/CustomModules/"..last, "--This watermark is used to delete the file if its cached, remove it to make the file persist after commits.\n"..publicrepo)
					end
				end 
			end
		end})
	end
	writefile("vape/CustomModules/cachechecked.txt", "verified")
end

GuiLibrary = loadstring(vapeGithubRequest("GuiLibrary.lua"))()
shared.GuiLibrary = GuiLibrary

local saveSettingsLoop = coroutine.create(function()
	if inputService.TouchEnabled then return end
	repeat
		GuiLibrary.SaveSettings()
        task.wait(10)
	until not vapeInjected or not GuiLibrary
end)

task.spawn(function()
	local image = Instance.new("ImageLabel")
	image.Image = downloadVapeAsset("vape/assets/CombatIcon.png")
	image.Position = UDim2.new()
	image.BackgroundTransparency = 1
	image.Size = UDim2.fromOffset(100, 100)
	image.ImageTransparency = 0.999
	image.Parent = GuiLibrary.MainGui
    image:GetPropertyChangedSignal("IsLoaded"):Connect(function()
        image:Destroy()
        image = nil
    end)
	task.spawn(function()
		task.wait(15)
		if image and image.ContentImageSize == Vector2.zero and (not errorPopupShown) and (not redownloadedAssets) and (not isfile("vape/assets/check3.txt")) then 
            errorPopupShown = true
            displayErrorPopup("Assets failed to load, Try another executor (executor : "..(identifyexecutor and identifyexecutor() or "Unknown")..")", {OK = function()
                writefile("vape/assets/check3.txt", "")
            end})
        end
	end)
end)

local GUI = GuiLibrary.CreateMainWindow()
local Combat = GuiLibrary.CreateWindow({
	Name = "Combat", 
	Icon = "vape/assets/CombatIcon.png", 
	IconSize = 15
})
local Blatant = GuiLibrary.CreateWindow({
	Name = "Blatant", 
	Icon = "vape/assets/BlatantIcon.png", 
	IconSize = 16
})
local Render = GuiLibrary.CreateWindow({
	Name = "Render", 
	Icon = "vape/assets/RenderIcon.png", 
	IconSize = 17
})
local Utility = GuiLibrary.CreateWindow({
	Name = "Utility", 
	Icon = "vape/assets/UtilityIcon.png", 
	IconSize = 17
})
local World = GuiLibrary.CreateWindow({
	Name = "World", 
	Icon = "vape/assets/WorldIcon.png", 
	IconSize = 16
})
local Friends = GuiLibrary.CreateWindow2({
	Name = "Friends", 
	Icon = "vape/assets/FriendsIcon.png", 
	IconSize = 17
})
local Targets = GuiLibrary.CreateWindow2({
	Name = "Targets", 
	Icon = "vape/assets/FriendsIcon.png", 
	IconSize = 17
})
local Profiles = GuiLibrary.CreateWindow2({
	Name = "Profiles", 
	Icon = "vape/assets/ProfilesIcon.png", 
	IconSize = 19
})
GUI.CreateDivider()
GUI.CreateButton({
	Name = "Combat", 
	Function = function(callback) Combat.SetVisible(callback) end, 
	Icon = "vape/assets/CombatIcon.png", 
	IconSize = 15
})
GUI.CreateButton({
	Name = "Blatant", 
	Function = function(callback) Blatant.SetVisible(callback) end, 
	Icon = "vape/assets/BlatantIcon.png", 
	IconSize = 16
})
GUI.CreateButton({
	Name = "Render", 
	Function = function(callback) Render.SetVisible(callback) end, 
	Icon = "vape/assets/RenderIcon.png", 
	IconSize = 17
})
GUI.CreateButton({
	Name = "Utility", 
	Function = function(callback) Utility.SetVisible(callback) end, 
	Icon = "vape/assets/UtilityIcon.png", 
	IconSize = 17
})
GUI.CreateButton({
	Name = "World", 
	Function = function(callback) World.SetVisible(callback) end, 
	Icon = "vape/assets/WorldIcon.png", 
	IconSize = 16
})
GUI.CreateDivider("MISC")
GUI.CreateButton({
	Name = "Friends", 
	Function = function(callback) Friends.SetVisible(callback) end, 
})
GUI.CreateButton({
	Name = "Targets", 
	Function = function(callback) Targets.SetVisible(callback) end, 
})
GUI.CreateButton({
	Name = "Profiles", 
	Function = function(callback) Profiles.SetVisible(callback) end, 
})

local FriendsTextListTable = {
	Name = "FriendsList", 
	TempText = "Username [Alias]", 
	Color = Color3.fromRGB(5, 133, 104)
}
local FriendsTextList = Friends.CreateCircleTextList(FriendsTextListTable)
FriendsTextList.FriendRefresh = Instance.new("BindableEvent")
FriendsTextList.FriendColorRefresh = Instance.new("BindableEvent")
local TargetsTextList = Targets.CreateCircleTextList({
	Name = "TargetsList", 
	TempText = "Username [Alias]", 
	Color = Color3.fromRGB(5, 133, 104)
})
local oldFriendRefresh = FriendsTextList.RefreshValues
FriendsTextList.RefreshValues = function(...)
	FriendsTextList.FriendRefresh:Fire()
	return oldFriendRefresh(...)
end
local oldTargetRefresh = TargetsTextList.RefreshValues
TargetsTextList.RefreshValues = function(...)
	FriendsTextList.FriendRefresh:Fire()
	return oldTargetRefresh(...)
end
Friends.CreateToggle({
	Name = "Use Friends",
	Function = function(callback) 
		FriendsTextList.FriendRefresh:Fire()
	end,
	Default = true
})
Friends.CreateToggle({
	Name = "Use Alias",
	Function = function(callback) end,
	Default = true,
})
Friends.CreateToggle({
	Name = "Spoof alias",
	Function = function(callback) end,
})
local friendRecolorToggle = Friends.CreateToggle({
	Name = "Recolor visuals",
	Function = function(callback) FriendsTextList.FriendColorRefresh:Fire() end,
	Default = true
})
local friendWindowFrame
Friends.CreateColorSlider({
	Name = "Friends Color", 
	Function = function(h, s, v) 
		local cachedColor = Color3.fromHSV(h, s, v)
		local addCircle = FriendsTextList.Object:FindFirstChild("AddButton", true)
		if addCircle then 
			addCircle.ImageColor3 = cachedColor
		end
		friendWindowFrame = friendWindowFrame or FriendsTextList.ScrollingObject and FriendsTextList.ScrollingObject:FindFirstChild("ScrollingFrame")
		if friendWindowFrame then 
			for i,v in pairs(friendWindowFrame:GetChildren()) do 
				local friendCircle = v:FindFirstChild("FriendCircle")
				local friendText = v:FindFirstChild("ItemText")
				if friendCircle and friendText then 
					friendCircle.BackgroundColor3 = friendText.TextColor3 == Color3.fromRGB(160, 160, 160) and cachedColor or friendCircle.BackgroundColor3
				end
			end
		end
		FriendsTextListTable.Color = cachedColor
		if friendRecolorToggle.Enabled then
			FriendsTextList.FriendColorRefresh:Fire()
		end
	end
})
local ProfilesTextList = {RefreshValues = function() end}
ProfilesTextList = Profiles.CreateTextList({
	Name = "ProfilesList",
	TempText = "Type name", 
	NoSave = true,
	AddFunction = function(profileName)
		GuiLibrary.Profiles[profileName] = {Keybind = "", Selected = false}
		local profiles = {}
		for i,v in pairs(GuiLibrary.Profiles) do 
			table.insert(profiles, i)
		end
		table.sort(profiles, function(a, b) return b == "default" and true or a:lower() < b:lower() end)
		ProfilesTextList.RefreshValues(profiles)
	end, 
	RemoveFunction = function(profileIndex, profileName) 
		if profileName ~= "default" and profileName ~= GuiLibrary.CurrentProfile then 
			pcall(function() delfile(baseDirectory.."Profiles/"..profileName..(shared.CustomSaveVape or game.PlaceId)..".vapeprofile.txt") end)
			GuiLibrary.Profiles[profileName] = nil
		else
			table.insert(ProfilesTextList.ObjectList, profileName)
			ProfilesTextList.RefreshValues(ProfilesTextList.ObjectList)
		end
	end, 
	CustomFunction = function(profileObject, profileName) 
		if GuiLibrary.Profiles[profileName] == nil then
			GuiLibrary.Profiles[profileName] = {Keybind = ""}
		end
		profileObject.MouseButton1Click:Connect(function()
			GuiLibrary.SwitchProfile(profileName)
		end)
		local newsize = UDim2.new(0, 20, 0, 21)
		local bindbkg = Instance.new("TextButton")
		bindbkg.Text = ""
		bindbkg.AutoButtonColor = false
		bindbkg.Size = UDim2.new(0, 20, 0, 21)
		bindbkg.Position = UDim2.new(1, -50, 0, 6)
		bindbkg.BorderSizePixel = 0
		bindbkg.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
		bindbkg.BackgroundTransparency = 0.95
		bindbkg.Visible = GuiLibrary.Profiles[profileName].Keybind ~= ""
		bindbkg.Parent = profileObject
		local bindimg = Instance.new("ImageLabel")
		bindimg.Image = downloadVapeAsset("vape/assets/KeybindIcon.png")
		bindimg.BackgroundTransparency = 1
		bindimg.Size = UDim2.new(0, 12, 0, 12)
		bindimg.Position = UDim2.new(0, 4, 0, 5)
		bindimg.ImageTransparency = 0.2
		bindimg.Active = false
		bindimg.Visible = (GuiLibrary.Profiles[profileName].Keybind == "")
		bindimg.Parent = bindbkg
		local bindtext = Instance.new("TextLabel")
		bindtext.Active = false
		bindtext.BackgroundTransparency = 1
		bindtext.TextSize = 16
		bindtext.Parent = bindbkg
		bindtext.Font = Enum.Font.SourceSans
		bindtext.Size = UDim2.new(1, 0, 1, 0)
		bindtext.TextColor3 = Color3.fromRGB(85, 85, 85)
		bindtext.Visible = (GuiLibrary.Profiles[profileName].Keybind ~= "")
		local bindtext2 = Instance.new("TextLabel")
		bindtext2.Text = "PRESS A KEY TO BIND"
		bindtext2.Size = UDim2.new(0, 150, 0, 33)
		bindtext2.Font = Enum.Font.SourceSans
		bindtext2.TextSize = 17
		bindtext2.TextColor3 = Color3.fromRGB(201, 201, 201)
		bindtext2.BackgroundColor3 = Color3.fromRGB(37, 37, 37)
		bindtext2.BorderSizePixel = 0
		bindtext2.Visible = false
		bindtext2.Parent = profileObject
		local bindround = Instance.new("UICorner")
		bindround.CornerRadius = UDim.new(0, 4)
		bindround.Parent = bindbkg
		bindbkg.MouseButton1Click:Connect(function()
			if not GuiLibrary.KeybindCaptured then
				GuiLibrary.KeybindCaptured = true
				task.spawn(function()
					bindtext2.Visible = true
					repeat task.wait() until GuiLibrary.PressedKeybindKey ~= ""
					local key = (GuiLibrary.PressedKeybindKey == GuiLibrary.Profiles[profileName].Keybind and "" or GuiLibrary.PressedKeybindKey)
					if key == "" then
						GuiLibrary.Profiles[profileName].Keybind = key
						newsize = UDim2.new(0, 20, 0, 21)
						bindbkg.Size = newsize
						bindbkg.Visible = true
						bindbkg.Position = UDim2.new(1, -(30 + newsize.X.Offset), 0, 6)
						bindimg.Visible = true
						bindtext.Visible = false
						bindtext.Text = key
					else
						local textsize = textService:GetTextSize(key, 16, bindtext.Font, Vector2.new(99999, 99999))
						newsize = UDim2.new(0, 13 + textsize.X, 0, 21)
						GuiLibrary.Profiles[profileName].Keybind = key
						bindbkg.Visible = true
						bindbkg.Size = newsize
						bindbkg.Position = UDim2.new(1, -(30 + newsize.X.Offset), 0, 6)
						bindimg.Visible = false
						bindtext.Visible = true
						bindtext.Text = key
					end
					GuiLibrary.PressedKeybindKey = ""
					GuiLibrary.KeybindCaptured = false
					bindtext2.Visible = false
				end)
			end
		end)
		bindbkg.MouseEnter:Connect(function() 
			bindimg.Image = downloadVapeAsset("vape/assets/PencilIcon.png") 
			bindimg.Visible = true
			bindtext.Visible = false
			bindbkg.Size = UDim2.new(0, 20, 0, 21)
			bindbkg.Position = UDim2.new(1, -50, 0, 6)
		end)
		bindbkg.MouseLeave:Connect(function() 
			bindimg.Image = downloadVapeAsset("vape/assets/KeybindIcon.png")
			if GuiLibrary.Profiles[profileName].Keybind ~= "" then
				bindimg.Visible = false
				bindtext.Visible = true
				bindbkg.Size = newsize
				bindbkg.Position = UDim2.new(1, -(30 + newsize.X.Offset), 0, 6)
			end
		end)
		profileObject.MouseEnter:Connect(function()
			bindbkg.Visible = true
		end)
		profileObject.MouseLeave:Connect(function()
			bindbkg.Visible = GuiLibrary.Profiles[profileName] and GuiLibrary.Profiles[profileName].Keybind ~= ""
		end)
		if GuiLibrary.Profiles[profileName].Keybind ~= "" then
			bindtext.Text = GuiLibrary.Profiles[profileName].Keybind
			local textsize = textService:GetTextSize(GuiLibrary.Profiles[profileName].Keybind, 16, bindtext.Font, Vector2.new(99999, 99999))
			newsize = UDim2.new(0, 13 + textsize.X, 0, 21)
			bindbkg.Size = newsize
			bindbkg.Position = UDim2.new(1, -(30 + newsize.X.Offset), 0, 6)
		end
		if profileName == GuiLibrary.CurrentProfile then
			profileObject.BackgroundColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"].Api.Hue, GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"].Api.Sat, GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"].Api.Value)
			profileObject.ImageButton.BackgroundColor3 = Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"].Api.Hue, GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"].Api.Sat, GuiLibrary.ObjectsThatCanBeSaved["Gui ColorSliderColor"].Api.Value)
			profileObject.ItemText.TextColor3 = Color3.new(1, 1, 1)
			profileObject.ItemText.TextStrokeTransparency = 0.75
			bindbkg.BackgroundTransparency = 0.9
			bindtext.TextColor3 = Color3.fromRGB(214, 214, 214)
		end
	end
})

local OnlineProfilesButton = Instance.new("TextButton")
OnlineProfilesButton.Name = "OnlineProfilesButton"
OnlineProfilesButton.LayoutOrder = 1
OnlineProfilesButton.AutoButtonColor = false
OnlineProfilesButton.Size = UDim2.new(0, 45, 0, 29)
OnlineProfilesButton.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
OnlineProfilesButton.Active = false
OnlineProfilesButton.Text = ""
OnlineProfilesButton.ZIndex = 1
OnlineProfilesButton.Font = Enum.Font.SourceSans
OnlineProfilesButton.TextXAlignment = Enum.TextXAlignment.Left
OnlineProfilesButton.Position = UDim2.new(0, 166, 0, 6)
OnlineProfilesButton.Parent = ProfilesTextList.Object
local OnlineProfilesButtonBKG = Instance.new("UIStroke")
OnlineProfilesButtonBKG.Color = Color3.fromRGB(38, 37, 38)
OnlineProfilesButtonBKG.Thickness = 1
OnlineProfilesButtonBKG.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
OnlineProfilesButtonBKG.Parent = OnlineProfilesButton
local OnlineProfilesButtonImage = Instance.new("ImageLabel")
OnlineProfilesButtonImage.BackgroundTransparency = 1
OnlineProfilesButtonImage.Position = UDim2.new(0, 14, 0, 7)
OnlineProfilesButtonImage.Size = UDim2.new(0, 17, 0, 16)
OnlineProfilesButtonImage.Image = downloadVapeAsset("vape/assets/OnlineProfilesButton.png")
OnlineProfilesButtonImage.ImageColor3 = Color3.fromRGB(121, 121, 121)
OnlineProfilesButtonImage.ZIndex = 1
OnlineProfilesButtonImage.Active = false
OnlineProfilesButtonImage.Parent = OnlineProfilesButton
local OnlineProfilesbuttonround1 = Instance.new("UICorner")
OnlineProfilesbuttonround1.CornerRadius = UDim.new(0, 5)
OnlineProfilesbuttonround1.Parent = OnlineProfilesButton
local OnlineProfilesbuttonTargetInfoMainInfoCorner = Instance.new("UICorner")
OnlineProfilesbuttonTargetInfoMainInfoCorner.CornerRadius = UDim.new(0, 5)
OnlineProfilesbuttonTargetInfoMainInfoCorner.Parent = OnlineProfilesButtonBKG
local OnlineProfilesFrame = Instance.new("Frame")
OnlineProfilesFrame.Size = UDim2.new(0, 660, 0, 445)
OnlineProfilesFrame.Position = UDim2.new(0.5, -330, 0.5, -223)
OnlineProfilesFrame.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
OnlineProfilesFrame.Parent = GuiLibrary.MainGui.ScaledGui.OnlineProfiles
local OnlineProfilesExitButton = Instance.new("ImageButton")
OnlineProfilesExitButton.Name = "OnlineProfilesExitButton"
OnlineProfilesExitButton.ImageColor3 = Color3.fromRGB(121, 121, 121)
OnlineProfilesExitButton.Size = UDim2.new(0, 24, 0, 24)
OnlineProfilesExitButton.AutoButtonColor = false
OnlineProfilesExitButton.Image = downloadVapeAsset("vape/assets/ExitIcon1.png")
OnlineProfilesExitButton.Visible = true
OnlineProfilesExitButton.Position = UDim2.new(1, -31, 0, 8)
OnlineProfilesExitButton.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
OnlineProfilesExitButton.Parent = OnlineProfilesFrame
local OnlineProfilesExitButtonround = Instance.new("UICorner")
OnlineProfilesExitButtonround.CornerRadius = UDim.new(0, 16)
OnlineProfilesExitButtonround.Parent = OnlineProfilesExitButton
OnlineProfilesExitButton.MouseEnter:Connect(function()
	game:GetService("TweenService"):Create(OnlineProfilesExitButton, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(60, 60, 60), ImageColor3 = Color3.fromRGB(255, 255, 255)}):Play()
end)
OnlineProfilesExitButton.MouseLeave:Connect(function()
	game:GetService("TweenService"):Create(OnlineProfilesExitButton, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.InOut), {BackgroundColor3 = Color3.fromRGB(26, 25, 26), ImageColor3 = Color3.fromRGB(121, 121, 121)}):Play()
end)
local OnlineProfilesFrameShadow = Instance.new("ImageLabel")
OnlineProfilesFrameShadow.AnchorPoint = Vector2.new(0.5, 0.5)
OnlineProfilesFrameShadow.Position = UDim2.new(0.5, 0, 0.5, 0)
OnlineProfilesFrameShadow.Image = downloadVapeAsset("vape/assets/WindowBlur.png")
OnlineProfilesFrameShadow.BackgroundTransparency = 1
OnlineProfilesFrameShadow.ZIndex = -1
OnlineProfilesFrameShadow.Size = UDim2.new(1, 6, 1, 6)
OnlineProfilesFrameShadow.ImageColor3 = Color3.new()
OnlineProfilesFrameShadow.ScaleType = Enum.ScaleType.Slice
OnlineProfilesFrameShadow.SliceCenter = Rect.new(10, 10, 118, 118)
OnlineProfilesFrameShadow.Parent = OnlineProfilesFrame
local OnlineProfilesFrameIcon = Instance.new("ImageLabel")
OnlineProfilesFrameIcon.Size = UDim2.new(0, 19, 0, 16)
OnlineProfilesFrameIcon.Image = downloadVapeAsset("vape/assets/ProfilesIcon.png")
OnlineProfilesFrameIcon.Name = "WindowIcon"
OnlineProfilesFrameIcon.BackgroundTransparency = 1
OnlineProfilesFrameIcon.Position = UDim2.new(0, 10, 0, 13)
OnlineProfilesFrameIcon.ImageColor3 = Color3.fromRGB(200, 200, 200)
OnlineProfilesFrameIcon.Parent = OnlineProfilesFrame
local OnlineProfilesFrameText = Instance.new("TextLabel")
OnlineProfilesFrameText.Size = UDim2.new(0, 155, 0, 41)
OnlineProfilesFrameText.BackgroundTransparency = 1
OnlineProfilesFrameText.Name = "WindowTitle"
OnlineProfilesFrameText.Position = UDim2.new(0, 36, 0, 0)
OnlineProfilesFrameText.TextXAlignment = Enum.TextXAlignment.Left
OnlineProfilesFrameText.Font = Enum.Font.SourceSans
OnlineProfilesFrameText.TextSize = 17
OnlineProfilesFrameText.Text = "Public Profiles"
OnlineProfilesFrameText.TextColor3 = Color3.fromRGB(201, 201, 201)
OnlineProfilesFrameText.Parent = OnlineProfilesFrame
local OnlineProfilesFrameText2 = Instance.new("TextLabel")
OnlineProfilesFrameText2.TextSize = 15
OnlineProfilesFrameText2.TextColor3 = Color3.fromRGB(85, 84, 85)
OnlineProfilesFrameText2.Text = "YOUR PROFILES"
OnlineProfilesFrameText2.Font = Enum.Font.SourceSans
OnlineProfilesFrameText2.BackgroundTransparency = 1
OnlineProfilesFrameText2.TextXAlignment = Enum.TextXAlignment.Left
OnlineProfilesFrameText2.TextYAlignment = Enum.TextYAlignment.Top
OnlineProfilesFrameText2.Size = UDim2.new(1, 0, 0, 20)
OnlineProfilesFrameText2.Position = UDim2.new(0, 10, 0, 48)
OnlineProfilesFrameText2.Parent = OnlineProfilesFrame
local OnlineProfilesFrameText3 = Instance.new("TextLabel")
OnlineProfilesFrameText3.TextSize = 15
OnlineProfilesFrameText3.TextColor3 = Color3.fromRGB(85, 84, 85)
OnlineProfilesFrameText3.Text = "PUBLIC PROFILES"
OnlineProfilesFrameText3.Font = Enum.Font.SourceSans
OnlineProfilesFrameText3.BackgroundTransparency = 1
OnlineProfilesFrameText3.TextXAlignment = Enum.TextXAlignment.Left
OnlineProfilesFrameText3.TextYAlignment = Enum.TextYAlignment.Top
OnlineProfilesFrameText3.Size = UDim2.new(1, 0, 0, 20)
OnlineProfilesFrameText3.Position = UDim2.new(0, 231, 0, 48)
OnlineProfilesFrameText3.Parent = OnlineProfilesFrame
local OnlineProfilesBorder1 = Instance.new("Frame")
OnlineProfilesBorder1.BackgroundColor3 = Color3.fromRGB(40, 39, 40)
OnlineProfilesBorder1.BorderSizePixel = 0
OnlineProfilesBorder1.Size = UDim2.new(1, 0, 0, 1)
OnlineProfilesBorder1.Position = UDim2.new(0, 0, 0, 41)
OnlineProfilesBorder1.Parent = OnlineProfilesFrame
local OnlineProfilesBorder2 = Instance.new("Frame")
OnlineProfilesBorder2.BackgroundColor3 = Color3.fromRGB(40, 39, 40)
OnlineProfilesBorder2.BorderSizePixel = 0
OnlineProfilesBorder2.Size = UDim2.new(0, 1, 1, -41)
OnlineProfilesBorder2.Position = UDim2.new(0, 220, 0, 41)
OnlineProfilesBorder2.Parent = OnlineProfilesFrame
local OnlineProfilesList = Instance.new("ScrollingFrame")
OnlineProfilesList.BackgroundTransparency = 1
OnlineProfilesList.Size = UDim2.new(0, 408, 0, 319)
OnlineProfilesList.Position = UDim2.new(0, 230, 0, 122)
OnlineProfilesList.CanvasSize = UDim2.new(0, 408, 0, 319)
OnlineProfilesList.Parent = OnlineProfilesFrame
local OnlineProfilesListGrid = Instance.new("UIGridLayout")
OnlineProfilesListGrid.CellSize = UDim2.new(0, 134, 0, 144)
OnlineProfilesListGrid.CellPadding = UDim2.new(0, 4, 0, 4)
OnlineProfilesListGrid.Parent = OnlineProfilesList
local OnlineProfilesFrameCorner = Instance.new("UICorner")
OnlineProfilesFrameCorner.CornerRadius = UDim.new(0, 4)
OnlineProfilesFrameCorner.Parent = OnlineProfilesFrame
OnlineProfilesButton.MouseButton1Click:Connect(function()
	GuiLibrary.MainGui.ScaledGui.OnlineProfiles.Visible = true
	GuiLibrary.MainGui.ScaledGui.ClickGui.Visible = false
	if not profilesLoaded then
		local onlineprofiles = {}
		local saveplaceid = tostring(shared.CustomSaveVape or game.PlaceId)
        local success, result = pcall(function()
            return game:GetService("HttpService"):JSONDecode(game:HttpGet("https://raw.githubusercontent.com/7GrandDadPGN/VapeProfiles/main/Profiles/"..saveplaceid.."/profilelist.txt", true))
        end)
		for i,v in pairs(success and result or {}) do 
			onlineprofiles[i] = v
		end
		for i2,v2 in pairs(onlineprofiles) do
			local profileurl = "https://raw.githubusercontent.com/7GrandDadPGN/VapeProfiles/main/Profiles/"..saveplaceid.."/"..v2.OnlineProfileName
			local profilebox = Instance.new("Frame")
			profilebox.BackgroundColor3 = Color3.fromRGB(31, 30, 31)
			profilebox.Parent = OnlineProfilesList
			local profiletext = Instance.new("TextLabel")
			profiletext.TextSize = 15
			profiletext.TextColor3 = Color3.fromRGB(137, 136, 137)
			profiletext.Size = UDim2.new(0, 100, 0, 20)
			profiletext.Position = UDim2.new(0, 18, 0, 25)
			profiletext.Font = Enum.Font.SourceSans
			profiletext.TextXAlignment = Enum.TextXAlignment.Left
			profiletext.TextYAlignment = Enum.TextYAlignment.Top
			profiletext.BackgroundTransparency = 1
			profiletext.Text = i2
			profiletext.Parent = profilebox
			local profiledownload = Instance.new("TextButton")
			profiledownload.BackgroundColor3 = Color3.fromRGB(31, 30, 31)
			profiledownload.Size = UDim2.new(0, 69, 0, 31)
			profiledownload.Font = Enum.Font.SourceSans
			profiledownload.TextColor3 = Color3.fromRGB(200, 200, 200)
			profiledownload.TextSize = 15
			profiledownload.AutoButtonColor = false
			profiledownload.Text = "DOWNLOAD"
			profiledownload.Position = UDim2.new(0, 14, 0, 96)
			profiledownload.Visible = false 
			profiledownload.Parent = profilebox
			profiledownload.ZIndex = 2
			local profiledownloadbkg = Instance.new("Frame")
			profiledownloadbkg.Size = UDim2.new(0, 71, 0, 33)
			profiledownloadbkg.BackgroundColor3 = Color3.fromRGB(42, 41, 42)
			profiledownloadbkg.Position = UDim2.new(0, 13, 0, 95)
			profiledownloadbkg.ZIndex = 1
			profiledownloadbkg.Visible = false
			profiledownloadbkg.Parent = profilebox
			profilebox.MouseEnter:Connect(function()
				profiletext.TextColor3 = Color3.fromRGB(200, 200, 200)
				profiledownload.Visible = true 
				profiledownloadbkg.Visible = true
			end)
			profilebox.MouseLeave:Connect(function()
				profiletext.TextColor3 = Color3.fromRGB(137, 136, 137)
				profiledownload.Visible = false
				profiledownloadbkg.Visible = false
			end)
			profiledownload.MouseEnter:Connect(function()
				profiledownload.BackgroundColor3 = Color3.fromRGB(5, 134, 105)
			end)
			profiledownload.MouseLeave:Connect(function()
				profiledownload.BackgroundColor3 = Color3.fromRGB(31, 30, 31)
			end)
			profiledownload.MouseButton1Click:Connect(function()
				writefile(baseDirectory.."Profiles/"..v2.ProfileName..saveplaceid..".vapeprofile.txt", game:HttpGet(profileurl, true))
				GuiLibrary.Profiles[v2.ProfileName] = {Keybind = "", Selected = false}
				local profiles = {}
				for i,v in pairs(GuiLibrary.Profiles) do 
					table.insert(profiles, i)
				end
				table.sort(profiles, function(a, b) return b == "default" and true or a:lower() < b:lower() end)
				ProfilesTextList.RefreshValues(profiles)
			end)
			local profileround = Instance.new("UICorner")
			profileround.CornerRadius = UDim.new(0, 4)
			profileround.Parent = profilebox
			local profileTargetInfoMainInfoCorner = Instance.new("UICorner")
			profileTargetInfoMainInfoCorner.CornerRadius = UDim.new(0, 4)
			profileTargetInfoMainInfoCorner.Parent = profiledownload
			local profileTargetInfoHealthBackgroundCorner = Instance.new("UICorner")
			profileTargetInfoHealthBackgroundCorner.CornerRadius = UDim.new(0, 4)
			profileTargetInfoHealthBackgroundCorner.Parent = profiledownloadbkg
		end
		profilesloaded = true
	end
end)
OnlineProfilesExitButton.MouseButton1Click:Connect(function()
	GuiLibrary.MainGui.ScaledGui.OnlineProfiles.Visible = false
	GuiLibrary.MainGui.ScaledGui.ClickGui.Visible = true
end)
GUI.CreateDivider()

local TextGUI = GuiLibrary.CreateCustomWindow({
	Name = "Text GUI", 
	Icon = "vape/assets/TextGUIIcon1.png", 
	IconSize = 21
})
local TextGUICircleObject = {CircleList = {}}
GUI.CreateCustomToggle({
	Name = "Text GUI", 
	Icon = "vape/assets/TextGUIIcon3.png",
	Function = function(callback) TextGUI.SetVisible(callback) end,
	Priority = 2
})	
local GUIColorSlider = {RainbowValue = false}
local TextGUIMode = {Value = "Normal"}
local TextGUISortMode = {Value = "Alphabetical"}
local TextGUIBackgroundToggle = {Enabled = false}
local TextGUIObjects = {Logo = {}, Labels = {}, ShadowLabels = {}, Backgrounds = {}}
local TextGUIConnections = {}
local TextGUIFormatted = {}
local VapeLogoFrame = Instance.new("Frame")
VapeLogoFrame.BackgroundTransparency = 1
VapeLogoFrame.Size = UDim2.new(1, 0, 1, 0)
VapeLogoFrame.Parent = TextGUI.GetCustomChildren()
local VapeLogo = Instance.new("ImageLabel")
VapeLogo.Parent = VapeLogoFrame
VapeLogo.Name = "Logo"
VapeLogo.Size = UDim2.new(0, 100, 0, 27)
VapeLogo.Position = UDim2.new(1, -140, 0, 3)
VapeLogo.BackgroundColor3 = Color3.new()
VapeLogo.BorderSizePixel = 0
VapeLogo.BackgroundTransparency = 1
VapeLogo.Visible = true
VapeLogo.Image = downloadVapeAsset("vape/assets/VapeLogo3.png")
local VapeLogoV4 = Instance.new("ImageLabel")
VapeLogoV4.Parent = VapeLogo
VapeLogoV4.Size = UDim2.new(0, 41, 0, 24)
VapeLogoV4.Name = "Logo2"
VapeLogoV4.Position = UDim2.new(1, 0, 0, 1)
VapeLogoV4.BorderSizePixel = 0
VapeLogoV4.BackgroundColor3 = Color3.new()
VapeLogoV4.BackgroundTransparency = 1
VapeLogoV4.Image = downloadVapeAsset("vape/assets/VapeLogo4.png")
local VapeLogoShadow = VapeLogo:Clone()
VapeLogoShadow.ImageColor3 = Color3.new()
VapeLogoShadow.ImageTransparency = 0.5
VapeLogoShadow.ZIndex = 0
VapeLogoShadow.Position = UDim2.new(0, 1, 0, 1)
VapeLogoShadow.Visible = false
VapeLogoShadow.Parent = VapeLogo
VapeLogoShadow.Logo2.ImageColor3 = Color3.new()
VapeLogoShadow.Logo2.ZIndex = 0
VapeLogoShadow.Logo2.ImageTransparency = 0.5
local VapeLogoGradient = Instance.new("UIGradient")
VapeLogoGradient.Rotation = 90
VapeLogoGradient.Parent = VapeLogo
local VapeLogoGradient2 = Instance.new("UIGradient")
VapeLogoGradient2.Rotation = 90
VapeLogoGradient2.Parent = VapeLogoV4
local VapeText = Instance.new("TextLabel")
VapeText.Parent = VapeLogoFrame
VapeText.Size = UDim2.new(1, 0, 1, 0)
VapeText.Position = UDim2.new(1, -154, 0, 35)
VapeText.TextColor3 = Color3.new(1, 1, 1)
VapeText.RichText = true
VapeText.BackgroundTransparency = 1
VapeText.LineHeight = 1.2
VapeText.TextXAlignment = Enum.TextXAlignment.Left
VapeText.TextYAlignment = Enum.TextYAlignment.Top
VapeText.BorderSizePixel = 0
VapeText.BackgroundColor3 = Color3.new()
VapeText.Font = Enum.Font.SourceSans
VapeText.Text = ""
VapeText.TextSize = 19
local VapeTextExtra = Instance.new("TextLabel")
VapeTextExtra.Name = "ExtraText"
VapeTextExtra.Parent = VapeText
VapeTextExtra.LineHeight = 1.2
VapeTextExtra.Size = UDim2.new(1, 0, 1, 0)
VapeTextExtra.Position = UDim2.new(0, 1, 0, 1)
VapeTextExtra.BorderSizePixel = 0
VapeTextExtra.Visible = false
VapeTextExtra.ZIndex = 0
VapeTextExtra.Text = ""
VapeTextExtra.BackgroundTransparency = 1
VapeTextExtra.TextTransparency = 0.5
VapeTextExtra.TextXAlignment = Enum.TextXAlignment.Left
VapeTextExtra.TextYAlignment = Enum.TextYAlignment.Top
VapeTextExtra.TextColor3 = Color3.new()
VapeTextExtra.Font = Enum.Font.SourceSans
VapeTextExtra.TextSize = 19
local VapeCustomText = Instance.new("TextLabel")
VapeCustomText.TextSize = 30
VapeCustomText.Font = Enum.Font.GothamBold
VapeCustomText.Size = UDim2.new(1, 0, 1, 0)
VapeCustomText.BackgroundTransparency = 1
VapeCustomText.Position = UDim2.new(0, 0, 0, 35)
VapeCustomText.TextXAlignment = Enum.TextXAlignment.Left
VapeCustomText.TextYAlignment = Enum.TextYAlignment.Top
VapeCustomText.Text = ""
VapeCustomText.Parent = VapeLogoFrame
local VapeCustomTextShadow = VapeCustomText:Clone()
VapeCustomTextShadow.ZIndex = -1
VapeCustomTextShadow.Size = UDim2.new(1, 0, 1, 0)
VapeCustomTextShadow.TextTransparency = 0.5
VapeCustomTextShadow.TextColor3 = Color3.new()
VapeCustomTextShadow.Position = UDim2.new(0, 1, 0, 1)
VapeCustomTextShadow.Parent = VapeCustomText
VapeCustomText:GetPropertyChangedSignal("TextXAlignment"):Connect(function()
	VapeCustomTextShadow.TextXAlignment = VapeCustomText.TextXAlignment
end)
local VapeBackground = Instance.new("Frame")
VapeBackground.BackgroundTransparency = 1
VapeBackground.BorderSizePixel = 0
VapeBackground.BackgroundColor3 = Color3.new()
VapeBackground.Size = UDim2.new(1, 0, 1, 0)
VapeBackground.Visible = false 
VapeBackground.Parent = VapeLogoFrame
VapeBackground.ZIndex = 0
local VapeBackgroundList = Instance.new("UIListLayout")
VapeBackgroundList.FillDirection = Enum.FillDirection.Vertical
VapeBackgroundList.SortOrder = Enum.SortOrder.LayoutOrder
VapeBackgroundList.Padding = UDim.new(0, 0)
VapeBackgroundList.Parent = VapeBackground
local VapeBackgroundTable = {}
local VapeScale = Instance.new("UIScale")
VapeScale.Parent = VapeLogoFrame
--why do other platforms do rendering differently
local TextGUIOffsets = {
	[Enum.Platform.Android] = {
		6,
		-10,
		15,
		12
	},
	[Enum.Platform.UWP] = {
		1,
		1,
		23,
		23
	}
}
TextGUIOffsets[Enum.Platform.IOS] = TextGUIOffsets[Enum.Platform.Android]
local function TextGUIUpdate()
	local scaledgui = vapeInjected and GuiLibrary.MainGui.ScaledGui
	if scaledgui and scaledgui.Visible then
		local formattedText = ""
		local moduleList = {}

		for i, v in pairs(GuiLibrary.ObjectsThatCanBeSaved) do
			if v.Type == "OptionsButton" and v.Api.Enabled then
                local blacklistedCheck = table.find(TextGUICircleObject.CircleList.ObjectList, v.Api.Name)
                blacklistedCheck = blacklistedCheck and TextGUICircleObject.CircleList.ObjectList[blacklistedCheck]
                if not blacklistedCheck then
					local extraText = v.Api.GetExtraText()
                    table.insert(moduleList, {Text = v.Api.Name, ExtraText = extraText ~= "" and " "..extraText or ""})
                end
			end
		end

		if TextGUISortMode.Value == "Alphabetical" then
			table.sort(moduleList, function(a, b) return a.Text:lower() < b.Text:lower() end)
		else
			table.sort(moduleList, function(a, b) 
				return textService:GetTextSize(a.Text..a.ExtraText, VapeText.TextSize, VapeText.Font, Vector2.new(1000000, 1000000)).X > textService:GetTextSize(b.Text..b.ExtraText, VapeText.TextSize, VapeText.Font, Vector2.new(1000000, 1000000)).X 
			end)
		end

		local backgroundList = {}
		local first = true
		for i, v in pairs(moduleList) do
            local newEntryText = v.Text..v.ExtraText
			if first then
				formattedText = "\n"..newEntryText
				first = false
			else
				formattedText = formattedText..'\n'..newEntryText
			end
			table.insert(backgroundList, newEntryText)
		end

		TextGUIFormatted = moduleList
		VapeTextExtra.Text = formattedText
        VapeText.Size = UDim2.fromOffset(154, (formattedText ~= "" and textService:GetTextSize(formattedText, VapeText.TextSize, VapeText.Font, Vector2.new(1000000, 1000000)) or Vector2.zero).Y)

		local offsets = {
			5,
			1,
			23,
			23
		}
        if TextGUI.GetCustomChildren().Parent then
            if (TextGUI.GetCustomChildren().Parent.Position.X.Offset + TextGUI.GetCustomChildren().Parent.Size.X.Offset / 2) >= (gameCamera.ViewportSize.X / 2) then
                VapeText.TextXAlignment = Enum.TextXAlignment.Right
                VapeTextExtra.TextXAlignment = Enum.TextXAlignment.Right
                VapeTextExtra.Position = UDim2.fromOffset(offsets[1], offsets[2])
                VapeLogo.Position = UDim2.new(1, -142, 0, 8)
                VapeText.Position = UDim2.new(1, -158, 0, (VapeLogo.Visible and (TextGUIBackgroundToggle.Enabled and 41 or 35) or 5) + 5 + (VapeCustomText.Visible and 25 or 0) - offsets[3])
                VapeCustomText.Position = UDim2.fromOffset(0, VapeLogo.Visible and 35 or 0)
                VapeCustomText.TextXAlignment = Enum.TextXAlignment.Right
                VapeBackgroundList.HorizontalAlignment = Enum.HorizontalAlignment.Right
                VapeBackground.Position = VapeText.Position + UDim2.fromOffset(-60, -2 + offsets[4])
            else
                VapeText.TextXAlignment = Enum.TextXAlignment.Left
                VapeTextExtra.TextXAlignment = Enum.TextXAlignment.Left
                VapeTextExtra.Position = UDim2.fromOffset(offsets[1], offsets[2])
                VapeLogo.Position = UDim2.fromOffset(2, 8)
                VapeText.Position = UDim2.fromOffset(6, (VapeLogo.Visible and (TextGUIBackgroundToggle.Enabled and 41 or 35) or 5) + 5 + (VapeCustomText.Visible and 25 or 0) - offsets[3])
				VapeCustomText.Position = UDim2.fromOffset(0, VapeLogo.Visible and 35 or 0)
				VapeCustomText.TextXAlignment = Enum.TextXAlignment.Left
                VapeBackgroundList.HorizontalAlignment = Enum.HorizontalAlignment.Left
                VapeBackground.Position = VapeText.Position + UDim2.fromOffset(-4, -2 + offsets[4])
            end
        end
        
		if TextGUIMode.Value == "Drawing" then 
			for i,v in pairs(TextGUIObjects.Labels) do 
				v.Visible = false
				v:Remove()
				TextGUIObjects.Labels[i] = nil
			end
			for i,v in pairs(TextGUIObjects.ShadowLabels) do 
				v.Visible = false
				v:Remove()
				TextGUIObjects.ShadowLabels[i] = nil
			end
			for i,v in pairs(backgroundList) do 
				local textdraw = Drawing.new("Text")
				textdraw.Text = v
				textdraw.Size = 23 * VapeScale.Scale
				textdraw.ZIndex = 2
				textdraw.Position = VapeText.AbsolutePosition + Vector2.new(VapeText.TextXAlignment == Enum.TextXAlignment.Right and (VapeText.AbsoluteSize.X - textdraw.TextBounds.X), ((textdraw.Size - 3) * i) + 6)
				textdraw.Visible = true
				local textdraw2 = Drawing.new("Text")
				textdraw2.Text = textdraw.Text
				textdraw2.Size = 23 * VapeScale.Scale
				textdraw2.Position = textdraw.Position + Vector2.new(1, 1)
				textdraw2.Color = Color3.new()
				textdraw2.Transparency = 0.5
				textdraw2.Visible = VapeTextExtra.Visible
				table.insert(TextGUIObjects.Labels, textdraw)
				table.insert(TextGUIObjects.ShadowLabels, textdraw2)
			end
		end

        for i,v in pairs(VapeBackground:GetChildren()) do
			table.clear(VapeBackgroundTable)
            if v:IsA("Frame") then v:Destroy() end
        end
        for i,v in pairs(backgroundList) do
            local textsize = textService:GetTextSize(v, VapeText.TextSize, VapeText.Font, Vector2.new(1000000, 1000000))
            local backgroundFrame = Instance.new("Frame")
            backgroundFrame.BorderSizePixel = 0
            backgroundFrame.BackgroundTransparency = 0.62
            backgroundFrame.BackgroundColor3 = Color3.new()
            backgroundFrame.Visible = true
            backgroundFrame.ZIndex = 0
            backgroundFrame.LayoutOrder = i
            backgroundFrame.Size = UDim2.fromOffset(textsize.X + 8, textsize.Y + 3)
            backgroundFrame.Parent = VapeBackground
            local backgroundLineFrame = Instance.new("Frame")
            backgroundLineFrame.Size = UDim2.new(0, 2, 1, 0)
            backgroundLineFrame.Position = (VapeBackgroundList.HorizontalAlignment == Enum.HorizontalAlignment.Left and UDim2.new() or UDim2.new(1, -2, 0, 0))
            backgroundLineFrame.BorderSizePixel = 0
            backgroundLineFrame.Name = "ColorFrame"
            backgroundLineFrame.Parent = backgroundFrame
            local backgroundLineExtra = Instance.new("Frame")
            backgroundLineExtra.BorderSizePixel = 0
            backgroundLineExtra.BackgroundTransparency = 0.95
            backgroundLineExtra.BackgroundColor3 = Color3.new()
            backgroundLineExtra.ZIndex = 0
            backgroundLineExtra.Size = UDim2.new(1, 0, 0, 2)
            backgroundLineExtra.Position = UDim2.new(0, 0, 1, -1)
            backgroundLineExtra.Parent = backgroundFrame
			table.insert(VapeBackgroundTable, backgroundFrame)
        end
		
		GuiLibrary.UpdateUI(GUIColorSlider.Hue, GUIColorSlider.Sat, GUIColorSlider.Value)
	end
end

TextGUI.GetCustomChildren().Parent:GetPropertyChangedSignal("Position"):Connect(TextGUIUpdate)
GuiLibrary.UpdateHudEvent.Event:Connect(TextGUIUpdate)
VapeScale:GetPropertyChangedSignal("Scale"):Connect(function()
	local childrenobj = TextGUI.GetCustomChildren()
	local check = (childrenobj.Parent.Position.X.Offset + childrenobj.Parent.Size.X.Offset / 2) >= (gameCamera.ViewportSize.X / 2)
	childrenobj.Position = UDim2.new((check and -(VapeScale.Scale - 1) or 0), (check and 0 or -6 * (VapeScale.Scale - 1)), 1, -6 * (VapeScale.Scale - 1))
	TextGUIUpdate()
end)
TextGUIMode = TextGUI.CreateDropdown({
	Name = "Mode",
	List = {"Normal", "Drawing"},
	Function = function(val)
		VapeLogoFrame.Visible = val == "Normal"
		for i,v in pairs(TextGUIConnections) do 
			v:Disconnect()
		end
		for i,v in pairs(TextGUIObjects) do 
			for i2,v2 in pairs(v) do 
				v2.Visible = false
				v2:Remove()
				v[i2] = nil
			end
		end
		if val == "Drawing" then
			local VapeLogoDrawing = Drawing.new("Image")
			VapeLogoDrawing.Data = readfile("vape/assets/VapeLogo3.png")
			VapeLogoDrawing.Size = VapeLogo.AbsoluteSize
			VapeLogoDrawing.Position = VapeLogo.AbsolutePosition + Vector2.new(0, 36)
			VapeLogoDrawing.ZIndex = 2
			VapeLogoDrawing.Visible = VapeLogo.Visible
			local VapeLogoV4Drawing = Drawing.new("Image")
			VapeLogoV4Drawing.Data = readfile("vape/assets/VapeLogo4.png")
			VapeLogoV4Drawing.Size = VapeLogoV4.AbsoluteSize
			VapeLogoV4Drawing.Position = VapeLogoV4.AbsolutePosition + Vector2.new(0, 36)
			VapeLogoV4Drawing.ZIndex = 2
			VapeLogoV4Drawing.Visible = VapeLogo.Visible
			local VapeLogoShadowDrawing = Drawing.new("Image")
			VapeLogoShadowDrawing.Data = readfile("vape/assets/VapeLogo3.png")
			VapeLogoShadowDrawing.Size = VapeLogo.AbsoluteSize
			VapeLogoShadowDrawing.Position = VapeLogo.AbsolutePosition + Vector2.new(1, 37)
			VapeLogoShadowDrawing.Transparency = 0.5
			VapeLogoShadowDrawing.Visible = VapeLogo.Visible and VapeLogoShadow.Visible
			local VapeLogo4Drawing = Drawing.new("Image")
			VapeLogo4Drawing.Data = readfile("vape/assets/VapeLogo4.png")
			VapeLogo4Drawing.Size = VapeLogoV4.AbsoluteSize
			VapeLogo4Drawing.Position = VapeLogoV4.AbsolutePosition + Vector2.new(1, 37)
			VapeLogo4Drawing.Transparency = 0.5
			VapeLogo4Drawing.Visible = VapeLogo.Visible and VapeLogoShadow.Visible
			local VapeCustomDrawingText = Drawing.new("Text")
			VapeCustomDrawingText.Size = 30
			VapeCustomDrawingText.Text = VapeCustomText.Text
			VapeCustomDrawingText.Color = VapeCustomText.TextColor3
			VapeCustomDrawingText.ZIndex = 2
			VapeCustomDrawingText.Position = VapeCustomText.AbsolutePosition + Vector2.new(VapeText.TextXAlignment == Enum.TextXAlignment.Right and (VapeCustomText.AbsoluteSize.X - VapeCustomDrawingText.TextBounds.X), 32)
			VapeCustomDrawingText.Visible = VapeCustomText.Visible
			local VapeCustomDrawingShadow = Drawing.new("Text")
			VapeCustomDrawingShadow.Size = 30
			VapeCustomDrawingShadow.Text = VapeCustomText.Text
			VapeCustomDrawingShadow.Transparency = 0.5
			VapeCustomDrawingShadow.Color = Color3.new()
			VapeCustomDrawingShadow.Position = VapeCustomDrawingText.Position + Vector2.new(1, 1)
			VapeCustomDrawingShadow.Visible = VapeCustomText.Visible and VapeTextExtra.Visible
			pcall(function()
				VapeLogoShadowDrawing.Color = Color3.new()
				VapeLogo4Drawing.Color = Color3.new()
				VapeLogoDrawing.Color = VapeLogoGradient.Color.Keypoints[1].Value
			end)
			table.insert(TextGUIObjects.Logo, VapeLogoDrawing)
			table.insert(TextGUIObjects.Logo, VapeLogoV4Drawing)
			table.insert(TextGUIObjects.Logo, VapeLogoShadowDrawing)
			table.insert(TextGUIObjects.Logo, VapeLogo4Drawing)
			table.insert(TextGUIObjects.Logo, VapeCustomDrawingText)
			table.insert(TextGUIObjects.Logo, VapeCustomDrawingShadow)
			table.insert(TextGUIConnections, VapeLogo:GetPropertyChangedSignal("AbsolutePosition"):Connect(function()
				VapeLogoDrawing.Position = VapeLogo.AbsolutePosition + Vector2.new(0, 36)
				VapeLogoShadowDrawing.Position = VapeLogo.AbsolutePosition + Vector2.new(1, 37)
			end))
			table.insert(TextGUIConnections, VapeLogo:GetPropertyChangedSignal("AbsoluteSize"):Connect(function()
				VapeLogoDrawing.Size = VapeLogo.AbsoluteSize
				VapeLogoShadowDrawing.Size = VapeLogo.AbsoluteSize
				VapeCustomDrawingText.Size = 30 * VapeScale.Scale
				VapeCustomDrawingShadow.Size = 30 * VapeScale.Scale
			end))
			table.insert(TextGUIConnections, VapeLogoV4:GetPropertyChangedSignal("AbsolutePosition"):Connect(function()
				VapeLogoV4Drawing.Position = VapeLogoV4.AbsolutePosition + Vector2.new(0, 36)
				VapeLogo4Drawing.Position = VapeLogoV4.AbsolutePosition + Vector2.new(1, 37)
			end))
			table.insert(TextGUIConnections, VapeLogoV4:GetPropertyChangedSignal("AbsoluteSize"):Connect(function()
				VapeLogoV4Drawing.Size = VapeLogoV4.AbsoluteSize
				VapeLogo4Drawing.Size = VapeLogoV4.AbsoluteSize
			end))
			table.insert(TextGUIConnections, VapeCustomText:GetPropertyChangedSignal("AbsolutePosition"):Connect(function()
				VapeCustomDrawingText.Position = VapeCustomText.AbsolutePosition + Vector2.new(VapeText.TextXAlignment == Enum.TextXAlignment.Right and (VapeCustomText.AbsoluteSize.X - VapeCustomDrawingText.TextBounds.X), 32)
				VapeCustomDrawingShadow.Position = VapeCustomDrawingText.Position + Vector2.new(1, 1)
			end))
			table.insert(TextGUIConnections, VapeLogoShadow:GetPropertyChangedSignal("Visible"):Connect(function()
				VapeLogoShadowDrawing.Visible = VapeLogoShadow.Visible
				VapeLogo4Drawing.Visible = VapeLogoShadow.Visible
			end))
			table.insert(TextGUIConnections, VapeTextExtra:GetPropertyChangedSignal("Visible"):Connect(function()
				for i,textdraw in pairs(TextGUIObjects.ShadowLabels) do 
					textdraw.Visible = VapeTextExtra.Visible
				end
				VapeCustomDrawingShadow.Visible = VapeCustomText.Visible and VapeTextExtra.Visible
			end))
			table.insert(TextGUIConnections, VapeLogo:GetPropertyChangedSignal("Visible"):Connect(function()
				VapeLogoDrawing.Visible = VapeLogo.Visible
				VapeLogoV4Drawing.Visible = VapeLogo.Visible
				VapeLogoShadowDrawing.Visible = VapeLogo.Visible and VapeTextExtra.Visible
				VapeLogo4Drawing.Visible = VapeLogo.Visible and VapeTextExtra.Visible
			end))
			table.insert(TextGUIConnections, VapeCustomText:GetPropertyChangedSignal("Visible"):Connect(function()
				VapeCustomDrawingText.Visible = VapeCustomText.Visible
				VapeCustomDrawingShadow.Visible = VapeCustomText.Visible and VapeTextExtra.Visible
			end))
			table.insert(TextGUIConnections, VapeCustomText:GetPropertyChangedSignal("Text"):Connect(function()
				VapeCustomDrawingText.Text = VapeCustomText.Text
				VapeCustomDrawingShadow.Text = VapeCustomText.Text
				VapeCustomDrawingText.Position = VapeCustomText.AbsolutePosition + Vector2.new(VapeText.TextXAlignment == Enum.TextXAlignment.Right and (VapeCustomText.AbsoluteSize.X - VapeCustomDrawingText.TextBounds.X), 32)
				VapeCustomDrawingShadow.Position = VapeCustomDrawingText.Position + Vector2.new(1, 1)
			end))
			table.insert(TextGUIConnections, VapeCustomText:GetPropertyChangedSignal("TextColor3"):Connect(function()
				VapeCustomDrawingText.Color = VapeCustomText.TextColor3
			end))
			table.insert(TextGUIConnections, VapeText:GetPropertyChangedSignal("AbsolutePosition"):Connect(function()
				for i,textdraw in pairs(TextGUIObjects.Labels) do 
					textdraw.Position = VapeText.AbsolutePosition + Vector2.new(VapeText.TextXAlignment == Enum.TextXAlignment.Right and (VapeText.AbsoluteSize.X - textdraw.TextBounds.X), ((textdraw.Size - 3) * i) + 6)
				end
				for i,textdraw in pairs(TextGUIObjects.ShadowLabels) do 
					textdraw.Position = Vector2.new(1, 1) + (VapeText.AbsolutePosition + Vector2.new(VapeText.TextXAlignment == Enum.TextXAlignment.Right and (VapeText.AbsoluteSize.X - textdraw.TextBounds.X), ((textdraw.Size - 3) * i) + 6))
				end
			end))
			table.insert(TextGUIConnections, VapeLogoGradient:GetPropertyChangedSignal("Color"):Connect(function()
				pcall(function()
					VapeLogoDrawing.Color = VapeLogoGradient.Color.Keypoints[1].Value
				end)
			end))
		end
	end
})
TextGUISortMode = TextGUI.CreateDropdown({
	Name = "Sort",
	List = {"Alphabetical", "Length"},
	Function = function(val)
		GuiLibrary.UpdateHudEvent:Fire()
	end
})
local TextGUIFonts = {"Arial"}
local TextGUIFonts2 = {"GothamBold"}
for i,v in pairs(Enum.Font:GetEnumItems()) do 
	if v.Name ~= "Arial" then
		table.insert(TextGUIFonts, v.Name)
	end
	if v.Name ~= "GothamBold" then
		table.insert(TextGUIFonts2, v.Name)
	end
end
TextGUI.CreateDropdown({
	Name = "Font",
	List = TextGUIFonts,
	Function = function(val)
		VapeText.Font = Enum.Font[val]
		VapeTextExtra.Font = Enum.Font[val]
		GuiLibrary.UpdateHudEvent:Fire()
	end
})
TextGUI.CreateDropdown({
	Name = "CustomTextFont",
	List = TextGUIFonts2,
	Function = function(val)
		VapeCustomText.Font = Enum.Font[val]
		VapeCustomTextShadow.Font = Enum.Font[val]
		GuiLibrary.UpdateHudEvent:Fire()
	end
})
TextGUI.CreateSlider({
	Name = "Scale",
	Min = 1,
	Max = 50,
	Default = 10,
	Function = function(val)
		VapeScale.Scale = val / 10
	end
})
TextGUI.CreateToggle({
	Name = "Shadow", 
	Function = function(callback) 
        VapeTextExtra.Visible = callback 
        VapeLogoShadow.Visible = callback 
    end,
	HoverText = "Renders shadowed text."
})
TextGUI.CreateToggle({
	Name = "Watermark", 
	Function = function(callback) 
		VapeLogo.Visible = callback
		GuiLibrary.UpdateHudEvent:Fire()
	end,
	HoverText = "Renders a vape watermark"
})
TextGUIBackgroundToggle = TextGUI.CreateToggle({
	Name = "Render background", 
	Function = function(callback)
		VapeBackground.Visible = callback
		GuiLibrary.UpdateHudEvent:Fire()
	end
})
TextGUI.CreateToggle({
	Name = "Hide Modules",
	Function = function(callback) 
		if TextGUICircleObject.Object then
			TextGUICircleObject.Object.Visible = callback
		end
	end
})
TextGUICircleObject = TextGUI.CreateCircleWindow({
	Name = "Blacklist",
	Type = "Blacklist",
	UpdateFunction = function()
		GuiLibrary.UpdateHudEvent:Fire()
	end
})
TextGUICircleObject.Object.Visible = false
local TextGUIGradient = TextGUI.CreateToggle({
	Name = "Gradient Logo",
	Function = function() 
		GuiLibrary.UpdateHudEvent:Fire()
	end
})
TextGUI.CreateToggle({
	Name = "Alternate Text",
	Function = function() 
		GuiLibrary.UpdateHudEvent:Fire()
	end
})
local CustomText = {Value = "", Object = nil}
TextGUI.CreateToggle({
	Name = "Add custom text", 
	Function = function(callback) 
		VapeCustomText.Visible = callback
		CustomText.Object.Visible = callback
		GuiLibrary.UpdateHudEvent:Fire()
	end,
	HoverText = "Renders a custom label"
})
CustomText = TextGUI.CreateTextBox({
	Name = "Custom text",
	FocusLost = function(enter)
		VapeCustomText.Text = CustomText.Value
		VapeCustomTextShadow.Text = CustomText.Value
	end
})
CustomText.Object.Visible = false

local function newHealthColor(percent)
	if percent > 0.5 then 
		return Color3.fromRGB(5, 134, 105):lerp(Color3.fromRGB(255, 255, 0), (0.5 - (percent - 0.5)) / 0.5)
	end
	return Color3.fromRGB(255, 255, 0):lerp(Color3.fromRGB(249, 57, 55), (0.5 - percent) / 0.5)
end

local TargetInfo = GuiLibrary.CreateCustomWindow({
	Name = "Target Info",
	Icon = "vape/assets/TargetInfoIcon1.png",
	IconSize = 16
})
local TargetInfoBackground = {Enabled = false}
local TargetInfoMainFrame = Instance.new("Frame")
TargetInfoMainFrame.BackgroundColor3 = Color3.fromRGB(26, 25, 26)
TargetInfoMainFrame.BorderSizePixel = 0
TargetInfoMainFrame.BackgroundTransparency = 1
TargetInfoMainFrame.Size = UDim2.new(0, 220, 0, 72)
TargetInfoMainFrame.Position = UDim2.new(0, 0, 0, 5)
TargetInfoMainFrame.Parent = TargetInfo.GetCustomChildren()
local TargetInfoMainInfo = Instance.new("Frame")
TargetInfoMainInfo.BackgroundColor3 = Color3.fromRGB(31, 30, 31)
TargetInfoMainInfo.Size = UDim2.new(0, 220, 0, 80)
TargetInfoMainInfo.BackgroundTransparency = 0.25
TargetInfoMainInfo.Position = UDim2.new(0, 0, 0, 0)
TargetInfoMainInfo.Name = "MainInfo"
TargetInfoMainInfo.Parent = TargetInfoMainFrame
local TargetInfoName = Instance.new("TextLabel")
TargetInfoName.TextSize = 14
TargetInfoName.Font = Enum.Font.Arial
TargetInfoName.TextColor3 = Color3.fromRGB(162, 162, 162)
TargetInfoName.Position = UDim2.new(0, 70, 0, 10)
TargetInfoName.TextStrokeTransparency = 1
TargetInfoName.BackgroundTransparency = 1
TargetInfoName.Size = UDim2.new(0, 80, 0, 20)
TargetInfoName.Text = "Target name"
TargetInfoName.ZIndex = 2
TargetInfoName.TextXAlignment = Enum.TextXAlignment.Left
TargetInfoName.TextYAlignment = Enum.TextYAlignment.Top
TargetInfoName.Parent = TargetInfoMainInfo
local TargetInfoNameShadow = TargetInfoName:Clone()
TargetInfoNameShadow.Size = UDim2.new(1, 0, 1, 0)
TargetInfoNameShadow.TextTransparency = 0.5
TargetInfoNameShadow.TextColor3 = Color3.new()
TargetInfoNameShadow.ZIndex = 1
TargetInfoNameShadow.Position = UDim2.new(0, 1, 0, 1)
TargetInfoName:GetPropertyChangedSignal("Text"):Connect(function()
	TargetInfoNameShadow.Text = TargetInfoName.Text
end)
TargetInfoNameShadow.Parent = TargetInfoName
local TargetInfoHealthBackground = Instance.new("Frame")
TargetInfoHealthBackground.BackgroundColor3 = Color3.fromRGB(54, 54, 54)
TargetInfoHealthBackground.Size = UDim2.new(0, 140, 0, 4)
TargetInfoHealthBackground.Position = UDim2.new(0, 72, 0, 32)
TargetInfoHealthBackground.Parent = TargetInfoMainInfo
local TargetInfoHealthBackgroundShadow = Instance.new("ImageLabel")
TargetInfoHealthBackgroundShadow.AnchorPoint = Vector2.new(0.5, 0.5)
TargetInfoHealthBackgroundShadow.Position = UDim2.new(0.5, 0, 0.5, 0)
TargetInfoHealthBackgroundShadow.Image = downloadVapeAsset("vape/assets/WindowBlur.png")
TargetInfoHealthBackgroundShadow.BackgroundTransparency = 1
TargetInfoHealthBackgroundShadow.ImageTransparency = 0.6
TargetInfoHealthBackgroundShadow.ZIndex = -1
TargetInfoHealthBackgroundShadow.Size = UDim2.new(1, 6, 1, 6)
TargetInfoHealthBackgroundShadow.ImageColor3 = Color3.new()
TargetInfoHealthBackgroundShadow.ScaleType = Enum.ScaleType.Slice
TargetInfoHealthBackgroundShadow.SliceCenter = Rect.new(10, 10, 118, 118)
TargetInfoHealthBackgroundShadow.Parent = TargetInfoHealthBackground
local TargetInfoHealth = Instance.new("Frame")
TargetInfoHealth.BackgroundColor3 = Color3.fromRGB(40, 137, 109)
TargetInfoHealth.Size = UDim2.new(1, 0, 1, 0)
TargetInfoHealth.ZIndex = 3
TargetInfoHealth.BorderSizePixel = 0
TargetInfoHealth.Parent = TargetInfoHealthBackground
local TargetInfoHealthExtra = Instance.new("Frame")
TargetInfoHealthExtra.BackgroundColor3 = Color3.fromRGB(255, 170, 0)
TargetInfoHealthExtra.Size = UDim2.new(0, 0, 1, 0)
TargetInfoHealthExtra.ZIndex = 4
TargetInfoHealthExtra.BorderSizePixel = 0
TargetInfoHealthExtra.AnchorPoint = Vector2.new(1, 0)
TargetInfoHealthExtra.Position = UDim2.new(1, 0, 0, 0)
TargetInfoHealthExtra.Parent = TargetInfoHealth
local TargetInfoImage = Instance.new("ImageLabel")
TargetInfoImage.Size = UDim2.new(0, 50, 0, 50)
TargetInfoImage.BackgroundTransparency = 1
TargetInfoImage.Image = 'rbxthumb://type=AvatarHeadShot&id='..playersService.LocalPlayer.UserId..'&w=420&h=420'
TargetInfoImage.Position = UDim2.new(0, 10, 0, 16)
TargetInfoImage.Parent = TargetInfoMainInfo
local TargetInfoMainInfoCorner = Instance.new("UICorner")
TargetInfoMainInfoCorner.CornerRadius = UDim.new(0, 4)
TargetInfoMainInfoCorner.Parent = TargetInfoMainInfo
local TargetInfoHealthBackgroundCorner = Instance.new("UICorner")
TargetInfoHealthBackgroundCorner.CornerRadius = UDim.new(0, 2048)
TargetInfoHealthBackgroundCorner.Parent = TargetInfoHealthBackground
local TargetInfoHealthCorner = Instance.new("UICorner")
TargetInfoHealthCorner.CornerRadius = UDim.new(0, 2048)
TargetInfoHealthCorner.Parent = TargetInfoHealth
local TargetInfoHealthCorner2 = Instance.new("UICorner")
TargetInfoHealthCorner2.CornerRadius = UDim.new(0, 2048)
TargetInfoHealthCorner2.Parent = TargetInfoHealthExtra
local TargetInfoHealthExtraCorner = Instance.new("UICorner")
TargetInfoHealthExtraCorner.CornerRadius = UDim.new(0, 4)
TargetInfoHealthExtraCorner.Parent = TargetInfoImage
TargetInfo.CreateDropdown({
	Name = "Font",
	List = TextGUIFonts,
	Function = function(val)
		TargetInfoName.Font = Enum.Font[val]
		TargetInfoNameShadow.Font = Enum.Font[val]
	end
})

TargetInfoBackground = TargetInfo.CreateToggle({
	Name = "Use Background",
	Function = function(callback) 
		TargetInfoMainInfo.BackgroundTransparency = callback and 0.25 or 1
		TargetInfoName.TextColor3 = callback and Color3.fromRGB(162, 162, 162) or Color3.new(1, 1, 1)
		TargetInfoName.Size = UDim2.new(0, 80, 0, callback and 16 or 18)
		TargetInfoName.TextSize = callback and 14 or 15
		TargetInfoHealthBackground.Size = UDim2.new(0, 138, 0, callback and 4 or 7)
	end,
	Default = true
})
local TargetInfoDisplayNames = TargetInfo.CreateToggle({
	Name = "Use Display Names",
	Function = function(callback) end,
	Default = true
})
local TargetInfoHealthTween
TargetInfo.GetCustomChildren().Parent:GetPropertyChangedSignal("Size"):Connect(function()
	TargetInfoMainInfo.Position = UDim2.fromOffset(0, TargetInfo.GetCustomChildren().Parent.Size ~= UDim2.fromOffset(220, 0) and -5 or 40)
end)
shared.VapeTargetInfo = {
	UpdateInfo = function(tab, targetsize) 
		if TargetInfo.GetCustomChildren().Parent then
			local hasTarget = false
			for _, v in pairs(shared.VapeTargetInfo.Targets) do
				hasTarget = true
				TargetInfoImage.Image = 'rbxthumb://type=AvatarHeadShot&id='..v.Player.UserId..'&w=420&h=420'
				TargetInfoHealth:TweenSize(UDim2.new(math.clamp(v.Humanoid.Health / v.Humanoid.MaxHealth, 0, 1), 0, 1, 0), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, 0.25, true)
				TargetInfoHealthExtra:TweenSize(UDim2.new(math.clamp((v.Humanoid.Health / v.Humanoid.MaxHealth) - 1, 0, 1), 0, 1, 0), Enum.EasingDirection.Out, Enum.EasingStyle.Quart, 0.25, true)
				if TargetInfoHealthTween then TargetInfoHealthTween:Cancel() end
				TargetInfoHealthTween = game:GetService("TweenService"):Create(TargetInfoHealth, TweenInfo.new(0.25, Enum.EasingStyle.Quart, Enum.EasingDirection.Out), {BackgroundColor3 = newHealthColor(math.clamp(v.Humanoid.Health / v.Humanoid.MaxHealth, 0, 1))})
				TargetInfoHealthTween:Play()
				TargetInfoName.Text = (TargetInfoDisplayNames.Enabled and v.Player.DisplayName or v.Player.Name)
				break
			end
			TargetInfoMainInfo.Visible = hasTarget or (TargetInfo.GetCustomChildren().Parent.Size ~= UDim2.new(0, 220, 0, 0))
		end
	end,
	Targets = {},
	Object = TargetInfo
}
task.spawn(function()
	repeat
		if shared.VapeTargetInfo then
			shared.VapeTargetInfo.UpdateInfo()
		end
		task.wait()
	until not vapeInjected
end)
GUI.CreateCustomToggle({
	Name = "Target Info", 
	Icon = "vape/assets/TargetInfoIcon2.png", 
	Function = function(callback) TargetInfo.SetVisible(callback) end,
	Priority = 1
})
local GeneralSettings = GUI.CreateDivider2("General Settings")
local ModuleSettings = GUI.CreateDivider2("Module Settings")
local GUISettings = GUI.CreateDivider2("GUI Settings")
local TeamsByColorToggle = {Enabled = false}
TeamsByColorToggle = ModuleSettings.CreateToggle({
	Name = "Teams by color", 
	Function = function() if TeamsByColorToggle.Refresh then TeamsByColorToggle.Refresh:Fire() end end,
	Default = true,
	HoverText = "Ignore players on your team designated by the game"
})
TeamsByColorToggle.Refresh = Instance.new("BindableEvent")
local MiddleClickInput
ModuleSettings.CreateToggle({
	Name = "MiddleClick friends", 
	Function = function(callback) 
		if callback then
			MiddleClickInput = inputService.InputBegan:Connect(function(input1)
				if input1.UserInputType == Enum.UserInputType.MouseButton3 then
					local entityLibrary = shared.vapeentity
					if entityLibrary then 
						local rayparams = RaycastParams.new()
						rayparams.FilterType = Enum.RaycastFilterType.Whitelist
						local chars = {}
						for i,v in pairs(entityLibrary.entityList) do 
							table.insert(chars, v.Character)
						end
						rayparams.FilterDescendantsInstances = chars
						local mouseunit = playersService.LocalPlayer:GetMouse().UnitRay
						local ray = workspace:Raycast(mouseunit.Origin, mouseunit.Direction * 10000, rayparams)
						if ray then 
							for i,v in pairs(entityLibrary.entityList) do 
								if ray.Instance:IsDescendantOf(v.Character) then 
									local found = table.find(FriendsTextList.ObjectList, v.Player.Name)
									if not found then
										table.insert(FriendsTextList.ObjectList, v.Player.Name)
										table.insert(FriendsTextList.ObjectListEnabled, true)
										FriendsTextList.RefreshValues(FriendsTextList.ObjectList)
									else
										table.remove(FriendsTextList.ObjectList, found)
										table.remove(FriendsTextList.ObjectListEnabled, found)
										FriendsTextList.RefreshValues(FriendsTextList.ObjectList)
									end
									break
								end
							end
						end
					end
				end
			end)
		else
			if MiddleClickInput then MiddleClickInput:Disconnect() end
		end
	end,
	HoverText = "Click middle mouse button to add the player you are hovering over as a friend"
})
ModuleSettings.CreateToggle({
	Name = "Lobby Check",
	Function = function() end,
	Default = true,
	HoverText = "Temporarily disables certain features in server lobbies."
})
GUIColorSlider = GUI.CreateColorSlider("GUI Theme", function(h, s, v) 
	GuiLibrary.UpdateUI(h, s, v) 
end)
local BlatantModeToggle = GUI.CreateToggle({
	Name = "Blatant mode",
	Function = function() end,
	HoverText = "Required for certain features."
})
local windowSortOrder = {
	CombatButton = 1,
	BlatantButton = 2,
	RenderButton = 3,
	UtilityButton = 4,
	WorldButton = 5,
	FriendsButton = 6,
	TargetsButton = 7,
	ProfilesButton = 8
}
local windowSortOrder2 = {"Combat", "Blatant", "Render", "Utility", "World"}

local function getVapeSaturation(val)
	local sat = 0.9
	if val < 0.03 then 
		sat = 0.75 + (0.15 * math.clamp(val / 0.03, 0, 1))
	end
	if val > 0.59 then 
		sat = 0.9 - (0.4 * math.clamp((val - 0.59) / 0.07, 0, 1))
	end
	if val > 0.68 then 
		sat = 0.5 + (0.4 * math.clamp((val - 0.68) / 0.14, 0, 1))
	end
	if val > 0.89 then 
		sat = 0.9 - (0.15 * math.clamp((val - 0.89) / 0.1, 0, 1))
	end
	return sat
end

GuiLibrary.UpdateUI = function(h, s, val, bypass)
	pcall(function()
		local rainbowGUICheck = GUIColorSlider.RainbowValue
		local mainRainbowSaturation = rainbowGUICheck and getVapeSaturation(h) or s
		local mainRainbowGradient = h + (rainbowGUICheck and -0.05 or 0)
		mainRainbowGradient = mainRainbowGradient % 1

		GuiLibrary.ObjectsThatCanBeSaved.GUIWindow.Object.Logo1.Logo2.ImageColor3 = Color3.fromHSV(h, mainRainbowSaturation, rainbowGUICheck and 1 or val)
		VapeText.TextColor3 = Color3.fromHSV(TextGUIGradient.Enabled and mainRainbowGradient or h, mainRainbowSaturation, rainbowGUICheck and 1 or val)
		VapeCustomText.TextColor3 = VapeText.TextColor3
		VapeLogoGradient.Color = ColorSequence.new({
			ColorSequenceKeypoint.new(0, Color3.fromHSV(h, mainRainbowSaturation, rainbowGUICheck and 1 or val)),
			ColorSequenceKeypoint.new(1, VapeText.TextColor3)
		})
		VapeLogoGradient2.Color = ColorSequence.new({
			ColorSequenceKeypoint.new(0, Color3.fromHSV(h, TextGUIGradient.Enabled and rainbowGUICheck and mainRainbowSaturation or 0, 1)),
			ColorSequenceKeypoint.new(1, Color3.fromHSV(TextGUIGradient.Enabled and mainRainbowGradient or h, TextGUIGradient.Enabled and rainbowGUICheck and mainRainbowSaturation or 0, 1))
		})

		local newTextGUIText = "\n"
		local backgroundTable = {}
		for i, v in pairs(TextGUIFormatted) do
			local rainbowcolor = h + (rainbowGUICheck and (-0.025 * (i + (TextGUIGradient.Enabled and 2 or 0))) or 0)
			rainbowcolor = rainbowcolor % 1
			local newcolor = Color3.fromHSV(rainbowcolor, rainbowGUICheck and getVapeSaturation(rainbowcolor) or mainRainbowSaturation, rainbowGUICheck and 1 or val)
			newTextGUIText = newTextGUIText..'<font color="rgb('..math.floor(newcolor.R * 255)..","..math.floor(newcolor.G * 255)..","..math.floor(newcolor.B * 255)..')">'..v.Text..'</font><font color="rgb(170, 170, 170)">'..v.ExtraText..'</font>\n'
			backgroundTable[i] = newcolor
		end

		if TextGUIMode.Value == "Drawing" then 
			for i,v in pairs(TextGUIObjects.Labels) do 
				if backgroundTable[i] then 
					v.Color = backgroundTable[i]
				end
			end
		end

		if TextGUIBackgroundToggle.Enabled then
			for i, v in pairs(VapeBackgroundTable) do
				v.ColorFrame.BackgroundColor3 = backgroundTable[v.LayoutOrder] or Color3.new()
			end
		end
		VapeText.Text = newTextGUIText

		if (not GuiLibrary.MainGui.ScaledGui.ClickGui.Visible) and (not GuiLibrary.MainGui.ScaledGui.LegitGui.Visible) and (not bypass) then return end
		GuiLibrary.MainGui.ScaledGui.ClickGui.SearchBar.LegitMode.ImageColor3 = Color3.fromHSV(h, mainRainbowSaturation, rainbowGUICheck and 1 or val)
		local buttonColorIndex = 0
		for i, v in pairs(GuiLibrary.ObjectsThatCanBeSaved) do
			if v.Type == "TargetFrame" then
				if v.Object2.Visible then
					v.Object.TextButton.Frame.BackgroundColor3 = Color3.fromHSV(h, mainRainbowSaturation, rainbowGUICheck and 1 or val)
				end
			elseif v.Type == "TargetButton" then
				if v.Api.Enabled then
					v.Object.BackgroundColor3 = Color3.fromHSV(h, mainRainbowSaturation, rainbowGUICheck and 1 or val)
				end
			elseif v.Type == "CircleListFrame" then
				if v.Object2.Visible then
					v.Object.TextButton.Frame.BackgroundColor3 = Color3.fromHSV(h, mainRainbowSaturation, rainbowGUICheck and 1 or val)
				end
			elseif v.Type == "LegitModule" then
				if v.Toggle.Visible and v.Api.Enabled  then
					v.Toggle.BackgroundColor3 = Color3.fromHSV(h, mainRainbowSaturation, rainbowGUICheck and 1 or val)
				end
			elseif (v.Type == "Button" or v.Type == "ButtonMain") and v.Api.Enabled then
				buttonColorIndex = buttonColorIndex + 1
				local rainbowcolor = h + (rainbowGUICheck and (-0.025 * windowSortOrder[i]) or 0)
				rainbowcolor = rainbowcolor % 1
				local newcolor = Color3.fromHSV(rainbowcolor, rainbowGUICheck and getVapeSaturation(rainbowcolor) or mainRainbowSaturation, rainbowGUICheck and 1 or val)
				v.Object.ButtonText.TextColor3 = newcolor
				if v.Object:FindFirstChild("ButtonIcon") then
					v.Object.ButtonIcon.ImageColor3 = newcolor
				end
			elseif v.Type == "OptionsButton" then
				if v.Api.Enabled then
					local newcolor = Color3.fromHSV(h, mainRainbowSaturation, rainbowGUICheck and 1 or val)
					if (not oldrainbow) then
						local mainRainbowGradient = table.find(windowSortOrder2, v.Object.Parent.Parent.Name)
						mainRainbowGradient = mainRainbowGradient and (mainRainbowGradient - 1) > 0 and GuiLibrary.ObjectsThatCanBeSaved[windowSortOrder2[mainRainbowGradient - 1].."Window"].SortOrder or 0
						local rainbowcolor = h + (rainbowGUICheck and (-0.025 * (mainRainbowGradient + v.SortOrder)) or 0)
						rainbowcolor = rainbowcolor % 1
						newcolor = Color3.fromHSV(rainbowcolor, rainbowGUICheck and getVapeSaturation(rainbowcolor) or mainRainbowSaturation, rainbowGUICheck and 1 or val)
					end
					v.Object.BackgroundColor3 = newcolor
				end
			elseif v.Type == "ExtrasButton" then
				if v.Api.Enabled then
					local rainbowcolor = h + (rainbowGUICheck and (-0.025 * buttonColorIndex) or 0)
					rainbowcolor = rainbowcolor % 1
					local newcolor = Color3.fromHSV(rainbowcolor, rainbowGUICheck and getVapeSaturation(rainbowcolor) or mainRainbowSaturation, rainbowGUICheck and 1 or val)
					v.Object.ImageColor3 = newcolor
				end
			elseif (v.Type == "Toggle" or v.Type == "ToggleMain") and v.Api.Enabled then
				v.Object.ToggleFrame1.BackgroundColor3 = Color3.fromHSV(h, mainRainbowSaturation, rainbowGUICheck and 1 or val)
			elseif v.Type == "Slider" or v.Type == "SliderMain" then
				v.Object.Slider.FillSlider.BackgroundColor3 = Color3.fromHSV(h, mainRainbowSaturation, rainbowGUICheck and 1 or val)
				v.Object.Slider.FillSlider.ButtonSlider.ImageColor3 = Color3.fromHSV(h, mainRainbowSaturation, rainbowGUICheck and 1 or val)
			elseif v.Type == "TwoSlider" then
				v.Object.Slider.FillSlider.BackgroundColor3 = Color3.fromHSV(h, mainRainbowSaturation, rainbowGUICheck and 1 or val)
				v.Object.Slider.ButtonSlider.ImageColor3 = Color3.fromHSV(h, mainRainbowSaturation, rainbowGUICheck and 1 or val)
				v.Object.Slider.ButtonSlider2.ImageColor3 = Color3.fromHSV(h, mainRainbowSaturation, rainbowGUICheck and 1 or val)
			end
		end

		local rainbowcolor = h + (rainbowGUICheck and (-0.025 * buttonColorIndex) or 0)
		rainbowcolor = rainbowcolor % 1
		GuiLibrary.ObjectsThatCanBeSaved.GUIWindow.Object.Children.Extras.MainButton.ImageColor3 = (GUI.GetVisibleIcons() > 0 and Color3.fromHSV(rainbowcolor, getVapeSaturation(rainbowcolor), 1) or Color3.fromRGB(199, 199, 199))

		for i, v in pairs(ProfilesTextList.ScrollingObject.ScrollingFrame:GetChildren()) do
			if v:IsA("TextButton") and v.ItemText.Text == GuiLibrary.CurrentProfile then
				v.BackgroundColor3 = Color3.fromHSV(h, mainRainbowSaturation, rainbowGUICheck and 1 or val)
				v.ImageButton.BackgroundColor3 = Color3.fromHSV(h, mainRainbowSaturation, rainbowGUICheck and 1 or val)
				v.ItemText.TextColor3 = Color3.new(1, 1, 1)
				v.ItemText.TextStrokeTransparency = 0.75
			end
		end
	end)
end

GUISettings.CreateToggle({
	Name = "Blur Background", 
	Function = function(callback) 
		GuiLibrary.MainBlur.Size = (callback and 25 or 0) 
		--game:GetService("RunService"):SetRobloxGuiFocused(GuiLibrary.MainGui.ScaledGui.ClickGui.Visible and callback) 
	end,
	Default = true,
	HoverText = "Blur the background of the GUI"
})
local welcomeMessage = GUISettings.CreateToggle({
	Name = "GUI bind indicator", 
	Function = function() end, 
	Default = true,
	HoverText = 'Displays a message indicating your GUI keybind upon injecting.\nI.E "Press RIGHTSHIFT to open GUI"'
})
GUISettings.CreateToggle({
	Name = "Old Rainbow", 
	Function = function(callback) oldrainbow = callback end,
	HoverText = "Reverts to old rainbow"
})
GUISettings.CreateToggle({
	Name = "Show Tooltips", 
	Function = function(callback) GuiLibrary.ToggleTooltips = callback end,
	Default = true,
	HoverText = "Toggles visibility of these"
})
local GUIRescaleToggle = GUISettings.CreateToggle({
	Name = "Rescale", 
	Function = function(callback) 
		task.spawn(function()
			GuiLibrary.MainRescale.Scale = (callback and math.clamp(gameCamera.ViewportSize.X / 1920, 0.5, 1) or 0.99)
			task.wait(0.01)
			GuiLibrary.MainRescale.Scale = (callback and math.clamp(gameCamera.ViewportSize.X / 1920, 0.5, 1) or 1)
		end)
	end,
	Default = true,
	HoverText = "Rescales the GUI"
})
gameCamera:GetPropertyChangedSignal("ViewportSize"):Connect(function()
	if GUIRescaleToggle.Enabled then
		GuiLibrary.MainRescale.Scale = math.clamp(gameCamera.ViewportSize.X / 1920, 0.5, 1)
	end
end)
GUISettings.CreateToggle({
	Name = "Notifications", 
	Function = function(callback) 
		GuiLibrary.Notifications = callback 
	end,
	Default = true,
	HoverText = "Shows notifications"
})
local ToggleNotifications
ToggleNotifications = GUISettings.CreateToggle({
	Name = "Toggle Alert", 
	Function = function(callback) GuiLibrary.ToggleNotifications = callback end,
	Default = true,
	HoverText = "Notifies you if a module is enabled/disabled."
})
ToggleNotifications.Object.BackgroundTransparency = 0
ToggleNotifications.Object.BorderSizePixel = 0
ToggleNotifications.Object.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
GUISettings.CreateSlider({
	Name = "Rainbow Speed",
	Function = function(val)
		GuiLibrary.RainbowSpeed = math.max((val / 10) - 0.4, 0)
	end,
	Min = 1,
	Max = 100,
	Default = 10
})

local GUIbind = GUI.CreateGUIBind()
local teleportConnection = playersService.LocalPlayer.OnTeleport:Connect(function(State)
    if (not teleportedServers) and (not shared.VapeIndependent) then
		teleportedServers = true
		local teleportScript = [[
			shared.VapeSwitchServers = true 
			if shared.VapeDeveloper then 
				loadstring(readfile("vape/NewMainScript.lua"))() 
			else 
				loadstring(game:HttpGet("https://raw.githubusercontent.com/7GrandDadPGN/VapeV4ForRoblox/"..readfile("vape/commithash.txt").."/NewMainScript.lua", true))() 
			end
		]]
		if shared.VapeDeveloper then
			teleportScript = 'shared.VapeDeveloper = true\n'..teleportScript
		end
		if shared.VapePrivate then
			teleportScript = 'shared.VapePrivate = true\n'..teleportScript
		end
		if shared.VapeCustomProfile then 
			teleportScript = "shared.VapeCustomProfile = '"..shared.VapeCustomProfile.."'\n"..teleportScript
		end
		GuiLibrary.SaveSettings()
		queueonteleport(teleportScript)
    end
end)

GuiLibrary.SelfDestruct = function()
	task.spawn(function()
		coroutine.close(saveSettingsLoop)
	end)
	if GuiLibrary.ColorStepped then GuiLibrary.ColorStepped:Disconnect() end

	if vapeInjected then 
		GuiLibrary.SaveSettings()
	end
	vapeInjected = false
	inputService.OverrideMouseIconBehavior = Enum.OverrideMouseIconBehavior.None

	for i,v in pairs(GuiLibrary.ObjectsThatCanBeSaved) do
		if (v.Type == "Button" or v.Type == "OptionsButton" or v.Type == "LegitModule") and v.Api.Enabled then
			v.Api.ToggleButton(false)
		end
	end

	for i,v in pairs(TextGUIConnections) do 
		v:Disconnect()
	end
	for i,v in pairs(TextGUIObjects) do 
		for i2,v2 in pairs(v) do 
			v2.Visible = false
			v2:Destroy()
			v[i2] = nil
		end
	end

	GuiLibrary.SelfDestructEvent:Fire()
	shared.VapeExecuted = nil
	shared.VapePrivate = nil
	shared.VapeFullyLoaded = nil
	shared.VapeSwitchServers = nil
	shared.GuiLibrary = nil
	shared.VapeIndependent = nil
	shared.VapeManualLoad = nil
	shared.CustomSaveVape = nil
	GuiLibrary.KeyInputHandler:Disconnect()
	GuiLibrary.KeyInputHandler2:Disconnect()
	if MiddleClickInput then
		MiddleClickInput:Disconnect()
	end
	teleportConnection:Disconnect()
	GuiLibrary.MainGui:Destroy()
	--game:GetService("RunService"):SetRobloxGuiFocused(false)	
end

GeneralSettings.CreateButton2({
	Name = "RESET CURRENT PROFILE", 
	Function = function()
		local vapePrivateCheck = shared.VapePrivate
		GuiLibrary.SelfDestruct()
		if delfile then
			delfile(baseDirectory.."Profiles/"..(GuiLibrary.CurrentProfile ~= "default" and GuiLibrary.CurrentProfile or "")..(shared.CustomSaveVape or game.PlaceId)..".vapeprofile.txt")
		else
			writefile(baseDirectory.."Profiles/"..(GuiLibrary.CurrentProfile ~= "default" and GuiLibrary.CurrentProfile or "")..(shared.CustomSaveVape or game.PlaceId)..".vapeprofile.txt", "")
		end
		shared.VapeSwitchServers = true
		shared.VapeOpenGui = true
		shared.VapePrivate = vapePrivateCheck
		loadstring(vapeGithubRequest("NewMainScript.lua"))()
	end
})
GUISettings.CreateButton2({
	Name = "RESET GUI POSITIONS", 
	Function = function()
		for i,v in pairs(GuiLibrary.ObjectsThatCanBeSaved) do
			if (v.Type == "Window" or v.Type == "CustomWindow") then
				v.Object.Position = (i == "GUIWindow" and UDim2.new(0, 6, 0, 6) or UDim2.new(0, 223, 0, 6))
			end
		end
	end
})
GUISettings.CreateButton2({
	Name = "SORT GUI", 
	Function = function()
		local sorttable = {}
		local movedown = false
		local sortordertable = {
			GUIWindow = 1,
			CombatWindow = 2,
			BlatantWindow = 3,
			RenderWindow = 4,
			UtilityWindow = 5,
			WorldWindow = 6,
			FriendsWindow = 7,
			TargetsWindow = 8,
			ProfilesWindow = 9,
			["Text GUICustomWindow"] = 10,
			TargetInfoCustomWindow = 11,
			RadarCustomWindow = 12,
		}
		local storedpos = {}
		local num = 6
		for i,v in pairs(GuiLibrary.ObjectsThatCanBeSaved) do
			local obj = GuiLibrary.ObjectsThatCanBeSaved[i]
			if obj then
				if v.Type == "Window" and v.Object.Visible then
					local sortordernum = (sortordertable[i] or #sorttable)
					sorttable[sortordernum] = v.Object
				end
			end
		end
		for i2,v2 in pairs(sorttable) do
			if num > 1697 then
				movedown = true
				num = 6
			end
			v2.Position = UDim2.new(0, num, 0, (movedown and (storedpos[num] and (storedpos[num] + 9) or 400) or 39))
			if not storedpos[num] then
				storedpos[num] = v2.AbsoluteSize.Y
				if v2.Name == "MainWindow" then
					storedpos[num] = 400
				end
			end
			num = num + 223
		end
	end
})
GeneralSettings.CreateButton2({
	Name = "UNINJECT",
	Function = GuiLibrary.SelfDestruct
})

local function loadVape()
	if not shared.VapeIndependent then
		loadstring(vapeGithubRequest("Universal.lua"))()
		if isfile("vape/CustomModules/"..game.PlaceId..".lua") then
			loadstring(readfile("vape/CustomModules/"..game.PlaceId..".lua"))()
		else
			if not shared.VapeDeveloper then
				local suc, publicrepo = pcall(function() return game:HttpGet("https://raw.githubusercontent.com/7GrandDadPGN/VapeV4ForRoblox/"..readfile("vape/commithash.txt").."/CustomModules/"..game.PlaceId..".lua") end)
				if suc and publicrepo and publicrepo ~= "404: Not Found" then
					writefile("vape/CustomModules/"..game.PlaceId..".lua", "--This watermark is used to delete the file if its cached, remove it to make the file persist after commits.\n"..publicrepo)
					loadstring(readfile("vape/CustomModules/"..game.PlaceId..".lua"))()
				end
			end
		end
		if shared.VapePrivate then
			if isfile("vapeprivate/CustomModules/"..game.PlaceId..".lua") then
				loadstring(readfile("vapeprivate/CustomModules/"..game.PlaceId..".lua"))()
			end	
		end
	else
		repeat task.wait() until shared.VapeManualLoad
	end
	if #ProfilesTextList.ObjectList == 0 then
		table.insert(ProfilesTextList.ObjectList, "default")
		ProfilesTextList.RefreshValues(ProfilesTextList.ObjectList)
	end
	GuiLibrary.LoadSettings(shared.VapeCustomProfile)
	local profiles = {}
	for i,v in pairs(GuiLibrary.Profiles) do 
		table.insert(profiles, i)
	end
	table.sort(profiles, function(a, b) return b == "default" and true or a:lower() < b:lower() end)
	ProfilesTextList.RefreshValues(profiles)
	GUIbind.Reload()
	TextGUIUpdate()
	GuiLibrary.UpdateUI(GUIColorSlider.Hue, GUIColorSlider.Sat, GUIColorSlider.Value, true)
	if not shared.VapeSwitchServers then
		if BlatantModeToggle.Enabled then
			pcall(function()
				local frame = GuiLibrary.CreateNotification("Blatant Enabled", "Vape is now in Blatant Mode.", 5.5, "assets/WarningNotification.png")
				frame.Frame.Frame.ImageColor3 = Color3.fromRGB(236, 129, 44)
			end)
		end
		GuiLibrary.LoadedAnimation(welcomeMessage.Enabled)
	else
		shared.VapeSwitchServers = nil
	end
	if shared.VapeOpenGui then
		GuiLibrary.MainGui.ScaledGui.ClickGui.Visible = true
		GuiLibrary.MainGui.ScaledGui.LegitGui.Visible = false
		--game:GetService("RunService"):SetRobloxGuiFocused(GuiLibrary.MainBlur.Size ~= 0) 
		shared.VapeOpenGui = nil
	end

	coroutine.resume(saveSettingsLoop)
	shared.VapeFullyLoaded = true
end

if shared.VapeIndependent then
	task.spawn(loadVape)
	shared.VapeFullyLoaded = true
	return GuiLibrary
else
	loadVape()
end
local GuiLibrary = shared.GuiLibrary
local playersService = game:GetService("Players")
local coreGui = game:GetService("CoreGui")
local textService = game:GetService("TextService")
local lightingService = game:GetService("Lighting")
local textChatService = game:GetService("TextChatService")
local inputService = game:GetService("UserInputService")
local runService = game:GetService("RunService")
local replicatedStorage = game:GetService("ReplicatedStorage")
local tweenService = game:GetService("TweenService")
local gameCamera = workspace.CurrentCamera
local lplr = playersService.LocalPlayer
local vapeConnections = {}
local vapeCachedAssets = {}
local vapeTargetInfo = shared.VapeTargetInfo
local vapeInjected = true
table.insert(vapeConnections, workspace:GetPropertyChangedSignal("CurrentCamera"):Connect(function()
	gameCamera = workspace.CurrentCamera or workspace:FindFirstChildWhichIsA("Camera")
end))
local isfile = isfile or function(file)
	local suc, res = pcall(function() return readfile(file) end)
	return suc and res ~= nil
end
local networkownerswitch = tick()
local isnetworkowner = function(part)
	local suc, res = pcall(function() return gethiddenproperty(part, "NetworkOwnershipRule") end)
	if suc and res == Enum.NetworkOwnership.Manual then
		sethiddenproperty(part, "NetworkOwnershipRule", Enum.NetworkOwnership.Automatic)
		networkownerswitch = tick() + 8
	end
	return networkownerswitch <= tick()
end
local vapeAssetTable = {["vape/assets/VapeCape.png"] = "rbxassetid://13380453812", ["vape/assets/ArrowIndicator.png"] = "rbxassetid://13350766521"}
local getcustomasset = getsynasset or getcustomasset or function(location) return vapeAssetTable[location] or "" end
local queueonteleport = syn and syn.queue_on_teleport or queue_on_teleport or function() end
local synapsev3 = syn and syn.toast_notification and "V3" or ""
local worldtoscreenpoint = function(pos)
	if synapsev3 == "V3" then
		local scr = worldtoscreen({pos})
		return scr[1] - Vector3.new(0, 36, 0), scr[1].Z > 0
	end
	return gameCamera.WorldToScreenPoint(gameCamera, pos)
end
local worldtoviewportpoint = function(pos)
	if synapsev3 == "V3" then
		local scr = worldtoscreen({pos})
		return scr[1], scr[1].Z > 0
	end
	return gameCamera.WorldToViewportPoint(gameCamera, pos)
end

local function vapeGithubRequest(scripturl)
	if not isfile("vape/"..scripturl) then
		local suc, res = pcall(function() return game:HttpGet("https://raw.githubusercontent.com/7GrandDadPGN/VapeV4ForRoblox/"..readfile("vape/commithash.txt").."/"..scripturl, true) end)
		assert(suc, res)
		assert(res ~= "404: Not Found", res)
		if scripturl:find(".lua") then res = "--This watermark is used to delete the file if its cached, remove it to make the file persist after commits.\n"..res end
		writefile("vape/"..scripturl, res)
	end
	return readfile("vape/"..scripturl)
end

local function downloadVapeAsset(path)
	if not isfile(path) then
		task.spawn(function()
			local textlabel = Instance.new("TextLabel")
			textlabel.Size = UDim2.new(1, 0, 0, 36)
			textlabel.Text = "Downloading "..path
			textlabel.BackgroundTransparency = 1
			textlabel.TextStrokeTransparency = 0
			textlabel.TextSize = 30
			textlabel.Font = Enum.Font.SourceSans
			textlabel.TextColor3 = Color3.new(1, 1, 1)
			textlabel.Position = UDim2.new(0, 0, 0, -36)
			textlabel.Parent = GuiLibrary.MainGui
			repeat task.wait() until isfile(path)
			textlabel:Destroy()
		end)
		local suc, req = pcall(function() return vapeGithubRequest(path:gsub("vape/assets", "assets")) end)
        if suc and req then
		    writefile(path, req)
        else
            return ""
        end
	end
	if not vapeCachedAssets[path] then vapeCachedAssets[path] = getcustomasset(path) end
	return vapeCachedAssets[path]
end

local function warningNotification(title, text, delay)
	local suc, res = pcall(function()
		local frame = GuiLibrary.CreateNotification(title, text, delay, "assets/WarningNotification.png")
		frame.Frame.Frame.ImageColor3 = Color3.fromRGB(236, 129, 44)
		return frame
	end)
	return (suc and res)
end

local function removeTags(str)
	str = str:gsub("<br%s*/>", "\n")
	return (str:gsub("<[^<>]->", ""))
end

local function run(func) func() end

local function isFriend(plr, recolor)
	if GuiLibrary.ObjectsThatCanBeSaved["Use FriendsToggle"].Api.Enabled then
		local friend = table.find(GuiLibrary.ObjectsThatCanBeSaved.FriendsListTextCircleList.Api.ObjectList, plr.Name)
		friend = friend and GuiLibrary.ObjectsThatCanBeSaved.FriendsListTextCircleList.Api.ObjectListEnabled[friend]
		if recolor then
			friend = friend and GuiLibrary.ObjectsThatCanBeSaved["Recolor visualsToggle"].Api.Enabled
		end
		return friend
	end
	return nil
end

local function isTarget(plr)
	local friend = table.find(GuiLibrary.ObjectsThatCanBeSaved.TargetsListTextCircleList.Api.ObjectList, plr.Name)
	friend = friend and GuiLibrary.ObjectsThatCanBeSaved.TargetsListTextCircleList.Api.ObjectListEnabled[friend]
	return friend
end

local function isVulnerable(plr)
	return plr.Humanoid.Health > 0 and not plr.Character.FindFirstChildWhichIsA(plr.Character, "ForceField")
end

local function getPlayerColor(plr)
	if isFriend(plr, true) then
		return Color3.fromHSV(GuiLibrary.ObjectsThatCanBeSaved["Friends ColorSliderColor"].Api.Hue, GuiLibrary.ObjectsThatCanBeSaved["Friends ColorSliderColor"].Api.Sat, GuiLibrary.ObjectsThatCanBeSaved["Friends ColorSliderColor"].Api.Value)
	end
	return tostring(plr.TeamColor) ~= "White" and plr.TeamColor.Color
end

local whitelist = {data = {WhitelistedUsers = {}}, hashes = {}, said = {}, alreadychecked = {}, customtags = {}, loaded = false, localprio = 0, hooked = false, get = function() return 0, true end}
local entityLibrary = loadstring(vapeGithubRequest("Libraries/entityHandler.lua"))()
shared.vapeentity = entityLibrary
do
	entityLibrary.selfDestruct()
	table.insert(vapeConnections, GuiLibrary.ObjectsThatCanBeSaved.FriendsListTextCircleList.Api.FriendRefresh.Event:Connect(function()
		entityLibrary.fullEntityRefresh()
	end))
	table.insert(vapeConnections, GuiLibrary.ObjectsThatCanBeSaved["Teams by colorToggle"].Api.Refresh.Event:Connect(function()
		entityLibrary.fullEntityRefresh()
	end))
	local oldUpdateBehavior = entityLibrary.getUpdateConnections
	entityLibrary.getUpdateConnections = function(newEntity)
		local oldUpdateConnections = oldUpdateBehavior(newEntity)
		table.insert(oldUpdateConnections, {Connect = function()
			newEntity.Friend = isFriend(newEntity.Player) and true
			newEntity.Target = isTarget(newEntity.Player) and true
			return {Disconnect = function() end}
		end})
		return oldUpdateConnections
	end
	entityLibrary.isPlayerTargetable = function(plr)
		if isFriend(plr) then return false end
		if not ({whitelist:get(plr)})[2] then return false end
		if (not GuiLibrary.ObjectsThatCanBeSaved["Teams by colorToggle"].Api.Enabled) then return true end
		if (not lplr.Team) then return true end
		if (not plr.Team) then return true end
		if plr.Team ~= lplr.Team then return true end
        return #plr.Team:GetPlayers() == playersService.NumPlayers
	end
	entityLibrary.fullEntityRefresh()
	entityLibrary.LocalPosition = Vector3.zero

	task.spawn(function()
		local postable = {}
		repeat
			task.wait()
			if entityLibrary.isAlive then
				table.insert(postable, {Time = tick(), Position = entityLibrary.character.HumanoidRootPart.Position})
				if #postable > 100 then
					table.remove(postable, 1)
				end
				local closestmag = 9e9
				local closestpos = entityLibrary.character.HumanoidRootPart.Position
				local currenttime = tick()
				for i, v in pairs(postable) do
					local mag = 0.1 - (currenttime - v.Time)
					if mag < closestmag and mag > 0 then
						closestmag = mag
						closestpos = v.Position
					end
				end
				entityLibrary.LocalPosition = closestpos
			end
		until not vapeInjected
	end)
end

local function calculateMoveVector(cameraRelativeMoveVector)
	local c, s
	local _, _, _, R00, R01, R02, _, _, R12, _, _, R22 = gameCamera.CFrame:GetComponents()
	if R12 < 1 and R12 > -1 then
		c = R22
		s = R02
	else
		c = R00
		s = -R01*math.sign(R12)
	end
	local norm = math.sqrt(c*c + s*s)
	return Vector3.new(
		(c*cameraRelativeMoveVector.X + s*cameraRelativeMoveVector.Z)/norm,
		0,
		(c*cameraRelativeMoveVector.Z - s*cameraRelativeMoveVector.X)/norm
	)
end

local raycastWallProperties = RaycastParams.new()
local function raycastWallCheck(char, checktable)
	if not checktable.IgnoreObject then
		checktable.IgnoreObject = raycastWallProperties
		local filter = {lplr.Character, gameCamera}
		for i,v in pairs(entityLibrary.entityList) do
			if v.Targetable then
				table.insert(filter, v.Character)
			end
		end
		for i,v in pairs(checktable.IgnoreTable or {}) do
			table.insert(filter, v)
		end
		raycastWallProperties.FilterDescendantsInstances = filter
	end
	local ray = workspace.Raycast(workspace, checktable.Origin, (char[checktable.AimPart].Position - checktable.Origin), checktable.IgnoreObject)
	return not ray
end

local function EntityNearPosition(distance, checktab)
	checktab = checktab or {}
	if entityLibrary.isAlive then
		local sortedentities = {}
		for i, v in pairs(entityLibrary.entityList) do -- loop through playersService
			if not v.Targetable then continue end
            if isVulnerable(v) then -- checks
				local playerPosition = v.RootPart.Position
				local mag = (entityLibrary.character.HumanoidRootPart.Position - playerPosition).magnitude
				if checktab.Prediction and mag > distance then
					mag = (entityLibrary.LocalPosition - playerPosition).magnitude
				end
                if mag <= distance then -- mag check
					table.insert(sortedentities, {entity = v, Magnitude = v.Target and -1 or mag})
                end
            end
        end
		table.sort(sortedentities, function(a, b) return a.Magnitude < b.Magnitude end)
		for i, v in pairs(sortedentities) do
			if checktab.WallCheck then
				if not raycastWallCheck(v.entity, checktab) then continue end
			end
			return v.entity
		end
	end
end

local function EntityNearMouse(distance, checktab)
	checktab = checktab or {}
    if entityLibrary.isAlive then
		local sortedentities = {}
		local mousepos = inputService.GetMouseLocation(inputService)
		for i, v in pairs(entityLibrary.entityList) do
			if not v.Targetable then continue end
            if isVulnerable(v) then
				local vec, vis = worldtoscreenpoint(v[checktab.AimPart].Position)
				local mag = (mousepos - Vector2.new(vec.X, vec.Y)).magnitude
                if vis and mag <= distance then
					table.insert(sortedentities, {entity = v, Magnitude = v.Target and -1 or mag})
                end
            end
        end
		table.sort(sortedentities, function(a, b) return a.Magnitude < b.Magnitude end)
		for i, v in pairs(sortedentities) do
			if checktab.WallCheck then
				if not raycastWallCheck(v.entity, checktab) then continue end
			end
			return v.entity
		end
    end
end

local function AllNearPosition(distance, amount, checktab)
	local returnedplayer = {}
	local currentamount = 0
	checktab = checktab or {}
    if entityLibrary.isAlive then
		local sortedentities = {}
		for i, v in pairs(entityLibrary.entityList) do
			if not v.Targetable then continue end
            if isVulnerable(v) then
				local playerPosition = v.RootPart.Position
				local mag = (entityLibrary.character.HumanoidRootPart.Position - playerPosition).magnitude
				if checktab.Prediction and mag > distance then
					mag = (entityLibrary.LocalPosition - playerPosition).magnitude
				end
                if mag <= distance then
					table.insert(sortedentities, {entity = v, Magnitude = mag})
                end
            end
        end
		table.sort(sortedentities, function(a, b) return a.Magnitude < b.Magnitude end)
		for i,v in pairs(sortedentities) do
			if checktab.WallCheck then
				if not raycastWallCheck(v.entity, checktab) then continue end
			end
			table.insert(returnedplayer, v.entity)
			currentamount = currentamount + 1
			if currentamount >= amount then break end
		end
	end
	return returnedplayer
end

local sha = loadstring(vapeGithubRequest("Libraries/sha.lua"))()
run(function()
	local olduninject
	function whitelist:get(plr)
		local plrstr = self:hash(plr.Name..plr.UserId)
		for i,v in self.data.WhitelistedUsers do
			if v.hash == plrstr then
				return v.level, v.attackable or whitelist.localprio >= v.level, v.tags
			end
		end
		return 0, true
	end

	function whitelist:isingame()
		for i, v in playersService:GetPlayers() do
			if self:get(v) ~= 0 then
				return true
			end
		end
		return false
	end

	function whitelist:tag(plr, text, rich)
		local plrtag = ({self:get(plr)})[3] or self.customtags[plr.Name] or {}
		if not text then return plrtag end
		local newtag = ''
		for i, v in plrtag do
			newtag = newtag..(rich and '<font color="#'..v.color:ToHex()..'">['..v.text..']</font>' or '['..removeTags(v.text)..']')..' '
		end
		return newtag
	end

	function whitelist:hash(str)
		if self.hashes[str] == nil and sha then
			self.hashes[str] = sha.sha512(str..'SelfReport')
		end
		return self.hashes[str] or ''
	end

	function whitelist:getplayer(arg)
		if arg == 'default' and self.localprio == 0 then return true end
		if arg == 'private' and self.localprio == 1 then return true end
		if arg and lplr.Name:lower():sub(1, arg:len()) == arg:lower() then return true end
		return false
	end

	function whitelist:playeradded(v, joined)
		if self:get(v) ~= 0 then
			if self.alreadychecked[v.UserId] then return end
			self.alreadychecked[v.UserId] = true
			self:hook()
			if self.localprio == 0 then
				olduninject = GuiLibrary.SelfDestruct
				GuiLibrary.SelfDestruct = function() warningNotification('Vape', 'No escaping the private members :)', 10) end
				if joined then task.wait(10) end
				if textChatService.ChatVersion == Enum.ChatVersion.TextChatService then
					local oldchannel = textChatService.ChatInputBarConfiguration.TargetTextChannel
					local newchannel = cloneref(game:GetService('RobloxReplicatedStorage')).ExperienceChat.WhisperChat:InvokeServer(v.UserId)
					if newchannel then newchannel:SendAsync('helloimusinginhaler') end
					textChatService.ChatInputBarConfiguration.TargetTextChannel = oldchannel
				elseif replicatedStorage:FindFirstChild('DefaultChatSystemChatEvents') then
					replicatedStorage.DefaultChatSystemChatEvents.SayMessageRequest:FireServer('/w '..v.Name..' helloimusinginhaler', 'All')
				end
			end
		end
	end

	function whitelist:checkmessage(msg, plr)
		local otherprio = self:get(plr)
		if plr == lplr and msg == 'helloimusinginhaler' then return true end
		if self.localprio > 0 and self.said[plr.Name] == nil and msg == 'helloimusinginhaler' and plr ~= lplr then
			self.said[plr.Name] = true
			notif('Vape', plr.Name..' is using vape!', 60)
			self.customtags[plr.Name] = {{text = 'VAPE USER', color = Color3.new(1, 1, 0)}}
			local newent = entityLibrary.getEntity(plr)
			if newent then entityLibrary.Events.EntityUpdated:Fire(newent) end
			return true
		end
		if self.localprio < otherprio or plr == lplr then
			local args = msg:split(' ')
			table.remove(args, 1)
			if self:getplayer(args[1]) then
				table.remove(args, 1)
				for i,v in self.commands do
					if msg:len() >= (i:len() + 1) and msg:sub(1, i:len() + 1):lower() == ";"..i:lower() then
						v(plr, args)
						return true
					end
				end
			end
		end
		return false
	end

	function whitelist:newchat(obj, plr, skip)
		obj.Text = self:tag(plr, true, true)..obj.Text
		local sub = obj.ContentText:find(': ')
		if sub then
			if not skip and self:checkmessage(obj.ContentText:sub(sub + 3, #obj.ContentText), plr) then
				obj.Visible = false
			end
		end
	end

	function whitelist:oldchat(func)
		local msgtable = debug.getupvalue(func, 3)
		if typeof(msgtable) == 'table' and msgtable.CurrentChannel then
			whitelist.oldchattable = msgtable
		end
		local oldchat

		oldchat = hookfunction(func, function(data, ...)
			local plr = playersService:GetPlayerByUserId(data.SpeakerUserId)
			if plr then
				data.ExtraData.Tags = data.ExtraData.Tags or {}
				for i, v in self:tag(plr) do
					table.insert(data.ExtraData.Tags, {TagText = v.text, TagColor = v.color})
				end
				if data.Message and self:checkmessage(data.Message, plr) then data.Message = '' end
			end
			return oldchat(data, ...)
		end)
		table.insert(vapeConnections, {Disconnect = function() hookfunction(func, oldchat) end})
	end

	function whitelist:hook()
		if self.hooked then return end
		self.hooked = true
		local exp = coreGui:FindFirstChild('ExperienceChat')
		if exp then
			local bubblechat = exp:WaitForChild('bubbleChat', 5)
			if bubblechat then
				table.insert(vape.Connections, bubblechat.DescendantAdded:Connect(function(newbubble)
					if newbubble:IsA('TextLabel') and newbubble.Text:find('helloimusinginhaler') then
						newbubble.Parent.Parent.Visible = false
					end
				end))
			end
		end
		if textChatService.ChatVersion == Enum.ChatVersion.TextChatService then
			if exp then
				table.insert(vape.Connections, exp:FindFirstChild('RCTScrollContentView', true).ChildAdded:Connect(function(obj)
					local plr = playersService:GetPlayerByUserId(tonumber(obj.Name:split('-')[1]) or 0)
					obj = obj:FindFirstChild('TextMessage', true)
					if obj then
						if plr then
							self:newchat(obj, plr, true)
							obj:GetPropertyChangedSignal('Text'):Wait()
							self:newchat(obj, plr)
						end
						if obj.ContentText:sub(1, 35) == 'You are now privately chatting with' then
							obj.Visible = false
						end
					end
				end))
			end
		elseif replicatedStorage:FindFirstChild('DefaultChatSystemChatEvents') then
			pcall(function()
				for i, v in getconnections(replicatedStorage.DefaultChatSystemChatEvents.OnNewMessage.OnClientEvent) do
					if table.find(debug.getconstants(v.Function), 'UpdateMessagePostedInChannel') then
						whitelist:oldchat(v.Function)
						break
					end
				end
				for i, v in getconnections(replicatedStorage.DefaultChatSystemChatEvents.OnMessageDoneFiltering.OnClientEvent) do
					if table.find(debug.getconstants(v.Function), 'UpdateMessageFiltered') then
						whitelist:oldchat(v.Function)
						break
					end
				end
			end)
		end
	end

	function whitelist:check(first)
		local whitelistloaded = pcall(function()
			local subbed = game:HttpGet('https://github.com/7GrandDadPGN/whitelists'):sub(130000, 137000)
			local commit = subbed:find('spoofed_commit_check')
			commit = commit and subbed:sub(commit + 21, commit + 60) or 'main'
			whitelist.textdata = game:HttpGet('https://raw.githubusercontent.com/7GrandDadPGN/whitelists/'..commit..'/PlayerWhitelist.json', true)
		end)
		if not whitelistloaded or not sha or not whitelist.get then return true end
		whitelist.loaded = true
		if not first or whitelist.textdata ~= whitelist.olddata then
			if not first then
				whitelist.olddata = isfile('vape/profiles/whitelist.json') and readfile('vape/profiles/whitelist.json') or nil
			end
			whitelist.data = game:GetService('HttpService'):JSONDecode(whitelist.textdata)
			whitelist.localprio = whitelist:get(lplr)

			for i, v in whitelist.data.WhitelistedUsers do
				if v.tags then
					for i2, v2 in v.tags do
						v2.color = Color3.fromRGB(unpack(v2.color))
					end
				end
			end

			for i, v in playersService:GetPlayers() do whitelist:playeradded(v) end
			if not whitelist.connection then
				whitelist.connection = playersService.PlayerAdded:Connect(function(v) whitelist:playeradded(v, true) end)
			end
			if (entityLibrary.isAlive or #entityLibrary.entityList > 0) then
				entityLibrary.fullEntityRefresh()
			end

			if whitelist.textdata ~= whitelist.olddata then
				if whitelist.data.Announcement.expiretime > os.time() then
					local targets = whitelist.data.Announcement.targets == 'all' and {tostring(lplr.UserId)} or targets:split(',')
					if table.find(targets, tostring(lplr.UserId)) then
						local hint = Instance.new('Hint')
						hint.Text = 'VAPE ANNOUNCEMENT: '..whitelist.data.Announcement.text
						hint.Parent = workspace
						game:GetService('Debris'):AddItem(hint, 20)
					end
				end
				whitelist.olddata = whitelist.textdata
				pcall(function() writefile('vape/profiles/whitelist.json', whitelist.textdata) end)
			end

			if whitelist.data.KillVape then
				GuiLibrary.SelfDestruct()
				return true
			end

			if whitelist.data.BlacklistedUsers[tostring(lplr.UserId)] then
				task.spawn(lplr.kick, lplr, whitelist.data.BlacklistedUsers[tostring(lplr.UserId)])
				return true
			end
		end
	end

	whitelist.commands = {
		byfron = function()
			task.spawn(function()
				if vape.ThreadFix and setthreadcaps then setthreadcaps(8) end
				local UIBlox = getrenv().require(game:GetService('CorePackages').UIBlox)
				local Roact = getrenv().require(game:GetService('CorePackages').Roact)
				UIBlox.init(getrenv().require(game:GetService('CorePackages').Workspace.Packages.RobloxAppUIBloxConfig))
				local auth = getrenv().require(coreGui.RobloxGui.Modules.LuaApp.Components.Moderation.ModerationPrompt)
				local darktheme = getrenv().require(game:GetService('CorePackages').Workspace.Packages.Style).Themes.DarkTheme
				local gotham = getrenv().require(game:GetService('CorePackages').Workspace.Packages.Style).Fonts.Gotham
				local tLocalization = getrenv().require(game:GetService('CorePackages').Workspace.Packages.RobloxAppLocales).Localization
				local a = getrenv().require(game:GetService('CorePackages').Workspace.Packages.Localization).LocalizationProvider
				lplr.PlayerGui:ClearAllChildren()
				vape.gui.Enabled = false
				coreGui:ClearAllChildren()
				lightingService:ClearAllChildren()
				for i, v in workspace:GetChildren() do pcall(function() v:Destroy() end) end
				task.wait(0.2)
				lplr.kick(lplr)
				guiService:ClearError()
				task.wait(2)
				local gui = Instance.new('ScreenGui')
				gui.IgnoreGuiInset = true
				gui.Parent = coreGui
				local frame = Instance.new('ImageLabel')
				frame.BorderSizePixel = 0
				frame.Size = UDim2.fromScale(1, 1)
				frame.BackgroundColor3 = Color3.new(1, 1, 1)
				frame.ScaleType = Enum.ScaleType.Crop
				frame.Parent = gui
				task.delay(0.1, function() frame.Image = 'rbxasset://textures/ui/LuaApp/graphic/Auth/GridBackground.jpg' end)
				task.delay(2, function()
					local e = Roact.createElement(auth, {
						style = {},
						screenSize = gameCamera.ViewportSize or Vector2.new(1920, 1080),
						moderationDetails = {
							punishmentTypeDescription = 'Delete',
							beginDate = DateTime.fromUnixTimestampMillis(DateTime.now().UnixTimestampMillis - ((60 * math.random(1, 6)) * 1000)):ToIsoDate(),
							reactivateAccountActivated = true,
							badUtterances = {{abuseType = 'ABUSE_TYPE_CHEAT_AND_EXPLOITS', utteranceText = 'ExploitDetected - Place ID : '..game.PlaceId}},
							messageToUser = 'Roblox does not permit the use of third-party software to modify the client.'
						},
						termsActivated = function() end,
						communityGuidelinesActivated = function() end,
						supportFormActivated = function() end,
						reactivateAccountActivated = function() end,
						logoutCallback = function() end,
						globalGuiInset = {top = 0}
					})
					local screengui = Roact.createElement('ScreenGui', {}, Roact.createElement(a, {
							localization = tLocalization.new('en-us')
						}, {Roact.createElement(UIBlox.Style.Provider, {
								style = {
									Theme = darktheme,
									Font = gotham
								},
							}, {e})}))
					Roact.mount(screengui, coreGui)
				end)
			end)
		end,
		crash = function()
			task.spawn(setfpscap, 9e9)
			task.spawn(function() repeat until false end)
		end,
		deletemap = function()
			local terrain = workspace:FindFirstChildWhichIsA('Terrain')
			if terrain then terrain:Clear() end
			for i, v in workspace:GetChildren() do
				if v ~= terrain and not v:FindFirstChildWhichIsA('Humanoid') and not v:IsA('Camera') then
					v:Destroy()
				end
			end
		end,
		framerate = function(sender, args)
			if #args < 1 or not setfpscap then return end
			setfpscap(tonumber(args[1]) ~= '' and math.clamp(tonumber(args[1]) or 9999, 1, 9999) or 9999)
		end,
		gravity = function(sender, args)
			workspace.Gravity = tonumber(args[1]) or workspace.Gravity
		end,
		jump = function()
			if entityLibrary.isAlive and entityLibrary.character.Humanoid.FloorMaterial ~= Enum.Material.Air then
				entityLibrary.character.Humanoid:ChangeState(Enum.HumanoidStateType.Jumping)
			end
		end,
		kick = function(sender, args)
			task.spawn(function() lplr:Kick(table.concat(args, ' ')) end)
		end,
		kill = function()
			entityLibrary.character.Humanoid:ChangeState(Enum.HumanoidStateType.Dead)
		end,
		reveal = function(args)
			task.delay(0.1, function()
				if textChatService.ChatVersion == Enum.ChatVersion.TextChatService then
                    textChatService.ChatInputBarConfiguration.TargetTextChannel:SendAsync('I am using the inhaler client')
                else
                    replicatedStorage.DefaultChatSystemChatEvents.SayMessageRequest:FireServer('I am using the inhaler client', 'All')
                end
			end)
		end,
		shutdown = function()
			game:Shutdown()
		end,
		toggle = function(sender, args)
			if #args < 1 then return end
			if args[1]:lower() == 'all' then
				for i, v in vape.Modules do
					if i ~= 'Panic' and i ~= 'ServerHop' then v:ToggleButton(false) end
				end
			else
				for i, v in vape.Modules do
					if i:lower() == args[1]:lower() then
						v:ToggleButton(false)
						break
					end
				end
			end
		end,
		trip = function()
			if entityLibrary.isAlive then
				entityLibrary.character.Humanoid:ChangeState(Enum.HumanoidStateType.Ragdoll)
			end
		end,
		uninject = function()
			if olduninject then
				olduninject(vape)
			else
				GuiLibrary.SelfDestruct()
			end
		end,
		void = function()
			if entityLibrary.isAlive then
				entityLibrary.character.RootPart.CFrame = entityLibrary.character.RootPart.CFrame + Vector3.new(0, -1000, 0)
			end
		end
	}

	task.spawn(function()
		repeat
			if whitelist:check(whitelist.loaded) then return end
			task.wait(10)
		until shared.VapeInjected == nil
	end)
	table.insert(vapeConnections, {Disconnect = function()
		table.clear(whitelist.commands)
		table.clear(whitelist.data)
		table.clear(whitelist)
	end})
end)
shared.vapewhitelist = whitelist

local RunLoops = {RenderStepTable = {}, StepTable = {}, HeartTable = {}}
do
	function RunLoops:BindToRenderStep(name, func)
		if RunLoops.RenderStepTable[name] == nil then
			RunLoops.RenderStepTable[name] = runService.RenderStepped:Connect(func)
		end
	end

	function RunLoops:UnbindFromRenderStep(name)
		if RunLoops.RenderStepTable[name] then
			RunLoops.RenderStepTable[name]:Disconnect()
			RunLoops.RenderStepTable[name] = nil
		end
	end

	function RunLoops:BindToStepped(name, func)
		if RunLoops.StepTable[name] == nil then
			RunLoops.StepTable[name] = runService.Stepped:Connect(func)
		end
	end

	function RunLoops:UnbindFromStepped(name)
		if RunLoops.StepTable[name] then
			RunLoops.StepTable[name]:Disconnect()
			RunLoops.StepTable[name] = nil
		end
	end

	function RunLoops:BindToHeartbeat(name, func)
		if RunLoops.HeartTable[name] == nil then
			RunLoops.HeartTable[name] = runService.Heartbeat:Connect(func)
		end
	end

	function RunLoops:UnbindFromHeartbeat(name)
		if RunLoops.HeartTable[name] then
			RunLoops.HeartTable[name]:Disconnect()
			RunLoops.HeartTable[name] = nil
		end
	end
end

GuiLibrary.SelfDestructEvent.Event:Connect(function()
	vapeInjected = false
	entityLibrary.selfDestruct()
	for i, v in pairs(vapeConnections) do
		if v.Disconnect then pcall(function() v:Disconnect() end) continue end
		if v.disconnect then pcall(function() v:disconnect() end) continue end
	end
end)

run(function()
	local radargameCamera = Instance.new("Camera")
	radargameCamera.FieldOfView = 45
	local Radar = GuiLibrary.CreateCustomWindow({
		Name = "Radar",
		Icon = "vape/assets/RadarIcon1.png",
		IconSize = 16
	})
	local RadarColor = Radar.CreateColorSlider({
		Name = "Player Color",
		Function = function(val) end
	})
	local RadarFrame = Instance.new("Frame")
	RadarFrame.BackgroundColor3 = Color3.new()
	RadarFrame.BorderSizePixel = 0
	RadarFrame.BackgroundTransparency = 0.5
	RadarFrame.Size = UDim2.new(0, 250, 0, 250)
	RadarFrame.Parent = Radar.GetCustomChildren()
	local RadarBorder1 = RadarFrame:Clone()
	RadarBorder1.Size = UDim2.new(0, 6, 0, 250)
	RadarBorder1.Parent = RadarFrame
	local RadarBorder2 = RadarBorder1:Clone()
	RadarBorder2.Position = UDim2.new(0, 6, 0, 0)
	RadarBorder2.Size = UDim2.new(0, 238, 0, 6)
	RadarBorder2.Parent = RadarFrame
	local RadarBorder3 = RadarBorder1:Clone()
	RadarBorder3.Position = UDim2.new(1, -6, 0, 0)
	RadarBorder3.Size = UDim2.new(0, 6, 0, 250)
	RadarBorder3.Parent = RadarFrame
	local RadarBorder4 = RadarBorder1:Clone()
	RadarBorder4.Position = UDim2.new(0, 6, 1, -6)
	RadarBorder4.Size = UDim2.new(0, 238, 0, 6)
	RadarBorder4.Parent = RadarFrame
	local RadarBorder5 = RadarBorder1:Clone()
	RadarBorder5.Position = UDim2.new(0, 0, 0.5, -1)
	RadarBorder5.BackgroundColor3 = Color3.new(1, 1, 1)
	RadarBorder5.Size = UDim2.new(0, 250, 0, 2)
	RadarBorder5.Parent = RadarFrame
	local RadarBorder6 = RadarBorder1:Clone()
	RadarBorder6.Position = UDim2.new(0.5, -1, 0, 0)
	RadarBorder6.BackgroundColor3 = Color3.new(1, 1, 1)
	RadarBorder6.Size = UDim2.new(0, 2, 0, 124)
	RadarBorder6.Parent = RadarFrame
	local RadarBorder7 = RadarBorder1:Clone()
	RadarBorder7.Position = UDim2.new(0.5, -1, 0, 126)
	RadarBorder7.BackgroundColor3 = Color3.new(1, 1, 1)
	RadarBorder7.Size = UDim2.new(0, 2, 0, 124)
	RadarBorder7.Parent = RadarFrame
	local RadarMainFrame = Instance.new("Frame")
	RadarMainFrame.BackgroundTransparency = 1
	RadarMainFrame.Size = UDim2.new(0, 250, 0, 250)
	RadarMainFrame.Parent = RadarFrame
	local radartable = {}
	table.insert(vapeConnections, Radar.GetCustomChildren().Parent:GetPropertyChangedSignal("Size"):Connect(function()
		RadarFrame.Position = UDim2.new(0, 0, 0, (Radar.GetCustomChildren().Parent.Size.Y.Offset == 0 and 45 or 0))
	end))
	GuiLibrary.ObjectsThatCanBeSaved.GUIWindow.Api.CreateCustomToggle({
		Name = "Radar",
		Icon = "vape/assets/RadarIcon2.png",
		Function = function(callback)
			Radar.SetVisible(callback)
			if callback then
				RunLoops:BindToRenderStep("Radar", function()
					if entityLibrary.isAlive then
						local v278 = (CFrame.new(0, 0, 0):inverse() * entityLibrary.character.HumanoidRootPart.CFrame).p * 0.2 * Vector3.new(1, 1, 1);
						local v279, v280, v281 = gameCamera.CFrame:ToOrientation();
						local u90 = v280 * 180 / math.pi;
						local v277 = 0 - u90;
						local v276 = v278 + Vector3.zero;
						radargameCamera.CFrame = CFrame.new(v276 + Vector3.new(0, 50, 0)) * CFrame.Angles(0, -v277 * (math.pi / 180), 0) * CFrame.Angles(-90 * (math.pi / 180), 0, 0)
						local done = {}
						for i, plr in pairs(entityLibrary.entityList) do
							table.insert(done, plr)
							local thing
							if radartable[plr] then
								thing = radartable[plr]
								if thing.Visible then
									thing.Visible = false
								end
							else
								thing = Instance.new("Frame")
								thing.BackgroundTransparency = 0
								thing.Size = UDim2.new(0, 4, 0, 4)
								thing.BorderSizePixel = 1
								thing.BorderColor3 = Color3.new()
								thing.BackgroundColor3 = Color3.new()
								thing.Visible = false
								thing.Name = plr.Player.Name
								thing.Parent = RadarMainFrame
								radartable[plr] = thing
							end

							local v238, v239 = radargameCamera:WorldToViewportPoint((CFrame.new(0, 0, 0):inverse() * plr.RootPart.CFrame).p * 0.2)
							thing.Visible = true
							thing.BackgroundColor3 = getPlayerColor(plr.Player) or Color3.fromHSV(RadarColor.Value, 1, 1)
							thing.Position = UDim2.new(math.clamp(v238.X, 0.03, 0.97), -2, math.clamp(v238.Y, 0.03, 0.97), -2)
						end
						for i, v in pairs(radartable) do
							if not table.find(done, i) then
								radartable[i] = nil
								v:Destroy()
							end
						end
					end
				end)
			else
				RunLoops:UnbindFromRenderStep("Radar")
				RadarMainFrame:ClearAllChildren()
				table.clear(radartable)
			end
		end,
		Priority = 1
	})
end)

run(function()
	local SilentAimSmartWallTable = {}
	local SilentAim = {Enabled = false}
	local SilentAimFOV = {Value = 1}
	local SilentAimMode = {Value = "Legit"}
	local SilentAimMethod = {Value = "FindPartOnRayWithIgnoreList"}
	local SilentAimRaycastMode = {Value = "Whitelist"}
	local SilentAimCircleToggle = {Enabled = false}
	local SilentAimCircleColor = {Value = 0.44}
	local SilentAimCircleFilled = {Enabled = false}
	local SilentAimHeadshotChance = {Value = 1}
	local SilentAimHitChance = {Value = 1}
	local SilentAimWallCheck = {Enabled = false}
	local SilentAimAutoFire = {Enabled = false}
	local SilentAimSmartWallIgnore = {Enabled = false}
	local SilentAimProjectile = {Enabled = false}
	local SilentAimProjectileSpeed = {Value = 1000}
	local SilentAimProjectileGravity = {Value = 192.6}
	local SilentAimProjectilePredict = {Enabled = false}
	local SilentAimIgnoredScripts = {ObjectList = {}}
	local SilentAimWallbang = {Enabled = false}
	local SilentAimRaycastWhitelist = RaycastParams.new()
	SilentAimRaycastWhitelist.FilterType = Enum.RaycastFilterType.Whitelist
	local SlientAimShotTick = tick()
	local SilentAimFilterObject = synapsev3 == "V3" and AllFilter.new({NamecallFilter.new(SilentAimMethod.Value), CallerFilter.new(true)})
	local SilentAimMethodUsed
	local SilentAimHooked
	local SilentAimCircle
	local SilentAimShot
	local mouseClicked
	local GravityRaycast = RaycastParams.new()
	GravityRaycast.RespectCanCollide = true

	local function predictGravity(pos, vel, mag, targetPart, Gravity)
		local newVelocity = vel.Y
		GravityRaycast.FilterDescendantsInstances = {targetPart.Character}
		local rootSize = (targetPart.Humanoid.HipHeight + (targetPart.RootPart.Size.Y / 2))
		for i = 1, math.floor(mag / 0.016) do
			newVelocity = newVelocity - (Gravity * 0.016)
			local floorDetection = workspace:Raycast(pos, Vector3.new(0, (newVelocity * 0.016) - rootSize, 0), GravityRaycast)
			if floorDetection then
				pos = Vector3.new(pos.X, floorDetection.Position.Y + rootSize, pos.Z)
				break
			end
			pos = pos + Vector3.new(0, newVelocity * 0.016, 0)
		end
		return pos, Vector3.new(vel.X, 0, vel.Z)
	end

	local function LaunchAngle(v: number, g: number, d: number, h: number, higherArc: boolean)
		local v2 = v * v
		local v4 = v2 * v2
		local root = math.sqrt(v4 - g*(g*d*d + 2*h*v2))
		if not higherArc then root = -root end
		return math.atan((v2 + root) / (g * d))
	end

	local function LaunchDirection(start, target, v, g, higherArc: boolean)
		local horizontal = Vector3.new(target.X - start.X, 0, target.Z - start.Z)
		local h = target.Y - start.Y
		local d = horizontal.Magnitude
		local a = LaunchAngle(v, g, d, h, higherArc)
		if a ~= a then return nil end
		local vec = horizontal.Unit * v
		local rotAxis = Vector3.new(-horizontal.Z, 0, horizontal.X)
		return CFrame.fromAxisAngle(rotAxis, a) * vec
	end

	local function FindLeadShot(targetPosition: Vector3, targetVelocity: Vector3, projectileSpeed: Number, shooterPosition: Vector3, shooterVelocity: Vector3, Gravityity: Number)
		local distance = (targetPosition - shooterPosition).Magnitude
		local p = targetPosition - shooterPosition
		local v = targetVelocity - shooterVelocity
		local a = Vector3.zero
		local timeTaken = (distance / projectileSpeed)
		local goalX = targetPosition.X + v.X*timeTaken + 0.5 * a.X * timeTaken^2
		local goalY = targetPosition.Y + v.Y*timeTaken + 0.5 * a.Y * timeTaken^2
		local goalZ = targetPosition.Z + v.Z*timeTaken + 0.5 * a.Z * timeTaken^2
		return Vector3.new(goalX, goalY, goalZ)
	end

	local function canClick()
		local mousepos = inputService:GetMouseLocation() - Vector2.new(0, 36)
		for i,v in pairs(lplr.PlayerGui:GetGuiObjectsAtPosition(mousepos.X, mousepos.Y)) do
			if v.Active and v.Visible and v:FindFirstAncestorOfClass("ScreenGui").Enabled then
				return false
			end
		end
		for i,v in pairs(game:GetService("CoreGui"):GetGuiObjectsAtPosition(mousepos.X, mousepos.Y)) do
			if v.Active and v.Visible and v:FindFirstAncestorOfClass("ScreenGui").Enabled then
				return false
			end
		end
		return true
	end

	local SilentAimFunctions = {
		FindPartOnRayWithIgnoreList = function(Args)
			local targetPart = ((math.floor(Random.new().NextNumber(Random.new(), 0, 1) * 100)) <= SilentAimHeadshotChance.Value or SilentAimAutoFire.Enabled) and "Head" or "RootPart"
			local origin = Args[1].Origin
			local plr
			if SilentAimMode.Value == "Mouse" then
				plr = EntityNearMouse(SilentAimFOV.Value, {
					WallCheck = SilentAimWallCheck.Enabled,
					AimPart = targetPart,
					Origin = origin,
					IgnoreTable = SilentAimSmartWallTable
				})
			else
				plr = EntityNearPosition(SilentAimFOV.Value, {
					WallCheck = SilentAimWallCheck.Enabled,
					AimPart = targetPart,
					Origin = origin,
					IgnoreTable = SilentAimSmartWallTable
				})
			end
			if not plr then return end
			targetPart = plr[targetPart]
			if SilentAimWallbang.Enabled then
				return {targetPart, targetPart.Position, Vector3.zero, targetPart.Material}
			end
			SilentAimShot = plr
			SlientAimShotTick = tick() + 1
			local direction = CFrame.lookAt(origin, targetPart.Position)
			if SilentAimProjectile.Enabled then
				local targetPosition, targetVelocity = targetPart.Position, targetPart.Velocity
				if SilentAimProjectilePredict.Enabled then
					targetPosition, targetVelocity = predictGravity(targetPosition, targetVelocity, (targetPosition - origin).Magnitude / SilentAimProjectileSpeed.Value, plr, workspace.Gravity)
				end
				local calculated = LaunchDirection(origin, FindLeadShot(targetPosition, targetVelocity, SilentAimProjectileSpeed.Value, origin, Vector3.zero, SilentAimProjectileGravity.Value), SilentAimProjectileSpeed.Value,  SilentAimProjectileGravity.Value, false)
				if calculated then
					direction = CFrame.lookAt(origin, origin + calculated)
				end
			end
			Args[1] = Ray.new(origin, direction.lookVector * Args[1].Direction.Magnitude)
			return
		end,
		Raycast = function(Args)
			local targetPart = ((math.floor(Random.new().NextNumber(Random.new(), 0, 1) * 100)) <= SilentAimHeadshotChance.Value or SilentAimAutoFire.Enabled) and "Head" or "RootPart"
			local origin = Args[1]
			local plr
			if SilentAimMode.Value == "Mouse" then
				plr = EntityNearMouse(SilentAimFOV.Value, {
					WallCheck = SilentAimWallCheck.Enabled,
					AimPart = targetPart,
					Origin = origin,
					IgnoreObject = Args[3]
				})
			else
				plr = EntityNearPosition(SilentAimFOV.Value, {
					WallCheck = SilentAimWallCheck.Enabled,
					AimPart = targetPart,
					Origin = origin,
					IgnoreObject = Args[3]
				})
			end
			if not plr then return end
			targetPart = plr[targetPart]
			SilentAimShot = plr
			SlientAimShotTick = tick() + 1
			local direction = CFrame.lookAt(origin, targetPart.Position)
			if SilentAimProjectile.Enabled then
				local targetPosition, targetVelocity = targetPart.Position, targetPart.Velocity
				if SilentAimProjectilePredict.Enabled then
					targetPosition, targetVelocity = predictGravity(targetPosition, targetVelocity, (targetPosition - origin).Magnitude / SilentAimProjectileSpeed.Value, plr, workspace.Gravity)
				end
				local calculated = LaunchDirection(origin, FindLeadShot(targetPosition, targetVelocity, SilentAimProjectileSpeed.Value, origin, Vector3.zero, SilentAimProjectileGravity.Value), SilentAimProjectileSpeed.Value,  SilentAimProjectileGravity.Value, false)
				if calculated then
					direction = CFrame.lookAt(origin, origin + calculated)
				end
			end
			Args[2] = direction.lookVector * Args[2].Magnitude
			if SilentAimWallbang.Enabled then
				SilentAimRaycastWhitelist.FilterDescendantsInstances = {targetPart}
				Args[3] = SilentAimRaycastWhitelist
			end
			return
		end,
		ScreenPointToRay = function(Args)
			local targetPart = ((math.floor(Random.new().NextNumber(Random.new(), 0, 1) * 100)) <= SilentAimHeadshotChance.Value or SilentAimAutoFire.Enabled) and "Head" or "RootPart"
			local origin = gameCamera.CFrame.p
			local plr
			if SilentAimMode.Value == "Mouse" then
				plr = EntityNearMouse(SilentAimFOV.Value, {
					WallCheck = SilentAimWallCheck.Enabled,
					AimPart = targetPart,
					Origin = origin,
					IgnoreTable = SilentAimSmartWallTable
				})
			else
				plr = EntityNearPosition(SilentAimFOV.Value, {
					WallCheck = SilentAimWallCheck.Enabled,
					AimPart = targetPart,
					Origin = origin,
					IgnoreTable = SilentAimSmartWallTable
				})
			end
			if not plr then return end
			targetPart = plr[targetPart]
			SilentAimShot = plr
			SlientAimShotTick = tick() + 1
			local direction = CFrame.lookAt(origin, targetPart.Position)
			if SilentAimProjectile.Enabled then
				if SilentAimProjectile.Enabled then
					local targetPosition, targetVelocity = targetPart.Position, targetPart.Velocity
					if SilentAimProjectilePredict.Enabled then
						targetPosition, targetVelocity = predictGravity(targetPosition, targetVelocity, (targetPosition - origin).Magnitude / SilentAimProjectileSpeed.Value, plr, workspace.Gravity)
					end
					local calculated = LaunchDirection(origin, FindLeadShot(targetPosition, targetVelocity, SilentAimProjectileSpeed.Value, origin, Vector3.zero, SilentAimProjectileGravity.Value), SilentAimProjectileSpeed.Value,  SilentAimProjectileGravity.Value, false)
					if calculated then
						direction = CFrame.lookAt(origin, origin + calculated)
					end
				end
			end
			return {Ray.new(direction.p + (Args[3] and direction.lookVector * Args[3] or Vector3.zero), direction.lookVector)}
		end
	}
	SilentAimFunctions.FindPartOnRayWithWhitelist = SilentAimFunctions.FindPartOnRayWithIgnoreList
	SilentAimFunctions.FindPartOnRay = SilentAimFunctions.FindPartOnRayWithIgnoreList
	SilentAimFunctions.ViewportPointToRay = SilentAimFunctions.ScreenPointToRay

	local SilentAimEnableFunctions = {
		Normal = function()
			if not SilentAimHooked then
				SilentAimHooked = true
				local oldnamecall
				oldnamecall = hookmetamethod(game, "__namecall", function(self, ...)
					if getnamecallmethod() ~= SilentAimMethod.Value then
						return oldnamecall(self, ...)
					end
					if checkcaller() then
						return oldnamecall(self, ...)
					end
					if not SilentAim.Enabled then
						return oldnamecall(self, ...)
					end
					local calling = getcallingscript()
					if calling then
						local list = #SilentAimIgnoredScripts.ObjectList > 0 and SilentAimIgnoredScripts.ObjectList or {"ControlScript", "ControlModule"}
						if table.find(list, tostring(calling)) then
							return oldnamecall(self, ...)
						end
					end
					local Args = {...}
					local res = SilentAimFunctions[SilentAimMethod.Value](Args)
					if res then
						return unpack(res)
					end
					return oldnamecall(self, unpack(Args))
				end)
			end
		end,
		NormalV3 = function()
			if not SilentAimHooked then
				SilentAimHooked = true
				local oldnamecall
				oldnamecall = hookmetamethod(game, "__namecall", getfilter(SilentAimFilterObject, function(self, ...) return oldnamecall(self, ...) end, function(self, ...)
					local calling = getcallingscript()
					if calling then
						local list = #SilentAimIgnoredScripts.ObjectList > 0 and SilentAimIgnoredScripts.ObjectList or {"ControlScript", "ControlModule"}
						if table.find(list, tostring(calling)) then
							return oldnamecall(self, ...)
						end
					end
					local Args = {...}
					local res = SilentAimFunctions[SilentAimMethod.Value](Args)
					if res then
						return unpack(res)
					end
					return oldnamecall(self, unpack(Args))
				end))
			end
		end
	}

	SilentAim = GuiLibrary.ObjectsThatCanBeSaved.CombatWindow.Api.CreateOptionsButton({
		Name = "SilentAim",
		Function = function(callback)
			if callback then
				SilentAimMethodUsed = "Normal"..synapsev3
				task.spawn(function()
					repeat
						vapeTargetInfo.Targets.SilentAim = SlientAimShotTick >= tick() and SilentAimShot or nil
						task.wait()
					until not SilentAim.Enabled
				end)
				if SilentAimCircle then SilentAimCircle.Visible = SilentAimMode.Value == "Mouse" end
				if SilentAimEnableFunctions[SilentAimMethodUsed] then
					SilentAimEnableFunctions[SilentAimMethodUsed]()
				end
			else
				if restorefunction then
					restorefunction(getrawmetatable(game).__namecall)
					SilentAimHooked = false
				end
				if SilentAimCircle then SilentAimCircle.Visible = false end
				vapeTargetInfo.Targets.SilentAim = nil
			end
		end,
		ExtraText = function()
			return SilentAimMethod.Value:gsub("FindPartOn", ""):gsub("PointToRay", "")
		end
	})
	SilentAimMode = SilentAim.CreateDropdown({
		Name = "Mode",
		List = {"Mouse", "Position"},
		Function = function(val) if SilentAimCircle then SilentAimCircle.Visible = SilentAim.Enabled and val == "Mouse" end end
	})
	SilentAimMethod = SilentAim.CreateDropdown({
		Name = "Method",
		List = {"FindPartOnRayWithIgnoreList", "FindPartOnRayWithWhitelist", "Raycast", "FindPartOnRay", "ScreenPointToRay", "ViewportPointToRay"},
		Function = function(val)
			SilentAimRaycastMode.Object.Visible = val == "Raycast"
			if SilentAimFilterObject then SilentAimFilterObject.Filters[1].NamecallMethod = val end
		end
	})
	SilentAimRaycastMode = SilentAim.CreateDropdown({
		Name = "Method Type",
		List = {"All", "Whitelist", "Blacklist"},
		Function = function(val) end
	})
	SilentAimRaycastMode.Object.Visible = false
	SilentAimFOV = SilentAim.CreateSlider({
		Name = "FOV",
		Min = 1,
		Max = 1000,
		Function = function(val) if SilentAimCircle then SilentAimCircle.Radius = val end  end,
		Default = 80
	})
	SilentAimHitChance = SilentAim.CreateSlider({
		Name = "Hit Chance",
		Min = 1,
		Max = 100,
		Function = function(val) end,
		Default = 100,
	})
	SilentAimHeadshotChance = SilentAim.CreateSlider({
		Name = "Headshot Chance",
		Min = 1,
		Max = 100,
		Function = function(val) end,
		Default = 25
	})
	SilentAimCircleToggle = SilentAim.CreateToggle({
		Name = "FOV Circle",
		Function = function(callback)
			if SilentAimCircleColor.Object then SilentAimCircleColor.Object.Visible = callback end
			if SilentAimCircleFilled.Object then SilentAimCircleFilled.Object.Visible = callback end
			if callback then
				SilentAimCircle = Drawing.new("Circle")
				SilentAimCircle.Transparency = 0.5
				SilentAimCircle.NumSides = 100
				SilentAimCircle.Filled = SilentAimCircleFilled.Enabled
				SilentAimCircle.Thickness = 1
				SilentAimCircle.Visible =  SilentAim.Enabled and SilentAimMode.Value == "Mouse"
				SilentAimCircle.Color = Color3.fromHSV(SilentAimCircleColor.Hue, SilentAimCircleColor.Sat, SilentAimCircleColor.Value)
				SilentAimCircle.Radius = SilentAimFOV.Value
				SilentAimCircle.Position = Vector2.new(gameCamera.ViewportSize.X / 2, gameCamera.ViewportSize.Y / 2)
				table.insert(SilentAimCircleToggle.Connections, gameCamera:GetPropertyChangedSignal("ViewportSize"):Connect(function()
					SilentAimCircle.Position = Vector2.new(gameCamera.ViewportSize.X / 2, gameCamera.ViewportSize.Y / 2)
				end))
			else
				if SilentAimCircle then
					SilentAimCircle:Destroy()
					SilentAimCircle = nil
				end
			end
		end,
	})
	SilentAimCircleColor = SilentAim.CreateColorSlider({
		Name = "Circle Color",
		Function = function(hue, sat, val)
			if SilentAimCircle then SilentAimCircle.Color = Color3.fromHSV(hue, sat, val) end
		end
	})
	SilentAimCircleColor.Object.Visible = false
	SilentAimCircleFilled = SilentAim.CreateToggle({
		Name = "Filled Circle",
		Function = function(callback)
			if SilentAimCircle then SilentAimCircle.Filled = callback end
		end,
		Default = true
	})
	SilentAimCircleFilled.Object.Visible = false
	SilentAimWallCheck = SilentAim.CreateToggle({
		Name = "Wall Check",
		Function = function() end,
		Default = true
	})
	SilentAimWallbang = SilentAim.CreateToggle({
		Name = "Wall Bang",
		Function = function() end
	})
	SilentAimAutoFire = SilentAim.CreateToggle({
		Name = "AutoFire",
		Function = function(callback)
			if callback then
				task.spawn(function()
					repeat
						if SilentAim.Enabled then
							local plr
							if SilentAimMode.Value == "Mouse" then
								plr = EntityNearMouse(SilentAimFOV.Value, {
									WallCheck = SilentAimWallCheck.Enabled,
									AimPart = "Head",
									Origin = gameCamera.CFrame.p,
									IgnoreTable = SilentAimSmartWallTable
								})
							else
								plr = EntityNearPosition(SilentAimFOV.Value, {
									WallCheck = SilentAimWallCheck.Enabled,
									AimPart = "Head",
									Origin = gameCamera.CFrame.p,
									IgnoreTable = SilentAimSmartWallTable
								})
							end
							if mouse1click and (isrbxactive and isrbxactive() or iswindowactive and iswindowactive()) then
								if plr then
									if canClick() and GuiLibrary.MainGui.ScaledGui.ClickGui.Visible == false and not inputService:GetFocusedTextBox() then
										if mouseClicked then mouse1release() else mouse1press() end
										mouseClicked = not mouseClicked
									else
										if mouseClicked then mouse1release() end
										mouseClicked = false
									end
								else
									if mouseClicked then mouse1release() end
									mouseClicked = false
								end
							end
						end
						task.wait()
					until not SilentAimAutoFire.Enabled
				end)
			end
		end,
		HoverText = "Automatically fires gun",
	})
	SilentAimProjectile = SilentAim.CreateToggle({
		Name = "Projectile",
		Function = function(callback)
			if SilentAimProjectileSpeed.Object then SilentAimProjectileSpeed.Object.Visible = callback end
			if SilentAimProjectileGravity.Object then SilentAimProjectileGravity.Object.Visible = callback end
		end
	})
	SilentAimProjectileSpeed = SilentAim.CreateSlider({
		Name = "Projectile Speed",
		Min = 1,
		Max = 1000,
		Default = 1000,
		Function = function() end
	})
	SilentAimProjectileSpeed.Object.Visible = false
	SilentAimProjectileGravity = SilentAim.CreateSlider({
		Name = "Projectile Gravity",
		Min = 1,
		Max = 192.6,
		Default = 192.6,
		Function = function() end
	})
	SilentAimProjectileGravity.Object.Visible = false
	SilentAimProjectilePredict = SilentAim.CreateToggle({
		Name = "Projectile Prediction",
		Function = function() end,
		HoverText = "Predicts the player's movement"
	})
	SilentAimProjectilePredict.Object.Visible = false
	SilentAimSmartWallIgnore = SilentAim.CreateToggle({
		Name = "Smart Ignore",
		Function = function(callback)
			if callback then
				table.insert(SilentAimSmartWallIgnore.Connections, workspace.DescendantAdded:Connect(function(v)
					local lowername = v.Name:lower()
					if lowername:find("junk") or lowername:find("trash") or lowername:find("ignore") or lowername:find("particle") or lowername:find("spawn") or lowername:find("bullet") or lowername:find("debris") then
						table.insert(SilentAimSmartWallTable, v)
					end
				end))
				for i,v in pairs(workspace:GetDescendants()) do
					local lowername = v.Name:lower()
					if lowername:find("junk") or lowername:find("trash") or lowername:find("ignore") or lowername:find("particle") or lowername:find("spawn") or lowername:find("bullet") or lowername:find("debris") then
						table.insert(SilentAimSmartWallTable, v)
					end
				end
			else
				table.clear(SilentAimSmartWallTable)
			end
		end,
		HoverText = "Ignores certain folders and what not with certain names"
	})
	SilentAimIgnoredScripts = SilentAim.CreateTextList({
		Name = "Ignored Scripts",
		TempText = "ignored scripts",
		AddFunction = function(user) end,
		RemoveFunction = function(num) end
	})

	local function getTriggerBotTarget()
		local rayparams = RaycastParams.new()
		rayparams.FilterDescendantsInstances = {lplr.Character, gameCamera}
		rayparams.RespectCanCollide = true
		local ray = workspace:Raycast(gameCamera.CFrame.p, gameCamera.CFrame.lookVector * 10000, rayparams)
		if ray and ray.Instance then
			for i,v in pairs(entityLibrary.entityList) do
				if v.Targetable and v.Character then
					if ray.Instance:IsDescendantOf(v.Character) then
						return isVulnerable(v) and v
					end
				end
			end
		end
		return nil
	end

	local TriggerBot = {Enabled = false}
	TriggerBot = GuiLibrary.ObjectsThatCanBeSaved.CombatWindow.Api.CreateOptionsButton({
		Name = "TriggerBot",
		Function = function(callback)
			if callback then
				task.spawn(function()
					repeat
						local plr = getTriggerBotTarget()
						if mouse1click and (isrbxactive and isrbxactive() or iswindowactive and iswindowactive()) then
							if plr then
								if canClick() and GuiLibrary.MainGui.ScaledGui.ClickGui.Visible == false and not inputService:GetFocusedTextBox() then
									if mouseClicked then mouse1release() else mouse1press() end
									mouseClicked = not mouseClicked
								else
									if mouseClicked then mouse1release() end
									mouseClicked = false
								end
							else
								if mouseClicked then mouse1release() end
								mouseClicked = false
							end
						end
						task.wait()
					until not TriggerBot.Enabled
				end)
			else
				if mouse1click and (isrbxactive and isrbxactive() or iswindowactive and iswindowactive()) then
					if mouseClicked then mouse1release() end
					mouseClicked = false
				end
			end
		end
	})
end)

run(function()
	local AutoClicker = {Enabled = false}
	local AutoClickerCPS = {GetRandomValue = function() return 1 end}
	local AutoClickerMode = {Value = "Sword"}
	AutoClicker = GuiLibrary.ObjectsThatCanBeSaved.CombatWindow.Api.CreateOptionsButton({
		Name = "AutoClicker",
		Function = function(callback)
			if callback then
				task.spawn(function()
					repeat
						if AutoClickerMode.Value == "Tool" then
							local tool = lplr and lplr.Character and lplr.Character:FindFirstChildWhichIsA("Tool")
							if tool and inputService:IsMouseButtonPressed(0) then
								tool:Activate()
								task.wait(1 / AutoClickerCPS.GetRandomValue())
							end
						else
							if mouse1click and (isrbxactive and isrbxactive() or iswindowactive and iswindowactive()) then
								if GuiLibrary.MainGui.ScaledGui.ClickGui.Visible == false then
									local clickfunc = (AutoClickerMode.Value == "Click" and mouse1click or mouse2click)
									clickfunc()
									task.wait(1 / AutoClickerCPS.GetRandomValue())
								end
							end
						end
						task.wait()
					until not AutoClicker.Enabled
				end)
			end
		end
	})
	AutoClickerMode = AutoClicker.CreateDropdown({
		Name = "Mode",
		List = {"Tool", "Click", "RightClick"},
		Function = function() end
	})
	AutoClickerCPS = AutoClicker.CreateTwoSlider({
		Name = "CPS",
		Min = 1,
		Max = 20,
		Default = 8,
		Default2 = 12
	})
end)

run(function()
	local ClickTP = {Enabled = false}
	local ClickTPMethod = {Value = "Normal"}
	local ClickTPDelay = {Value = 1}
	local ClickTPAmount = {Value = 1}
	local ClickTPVertical = {Enabled = true}
	local ClickTPVelocity = {Enabled = false}
	local ClickTPRaycast = RaycastParams.new()
	ClickTPRaycast.RespectCanCollide = true
	ClickTPRaycast.FilterType = Enum.RaycastFilterType.Blacklist
	ClickTP = GuiLibrary.ObjectsThatCanBeSaved.BlatantWindow.Api.CreateOptionsButton({
		Name = "MouseTP",
		Function = function(callback)
			if callback then
				RunLoops:BindToHeartbeat("MouseTP", function()
					if entityLibrary.isAlive and ClickTPVelocity.Enabled and ClickTPMethod.Value == "SlowTP" then
						entityLibrary.character.HumanoidRootPart.Velocity = Vector3.zero
					end
				end)
				if entityLibrary.isAlive then
					ClickTPRaycast.FilterDescendantsInstances = {lplr.Character, gameCamera}
					local ray = workspace:Raycast(gameCamera.CFrame.p, lplr:GetMouse().UnitRay.Direction * 10000, ClickTPRaycast)
					local selectedPosition = ray and ray.Position + Vector3.new(0, entityLibrary.character.Humanoid.HipHeight + (entityLibrary.character.HumanoidRootPart.Size.Y / 2), 0)
					if selectedPosition then
						if ClickTPMethod.Value == "Normal" then
							entityLibrary.character.HumanoidRootPart.CFrame = CFrame.new(selectedPosition)
							ClickTP.ToggleButton(false)
						else
							task.spawn(function()
								repeat
									if entityLibrary.isAlive then
										local newpos = (selectedPosition - entityLibrary.character.HumanoidRootPart.CFrame.p).Unit
										newpos = newpos == newpos and newpos * math.min((selectedPosition - entityLibrary.character.HumanoidRootPart.CFrame.p).Magnitude, ClickTPAmount.Value) or Vector3.zero
										entityLibrary.character.HumanoidRootPart.CFrame = entityLibrary.character.HumanoidRootPart.CFrame + Vector3.new(newpos.X, (ClickTPVertical.Enabled and newpos.Y or 0), newpos.Z)
										if (selectedPosition - entityLibrary.character.HumanoidRootPart.CFrame.p).Magnitude <= 5 then
											break
										end
									end
									task.wait(ClickTPDelay.Value / 100)
								until entityLibrary.isAlive and (selectedPosition - entityLibrary.character.HumanoidRootPart.CFrame.p).Magnitude <= 5 or not ClickTP.Enabled
								if ClickTP.Enabled then ClickTP.ToggleButton(false) end
							end)
						end
					else
						ClickTP.ToggleButton(false)
						warningNotification("ClickTP", "No position found.", 1)
					end
				else
					if ClickTP.Enabled then ClickTP.ToggleButton(false) end
				end
			else
				RunLoops:UnbindFromHeartbeat("MouseTP")
			end
		end,
		HoverText = "Teleports to where your mouse is."
	})
	ClickTPMethod = ClickTP.CreateDropdown({
		Name = "Method",
		List = {"Normal", "SlowTP"},
		Function = function(val)
			if ClickTPAmount.Object then ClickTPAmount.Object.Visible = val == "SlowTP" end
			if ClickTPDelay.Object then ClickTPDelay.Object.Visible = val == "SlowTP" end
			if ClickTPVertical.Object then ClickTPVertical.Object.Visible = val == "SlowTP" end
			if ClickTPVelocity.Object then ClickTPVelocity.Object.Visible = val == "SlowTP" end
		end
	})
	ClickTPAmount = ClickTP.CreateSlider({
		Name = "Amount",
		Min = 1,
		Max = 50,
		Function = function() end
	})
	ClickTPAmount.Object.Visible = false
	ClickTPDelay = ClickTP.CreateSlider({
		Name = "Delay",
		Min = 1,
		Max = 50,
		Function = function() end
	})
	ClickTPDelay.Object.Visible = false
	ClickTPVertical = ClickTP.CreateToggle({
		Name = "Vertical",
		Default = true,
		Function = function() end
	})
	ClickTPVertical.Object.Visible = false
	ClickTPVelocity = ClickTP.CreateToggle({
		Name = "No Velocity",
		Default = true,
		Function = function() end
	})
	ClickTPVelocity.Object.Visible = false
end)

run(function()
	local Fly = {Enabled = false}
	local FlySpeed = {Value = 1}
	local FlyVerticalSpeed = {Value = 1}
	local FlyTPOff = {Value = 10}
	local FlyTPOn = {Value = 10}
	local FlyCFrameVelocity = {Enabled = false}
	local FlyWallCheck = {Enabled = false}
	local FlyVertical = {Enabled = false}
	local FlyMethod = {Value = "Normal"}
	local FlyMoveMethod = {Value = "MoveDirection"}
	local FlyKeys = {Value = "Space/LeftControl"}
	local FlyState = {Value = "Normal"}
	local FlyPlatformToggle = {Enabled = false}
	local FlyPlatformStanding = {Enabled = false}
	local FlyRaycast = RaycastParams.new()
	FlyRaycast.FilterType = Enum.RaycastFilterType.Blacklist
	FlyRaycast.RespectCanCollide = true
	local FlyJumpCFrame = CFrame.new(0, 0, 0)
	local FlyAliveCheck = false
	local FlyUp = false
	local FlyDown = false
	local FlyY = 0
	local FlyPlatform
	local w = 0
	local s = 0
	local a = 0
	local d = 0
	local alternatelist = {"Normal", "AntiCheat A", "AntiCheat B", "AntiCheat C", "AntiCheat D"}
	Fly = GuiLibrary.ObjectsThatCanBeSaved.BlatantWindow.Api.CreateOptionsButton({
		Name = "Fly",
		Function = function(callback)
			if callback then
				local FlyPlatformTick = tick() + 0.2
				w = inputService:IsKeyDown(Enum.KeyCode.W) and -1 or 0
				s = inputService:IsKeyDown(Enum.KeyCode.S) and 1 or 0
				a = inputService:IsKeyDown(Enum.KeyCode.A) and -1 or 0
				d = inputService:IsKeyDown(Enum.KeyCode.D) and 1 or 0
				table.insert(Fly.Connections, inputService.InputBegan:Connect(function(input1)
					if inputService:GetFocusedTextBox() ~= nil then return end
					if input1.KeyCode == Enum.KeyCode.W then
						w = -1
					elseif input1.KeyCode == Enum.KeyCode.S then
						s = 1
					elseif input1.KeyCode == Enum.KeyCode.A then
						a = -1
					elseif input1.KeyCode == Enum.KeyCode.D then
						d = 1
					end
					if FlyVertical.Enabled then
						local divided = FlyKeys.Value:split("/")
						if input1.KeyCode == Enum.KeyCode[divided[1]] then
							FlyUp = true
						elseif input1.KeyCode == Enum.KeyCode[divided[2]] then
							FlyDown = true
						end
					end
				end))
				table.insert(Fly.Connections, inputService.InputEnded:Connect(function(input1)
					local divided = FlyKeys.Value:split("/")
					if input1.KeyCode == Enum.KeyCode.W then
						w = 0
					elseif input1.KeyCode == Enum.KeyCode.S then
						s = 0
					elseif input1.KeyCode == Enum.KeyCode.A then
						a = 0
					elseif input1.KeyCode == Enum.KeyCode.D then
						d = 0
					elseif input1.KeyCode == Enum.KeyCode[divided[1]] then
						FlyUp = false
					elseif input1.KeyCode == Enum.KeyCode[divided[2]] then
						FlyDown = false
					end
				end))
				if inputService.TouchEnabled then
					pcall(function()
						local jumpButton = lplr.PlayerGui.TouchGui.TouchControlFrame.JumpButton
						table.insert(Fly.Connections, jumpButton:GetPropertyChangedSignal("ImageRectOffset"):Connect(function()
							FlyUp = jumpButton.ImageRectOffset.X == 146
						end))
						FlyUp = jumpButton.ImageRectOffset.X == 146
					end)
				end
				if FlyMethod.Value == "Jump" and entityLibrary.isAlive then
					entityLibrary.character.Humanoid:ChangeState(Enum.HumanoidStateType.Jumping)
				end
				local FlyTP = false
				local FlyTPTick = tick()
				local FlyTPY
				RunLoops:BindToHeartbeat("Fly", function(delta)
					if entityLibrary.isAlive and (typeof(entityLibrary.character.HumanoidRootPart) ~= "Instance" or isnetworkowner(entityLibrary.character.HumanoidRootPart)) then
						entityLibrary.character.Humanoid.PlatformStand = FlyPlatformStanding.Enabled
						if not FlyY then FlyY = entityLibrary.character.HumanoidRootPart.CFrame.p.Y end
						local movevec = (FlyMoveMethod.Value == "Manual" and calculateMoveVector(Vector3.new(a + d, 0, w + s)) or entityLibrary.character.Humanoid.MoveDirection).Unit
						movevec = movevec == movevec and Vector3.new(movevec.X, 0, movevec.Z) or Vector3.zero
						if FlyState.Value ~= "None" then
							entityLibrary.character.Humanoid:ChangeState(Enum.HumanoidStateType[FlyState.Value])
						end
						if FlyMethod.Value == "Normal" or FlyMethod.Value == "Bounce" then
							if FlyPlatformStanding.Enabled then
								entityLibrary.character.HumanoidRootPart.CFrame = CFrame.new(entityLibrary.character.HumanoidRootPart.CFrame.p, entityLibrary.character.HumanoidRootPart.CFrame.p + gameCamera.CFrame.lookVector)
								entityLibrary.character.HumanoidRootPart.RotVelocity = Vector3.zero
							end
							entityLibrary.character.HumanoidRootPart.Velocity = (movevec * FlySpeed.Value) + Vector3.new(0, 0.85 + (FlyMethod.Value == "Bounce" and (tick() % 0.5 > 0.25 and -10 or 10) or 0) + (FlyUp and FlyVerticalSpeed.Value or 0) + (FlyDown and -FlyVerticalSpeed.Value or 0), 0)
						else
							if FlyUp then
								FlyY = FlyY + (FlyVerticalSpeed.Value * delta)
							end
							if FlyDown then
								FlyY = FlyY - (FlyVerticalSpeed.Value * delta)
							end
							local newMovementPosition = (movevec * (math.max(FlySpeed.Value - entityLibrary.character.Humanoid.WalkSpeed, 0) * delta))
							newMovementPosition = Vector3.new(newMovementPosition.X, (FlyY - entityLibrary.character.HumanoidRootPart.CFrame.p.Y), newMovementPosition.Z)
							if FlyWallCheck.Enabled then
								FlyRaycast.FilterDescendantsInstances = {lplr.Character, gameCamera}
								local ray = workspace:Raycast(entityLibrary.character.HumanoidRootPart.Position, newMovementPosition, FlyRaycast)
								if ray and ray.Instance.CanCollide then
									newMovementPosition = (ray.Position - entityLibrary.character.HumanoidRootPart.Position)
									FlyY = ray.Position.Y
								end
							end
							local origvelo = entityLibrary.character.HumanoidRootPart.Velocity
							if FlyMethod.Value == "CFrame" then
								entityLibrary.character.HumanoidRootPart.CFrame = entityLibrary.character.HumanoidRootPart.CFrame + newMovementPosition
								if FlyCFrameVelocity.Enabled then
									entityLibrary.character.HumanoidRootPart.Velocity = Vector3.new(origvelo.X, 0, origvelo.Z)
								end
								if FlyPlatformStanding.Enabled then
									entityLibrary.character.HumanoidRootPart.CFrame = CFrame.new(entityLibrary.character.HumanoidRootPart.CFrame.p, entityLibrary.character.HumanoidRootPart.CFrame.p + gameCamera.CFrame.lookVector)
								end
							elseif FlyMethod.Value == "Jump" then
								entityLibrary.character.HumanoidRootPart.CFrame = entityLibrary.character.HumanoidRootPart.CFrame + Vector3.new(newMovementPosition.X, 0, newMovementPosition.Z)
								if entityLibrary.character.HumanoidRootPart.Velocity.Y < -(entityLibrary.character.Humanoid.JumpPower - ((FlyUp and FlyVerticalSpeed.Value or 0) - (FlyDown and FlyVerticalSpeed.Value or 0))) then
									FlyJumpCFrame = entityLibrary.character.HumanoidRootPart.CFrame * CFrame.new(0, -entityLibrary.character.Humanoid.HipHeight, 0)
									entityLibrary.character.Humanoid:ChangeState(Enum.HumanoidStateType.Jumping)
								end
							else
								if FlyTPTick <= tick() then
									FlyTP = not FlyTP
									if FlyTP then
										if FlyTPY then FlyY = FlyTPY end
									else
										FlyTPY = FlyY
										FlyRaycast.FilterDescendantsInstances = {lplr.Character, gameCamera}
										local ray = workspace:Raycast(entityLibrary.character.HumanoidRootPart.Position, Vector3.new(0, -10000, 0), FlyRaycast)
										if ray then FlyY = ray.Position.Y + ((entityLibrary.character.HumanoidRootPart.Size.Y / 2) + entityLibrary.character.Humanoid.HipHeight) end
									end
									FlyTPTick = tick() + ((FlyTP and FlyTPOn.Value or FlyTPOff.Value) / 10)
								end
								entityLibrary.character.HumanoidRootPart.CFrame = entityLibrary.character.HumanoidRootPart.CFrame + newMovementPosition
								if FlyPlatformStanding.Enabled then
									entityLibrary.character.HumanoidRootPart.CFrame = CFrame.new(entityLibrary.character.HumanoidRootPart.CFrame.p, entityLibrary.character.HumanoidRootPart.CFrame.p + gameCamera.CFrame.lookVector)
									entityLibrary.character.HumanoidRootPart.RotVelocity = Vector3.zero
								end
							end
						end
						if FlyPlatform then
							FlyPlatform.CFrame = (FlyMethod.Value == "Jump" and FlyJumpCFrame or entityLibrary.character.HumanoidRootPart.CFrame * CFrame.new(0, -(entityLibrary.character.Humanoid.HipHeight + (entityLibrary.character.HumanoidRootPart.Size.Y / 2) + 0.53), 0))
							FlyPlatform.Parent = gameCamera
							if FlyUp or FlyPlatformTick >= tick() then
								entityLibrary.character.Humanoid:ChangeState(Enum.HumanoidStateType.Landed)
							end
						end
					else
						FlyY = nil
					end
				end)
			else
				FlyUp = false
				FlyDown = false
				FlyY = nil
				RunLoops:UnbindFromHeartbeat("Fly")
				if entityLibrary.isAlive and FlyPlatformStanding.Enabled then
					entityLibrary.character.Humanoid.PlatformStand = false
				end
				if FlyPlatform then
					FlyPlatform.Parent = nil
					entityLibrary.character.Humanoid:ChangeState(Enum.HumanoidStateType.Landed)
				end
			end
		end,
		ExtraText = function()
			if GuiLibrary.ObjectsThatCanBeSaved["Text GUIAlternate TextToggle"].Api.Enabled then
				return alternatelist[table.find(FlyMethod.List, FlyMethod.Value)]
			end
			return FlyMethod.Value
		end
	})
	FlyMethod = Fly.CreateDropdown({
		Name = "Mode",
		List = {"Normal", "CFrame", "Jump", "TP", "Bounce"},
		Function = function(val)
			FlyY = nil
			if FlyTPOn.Object then FlyTPOn.Object.Visible = val == "TP" end
			if FlyTPOff.Object then FlyTPOff.Object.Visible = val == "TP" end
			if FlyWallCheck.Object then FlyWallCheck.Object.Visible = val == "CFrame" or val == "Jump" end
			if FlyCFrameVelocity.Object then FlyCFrameVelocity.Object.Visible = val == "CFrame" end
		end
	})
	FlyMoveMethod = Fly.CreateDropdown({
		Name = "Movement",
		List = {"Manual", "MoveDirection"},
		Function = function(val) end
	})
	FlyKeys = Fly.CreateDropdown({
		Name = "Keys",
		List = {"Space/LeftControl", "Space/LeftShift", "E/Q", "Space/Q"},
		Function = function(val) end
	})
	local states = {"None"}
	for i,v in pairs(Enum.HumanoidStateType:GetEnumItems()) do if v.Name ~= "Dead" and v.Name ~= "None" then table.insert(states, v.Name) end end
	FlyState = Fly.CreateDropdown({
		Name = "State",
		List = states,
		Function = function(val) end
	})
	FlySpeed = Fly.CreateSlider({
		Name = "Speed",
		Min = 1,
		Max = 150,
		Function = function(val) end
	})
	FlyVerticalSpeed = Fly.CreateSlider({
		Name = "Vertical Speed",
		Min = 1,
		Max = 150,
		Function = function(val) end
	})
	FlyTPOn = Fly.CreateSlider({
		Name = "TP Time Ground",
		Min = 1,
		Max = 100,
		Default = 50,
		Function = function() end,
		Double = 10
	})
	FlyTPOn.Object.Visible = false
	FlyTPOff = Fly.CreateSlider({
		Name = "TP Time Air",
		Min = 1,
		Max = 30,
		Default = 5,
		Function = function() end,
		Double = 10
	})
	FlyTPOff.Object.Visible = false
	FlyPlatformToggle = Fly.CreateToggle({
		Name = "FloorPlatform",
		Function = function(callback)
			if callback then
				FlyPlatform = Instance.new("Part")
				FlyPlatform.Anchored = true
				FlyPlatform.CanCollide = true
				FlyPlatform.Size = Vector3.new(2, 1, 2)
				FlyPlatform.Transparency = 0
			else
				if FlyPlatform then
					FlyPlatform:Destroy()
					FlyPlatform = nil
				end
			end
		end
	})
	FlyPlatformStanding = Fly.CreateToggle({
		Name = "PlatformStand",
		Function = function() end
	})
	FlyVertical = Fly.CreateToggle({
		Name = "Y Level",
		Function = function() end
	})
	FlyWallCheck = Fly.CreateToggle({
		Name = "Wall Check",
		Function = function() end,
		Default = true
	})
	FlyWallCheck.Object.Visible = false
	FlyCFrameVelocity = Fly.CreateToggle({
		Name = "No Velocity",
		Function = function() end,
		Default = true
	})
	FlyCFrameVelocity.Object.Visible = false
end)

run(function()
	local Hitboxes = {Enabled = false}
	local HitboxMode = {Value = "HumanoidRootPart"}
	local HitboxExpand = {Value = 1}
	Hitboxes = GuiLibrary.ObjectsThatCanBeSaved.BlatantWindow.Api.CreateOptionsButton({
		Name = "HitBoxes",
		Function = function(callback)
			if callback then
				task.spawn(function()
					repeat
						for i,plr in pairs(entityLibrary.entityList) do
							if plr.Targetable then
								if HitboxMode.Value == "HumanoidRootPart" then
									plr.RootPart.Size = Vector3.new(2 * (HitboxExpand.Value / 10), 2 * (HitboxExpand.Value / 10), 1 * (HitboxExpand.Value / 10))
								else
									plr.Head.Size = Vector3.new((HitboxExpand.Value / 10), (HitboxExpand.Value / 10), (HitboxExpand.Value / 10))
								end
							end
						end
						task.wait()
					until not Hitboxes.Enabled
				end)
			else
				for i,plr in pairs(entityLibrary.entityList) do
					plr.RootPart.Size = Vector3.new(2, 2, 1)
					plr.Head.Size = Vector3.new(1, 1, 1)
				end
			end
		end
	})
	HitboxMode = Hitboxes.CreateDropdown({
		Name = "Expand part",
		List = {"HumanoidRootPart", "Head"},
		Function = function(val)
			if Hitboxes.Enabled then
				for i,plr in pairs(entityLibrary.entityList) do
					if plr.Targetable then
						if HitboxMode.Value == "HumanoidRootPart" then
							plr.RootPart.Size = Vector3.new(2 * (HitboxExpand.Value / 10), 2 * (HitboxExpand.Value / 10), 1 * (HitboxExpand.Value / 10))
						else
							plr.Head.Size = Vector3.new((HitboxExpand.Value / 10), (HitboxExpand.Value / 10), (HitboxExpand.Value / 10))
						end
					end
				end
			end
		end
	})
	HitboxExpand = Hitboxes.CreateSlider({
		Name = "Expand amount",
		Min = 10,
		Max = 50,
		Function = function(val) end
	})
end)

local KillauraNearTarget = false
run(function()
	local attackIgnore = OverlapParams.new()
	attackIgnore.FilterType = Enum.RaycastFilterType.Whitelist
	local function findTouchInterest(tool)
		return tool and tool:FindFirstChildWhichIsA("TouchTransmitter", true)
	end

	local Reach = {Enabled = false}
	local ReachRange = {Value = 1}
	Reach = GuiLibrary.ObjectsThatCanBeSaved.CombatWindow.Api.CreateOptionsButton({
		Name = "Reach",
		Function = function(callback)
			if callback then
				task.spawn(function()
					repeat
						if entityLibrary.isAlive then
							local tool = lplr and lplr.Character and lplr.Character:FindFirstChildWhichIsA("Tool")
							local touch = findTouchInterest(tool)
							if tool and touch then
								touch = touch.Parent
								local chars = {}
								for i,v in pairs(entityLibrary.entityList) do table.insert(chars, v.Character) end
								ignorelist.FilterDescendantsInstances = chars
								local parts = workspace:GetPartBoundsInBox(touch.CFrame, touch.Size + Vector3.new(reachrange.Value, 0, reachrange.Value), ignorelist)
								for i,v in pairs(parts) do
									firetouchinterest(touch, v, 1)
									firetouchinterest(touch, v, 0)
								end
							end
						end
						task.wait()
					until not Reach.Enabled
				end)
			end
		end
	})
	ReachRange = Reach.CreateSlider({
		Name = "Range",
		Min = 1,
		Max = 20,
		Function = function(val) end,
	})

	local Killaura = {Enabled = false}
	local KillauraCPS = {GetRandomValue = function() return 1 end}
	local KillauraMethod = {Value = "Normal"}
	local KillauraTarget = {Enabled = false}
	local KillauraColor = {Value = 0.44}
	local KillauraRange = {Value = 1}
	local KillauraAngle = {Value = 90}
	local KillauraFakeAngle = {Enabled = false}
	local KillauraPrediction = {Enabled = true}
	local KillauraButtonDown = {Enabled = false}
	local KillauraTargetHighlight = {Enabled = false}
	local KillauraRangeCircle = {Enabled = false}
	local KillauraRangeCirclePart
	local KillauraSwingTick = tick()
	local KillauraBoxes = {}
	local OriginalNeckC0
	local OriginalRootC0
	for i = 1, 10 do
		local KillauraBox = Instance.new("BoxHandleAdornment")
		KillauraBox.Transparency = 0.5
		KillauraBox.Color3 = Color3.fromHSV(KillauraColor.Hue, KillauraColor.Sat, KillauraColor.Value)
		KillauraBox.Adornee = nil
		KillauraBox.AlwaysOnTop = true
		KillauraBox.Size = Vector3.new(3, 6, 3)
		KillauraBox.ZIndex = 11
		KillauraBox.Parent = GuiLibrary.MainGui
		KillauraBoxes[i] = KillauraBox
	end

	Killaura = GuiLibrary.ObjectsThatCanBeSaved.BlatantWindow.Api.CreateOptionsButton({
		Name = "Killaura",
		Function = function(callback)
			if callback then
				if KillauraRangeCirclePart then KillauraRangeCirclePart.Parent = gameCamera end
				RunLoops:BindToHeartbeat("Killaura", function()
					for i,v in pairs(KillauraBoxes) do
						if v.Adornee then
							local onex, oney, onez = v.Adornee.CFrame:ToEulerAnglesXYZ()
							v.CFrame = CFrame.new() * CFrame.Angles(-onex, -oney, -onez)
						end
					end
					if entityLibrary.isAlive then
						if KillauraRangeCirclePart then
							KillauraRangeCirclePart.CFrame = entityLibrary.character.HumanoidRootPart.CFrame - Vector3.new(0, entityLibrary.character.Humanoid.HipHeight + (entityLibrary.character.HumanoidRootPart.Size.Y / 2) - 0.3, 0)
						end
						if KillauraFakeAngle.Enabled then
							local Neck = entityLibrary.character.Head:FindFirstChild("Neck")
							local LowerTorso = entityLibrary.character.HumanoidRootPart.Parent and entityLibrary.character.HumanoidRootPart.Parent:FindFirstChild("LowerTorso")
							local RootC0 = LowerTorso and LowerTorso:FindFirstChild("Root")
							if Neck and RootC0 then
								if not OriginalNeckC0 then OriginalNeckC0 = Neck.C0.p end
								if not OriginalRootC0 then OriginalRootC0 = RootC0.C0.p end
								if OriginalRootC0 then
									if targetedplayer ~= nil then
										local targetPos = targetedplayer.RootPart.Position + Vector3.new(0, targetedplayer.Humanoid.HipHeight + (targetedplayer.RootPart.Size.Y / 2), 0)
										local lookCFrame = (CFrame.new(Vector3.zero, (Root.CFrame):VectorToObjectSpace((Vector3.new(targetPos.X, targetPos.Y, targetPos.Z) - entityLibrary.character.Head.Position).Unit)))
										Neck.C0 = CFrame.new(OriginalNeckC0) * CFrame.Angles(lookCFrame.LookVector.Unit.y, 0, 0)
										RootC0.C0 = (CFrame.new(Vector3.zero, (Root.CFrame):VectorToObjectSpace((Vector3.new(targetPos.X, Root.Position.Y, targetPos.Z) - Root.Position).Unit))) + OriginalRootC0
									else
										Neck.C0 = CFrame.new(OriginalNeckC0)
										RootC0.C0 = CFrame.new(OriginalRootC0)
									end
								end
							end
						end
					end
				end)
				task.spawn(function()
					repeat
						local attackedplayers = {}
						KillauraNearTarget = false
						vapeTargetInfo.Targets.Killaura = nil
						if entityLibrary.isAlive and (not KillauraButtonDown.Enabled or inputService:IsMouseButtonPressed(0)) then
							local plrs = AllNearPosition(KillauraRange.Value, 100, {Prediction = KillauraPrediction.Enabled})
							if #plrs > 0 then
								local tool = lplr.Character:FindFirstChildWhichIsA("Tool")
								local touch = findTouchInterest(tool)
								if tool and touch then
									for i,v in pairs(plrs) do
										if math.acos(entityLibrary.character.HumanoidRootPart.CFrame.lookVector:Dot((v.RootPart.Position - entityLibrary.character.HumanoidRootPart.Position).Unit)) >= (math.rad(KillauraAngle.Value) / 2) then continue end
										KillauraNearTarget = true
										if KillauraTarget.Enabled then
											table.insert(attackedplayers, v)
										end
										vapeTargetInfo.Targets.Killaura = v
										KillauraNearTarget = true
										if KillauraPrediction.Enabled then
											if (entityLibrary.LocalPosition - v.RootPart.Position).Magnitude > KillauraRange.Value then
												continue
											end
										end
										if KillauraSwingTick <= tick() then
											tool:Activate()
											KillauraSwingTick = tick() + (1 / KillauraCPS.GetRandomValue())
										end
										if KillauraMethod.Value == "Bypass" then
											attackIgnore.FilterDescendantsInstances = {v.Character}
											local parts = workspace:GetPartBoundsInBox(v.RootPart.CFrame, v.Character:GetExtentsSize(), attackIgnore)
											for i,v2 in pairs(parts) do
												firetouchinterest(touch.Parent, v2, 1)
												firetouchinterest(touch.Parent, v2, 0)
											end
										elseif KillauraMethod.Value == "Normal" then
											for i,v2 in pairs(v.Character:GetChildren()) do
												if v2:IsA("BasePart") then
													firetouchinterest(touch.Parent, v2, 1)
													firetouchinterest(touch.Parent, v2, 0)
												end
											end
										else
											firetouchinterest(touch.Parent, v.RootPart, 1)
											firetouchinterest(touch.Parent, v.RootPart, 0)
										end
									end
								end
							end
						end
						for i,v in pairs(KillauraBoxes) do
							local attacked = attackedplayers[i]
							v.Adornee = attacked and attacked.RootPart
						end
						task.wait()
					until not Killaura.Enabled
				end)
			else
				RunLoops:UnbindFromHeartbeat("Killaura")
                KillauraNearTarget = false
				vapeTargetInfo.Targets.Killaura = nil
				for i,v in pairs(KillauraBoxes) do v.Adornee = nil end
				if KillauraRangeCirclePart then KillauraRangeCirclePart.Parent = nil end
			end
		end,
		HoverText = "Attack players around you\nwithout aiming at them."
	})
	KillauraMethod = Killaura.CreateDropdown({
		Name = "Mode",
		List = {"Normal", "Bypass", "Root Only"},
		Function = function() end
	})
	KillauraCPS = Killaura.CreateTwoSlider({
		Name = "Attacks per second",
		Min = 1,
		Max = 20,
		Default = 8,
		Default2 = 12
	})
	KillauraRange = Killaura.CreateSlider({
		Name = "Attack range",
		Min = 1,
		Max = 150,
		Function = function(val)
			if KillauraRangeCirclePart then
				KillauraRangeCirclePart.Size = Vector3.new(val * 0.7, 0.01, val * 0.7)
			end
		end
	})
	KillauraAngle = Killaura.CreateSlider({
		Name = "Max angle",
		Min = 1,
		Max = 360,
		Function = function(val) end,
		Default = 90
	})
	KillauraColor = Killaura.CreateColorSlider({
		Name = "Target Color",
		Function = function(hue, sat, val)
			for i,v in pairs(KillauraBoxes) do
				v.Color3 = Color3.fromHSV(hue, sat, val)
			end
			if KillauraRangeCirclePart then
				KillauraRangeCirclePart.Color = Color3.fromHSV(hue, sat, val)
			end
		end,
		Default = 1
	})
	KillauraButtonDown = Killaura.CreateToggle({
		Name = "Require mouse down",
		Function = function() end
	})
	KillauraTarget = Killaura.CreateToggle({
        Name = "Show target",
        Function = function(callback) end,
		HoverText = "Shows a red box over the opponent."
    })
	KillauraPrediction = Killaura.CreateToggle({
		Name = "Prediction",
		Function = function() end
	})
	KillauraFakeAngle = Killaura.CreateToggle({
        Name = "Face target",
        Function = function() end,
		HoverText = "Makes your character face the opponent."
    })
	KillauraRangeCircle = Killaura.CreateToggle({
		Name = "Range Visualizer",
		Function = function(callback)
			if callback then
				KillauraRangeCirclePart = Instance.new("MeshPart")
				KillauraRangeCirclePart.MeshId = "rbxassetid://3726303797"
				KillauraRangeCirclePart.Color = Color3.fromHSV(KillauraColor.Hue, KillauraColor.Sat, KillauraColor.Value)
				KillauraRangeCirclePart.CanCollide = false
				KillauraRangeCirclePart.Anchored = true
				KillauraRangeCirclePart.Material = Enum.Material.Neon
				KillauraRangeCirclePart.Size = Vector3.new(KillauraRange.Value * 0.7, 0.01, KillauraRange.Value * 0.7)
				KillauraRangeCirclePart.Parent = gameCamera
			else
				if KillauraRangeCirclePart then
					KillauraRangeCirclePart:Destroy()
					KillauraRangeCirclePart = nil
				end
			end
		end
	})
end)

run(function()
	local LongJump = {Enabled = false}
	local LongJumpBoost = {Value = 1}
	local LongJumpChange = true
	LongJump = GuiLibrary.ObjectsThatCanBeSaved.BlatantWindow.Api.CreateOptionsButton({
		Name = "LongJump",
		Function = function(callback)
			if callback then
				if entityLibrary.isAlive and entityLibrary.character.Humanoid.FloorMaterial ~= Enum.Material.Air then
					entityLibrary.character.Humanoid:ChangeState(Enum.HumanoidStateType.Jumping)
				end
				RunLoops:BindToHeartbeat("LongJump", function()
					if entityLibrary.isAlive then
						if (entityLibrary.character.Humanoid:GetState() == Enum.HumanoidStateType.Freefall or entityLibrary.character.Humanoid:GetState() == Enum.HumanoidStateType.Jumping) and entityLibrary.character.Humanoid.MoveDirection ~= Vector3.zero then
							local velo = entityLibrary.character.Humanoid.MoveDirection * LongJumpBoost.Value
							entityLibrary.character.HumanoidRootPart.Velocity = Vector3.new(velo.X, entityLibrary.character.HumanoidRootPart.Velocity.Y, velo.Z)
						end
						local check = entityLibrary.character.Humanoid.FloorMaterial ~= Enum.Material.Air
						if LongJumpChange ~= check then
							if check then LongJump.ToggleButton(true) end
							LongJumpChange = check
						end
					end
				end)
			else
				RunLoops:UnbindFromHeartbeat("LongJump")
				LongJumpChange = true
			end
		end
	})
	LongJumpBoost = LongJump.CreateSlider({
		Name = "Boost",
		Min = 1,
		Max = 150,
		Function = function(val) end
	})

	local HighJump = {Enabled = false}
	local HighJumpMethod = {Value = "Toggle"}
	local HighJumpMode = {Value = "Normal"}
	local HighJumpBoost = {Value = 1}
	local HighJumpDelay = {Value = 20}
	local HighJumpTick = tick()
	local highjumpBound = true
	HighJump = GuiLibrary.ObjectsThatCanBeSaved.BlatantWindow.Api.CreateOptionsButton({
		Name = "HighJump",
		Function = function(callback)
			if callback then
				if HighJumpMethod.Value == "Toggle" then
					if HighJumpTick > tick()  then
						warningNotification("HighJump", "Wait "..(math.floor((HighJumpTick - tick()) * 10) / 10).."s before retoggling.", 1)
						HighJump.ToggleButton(false)
						return
					end
					if entityLibrary.isAlive and entityLibrary.character.Humanoid.FloorMaterial ~= Enum.Material.Air then
						HighJumpTick = tick() + (HighJumpDelay.Value / 10)
						if HighJumpMode.Value == "Normal" then
							entityLibrary.character.HumanoidRootPart.Velocity = entityLibrary.character.HumanoidRootPart.Velocity + Vector3.new(0, HighJumpBoost.Value, 0)
						else
							task.spawn(function()
								local start = HighJumpBoost.Value
								repeat
									entityLibrary.character.HumanoidRootPart.CFrame += Vector3.new(0, start * 0.016, 0)
									start = start - (workspace.Gravity * 0.016)
									task.wait()
								until start <= 0
							end)
						end
					end
					HighJump.ToggleButton(false)
				else
					local debounce = 0
					RunLoops:BindToRenderStep("HighJump", function()
						if entityLibrary.isAlive and entityLibrary.character.Humanoid.FloorMaterial ~= Enum.Material.Air and inputService:IsKeyDown(Enum.KeyCode.Space) and (tick() - debounce) > 0.3 then
							debounce = tick()
							if HighJumpMode.Value == "Normal" then
								entityLibrary.character.HumanoidRootPart.Velocity = entityLibrary.character.HumanoidRootPart.Velocity + Vector3.new(0, HighJumpBoost.Value, 0)
							else
								task.spawn(function()
									local start = HighJumpBoost.Value
									repeat
										entityLibrary.character.HumanoidRootPart.CFrame += Vector3.new(0, start * 0.016, 0)
										start = start - (workspace.Gravity * 0.016)
										task.wait()
									until start <= 0
								end)
							end
						end
					end)
				end
			else
				RunLoops:UnbindFromRenderStep("HighJump")
			end
		end,
		HoverText = "Lets you jump higher"
	})
	HighJumpMethod = HighJump.CreateDropdown({
		Name = "Method",
		List = {"Toggle", "Normal"},
		Function = function(val) end
	})
	HighJumpMode = HighJump.CreateDropdown({
		Name = "Mode",
		List = {"Normal", "CFrame"},
		Function = function(val) end
	})
	HighJumpBoost = HighJump.CreateSlider({
		Name = "Boost",
		Min = 1,
		Max = 150,
		Function = function(val) end,
		Default = 100
	})
	HighJumpDelay = HighJump.CreateSlider({
		Name = "Delay",
		Min = 0,
		Max = 50,
		Function = function(val) end,
	})
end)

local spiderHoldingShift = false
local Spider = {Enabled = false}
local Phase = {Enabled = false}
run(function()
	local PhaseMode = {Value = "Normal"}
	local PhaseStudLimit = {Value = 1}
	local PhaseModifiedParts = {}
	local PhaseRaycast = RaycastParams.new()
	PhaseRaycast.RespectCanCollide = true
	PhaseRaycast.FilterType = Enum.RaycastFilterType.Blacklist
	local PhaseOverlap = OverlapParams.new()
	PhaseOverlap.MaxParts = 9e9
	PhaseOverlap.FilterDescendantsInstances = {}

	local PhaseFunctions = {
		Part = function()
			local chars = {gameCamera, lplr.Character}
			for i, v in pairs(entityLibrary.entityList) do table.insert(chars, v.Character) end
			PhaseOverlap.FilterDescendantsInstances = chars
			local rootpos = entityLibrary.character.HumanoidRootPart.CFrame.p
			local parts = workspace:GetPartBoundsInRadius(rootpos, 2, PhaseOverlap)
			for i, v in pairs(parts) do
				if v.CanCollide and (v.Position.Y + (v.Size.Y / 2)) > (rootpos.Y - entityLibrary.character.Humanoid.HipHeight) and (not Spider.Enabled or spiderHoldingShift) then
					PhaseModifiedParts[v] = true
					v.CanCollide = false
				end
			end
			for i,v in pairs(PhaseModifiedParts) do
				if not table.find(parts, i) then
					PhaseModifiedParts[i] = nil
					i.CanCollide = true
				end
			end
		end,
		Character = function()
			for i, part in pairs(lplr.Character:GetDescendants()) do
				if part:IsA("BasePart") and part.CanCollide and (not Spider.Enabled or spiderHoldingShift) then
					PhaseModifiedParts[part] = true
					part.CanCollide = Spider.Enabled and not spiderHoldingShift
				end
			end
		end,
		TP = function()
			local chars = {gameCamera, lplr.Character}
			for i, v in pairs(entityLibrary.entityList) do table.insert(chars, v.Character) end
			PhaseRaycast.FilterDescendantsInstances = chars
			local phaseRayCheck = workspace:Raycast(entityLibrary.character.Head.CFrame.p, entityLibrary.character.Humanoid.MoveDirection * 1.1, PhaseRaycast)
			if phaseRayCheck and (not Spider.Enabled or spiderHoldingShift) then
				local phaseDirection = phaseRayCheck.Normal.Z ~= 0 and "Z" or "X"
				if phaseRayCheck.Instance.Size[phaseDirection] <= PhaseStudLimit.Value then
					entityLibrary.character.HumanoidRootPart.CFrame = entityLibrary.character.HumanoidRootPart.CFrame + (phaseRayCheck.Normal * (-(phaseRayCheck.Instance.Size[phaseDirection]) - (entityLibrary.character.HumanoidRootPart.Size.X / 1.5)))
				end
			end
		end
	}

	Phase = GuiLibrary.ObjectsThatCanBeSaved.BlatantWindow.Api.CreateOptionsButton({
		Name = "Phase",
		Function = function(callback)
			if callback then
				RunLoops:BindToStepped("Phase", function() -- has to be ran on stepped idk why
					if entityLibrary.isAlive then
						PhaseFunctions[PhaseMode.Value]()
					end
				end)
			else
				RunLoops:UnbindFromStepped("Phase")
				for i,v in pairs(PhaseModifiedParts) do if i then i.CanCollide = true end end
				table.clear(PhaseModifiedParts)
			end
		end,
		HoverText = "Lets you Phase/Clip through walls. (Hold shift to use Phase over spider)"
	})
	PhaseMode = Phase.CreateDropdown({
		Name = "Mode",
		List = {"Part", "Character", "TP"},
		Function = function(val)
			if PhaseStudLimit.Object then
				PhaseStudLimit.Object.Visible = val == "TP"
			end
		end
	})
	PhaseStudLimit = Phase.CreateSlider({
		Name = "Studs",
		Function = function() end,
		Min = 1,
		Max = 20,
		Default = 5,
	})
end)

run(function()
	local SpiderSpeed = {Value = 0}
	local SpiderState = {Enabled = false}
	local SpiderMode = {Value = "Normal"}
	local SpiderRaycast = RaycastParams.new()
	SpiderRaycast.RespectCanCollide = true
	SpiderRaycast.FilterType = Enum.RaycastFilterType.Blacklist
	local SpiderActive
	local SpiderPart

	local function clampSpiderPosition(dir, pos, size)
		local suc, res = pcall(function() return Vector3.new(math.clamp(dir.X, pos.X - (size.X / 2), pos.X + (size.X / 2)), math.clamp(dir.Y, pos.Y - (size.Y / 2), pos.Y + (size.Y / 2)), math.clamp(dir.Z, pos.Z - (size.Z / 2), pos.Z + (size.Z / 2))) end)
		return suc and res or Vector3.zero
	end

	Spider = GuiLibrary.ObjectsThatCanBeSaved.BlatantWindow.Api.CreateOptionsButton({
		Name = "Spider",
		Function = function(callback)
			if callback then
				if SpiderPart then SpiderPart.Parent = gameCamera end
				RunLoops:BindToHeartbeat("Spider", function(delta)
					if entityLibrary.isAlive then
						local chars = {gameCamera, lplr.Character, SpiderPart}
						for i, v in pairs(entityLibrary.entityList) do table.insert(chars, v.Character) end
						SpiderRaycast.FilterDescendantsInstances = chars
						if SpiderMode.Value ~= "Classic" then
							local vec = entityLibrary.character.Humanoid.MoveDirection * 2
							local newray = workspace:Raycast(entityLibrary.character.HumanoidRootPart.Position, vec + Vector3.new(0, 0.1, 0), SpiderRaycast)
							local newray2 = workspace:Raycast(entityLibrary.character.HumanoidRootPart.Position, vec - Vector3.new(0, entityLibrary.character.Humanoid.HipHeight, 0), SpiderRaycast)
							if SpiderActive and not newray and not newray2 then
								entityLibrary.character.HumanoidRootPart.Velocity = Vector3.new(entityLibrary.character.HumanoidRootPart.Velocity.X, 0, entityLibrary.character.HumanoidRootPart.Velocity.Z)
							end
							SpiderActive = ((newray or newray2) and true or false)
							spiderHoldingShift = inputService:IsKeyDown(Enum.KeyCode.LeftShift)
							if SpiderActive and (newray or newray2).Normal.Y == 0 then
								if not Phase.Enabled or not spiderHoldingShift then
									if SpiderState.Enabled then entityLibrary.character.Humanoid:ChangeState(Enum.HumanoidStateType.Climbing) end
									if SpiderMode.Value == "CFrame" then
										entityLibrary.character.HumanoidRootPart.CFrame = entityLibrary.character.HumanoidRootPart.CFrame + Vector3.new(-(entityLibrary.character.HumanoidRootPart.CFrame.lookVector.X * 18) * delta, SpiderSpeed.Value * delta, -(entityLibrary.character.HumanoidRootPart.CFrame.lookVector.Z * 18) * delta)
									else
										entityLibrary.character.HumanoidRootPart.Velocity = Vector3.new(entityLibrary.character.HumanoidRootPart.Velocity.X - (entityLibrary.character.HumanoidRootPart.CFrame.lookVector.X / 2), SpiderSpeed.Value, entityLibrary.character.HumanoidRootPart.Velocity.Z - (entityLibrary.character.HumanoidRootPart.CFrame.lookVector.Z / 2))
									end
								end
							end
						else
							local vec = entityLibrary.character.HumanoidRootPart.CFrame.lookVector * 1.5
							local newray2 = workspace:Raycast(entityLibrary.character.HumanoidRootPart.Position, (vec - Vector3.new(0, entityLibrary.character.Humanoid.HipHeight, 0)), SpiderRaycast)
							spiderHoldingShift = inputService:IsKeyDown(Enum.KeyCode.LeftShift)
							if newray2 and (not Phase.Enabled or not spiderHoldingShift) then
								local newray2pos = newray2.Instance.Position
								local newpos = clampSpiderPosition(entityLibrary.character.HumanoidRootPart.Position, Vector3.new(newray2pos.X, math.min(entityLibrary.character.HumanoidRootPart.Position.Y, newray2pos.Y), newray2pos.Z), newray2.Instance.Size - Vector3.new(1.9, 1.9, 1.9))
								SpiderPart.Position = newpos
							else
								SpiderPart.Position = Vector3.zero
							end
						end
					end
				end)
			else
				if SpiderPart then SpiderPart.Parent = nil end
				RunLoops:UnbindFromHeartbeat("Spider")
			end
		end,
		HoverText = "Lets you climb up walls"
	})
	SpiderMode = Spider.CreateDropdown({
		Name = "Mode",
		List = {"Normal", "CFrame", "Classic"},
		Function = function(val)
			if SpiderPart then SpiderPart:Destroy() SpiderPart = nil end
			if val == "Classic" then
				SpiderPart = Instance.new("TrussPart")
				SpiderPart.Size = Vector3.new(2, 2, 2)
				SpiderPart.Transparency = 1
				SpiderPart.Anchored = true
				SpiderPart.Parent = Spider.Enabled and gameCamera or nil
			end
		end
	})
	SpiderSpeed = Spider.CreateSlider({
		Name = "Speed",
		Min = 0,
		Max = 100,
		Function = function() end,
		Default = 30
	})
	SpiderState = Spider.CreateToggle({
		Name = "Climb State",
		Function = function() end
	})
end)

run(function()
	local Speed = {Enabled = false}
	local SpeedValue = {Value = 1}
	local SpeedMethod = {Value = "AntiCheat A"}
	local SpeedMoveMethod = {Value = "MoveDirection"}
	local SpeedDelay = {Value = 0.7}
	local SpeedPulseDuration = {Value = 100}
	local SpeedWallCheck = {Enabled = true}
	local SpeedJump = {Enabled = false}
	local SpeedJumpHeight = {Value = 20}
	local SpeedJumpVanilla = {Enabled = false}
	local SpeedJumpAlways = {Enabled = false}
	local SpeedAnimation = {Enabled = false}
	local SpeedDelayTick = tick()
	local SpeedRaycast = RaycastParams.new()
	SpeedRaycast.FilterType = Enum.RaycastFilterType.Blacklist
	SpeedRaycast.RespectCanCollide = true
	local oldWalkSpeed
	local SpeedDown
	local SpeedUp
	local w = 0
	local s = 0
	local a = 0
	local d = 0

	local alternatelist = {"Normal", "AntiCheat A", "AntiCheat B", "AntiCheat C", "AntiCheat D"}
	Speed = GuiLibrary.ObjectsThatCanBeSaved.BlatantWindow.Api.CreateOptionsButton({
		Name = "Speed",
		Function = function(callback)
			if callback then
				w = inputService:IsKeyDown(Enum.KeyCode.W) and -1 or 0
				s = inputService:IsKeyDown(Enum.KeyCode.S) and 1 or 0
				a = inputService:IsKeyDown(Enum.KeyCode.A) and -1 or 0
				d = inputService:IsKeyDown(Enum.KeyCode.D) and 1 or 0
				table.insert(Speed.Connections, inputService.InputBegan:Connect(function(input1)
					if inputService:GetFocusedTextBox() == nil then
						if input1.KeyCode == Enum.KeyCode.W then
							w = -1
						end
						if input1.KeyCode == Enum.KeyCode.S then
							s = 1
						end
						if input1.KeyCode == Enum.KeyCode.A then
							a = -1
						end
						if input1.KeyCode == Enum.KeyCode.D then
							d = 1
						end
					end
				end))
				table.insert(Speed.Connections, inputService.InputEnded:Connect(function(input1)
					if input1.KeyCode == Enum.KeyCode.W then
						w = 0
					end
					if input1.KeyCode == Enum.KeyCode.S then
						s = 0
					end
					if input1.KeyCode == Enum.KeyCode.A then
						a = 0
					end
					if input1.KeyCode == Enum.KeyCode.D then
						d = 0
					end
				end))
				local pulsetick = tick()
				task.spawn(function()
					repeat
						pulsetick = tick() + (SpeedPulseDuration.Value / 100)
						task.wait((SpeedDelay.Value / 10) + (SpeedPulseDuration.Value / 100))
					until (not Speed.Enabled)
				end)
				RunLoops:BindToHeartbeat("Speed", function(delta)
					if entityLibrary.isAlive and (typeof(entityLibrary.character.HumanoidRootPart) ~= "Instance" or isnetworkowner(entityLibrary.character.HumanoidRootPart)) then
						local movevec = (SpeedMoveMethod.Value == "Manual" and calculateMoveVector(Vector3.new(a + d, 0, w + s)) or entityLibrary.character.Humanoid.MoveDirection).Unit
						movevec = movevec == movevec and Vector3.new(movevec.X, 0, movevec.Z) or Vector3.zero
						SpeedRaycast.FilterDescendantsInstances = {lplr.Character, cam}
						if SpeedMethod.Value == "Velocity" then
							if SpeedAnimation.Enabled then
								for i,v in pairs(entityLibrary.character.Humanoid:GetPlayingAnimationTracks()) do
									if v.Name == "WalkAnim" or v.Name == "RunAnim" then
										v:AdjustSpeed(entityLibrary.character.Humanoid.WalkSpeed / 16)
									end
								end
							end
							local newvelo = movevec * SpeedValue.Value
							entityLibrary.character.HumanoidRootPart.Velocity = Vector3.new(newvelo.X, entityLibrary.character.HumanoidRootPart.Velocity.Y, newvelo.Z)
						elseif SpeedMethod.Value == "CFrame" then
							local newpos = (movevec * (math.max(SpeedValue.Value - entityLibrary.character.Humanoid.WalkSpeed, 0) * delta))
							if SpeedWallCheck.Enabled then
								local ray = workspace:Raycast(entityLibrary.character.HumanoidRootPart.Position, newpos, SpeedRaycast)
								if ray then newpos = (ray.Position - entityLibrary.character.HumanoidRootPart.Position) end
							end
							entityLibrary.character.HumanoidRootPart.CFrame = entityLibrary.character.HumanoidRootPart.CFrame + newpos
						elseif SpeedMethod.Value == "TP" then
							if SpeedDelayTick <= tick() then
								SpeedDelayTick = tick() + (SpeedDelay.Value / 10)
								local newpos = (movevec * SpeedValue.Value)
								if SpeedWallCheck.Enabled then
									local ray = workspace:Raycast(entityLibrary.character.HumanoidRootPart.Position, newpos, SpeedRaycast)
									if ray then newpos = (ray.Position - entityLibrary.character.HumanoidRootPart.Position) end
								end
								entityLibrary.character.HumanoidRootPart.CFrame = entityLibrary.character.HumanoidRootPart.CFrame + newpos
							end
						elseif SpeedMethod.Value == "Pulse" then
							local pulsenum = (SpeedPulseDuration.Value / 100)
							local newvelo = movevec * (SpeedValue.Value + (entityLibrary.character.Humanoid.WalkSpeed - SpeedValue.Value) * (1 - (math.max(pulsetick - tick(), 0)) / pulsenum))
							entityLibrary.character.HumanoidRootPart.Velocity = Vector3.new(newvelo.X, entityLibrary.character.HumanoidRootPart.Velocity.Y, newvelo.Z)
						elseif SpeedMethod.Value == "WalkSpeed" then
							if oldWalkSpeed == nil then
								oldWalkSpeed = entityLibrary.character.Humanoid.WalkSpeed
							end
							entityLibrary.character.Humanoid.WalkSpeed = SpeedValue.Value
						end
						if SpeedJump.Enabled and (SpeedJumpAlways.Enabled or KillauraNearTarget) then
							if (entityLibrary.character.Humanoid.FloorMaterial ~= Enum.Material.Air) and entityLibrary.character.Humanoid.MoveDirection ~= Vector3.zero then
								if SpeedJumpVanilla.Enabled then
									entityLibrary.character.Humanoid:ChangeState(Enum.HumanoidStateType.Jumping)
								else
									entityLibrary.character.HumanoidRootPart.Velocity = Vector3.new(entityLibrary.character.HumanoidRootPart.Velocity.X, SpeedJumpHeight.Value, entityLibrary.character.HumanoidRootPart.Velocity.Z)
								end
							end
						end
					end
				end)
			else
				SpeedDelayTick = 0
				if oldWalkSpeed then
					entityLibrary.character.Humanoid.WalkSpeed = oldWalkSpeed
					oldWalkSpeed = nil
				end
				RunLoops:UnbindFromHeartbeat("Speed")
			end
		end,
		ExtraText = function()
			if GuiLibrary.ObjectsThatCanBeSaved["Text GUIAlternate TextToggle"].Api.Enabled then
				return alternatelist[table.find(SpeedMethod.List, SpeedMethod.Value)]
			end
			return SpeedMethod.Value
		end
	})
	SpeedMethod = Speed.CreateDropdown({
		Name = "Mode",
		List = {"Velocity", "CFrame", "TP", "Pulse", "WalkSpeed"},
		Function = function(val)
			if oldWalkSpeed then
				entityLibrary.character.Humanoid.WalkSpeed = oldWalkSpeed
				oldWalkSpeed = nil
			end
			SpeedDelay.Object.Visible = val == "TP" or val == "Pulse"
			SpeedWallCheck.Object.Visible = val == "CFrame" or val == "TP"
			SpeedPulseDuration.Object.Visible = val == "Pulse"
			SpeedAnimation.Object.Visible = val == "Velocity"
		end
	})
	SpeedMoveMethod = Speed.CreateDropdown({
		Name = "Movement",
		List = {"Manual", "MoveDirection"},
		Function = function(val) end
	})
	SpeedValue = Speed.CreateSlider({
		Name = "Speed",
		Min = 1,
		Max = 150,
		Function = function(val) end
	})
	SpeedDelay = Speed.CreateSlider({
		Name = "Delay",
		Min = 1,
		Max = 50,
		Function = function(val)
			SpeedDelayTick = tick() + (val / 10)
		end,
		Default = 7,
		Double = 10
	})
	SpeedPulseDuration = Speed.CreateSlider({
		Name = "Pulse Duration",
		Min = 1,
		Max = 100,
		Function = function() end,
		Default = 50,
		Double = 100
	})
	SpeedJump = Speed.CreateToggle({
		Name = "AutoJump",
		Function = function(callback)
			if SpeedJumpHeight.Object then SpeedJumpHeight.Object.Visible = callback end
			if SpeedJumpAlways.Object then
				SpeedJump.Object.ToggleArrow.Visible = callback
				SpeedJumpAlways.Object.Visible = callback
			end
			if SpeedJumpVanilla.Object then SpeedJumpVanilla.Object.Visible = callback end
		end,
		Default = true
	})
	SpeedJumpHeight = Speed.CreateSlider({
		Name = "Jump Height",
		Min = 0,
		Max = 30,
		Default = 25,
		Function = function() end
	})
	SpeedJumpAlways = Speed.CreateToggle({
		Name = "Always Jump",
		Function = function() end
	})
	SpeedJumpVanilla = Speed.CreateToggle({
		Name = "Real Jump",
		Function = function() end
	})
	SpeedWallCheck = Speed.CreateToggle({
		Name = "Wall Check",
		Function = function() end,
		Default = true
	})
	SpeedAnimation = Speed.CreateToggle({
		Name = "Slowdown Anim",
		Function = function() end
	})
end)

run(function()
	local SpinBot = {Enabled = false}
	local SpinBotX = {Enabled = false}
	local SpinBotY = {Enabled = false}
	local SpinBotZ = {Enabled = false}
	local SpinBotSpeed = {Value = 1}
	SpinBot = GuiLibrary.ObjectsThatCanBeSaved.BlatantWindow.Api.CreateOptionsButton({
		Name = "SpinBot",
		Function = function(callback)
			if callback then
				RunLoops:BindToHeartbeat("SpinBot", function()
					if entityLibrary.isAlive then
						local originalRotVelocity = entityLibrary.character.HumanoidRootPart.RotVelocity
						entityLibrary.character.HumanoidRootPart.RotVelocity = Vector3.new(SpinBotX.Enabled and SpinBotSpeed.Value or originalRotVelocity.X, SpinBotY.Enabled and SpinBotSpeed.Value or originalRotVelocity.Y, SpinBotZ.Enabled and SpinBotSpeed.Value or originalRotVelocity.Z)
					end
				end)
			else
				RunLoops:UnbindFromHeartbeat("SpinBot")
			end
		end,
		HoverText = "Makes your character spin around in circles (does not work in first person)"
	})
	SpinBotSpeed = SpinBot.CreateSlider({
		Name = "Speed",
		Min = 1,
		Max = 100,
		Default = 40,
		Function = function() end
	})
	SpinBotX = SpinBot.CreateToggle({
		Name = "Spin X",
		Function = function() end
	})
	SpinBotY = SpinBot.CreateToggle({
		Name = "Spin Y",
		Function = function() end,
		Default = true
	})
	SpinBotZ = SpinBot.CreateToggle({
		Name = "Spin Z",
		Function = function() end
	})
end)

local GravityChangeTick = tick()
run(function()
	local Gravity = {Enabled = false}
	local GravityValue = {Value = 100}
	local oldGravity
	Gravity = GuiLibrary.ObjectsThatCanBeSaved.BlatantWindow.Api.CreateOptionsButton({
		Name = "Gravity",
		Function = function(callback)
			if callback then
				oldGravity = workspace.Gravity
				workspace.Gravity = GravityValue.Value
				table.insert(Gravity.Connections, workspace:GetPropertyChangedSignal("Gravity"):Connect(function()
					if GravityChangeTick > tick() then return end
					oldGravity = workspace.Gravity
					GravityChangeTick = tick() + 0.1
					workspace.Gravity = GravityValue.Value
				end))
			else
				workspace.Gravity = oldGravity
			end
		end,
		HoverText = "Changes workspace gravity"
	})
	GravityValue = Gravity.CreateSlider({
		Name = "Gravity",
		Min = 0,
		Max = 192,
		Function = function(val)
			if Gravity.Enabled then
				GravityChangeTick = tick() + 0.1
				workspace.Gravity = val
			end
		end,
		Default = 192
	})
end)

run(function()
    local ArrowsFolder = Instance.new("Folder")
    ArrowsFolder.Name = "ArrowsFolder"
    ArrowsFolder.Parent = GuiLibrary.MainGui
    local ArrowsFolderTable = {}
    local ArrowsColor = {Value = 0.44}
    local ArrowsTeammate = {Enabled = true}

    local arrowAddFunction = function(plr)
        if ArrowsTeammate.Enabled and (not plr.Targetable) and (not plr.Friend) then return end
        local arrowObject = Instance.new("ImageLabel")
        arrowObject.BackgroundTransparency = 1
        arrowObject.BorderSizePixel = 0
        arrowObject.Size = UDim2.new(0, 256, 0, 256)
        arrowObject.AnchorPoint = Vector2.new(0.5, 0.5)
        arrowObject.Position = UDim2.new(0.5, 0, 0.5, 0)
        arrowObject.Visible = false
        arrowObject.Image = downloadVapeAsset("vape/assets/ArrowIndicator.png")
		arrowObject.ImageColor3 = getPlayerColor(plr.Player) or Color3.fromHSV(ArrowsColor.Hue, ArrowsColor.Sat, ArrowsColor.Value)
        arrowObject.Name = plr.Player.Name
        arrowObject.Parent = ArrowsFolder
        ArrowsFolderTable[plr.Player] = {entity = plr, Main = arrowObject}
    end

    local arrowRemoveFunction = function(ent)
        local v = ArrowsFolderTable[ent]
        ArrowsFolderTable[ent] = nil
        if v then v.Main:Destroy() end
    end

    local arrowColorFunction = function(hue, sat, val)
        local color = Color3.fromHSV(hue, sat, val)
        for i,v in pairs(ArrowsFolderTable) do
            v.Main.ImageColor3 = getPlayerColor(v.entity.Player) or color
        end
    end

    local arrowLoopFunction = function()
        for i,v in pairs(ArrowsFolderTable) do
            local rootPos, rootVis = worldtoscreenpoint(v.entity.RootPart.Position)
            if rootVis then
                v.Main.Visible = false
                continue
            end
            local camcframeflat = CFrame.new(gameCamera.CFrame.p, gameCamera.CFrame.p + gameCamera.CFrame.lookVector * Vector3.new(1, 0, 1))
            local pointRelativeToCamera = camcframeflat:pointToObjectSpace(v.entity.RootPart.Position)
            local unitRelativeVector = (pointRelativeToCamera * Vector3.new(1, 0, 1)).unit
            local rotation = math.atan2(unitRelativeVector.Z, unitRelativeVector.X)
            v.Main.Visible = true
            v.Main.Rotation = math.deg(rotation)
        end
    end

    local Arrows = {Enabled = false}
	Arrows = GuiLibrary.ObjectsThatCanBeSaved.RenderWindow.Api.CreateOptionsButton({
        Name = "Arrows",
        Function = function(callback)
            if callback then
				table.insert(Arrows.Connections, entityLibrary.entityRemovedEvent:Connect(arrowRemoveFunction))
				for i,v in pairs(entityLibrary.entityList) do
                    if ArrowsFolderTable[v.Player] then arrowRemoveFunction(v.Player) end
                    arrowAddFunction(v)
                end
                table.insert(Arrows.Connections, entityLibrary.entityAddedEvent:Connect(function(ent)
                    if ArrowsFolderTable[ent.Player] then arrowRemoveFunction(ent.Player) end
                    arrowAddFunction(ent)
                end))
				table.insert(Arrows.Connections, GuiLibrary.ObjectsThatCanBeSaved.FriendsListTextCircleList.Api.FriendColorRefresh.Event:Connect(function()
                    arrowColorFunction(ESPColor.Hue, ESPColor.Sat, ESPColor.Value)
                end))
				RunLoops:BindToRenderStep("Arrows", arrowLoopFunction)
            else
                RunLoops:UnbindFromRenderStep("Arrows")
				for i,v in pairs(ArrowsFolderTable) do
                    arrowRemoveFunction(i)
                end
            end
        end,
        HoverText = "Draws arrows on screen when entities\nare out of your field of view."
    })
    ArrowsColor = Arrows.CreateColorSlider({
        Name = "Player Color",
        Function = function(hue, sat, val)
			if Arrows.Enabled then
				arrowColorFunction(hue, sat, val)
			end
		end,
    })
    ArrowsTeammate = Arrows.CreateToggle({
        Name = "Teammate",
        Function = function() end,
        Default = true
    })
end)


run(function()
	local Disguise = {Enabled = false}
	local DisguiseId = {Value = ""}
	local DisguiseDescription

	local function Disguisechar(char)
		task.spawn(function()
			if not char then return end
			local hum = char:WaitForChild("Humanoid", 9e9)
			char:WaitForChild("Head", 9e9)
			local DisguiseDescription
			if DisguiseDescription == nil then
				local suc = false
				repeat
					suc = pcall(function()
						DisguiseDescription = playersService:GetHumanoidDescriptionFromUserId(DisguiseId.Value == "" and 239702688 or tonumber(DisguiseId.Value))
					end)
					if suc then break end
					task.wait(1)
				until suc or (not Disguise.Enabled)
			end
			if (not Disguise.Enabled) then return end
			local desc = hum:WaitForChild("HumanoidDescription", 2) or {HeightScale = 1, SetEmotes = function() end, SetEquippedEmotes = function() end}
			DisguiseDescription.HeightScale = desc.HeightScale
			char.Archivable = true
			local Disguiseclone = char:Clone()
			Disguiseclone.Name = "Disguisechar"
			Disguiseclone.Parent = workspace
			for i,v in pairs(Disguiseclone:GetChildren()) do
				if v:IsA("Accessory") or v:IsA("ShirtGraphic") or v:IsA("Shirt") or v:IsA("Pants") then
					v:Destroy()
				end
			end
			if not Disguiseclone:FindFirstChildWhichIsA("Humanoid") then
				Disguiseclone:Destroy()
				return
			end
			Disguiseclone.Humanoid:ApplyDescriptionClientServer(DisguiseDescription)
			for i,v in pairs(char:GetChildren()) do
				if (v:IsA("Accessory") and v:GetAttribute("InvItem") == nil and v:GetAttribute("ArmorSlot") == nil) or v:IsA("ShirtGraphic") or v:IsA("Shirt") or v:IsA("Pants") or v:IsA("BodyColors") or v:IsA("Folder") or v:IsA("Model") then
					v.Parent = game
				end
			end
			char.ChildAdded:Connect(function(v)
				if ((v:IsA("Accessory") and v:GetAttribute("InvItem") == nil and v:GetAttribute("ArmorSlot") == nil) or v:IsA("ShirtGraphic") or v:IsA("Shirt") or v:IsA("Pants") or v:IsA("BodyColors")) and v:GetAttribute("Disguise") == nil then
					repeat task.wait() v.Parent = game until v.Parent == game
				end
			end)
			for i,v in pairs(Disguiseclone:WaitForChild("Animate"):GetChildren()) do
				v:SetAttribute("Disguise", true)
				if not char:FindFirstChild("Animate") then return end
				local real = char.Animate:FindFirstChild(v.Name)
				if v:IsA("StringValue") and real then
					real.Parent = game
					v.Parent = char.Animate
				end
			end
			for i,v in pairs(Disguiseclone:GetChildren()) do
				v:SetAttribute("Disguise", true)
				if v:IsA("Accessory") then
					for i2,v2 in pairs(v:GetDescendants()) do
						if v2:IsA("Weld") and v2.Part1 then
							v2.Part1 = char[v2.Part1.Name]
						end
					end
					v.Parent = char
				elseif v:IsA("ShirtGraphic") or v:IsA("Shirt") or v:IsA("Pants") or v:IsA("BodyColors") then
					v.Parent = char
				elseif v.Name == "Head" and char.Head:IsA("MeshPart") then
					char.Head.MeshId = v.MeshId
				end
			end
			local localface = char:FindFirstChild("face", true)
			local cloneface = Disguiseclone:FindFirstChild("face", true)
			if localface and cloneface then localface.Parent = game cloneface.Parent = char.Head end
			desc:SetEmotes(DisguiseDescription:GetEmotes())
			desc:SetEquippedEmotes(DisguiseDescription:GetEquippedEmotes())
			Disguiseclone:Destroy()
		end)
	end

	Disguise = GuiLibrary.ObjectsThatCanBeSaved.RenderWindow.Api.CreateOptionsButton({
		Name = "Disguise",
		Function = function(callback)
			if callback then
				table.insert(Disguise.Connections, lplr.CharacterAdded:Connect(Disguisechar))
				Disguisechar(lplr.Character)
			end
		end
	})
	DisguiseId = Disguise.CreateTextBox({
		Name = "Disguise",
		TempText = "Disguise User Id",
		FocusLost = function(enter)
			if Disguise.Enabled then
				Disguise.ToggleButton(false)
				Disguise.ToggleButton(false)
			end
		end
	})
end)

run(function()
	local ESPColor = {Value = 0.44}
	local ESPHealthBar = {Enabled = false}
	local ESPBoundingBox = {Enabled = true}
	local ESPName = {Enabled = true}
	local ESPMethod = {Value = "2D"}
	local ESPTeammates = {Enabled = true}
	local espfolderdrawing = {}
	local espconnections = {}
	local methodused

	local function floorESPPosition(pos)
		return Vector2.new(math.floor(pos.X), math.floor(pos.Y))
	end

	local function ESPWorldToViewport(pos)
		local newpos = worldtoviewportpoint(gameCamera.CFrame:pointToWorldSpace(gameCamera.CFrame:pointToObjectSpace(pos)))
		return Vector2.new(newpos.X, newpos.Y)
	end

	local espfuncs1 = {
		Drawing2D = function(plr)
			if ESPTeammates.Enabled and (not plr.Targetable) and (not plr.Friend) then return end
			local thing = {}
			thing.Quad1 = Drawing.new("Square")
			thing.Quad1.Transparency = ESPBoundingBox.Enabled and 1 or 0
			thing.Quad1.ZIndex = 2
			thing.Quad1.Filled = false
			thing.Quad1.Thickness = 1
			thing.Quad1.Color = getPlayerColor(plr.Player) or Color3.fromHSV(ESPColor.Hue, ESPColor.Sat, ESPColor.Value)
			thing.QuadLine2 = Drawing.new("Square")
			thing.QuadLine2.Transparency = ESPBoundingBox.Enabled and 0.5 or 0
			thing.QuadLine2.ZIndex = 1
			thing.QuadLine2.Thickness = 1
			thing.QuadLine2.Filled = false
			thing.QuadLine2.Color = Color3.new()
			thing.QuadLine3 = Drawing.new("Square")
			thing.QuadLine3.Transparency = ESPBoundingBox.Enabled and 0.5 or 0
			thing.QuadLine3.ZIndex = 1
			thing.QuadLine3.Thickness = 1
			thing.QuadLine3.Filled = false
			thing.QuadLine3.Color = Color3.new()
			if ESPHealthBar.Enabled then
				thing.Quad3 = Drawing.new("Line")
				thing.Quad3.Thickness = 1
				thing.Quad3.ZIndex = 2
				thing.Quad3.Color = Color3.new(0, 1, 0)
				thing.Quad4 = Drawing.new("Line")
				thing.Quad4.Thickness = 3
				thing.Quad4.Transparency = 0.5
				thing.Quad4.ZIndex = 1
				thing.Quad4.Color = Color3.new()
			end
			if ESPName.Enabled then
				thing.Drop = Drawing.new("Text")
				thing.Drop.Color = Color3.new()
				thing.Drop.Text = whitelist:tag(plr.Player, true)..(plr.Player.DisplayName or plr.Player.Name)
				thing.Drop.ZIndex = 1
				thing.Drop.Center = true
				thing.Drop.Size = 20
				thing.Text = Drawing.new("Text")
				thing.Text.Text = thing.Drop.Text
				thing.Text.ZIndex = 2
				thing.Text.Color = thing.Quad1.Color
				thing.Text.Center = true
				thing.Text.Size = 20
			end
			espfolderdrawing[plr.Player] = {entity = plr, Main = thing}
		end,
		Drawing2DV3 = function(plr)
			if ESPTeammates.Enabled and (not plr.Targetable) and (not plr.Friend) then return end
			local toppoint = PointInstance.new(plr.RootPart, CFrame.new(2, 3, 0))
			local bottompoint = PointInstance.new(plr.RootPart, CFrame.new(-2, -3.5, 0))
			local newobj = RectDynamic.new(toppoint)
			newobj.BottomRight = bottompoint
			newobj.Outlined = ESPBoundingBox.Enabled
			newobj.Opacity = ESPBoundingBox.Enabled and 1 or 0
			newobj.OutlineOpacity = 0.5
			newobj.Color = getPlayerColor(plr.Player) or Color3.fromHSV(ESPColor.Hue, ESPColor.Sat, ESPColor.Value)
			local newobj2 = {}
			local newobj3 = {}
			if ESPHealthBar.Enabled then
				local topoffset = PointOffset.new(PointInstance.new(plr.RootPart, CFrame.new(-2, 3, 0)), Vector2.new(-5, -1))
				local bottomoffset = PointOffset.new(PointInstance.new(plr.RootPart, CFrame.new(-2, -3.5, 0)), Vector2.new(-3, 1))
				local healthoffset = PointOffset.new(bottomoffset, Vector2.new(0, -1))
				local healthoffset2 = PointOffset.new(bottomoffset, Vector2.new(-1, -((bottomoffset.ScreenPos.Y - topoffset.ScreenPos.Y) - 1)))
				newobj2.Bkg = RectDynamic.new(topoffset)
				newobj2.Bkg.Filled = true
				newobj2.Bkg.Opacity = 0.5
				newobj2.Bkg.BottomRight = bottomoffset
				newobj2.Line = RectDynamic.new(healthoffset)
				newobj2.Line.Filled = true
				newobj2.Line.YAlignment = YAlignment.Bottom
				newobj2.Line.BottomRight = healthoffset2
				newobj2.Line.Color = Color3.fromHSV(math.clamp(plr.Humanoid.Health / plr.Humanoid.MaxHealth, 0, 1) / 2.5, 0.89, 1)
				newobj2.Offset = healthoffset2
				newobj2.TopOffset = topoffset
				newobj2.BottomOffset = bottomoffset
			end
			if ESPName.Enabled then
				local nameoffset1 = PointOffset.new(PointInstance.new(plr.RootPart, CFrame.new(0, 3, 0)), Vector2.new(0, -15))
				local nameoffset2 = PointOffset.new(nameoffset1, Vector2.new(1, 1))
				newobj3.Text = TextDynamic.new(nameoffset1)
				newobj3.Text.Text = whitelist:tag(plr.Player, true)..(plr.Player.DisplayName or plr.Player.Name)
				newobj3.Text.Color = newobj.Color
				newobj3.Text.ZIndex = 2
				newobj3.Text.Size = 20
				newobj3.Drop = TextDynamic.new(nameoffset2)
				newobj3.Drop.Text = newobj3.Text.Text
				newobj3.Drop.Color = Color3.new()
				newobj3.Drop.ZIndex = 1
				newobj3.Drop.Size = 20
			end
			espfolderdrawing[plr.Player] = {entity = plr, Main = newobj, HealthBar = newobj2, Name = newobj3}
		end,
		DrawingSkeleton = function(plr)
			if ESPTeammates.Enabled and (not plr.Targetable) and (not plr.Friend) then return end
			local thing = {}
			thing.Head = Drawing.new("Line")
			thing.Head2 = Drawing.new("Line")
			thing.Torso = Drawing.new("Line")
			thing.Torso2 = Drawing.new("Line")
			thing.Torso3 = Drawing.new("Line")
			thing.LeftArm = Drawing.new("Line")
			thing.RightArm = Drawing.new("Line")
			thing.LeftLeg = Drawing.new("Line")
			thing.RightLeg = Drawing.new("Line")
			local color = getPlayerColor(plr.Player) or Color3.fromHSV(ESPColor.Hue, ESPColor.Sat, ESPColor.Value)
			for i,v in pairs(thing) do v.Thickness = 2 v.Color = color end
			espfolderdrawing[plr.Player] = {entity = plr, Main = thing}
		end,
		DrawingSkeletonV3 = function(plr)
			if ESPTeammates.Enabled and (not plr.Targetable) and (not plr.Friend) then return end
			local thing = {Main = {}, entity = plr}
			local rigcheck = plr.Humanoid.RigType == Enum.HumanoidRigType.R6
			local head = PointInstance.new(plr.Head)
			head.RotationType = CFrameRotationType.TargetRelative
			local headfront = PointInstance.new(plr.Head, CFrame.new(0, 0, -0.5))
			headfront.RotationType = CFrameRotationType.TargetRelative
			local toplefttorso = PointInstance.new(plr.Character[(rigcheck and "Torso" or "UpperTorso")], CFrame.new(-1.5, 0.8, 0))
			toplefttorso.RotationType = CFrameRotationType.TargetRelative
			local toprighttorso = PointInstance.new(plr.Character[(rigcheck and "Torso" or "UpperTorso")], CFrame.new(1.5, 0.8, 0))
			toprighttorso.RotationType = CFrameRotationType.TargetRelative
			local toptorso = PointInstance.new(plr.Character[(rigcheck and "Torso" or "UpperTorso")], CFrame.new(0, 0.8, 0))
			toptorso.RotationType = CFrameRotationType.TargetRelative
			local bottomtorso = PointInstance.new(plr.Character[(rigcheck and "Torso" or "UpperTorso")], CFrame.new(0, -0.8, 0))
			bottomtorso.RotationType = CFrameRotationType.TargetRelative
			local bottomlefttorso = PointInstance.new(plr.Character[(rigcheck and "Torso" or "UpperTorso")], CFrame.new(-0.5, -0.8, 0))
			bottomlefttorso.RotationType = CFrameRotationType.TargetRelative
			local bottomrighttorso = PointInstance.new(plr.Character[(rigcheck and "Torso" or "UpperTorso")], CFrame.new(0.5, -0.8, 0))
			bottomrighttorso.RotationType = CFrameRotationType.TargetRelative
			local leftarm = PointInstance.new(plr.Character[(rigcheck and "Left Arm" or "LeftHand")], CFrame.new(0, -0.8, 0))
			leftarm.RotationType = CFrameRotationType.TargetRelative
			local rightarm = PointInstance.new(plr.Character[(rigcheck and "Right Arm" or "RightHand")], CFrame.new(0, -0.8, 0))
			rightarm.RotationType = CFrameRotationType.TargetRelative
			local leftleg = PointInstance.new(plr.Character[(rigcheck and "Left Leg" or "LeftFoot")], CFrame.new(0, -0.8, 0))
			leftleg.RotationType = CFrameRotationType.TargetRelative
			local rightleg = PointInstance.new(plr.Character[(rigcheck and "Right Leg" or "RightFoot")], CFrame.new(0, -0.8, 0))
			rightleg.RotationType = CFrameRotationType.TargetRelative
			thing.Main.Head = LineDynamic.new(toptorso, head)
			thing.Main.Head2 = LineDynamic.new(head, headfront)
			thing.Main.Torso = LineDynamic.new(toplefttorso, toprighttorso)
			thing.Main.Torso2 = LineDynamic.new(toptorso, bottomtorso)
			thing.Main.Torso3 = LineDynamic.new(bottomlefttorso, bottomrighttorso)
			thing.Main.LeftArm = LineDynamic.new(toplefttorso, leftarm)
			thing.Main.RightArm = LineDynamic.new(toprighttorso, rightarm)
			thing.Main.LeftLeg = LineDynamic.new(bottomlefttorso, leftleg)
			thing.Main.RightLeg = LineDynamic.new(bottomrighttorso, rightleg)
			local color = getPlayerColor(plr.Player) or Color3.fromHSV(ESPColor.Hue, ESPColor.Sat, ESPColor.Value)
			for i,v in pairs(thing.Main) do v.Thickness = 2 v.Color = color end
			espfolderdrawing[plr.Player] = thing
		end,
		Drawing3D = function(plr)
			if ESPTeammates.Enabled and (not plr.Targetable) and (not plr.Friend) then return end
			local thing = {}
			thing.Line1 = Drawing.new("Line")
			thing.Line2 = Drawing.new("Line")
			thing.Line3 = Drawing.new("Line")
			thing.Line4 = Drawing.new("Line")
			thing.Line5 = Drawing.new("Line")
			thing.Line6 = Drawing.new("Line")
			thing.Line7 = Drawing.new("Line")
			thing.Line8 = Drawing.new("Line")
			thing.Line9 = Drawing.new("Line")
			thing.Line10 = Drawing.new("Line")
			thing.Line11 = Drawing.new("Line")
			thing.Line12 = Drawing.new("Line")
			local color = getPlayerColor(plr.Player) or Color3.fromHSV(ESPColor.Hue, ESPColor.Sat, ESPColor.Value)
			for i,v in pairs(thing) do v.Thickness = 1 v.Color = color end
			espfolderdrawing[plr.Player] = {entity = plr, Main = thing}
		end,
		Drawing3DV3 = function(plr)
			if ESPTeammates.Enabled and (not plr.Targetable) and (not plr.Friend) then return end
			local thing = {}
			local point1 = PointInstance.new(plr.RootPart, CFrame.new(1.5, 3, 1.5))
			point1.RotationType = CFrameRotationType.Ignore
			local point2 = PointInstance.new(plr.RootPart, CFrame.new(1.5, -3, 1.5))
			point2.RotationType = CFrameRotationType.Ignore
			local point3 = PointInstance.new(plr.RootPart, CFrame.new(-1.5, 3, 1.5))
			point3.RotationType = CFrameRotationType.Ignore
			local point4 = PointInstance.new(plr.RootPart, CFrame.new(-1.5, -3, 1.5))
			point4.RotationType = CFrameRotationType.Ignore
			local point5 = PointInstance.new(plr.RootPart, CFrame.new(1.5, 3, -1.5))
			point5.RotationType = CFrameRotationType.Ignore
			local point6 = PointInstance.new(plr.RootPart, CFrame.new(1.5, -3, -1.5))
			point6.RotationType = CFrameRotationType.Ignore
			local point7 = PointInstance.new(plr.RootPart, CFrame.new(-1.5, 3, -1.5))
			point7.RotationType = CFrameRotationType.Ignore
			local point8 = PointInstance.new(plr.RootPart, CFrame.new(-1.5, -3, -1.5))
			point8.RotationType = CFrameRotationType.Ignore
			thing.Line1 = LineDynamic.new(point1, point2)
			thing.Line2 = LineDynamic.new(point3, point4)
			thing.Line3 = LineDynamic.new(point5, point6)
			thing.Line4 = LineDynamic.new(point7, point8)
			thing.Line5 = LineDynamic.new(point1, point3)
			thing.Line6 = LineDynamic.new(point1, point5)
			thing.Line7 = LineDynamic.new(point5, point7)
			thing.Line8 = LineDynamic.new(point7, point3)
			thing.Line9 = LineDynamic.new(point2, point4)
			thing.Line10 = LineDynamic.new(point2, point6)
			thing.Line11 = LineDynamic.new(point6, point8)
			thing.Line12 = LineDynamic.new(point8, point4)
			local color = getPlayerColor(plr.Player) or Color3.fromHSV(ESPColor.Hue, ESPColor.Sat, ESPColor.Value)
			for i,v in pairs(thing) do v.Thickness = 1 v.Color = color end
			espfolderdrawing[plr.Player] = {entity = plr, Main = thing}
		end
	}
	local espfuncs2 = {
		Drawing2D = function(ent)
			local v = espfolderdrawing[ent]
			espfolderdrawing[ent] = nil
			if v then
				for i2,v2 in pairs(v.Main) do
					pcall(function() v2.Visible = false v2:Remove() end)
				end
			end
		end,
		Drawing2DV3 = function(ent)
			local v = espfolderdrawing[ent]
			espfolderdrawing[ent] = nil
			if v then
				v.Main.Visible = false
				for i2,v2 in pairs(v.HealthBar) do
					if typeof(v2):find("Point") == nil then
						v2.Visible = false
					end
				end
				for i2,v2 in pairs(v.Name) do
					if typeof(v2):find("Point") == nil then
						v2.Visible = false
					end
				end
			end
		end,
		Drawing3D = function(ent)
			local v = espfolderdrawing[ent]
			espfolderdrawing[ent] = nil
			if v then
				for i2,v2 in pairs(v.Main) do
					pcall(function() v2.Visible = false v2:Remove() end)
				end
			end
		end,
		Drawing3DV3 = function(ent)
			local v = espfolderdrawing[ent]
			espfolderdrawing[ent] = nil
			if v then
				for i2,v2 in pairs(v.Main) do
					if typeof(v2):find("Dynamic") then
						v2.Visible = false
					end
				end
			end
		end,
		DrawingSkeleton = function(ent)
			local v = espfolderdrawing[ent]
			espfolderdrawing[ent] = nil
			if v then
				for i2,v2 in pairs(v.Main) do
					pcall(function() v2.Visible = false v2:Remove() end)
				end
			end
		end,
		DrawingSkeletonV3 = function(ent)
			local v = espfolderdrawing[ent]
			espfolderdrawing[ent] = nil
			if v then
				for i2,v2 in pairs(v.Main) do
					if typeof(v2):find("Dynamic") then
						v2.Visible = false
					end
				end
			end
		end
	}
	local espupdatefuncs = {
		Drawing2D = function(ent)
			local v = espfolderdrawing[ent.Player]
			if v and v.Main.Quad3 then
				local color = Color3.fromHSV(math.clamp(ent.Humanoid.Health / ent.Humanoid.MaxHealth, 0, 1) / 2.5, 0.89, 1)
				v.Main.Quad3.Color = color
			end
			if v and v.Text then
				v.Text.Text = whitelist:tag(ent.Player, true)..(ent.Player.DisplayName or ent.Player.Name)
				v.Drop.Text = v.Text.Text
			end
		end,
		Drawing2DV3 = function(ent)
			local v = espfolderdrawing[ent.Player]
			if v and v.HealthBar.Line then
				local health = ent.Humanoid.Health / ent.Humanoid.MaxHealth
				local color = Color3.fromHSV(math.clamp(health, 0, 1) / 2.5, 0.89, 1)
				v.HealthBar.Line.Color = color
			end
			if v and v.Name and v.Name.Text then
				v.Name.Text.Text = whitelist:tag(ent.Player, true)..(ent.Player.DisplayName or ent.Player.Name)
				v.Name.Drop.Text = v.Name.Text.Text
			end
		end
	}
	local espcolorfuncs = {
		Drawing2D = function(hue, sat, value)
			local color = Color3.fromHSV(hue, sat, value)
			for i,v in pairs(espfolderdrawing) do
				v.Main.Quad1.Color = getPlayerColor(v.entity.Player) or color
				if v.Main.Text then
					v.Main.Text.Color = v.Main.Quad1.Color
				end
			end
		end,
		Drawing2DV3 = function(hue, sat, value)
			local color = Color3.fromHSV(hue, sat, value)
			for i,v in pairs(espfolderdrawing) do
				v.Main.Color = getPlayerColor(v.entity.Player) or color
				if v.Name.Text then
					v.Name.Text.Color = v.Main.Color
				end
			end
		end,
		Drawing3D = function(hue, sat, value)
			local color = Color3.fromHSV(hue, sat, value)
			for i,v in pairs(espfolderdrawing) do
				local newcolor = getPlayerColor(v.entity.Player) or color
				for i2,v2 in pairs(v.Main) do
					v2.Color = newcolor
				end
			end
		end,
		Drawing3DV3 = function(hue, sat, value)
			local color = Color3.fromHSV(hue, sat, value)
			for i,v in pairs(espfolderdrawing) do
				local newcolor = getPlayerColor(v.entity.Player) or color
				for i2,v2 in pairs(v.Main) do
					if typeof(v2):find("Dynamic") then
						v2.Color = newcolor
					end
				end
			end
		end,
		DrawingSkeleton = function(hue, sat, value)
			local color = Color3.fromHSV(hue, sat, value)
			for i,v in pairs(espfolderdrawing) do
				local newcolor = getPlayerColor(v.entity.Player) or color
				for i2,v2 in pairs(v.Main) do
					v2.Color = newcolor
				end
			end
		end,
		DrawingSkeletonV3 = function(hue, sat, value)
			local color = Color3.fromHSV(hue, sat, value)
			for i,v in pairs(espfolderdrawing) do
				local newcolor = getPlayerColor(v.entity.Player) or color
				for i2,v2 in pairs(v.Main) do
					if typeof(v2):find("Dynamic") then
						v2.Color = newcolor
					end
				end
			end
		end,
	}
	local esploop = {
		Drawing2D = function()
			for i,v in pairs(espfolderdrawing) do
				local rootPos, rootVis = worldtoviewportpoint(v.entity.RootPart.Position)
				if not rootVis then
					v.Main.Quad1.Visible = false
					v.Main.QuadLine2.Visible = false
					v.Main.QuadLine3.Visible = false
					if v.Main.Quad3 then
						v.Main.Quad3.Visible = false
						v.Main.Quad4.Visible = false
					end
					if v.Main.Text then
						v.Main.Text.Visible = false
						v.Main.Drop.Visible = false
					end
					continue
				end
				local topPos, topVis = worldtoviewportpoint((CFrame.new(v.entity.RootPart.Position, v.entity.RootPart.Position + gameCamera.CFrame.lookVector) * CFrame.new(2, 3, 0)).p)
				local bottomPos, bottomVis = worldtoviewportpoint((CFrame.new(v.entity.RootPart.Position, v.entity.RootPart.Position + gameCamera.CFrame.lookVector) * CFrame.new(-2, -3.5, 0)).p)
				local sizex, sizey = topPos.X - bottomPos.X, topPos.Y - bottomPos.Y
				local posx, posy = (rootPos.X - sizex / 2),  ((rootPos.Y - sizey / 2))
				v.Main.Quad1.Position = floorESPPosition(Vector2.new(posx, posy))
				v.Main.Quad1.Size = floorESPPosition(Vector2.new(sizex, sizey))
				v.Main.Quad1.Visible = true
				v.Main.QuadLine2.Position = floorESPPosition(Vector2.new(posx - 1, posy + 1))
				v.Main.QuadLine2.Size = floorESPPosition(Vector2.new(sizex + 2, sizey - 2))
				v.Main.QuadLine2.Visible = true
				v.Main.QuadLine3.Position = floorESPPosition(Vector2.new(posx + 1, posy - 1))
				v.Main.QuadLine3.Size = floorESPPosition(Vector2.new(sizex - 2, sizey + 2))
				v.Main.QuadLine3.Visible = true
				if v.Main.Quad3 then
					local healthposy = sizey * math.clamp(v.entity.Humanoid.Health / v.entity.Humanoid.MaxHealth, 0, 1)
					v.Main.Quad3.Visible = v.entity.Humanoid.Health > 0
					v.Main.Quad3.From = floorESPPosition(Vector2.new(posx - 4, posy + (sizey - (sizey - healthposy))))
					v.Main.Quad3.To = floorESPPosition(Vector2.new(posx - 4, posy))
					v.Main.Quad4.Visible = true
					v.Main.Quad4.From = floorESPPosition(Vector2.new(posx - 4, posy))
					v.Main.Quad4.To = floorESPPosition(Vector2.new(posx - 4, (posy + sizey)))
				end
				if v.Main.Text then
					v.Main.Text.Visible = true
					v.Main.Drop.Visible = true
					v.Main.Text.Position = floorESPPosition(Vector2.new(posx + (sizex / 2), posy + (sizey - 25)))
					v.Main.Drop.Position = v.Main.Text.Position + Vector2.new(1, 1)
				end
			end
		end,
		Drawing2DV3 = function()
			for i,v in pairs(espfolderdrawing) do
				if v.HealthBar.Offset then
					v.HealthBar.Offset.Offset = Vector2.new(-1, -(((v.HealthBar.BottomOffset.ScreenPos.Y - v.HealthBar.TopOffset.ScreenPos.Y) - 1) * (v.entity.Humanoid.Health / v.entity.Humanoid.MaxHealth)))
					v.HealthBar.Line.Visible = v.entity.Humanoid.Health > 0
				end
			end
		end,
		Drawing3D = function()
			for i,v in pairs(espfolderdrawing) do
				local rootPos, rootVis = worldtoviewportpoint(v.entity.RootPart.Position)
				if not rootVis then
					for i,v in pairs(v.Main) do
						v.Visible = false
					end
					continue
				end
				for i,v in pairs(v.Main) do
					v.Visible = true
				end
				local point1 = ESPWorldToViewport(v.entity.RootPart.Position + Vector3.new(1.5, 3, 1.5))
				local point2 = ESPWorldToViewport(v.entity.RootPart.Position + Vector3.new(1.5, -3, 1.5))
				local point3 = ESPWorldToViewport(v.entity.RootPart.Position + Vector3.new(-1.5, 3, 1.5))
				local point4 = ESPWorldToViewport(v.entity.RootPart.Position + Vector3.new(-1.5, -3, 1.5))
				local point5 = ESPWorldToViewport(v.entity.RootPart.Position + Vector3.new(1.5, 3, -1.5))
				local point6 = ESPWorldToViewport(v.entity.RootPart.Position + Vector3.new(1.5, -3, -1.5))
				local point7 = ESPWorldToViewport(v.entity.RootPart.Position + Vector3.new(-1.5, 3, -1.5))
				local point8 = ESPWorldToViewport(v.entity.RootPart.Position + Vector3.new(-1.5, -3, -1.5))
				v.Main.Line1.From = point1
				v.Main.Line1.To = point2
				v.Main.Line2.From = point3
				v.Main.Line2.To = point4
				v.Main.Line3.From = point5
				v.Main.Line3.To = point6
				v.Main.Line4.From = point7
				v.Main.Line4.To = point8
				v.Main.Line5.From = point1
				v.Main.Line5.To = point3
				v.Main.Line6.From = point1
				v.Main.Line6.To = point5
				v.Main.Line7.From = point5
				v.Main.Line7.To = point7
				v.Main.Line8.From = point7
				v.Main.Line8.To = point3
				v.Main.Line9.From = point2
				v.Main.Line9.To = point4
				v.Main.Line10.From = point2
				v.Main.Line10.To = point6
				v.Main.Line11.From = point6
				v.Main.Line11.To = point8
				v.Main.Line12.From = point8
				v.Main.Line12.To = point4
			end
		end,
		DrawingSkeleton = function()
			for i,v in pairs(espfolderdrawing) do
				local rootPos, rootVis = worldtoviewportpoint(v.entity.RootPart.Position)
				if not rootVis then
					for i,v in pairs(v.Main) do
						v.Visible = false
					end
					continue
				end
				for i,v in pairs(v.Main) do
					v.Visible = true
				end
				local rigcheck = v.entity.Humanoid.RigType == Enum.HumanoidRigType.R6
				local head = ESPWorldToViewport((v.entity.Head.CFrame).p)
				local headfront = ESPWorldToViewport((v.entity.Head.CFrame * CFrame.new(0, 0, -0.5)).p)
				local toplefttorso = ESPWorldToViewport((v.entity.Character[(rigcheck and "Torso" or "UpperTorso")].CFrame * CFrame.new(-1.5, 0.8, 0)).p)
				local toprighttorso = ESPWorldToViewport((v.entity.Character[(rigcheck and "Torso" or "UpperTorso")].CFrame * CFrame.new(1.5, 0.8, 0)).p)
				local toptorso = ESPWorldToViewport((v.entity.Character[(rigcheck and "Torso" or "UpperTorso")].CFrame * CFrame.new(0, 0.8, 0)).p)
				local bottomtorso = ESPWorldToViewport((v.entity.Character[(rigcheck and "Torso" or "UpperTorso")].CFrame * CFrame.new(0, -0.8, 0)).p)
				local bottomlefttorso = ESPWorldToViewport((v.entity.Character[(rigcheck and "Torso" or "UpperTorso")].CFrame * CFrame.new(-0.5, -0.8, 0)).p)
				local bottomrighttorso = ESPWorldToViewport((v.entity.Character[(rigcheck and "Torso" or "UpperTorso")].CFrame * CFrame.new(0.5, -0.8, 0)).p)
				local leftarm = ESPWorldToViewport((v.entity.Character[(rigcheck and "Left Arm" or "LeftHand")].CFrame * CFrame.new(0, -0.8, 0)).p)
				local rightarm = ESPWorldToViewport((v.entity.Character[(rigcheck and "Right Arm" or "RightHand")].CFrame * CFrame.new(0, -0.8, 0)).p)
				local leftleg = ESPWorldToViewport((v.entity.Character[(rigcheck and "Left Leg" or "LeftFoot")].CFrame * CFrame.new(0, -0.8, 0)).p)
				local rightleg = ESPWorldToViewport((v.entity.Character[(rigcheck and "Right Leg" or "RightFoot")].CFrame * CFrame.new(0, -0.8, 0)).p)
				v.Main.Torso.From = toplefttorso
				v.Main.Torso.To = toprighttorso
				v.Main.Torso2.From = toptorso
				v.Main.Torso2.To = bottomtorso
				v.Main.Torso3.From = bottomlefttorso
				v.Main.Torso3.To = bottomrighttorso
				v.Main.LeftArm.From = toplefttorso
				v.Main.LeftArm.To = leftarm
				v.Main.RightArm.From = toprighttorso
				v.Main.RightArm.To = rightarm
				v.Main.LeftLeg.From = bottomlefttorso
				v.Main.LeftLeg.To = leftleg
				v.Main.RightLeg.From = bottomrighttorso
				v.Main.RightLeg.To = rightleg
				v.Main.Head.From = toptorso
				v.Main.Head.To = head
				v.Main.Head2.From = head
				v.Main.Head2.To = headfront
			end
		end
	}

	local ESP = {Enabled = false}
	ESP = GuiLibrary.ObjectsThatCanBeSaved.RenderWindow.Api.CreateOptionsButton({
		Name = "ESP",
		Function = function(callback)
			if callback then
				methodused = "Drawing"..ESPMethod.Value..synapsev3
				if espfuncs2[methodused] then
					table.insert(ESP.Connections, entityLibrary.entityRemovedEvent:Connect(espfuncs2[methodused]))
				end
				if espfuncs1[methodused] then
					local addfunc = espfuncs1[methodused]
					for i,v in pairs(entityLibrary.entityList) do
						if espfolderdrawing[v.Player] then espfuncs2[methodused](v.Player) end
						addfunc(v)
					end
					table.insert(ESP.Connections, entityLibrary.entityAddedEvent:Connect(function(ent)
						if espfolderdrawing[ent.Player] then espfuncs2[methodused](ent.Player) end
						addfunc(ent)
					end))
				end
				if espupdatefuncs[methodused] then
					table.insert(ESP.Connections, entityLibrary.entityUpdatedEvent:Connect(espupdatefuncs[methodused]))
					for i,v in pairs(entityLibrary.entityList) do
						espupdatefuncs[methodused](v)
					end
				end
				if espcolorfuncs[methodused] then
					table.insert(ESP.Connections, GuiLibrary.ObjectsThatCanBeSaved.FriendsListTextCircleList.Api.FriendColorRefresh.Event:Connect(function()
						espcolorfuncs[methodused](ESPColor.Hue, ESPColor.Sat, ESPColor.Value)
					end))
				end
				if esploop[methodused] then
					RunLoops:BindToRenderStep("ESP", esploop[methodused])
				end
			else
				RunLoops:UnbindFromRenderStep("ESP")
				if espfuncs2[methodused] then
					for i,v in pairs(espfolderdrawing) do
						espfuncs2[methodused](i)
					end
				end
			end
		end,
		HoverText = "Extra Sensory Perception\nRenders an ESP on players."
	})
	ESPColor = ESP.CreateColorSlider({
		Name = "Player Color",
		Function = function(hue, sat, val)
			if ESP.Enabled and espcolorfuncs[methodused] then
				espcolorfuncs[methodused](hue, sat, val)
			end
		end
	})
	ESPMethod = ESP.CreateDropdown({
		Name = "Mode",
		List = {"2D", "3D", "Skeleton"},
		Function = function(val)
			if ESP.Enabled then ESP.ToggleButton(true) ESP.ToggleButton(true) end
			ESPBoundingBox.Object.Visible = (val == "2D")
			ESPHealthBar.Object.Visible = (val == "2D")
			ESPName.Object.Visible = (val == "2D")
		end,
	})
	ESPBoundingBox = ESP.CreateToggle({
		Name = "Bounding Box",
		Function = function() if ESP.Enabled then ESP.ToggleButton(true) ESP.ToggleButton(true) end end,
		Default = true
	})
	ESPTeammates = ESP.CreateToggle({
		Name = "Priority Only",
		Function = function() if ESP.Enabled then ESP.ToggleButton(true) ESP.ToggleButton(true) end end,
		Default = true
	})
	ESPHealthBar = ESP.CreateToggle({
		Name = "Health Bar",
		Function = function(callback) if ESP.Enabled then ESP.ToggleButton(true) ESP.ToggleButton(true) end end
	})
	ESPName = ESP.CreateToggle({
		Name = "Name",
		Function = function(callback) if ESP.Enabled then ESP.ToggleButton(true) ESP.ToggleButton(true) end end
	})
end)


run(function()
	local ChamsFolder = Instance.new("Folder")
	ChamsFolder.Name = "ChamsFolder"
	ChamsFolder.Parent = GuiLibrary.MainGui
	local chamstable = {}
	local ChamsColor = {Value = 0.44}
	local ChamsOutlineColor = {Value = 0.44}
	local ChamsTransparency = {Value = 1}
	local ChamsOutlineTransparency = {Value = 1}
	local ChamsOnTop = {Enabled = true}
	local ChamsTeammates = {Enabled = true}

	local function addfunc(ent)
		local chamfolder = Instance.new("Highlight")
		chamfolder.Name = ent.Player.Name
		chamfolder.Enabled = true
		chamfolder.Adornee = ent.Character
		chamfolder.OutlineTransparency = ChamsOutlineTransparency.Value / 100
		chamfolder.DepthMode = Enum.HighlightDepthMode[(ChamsOnTop.Enabled and "AlwaysOnTop" or "Occluded")]
		chamfolder.FillColor = getPlayerColor(ent.Player) or Color3.fromHSV(ChamsColor.Hue, ChamsColor.Sat, ChamsColor.Value)
		chamfolder.OutlineColor = getPlayerColor(ent.Player) or Color3.fromHSV(ChamsOutlineColor.Hue, ChamsOutlineColor.Sat, ChamsOutlineColor.Value)
		chamfolder.FillTransparency = ChamsTransparency.Value / 100
		chamfolder.Parent = ChamsFolder
		chamstable[ent.Player] = {Main = chamfolder, entity = ent}
	end

	local function removefunc(ent)
		local v = chamstable[ent]
		chamstable[ent] = nil
		if v then
			v.Main:Destroy()
		end
	end

	local Chams = {Enabled = false}
	Chams = GuiLibrary.ObjectsThatCanBeSaved.RenderWindow.Api.CreateOptionsButton({
		Name = "Chams",
		Function = function(callback)
			if callback then
				table.insert(Chams.Connections, entityLibrary.entityRemovedEvent:Connect(removefunc))
				for i,v in pairs(entityLibrary.entityList) do
					if chamstable[v.Player] then removefunc(v.Player) end
					addfunc(v)
				end
				table.insert(Chams.Connections, entityLibrary.entityAddedEvent:Connect(function(ent)
					if chamstable[ent.Player] then removefunc(ent.Player) end
					addfunc(ent)
				end))
				table.insert(Chams.Connections, GuiLibrary.ObjectsThatCanBeSaved.FriendsListTextCircleList.Api.FriendColorRefresh.Event:Connect(function()
					for i,v in pairs(chamstable) do
						v.Main.FillColor = getPlayerColor(i) or Color3.fromHSV(ChamsColor.Hue, ChamsColor.Sat, ChamsColor.Value)
						v.Main.OutlineColor = getPlayerColor(i) or Color3.fromHSV(ChamsOutlineColor.Hue, ChamsOutlineColor.Sat, ChamsOutlineColor.Value)
					end
				end))
			else
				for i,v in pairs(chamstable) do
					removefunc(i)
				end
			end
		end,
		HoverText = "Render players through walls"
	})
	ChamsColor = Chams.CreateColorSlider({
		Name = "Player Color",
		Function = function(val)
			for i,v in pairs(chamstable) do
				v.Main.FillColor = getPlayerColor(i) or Color3.fromHSV(ChamsColor.Hue, ChamsColor.Sat, ChamsColor.Value)
			end
		end
	})
	ChamsOutlineColor = Chams.CreateColorSlider({
		Name = "Outline Player Color",
		Function = function(val)
			for i,v in pairs(chamstable) do
				v.Main.OutlineColor = getPlayerColor(i) or Color3.fromHSV(ChamsOutlineColor.Hue, ChamsOutlineColor.Sat, ChamsOutlineColor.Value)
			end
		end
	})
	ChamsTransparency = Chams.CreateSlider({
		Name = "Transparency",
		Min = 1,
		Max = 100,
		Function = function(callback) if Chams.Enabled then Chams.ToggleButton(true) Chams.ToggleButton(true) end end,
		Default = 50
	})
	ChamsOutlineTransparency = Chams.CreateSlider({
		Name = "Outline Transparency",
		Min = 1,
		Max = 100,
		Function = function(callback) if Chams.Enabled then Chams.ToggleButton(true) Chams.ToggleButton(true) end end,
		Default = 1
	})
	ChamsTeammates = Chams.CreateToggle({
		Name = "Teammates",
		Function = function(callback) if Chams.Enabled then Chams.ToggleButton(true) Chams.ToggleButton(true) end end,
		Default = true
	})
	ChamsOnTop = Chams.CreateToggle({
		Name = "Bypass Walls",
		Function = function(callback) if Chams.Enabled then Chams.ToggleButton(true) Chams.ToggleButton(true) end end
	})
end)

run(function()
	local lightingsettings = {}
	local lightingchanged = false
	local Fullbright = {Enabled = false}
	Fullbright = GuiLibrary.ObjectsThatCanBeSaved.RenderWindow.Api.CreateOptionsButton({
		Name = "Fullbright",
		Function = function(callback)
			if callback then
				lightingsettings.Brightness = lightingService.Brightness
				lightingsettings.ClockTime = lightingService.ClockTime
				lightingsettings.FogEnd = lightingService.FogEnd
				lightingsettings.GlobalShadows = lightingService.GlobalShadows
				lightingsettings.OutdoorAmbient = lightingService.OutdoorAmbient
				lightingchanged = true
				lightingService.Brightness = 2
				lightingService.ClockTime = 14
				lightingService.FogEnd = 100000
				lightingService.GlobalShadows = false
				lightingService.OutdoorAmbient = Color3.fromRGB(128, 128, 128)
				lightingchanged = false
				table.insert(Fullbright.Connections, lightingService.Changed:Connect(function()
					if not lightingchanged then
						lightingsettings.Brightness = lightingService.Brightness
						lightingsettings.ClockTime = lightingService.ClockTime
						lightingsettings.FogEnd = lightingService.FogEnd
						lightingsettings.GlobalShadows = lightingService.GlobalShadows
						lightingsettings.OutdoorAmbient = lightingService.OutdoorAmbient
						lightingchanged = true
						lightingService.Brightness = 2
						lightingService.ClockTime = 14
						lightingService.FogEnd = 100000
						lightingService.GlobalShadows = false
						lightingService.OutdoorAmbient = Color3.fromRGB(128, 128, 128)
						lightingchanged = false
					end
				end))
			else
				for name, val in pairs(lightingsettings) do
					lightingService[name] = val
				end
			end
		end
	})
end)

run(function()
	local Health = {Enabled = false}
	Health =  GuiLibrary.ObjectsThatCanBeSaved.RenderWindow.Api.CreateOptionsButton({
		Name = "Health",
		Function = function(callback)
			if callback then
				HealthText = Drawing.new("Text")
				HealthText.Size = 20
				HealthText.Text = "100HP"
				HealthText.Position = Vector2.new(0, 0)
				HealthText.Color = Color3.fromRGB(0, 255, 0)
				HealthText.Center = true
				HealthText.Visible = true
				task.spawn(function()
					repeat
						if entityLibrary.isAlive then
							HealthText.Text = tostring(math.round(entityLibrary.character.Humanoid.Health)).."HP"
							HealthText.Color = Color3.fromHSV(math.clamp(entityLibrary.character.Humanoid.Health / entityLibrary.character.Humanoid.MaxHealth, 0, 1) / 2.5, 0.89, 1)
						end
						HealthText.Position = Vector2.new(gameCamera.ViewportSize.X / 2, gameCamera.ViewportSize.Y / 2 + 70)
						task.wait(0.1)
					until not Health.Enabled
				end)
			else
				if HealthText then HealthText:Remove() end
				RunLoops:UnbindFromRenderStep("Health")
			end
		end,
		HoverText = "Displays your health in the center of your screen."
	})
end)

run(function()
	local function floorNameTagPosition(pos)
		return Vector2.new(math.floor(pos.X), math.floor(pos.Y))
	end

	local NameTagsFolder = Instance.new("Folder")
	NameTagsFolder.Name = "NameTagsFolder"
	NameTagsFolder.Parent = GuiLibrary.MainGui
	local nametagsfolderdrawing = {}
	local NameTagsColor = {Value = 0.44}
	local NameTagsDisplayName = {Enabled = false}
	local NameTagsHealth = {Enabled = false}
	local NameTagsDistance = {Enabled = false}
	local NameTagsBackground = {Enabled = true}
	local NameTagsScale = {Value = 10}
	local NameTagsFont = {Value = "SourceSans"}
	local NameTagsTeammates = {Enabled = true}
	local fontitems = {"SourceSans"}
	local nametagstrs = {}
	local nametagsizes = {}

	local nametagfuncs1 = {
		Normal = function(plr)
			if NameTagsTeammates.Enabled and (not plr.Targetable) and (not plr.Friend) then return end
			local thing = Instance.new("TextLabel")
			thing.BackgroundColor3 = Color3.new()
			thing.BorderSizePixel = 0
			thing.Visible = false
			thing.RichText = true
			thing.AnchorPoint = Vector2.new(0.5, 1)
			thing.Name = plr.Player.Name
			thing.Font = Enum.Font[NameTagsFont.Value]
			thing.TextSize = 14 * (NameTagsScale.Value / 10)
			thing.BackgroundTransparency = NameTagsBackground.Enabled and 0.5 or 1
			nametagstrs[plr.Player] = whitelist:tag(plr.Player, true)..(NameTagsDisplayName.Enabled and plr.Player.DisplayName or plr.Player.Name)
			if NameTagsHealth.Enabled then
				local color = Color3.fromHSV(math.clamp(plr.Humanoid.Health / plr.Humanoid.MaxHealth, 0, 1) / 2.5, 0.89, 1)
				nametagstrs[plr.Player] = nametagstrs[plr.Player]..' <font color="rgb('..tostring(math.floor(color.R * 255))..','..tostring(math.floor(color.G * 255))..','..tostring(math.floor(color.B * 255))..')">'..math.round(plr.Humanoid.Health).."</font>"
			end
			if NameTagsDistance.Enabled then
				nametagstrs[plr.Player] = '<font color="rgb(85, 255, 85)">[</font><font color="rgb(255, 255, 255)">%s</font><font color="rgb(85, 255, 85)">]</font> '..nametagstrs[plr.Player]
			end
			local nametagSize = textService:GetTextSize(removeTags(nametagstrs[plr.Player]), thing.TextSize, thing.Font, Vector2.new(100000, 100000))
			thing.Size = UDim2.new(0, nametagSize.X + 4, 0, nametagSize.Y)
			thing.Text = nametagstrs[plr.Player]
			thing.TextColor3 = getPlayerColor(plr.Player) or Color3.fromHSV(NameTagsColor.Hue, NameTagsColor.Sat, NameTagsColor.Value)
			thing.Parent = NameTagsFolder
			nametagsfolderdrawing[plr.Player] = {entity = plr, Main = thing}
		end,
		Drawing = function(plr)
			if NameTagsTeammates.Enabled and (not plr.Targetable) and (not plr.Friend) then return end
			local thing = {Main = {}, entity = plr}
			thing.Main.Text = Drawing.new("Text")
			thing.Main.Text.Size = 17 * (NameTagsScale.Value / 10)
			thing.Main.Text.Font = (math.clamp((table.find(fontitems, NameTagsFont.Value) or 1) - 1, 0, 3))
			thing.Main.Text.ZIndex = 2
			thing.Main.BG = Drawing.new("Square")
			thing.Main.BG.Filled = true
			thing.Main.BG.Transparency = 0.5
			thing.Main.BG.Visible = NameTagsBackground.Enabled
			thing.Main.BG.Color = Color3.new()
			thing.Main.BG.ZIndex = 1
			nametagstrs[plr.Player] = whitelist:tag(plr.Player, true)..(NameTagsDisplayName.Enabled and plr.Player.DisplayName or plr.Player.Name)
			if NameTagsHealth.Enabled then
				local color = Color3.fromHSV(math.clamp(plr.Humanoid.Health / plr.Humanoid.MaxHealth, 0, 1) / 2.5, 0.89, 1)
				nametagstrs[plr.Player] = nametagstrs[plr.Player]..' '..math.round(plr.Humanoid.Health)
			end
			if NameTagsDistance.Enabled then
				nametagstrs[plr.Player] = '[%s] '..nametagstrs[plr.Player]
			end
			thing.Main.Text.Text = nametagstrs[plr.Player]
			thing.Main.BG.Size = Vector2.new(thing.Main.Text.TextBounds.X + 4, thing.Main.Text.TextBounds.Y)
			thing.Main.Text.Color = getPlayerColor(plr.Player) or Color3.fromHSV(NameTagsColor.Hue, NameTagsColor.Sat, NameTagsColor.Value)
			nametagsfolderdrawing[plr.Player] = thing
		end
	}

	local nametagfuncs2 = {
		Normal = function(ent)
			local v = nametagsfolderdrawing[ent]
			nametagsfolderdrawing[ent] = nil
			if v then
				v.Main:Destroy()
			end
		end,
		Drawing = function(ent)
			local v = nametagsfolderdrawing[ent]
			nametagsfolderdrawing[ent] = nil
			if v then
				for i2,v2 in pairs(v.Main) do
					pcall(function() v2.Visible = false v2:Remove() end)
				end
			end
		end
	}

	local nametagupdatefuncs = {
		Normal = function(ent)
			local v = nametagsfolderdrawing[ent.Player]
			if v then
				nametagstrs[ent.Player] = whitelist:tag(ent.Player, true)..(NameTagsDisplayName.Enabled and ent.Player.DisplayName or ent.Player.Name)
				if NameTagsHealth.Enabled then
					local color = Color3.fromHSV(math.clamp(ent.Humanoid.Health / ent.Humanoid.MaxHealth, 0, 1) / 2.5, 0.89, 1)
					nametagstrs[ent.Player] = nametagstrs[ent.Player]..' <font color="rgb('..tostring(math.floor(color.R * 255))..','..tostring(math.floor(color.G * 255))..','..tostring(math.floor(color.B * 255))..')">'..math.round(ent.Humanoid.Health).."</font>"
				end
				if NameTagsDistance.Enabled then
					nametagstrs[ent.Player] = '<font color="rgb(85, 255, 85)">[</font><font color="rgb(255, 255, 255)">%s</font><font color="rgb(85, 255, 85)">]</font> '..nametagstrs[ent.Player]
				end
				local nametagSize = textService:GetTextSize(removeTags(nametagstrs[ent.Player]), v.Main.TextSize, v.Main.Font, Vector2.new(100000, 100000))
				v.Main.Size = UDim2.new(0, nametagSize.X + 4, 0, nametagSize.Y)
				v.Main.Text = nametagstrs[ent.Player]
			end
		end,
		Drawing = function(ent)
			local v = nametagsfolderdrawing[ent.Player]
			if v then
				nametagstrs[ent.Player] = whitelist:tag(ent.Player, true)..(NameTagsDisplayName.Enabled and ent.Player.DisplayName or ent.Player.Name)
				if NameTagsHealth.Enabled then
					nametagstrs[ent.Player] = nametagstrs[ent.Player]..' '..math.round(ent.Humanoid.Health)
				end
				if NameTagsDistance.Enabled then
					nametagstrs[ent.Player] = '[%s] '..nametagstrs[ent.Player]
					v.Main.Text.Text = entityLibrary.isAlive and string.format(nametagstrs[ent.Player], math.floor((entityLibrary.character.HumanoidRootPart.Position - ent.RootPart.Position).Magnitude)) or nametagstrs[ent.Player]
				else
					v.Main.Text.Text = nametagstrs[ent.Player]
				end
				v.Main.BG.Size = Vector2.new(v.Main.Text.TextBounds.X + 4, v.Main.Text.TextBounds.Y)
				v.Main.Text.Color = getPlayerColor(ent.Player) or Color3.fromHSV(NameTagsColor.Hue, NameTagsColor.Sat, NameTagsColor.Value)
			end
		end
	}

	local nametagcolorfuncs = {
		Normal = function(hue, sat, value)
			local color = Color3.fromHSV(hue, sat, value)
			for i,v in pairs(nametagsfolderdrawing) do
				v.Main.TextColor3 = getPlayerColor(v.entity.Player) or color
			end
		end,
		Drawing = function(hue, sat, value)
			local color = Color3.fromHSV(hue, sat, value)
			for i,v in pairs(nametagsfolderdrawing) do
				v.Main.Text.Color = getPlayerColor(v.entity.Player) or color
			end
		end
	}

	local nametagloop = {
		Normal = function()
			for i,v in pairs(nametagsfolderdrawing) do
				local headPos, headVis = worldtoscreenpoint((v.entity.RootPart:GetRenderCFrame() * CFrame.new(0, v.entity.Head.Size.Y + v.entity.RootPart.Size.Y, 0)).Position)
				if not headVis then
					v.Main.Visible = false
					continue
				end
				if NameTagsDistance.Enabled and entityLibrary.isAlive then
					local mag = math.floor((entityLibrary.character.HumanoidRootPart.Position - v.entity.RootPart.Position).Magnitude)
					local stringsize = tostring(mag):len()
					if nametagsizes[v.entity.Player] ~= stringsize then
						local nametagSize = textService:GetTextSize(removeTags(string.format(nametagstrs[v.entity.Player], mag)), v.Main.TextSize, v.Main.Font, Vector2.new(100000, 100000))
						v.Main.Size = UDim2.new(0, nametagSize.X + 4, 0, nametagSize.Y)
					end
					nametagsizes[v.entity.Player] = stringsize
					v.Main.Text = string.format(nametagstrs[v.entity.Player], mag)
				end
				v.Main.Position = UDim2.new(0, headPos.X, 0, headPos.Y)
				v.Main.Visible = true
			end
		end,
		Drawing = function()
			for i,v in pairs(nametagsfolderdrawing) do
				local headPos, headVis = worldtoscreenpoint((v.entity.RootPart:GetRenderCFrame() * CFrame.new(0, v.entity.Head.Size.Y + v.entity.RootPart.Size.Y, 0)).Position)
				if not headVis then
					v.Main.Text.Visible = false
					v.Main.BG.Visible = false
					continue
				end
				if NameTagsDistance.Enabled and entityLibrary.isAlive then
					local mag = math.floor((entityLibrary.character.HumanoidRootPart.Position - v.entity.RootPart.Position).Magnitude)
					local stringsize = tostring(mag):len()
					v.Main.Text.Text = string.format(nametagstrs[v.entity.Player], mag)
					if nametagsizes[v.entity.Player] ~= stringsize then
						v.Main.BG.Size = Vector2.new(v.Main.Text.TextBounds.X + 4, v.Main.Text.TextBounds.Y)
					end
					nametagsizes[v.entity.Player] = stringsize
				end
				v.Main.BG.Position = Vector2.new(headPos.X - (v.Main.BG.Size.X / 2), (headPos.Y + v.Main.BG.Size.Y))
				v.Main.Text.Position = v.Main.BG.Position + Vector2.new(2, 0)
				v.Main.Text.Visible = true
				v.Main.BG.Visible = NameTagsBackground.Enabled
			end
		end
	}

	local methodused

	local NameTags = {Enabled = false}
	NameTags = GuiLibrary.ObjectsThatCanBeSaved.RenderWindow.Api.CreateOptionsButton({
		Name = "NameTags",
		Function = function(callback)
			if callback then
				methodused = NameTagsDrawing.Enabled and "Drawing" or "Normal"
				if nametagfuncs2[methodused] then
					table.insert(NameTags.Connections, entityLibrary.entityRemovedEvent:Connect(nametagfuncs2[methodused]))
				end
				if nametagfuncs1[methodused] then
					local addfunc = nametagfuncs1[methodused]
					for i,v in pairs(entityLibrary.entityList) do
						if nametagsfolderdrawing[v.Player] then nametagfuncs2[methodused](v.Player) end
						addfunc(v)
					end
					table.insert(NameTags.Connections, entityLibrary.entityAddedEvent:Connect(function(ent)
						if nametagsfolderdrawing[ent.Player] then nametagfuncs2[methodused](ent.Player) end
						addfunc(ent)
					end))
				end
				if nametagupdatefuncs[methodused] then
					table.insert(NameTags.Connections, entityLibrary.entityUpdatedEvent:Connect(nametagupdatefuncs[methodused]))
					for i,v in pairs(entityLibrary.entityList) do
						nametagupdatefuncs[methodused](v)
					end
				end
				if nametagcolorfuncs[methodused] then
					table.insert(NameTags.Connections, GuiLibrary.ObjectsThatCanBeSaved.FriendsListTextCircleList.Api.FriendColorRefresh.Event:Connect(function()
						nametagcolorfuncs[methodused](NameTagsColor.Hue, NameTagsColor.Sat, NameTagsColor.Value)
					end))
				end
				if nametagloop[methodused] then
					RunLoops:BindToRenderStep("NameTags", nametagloop[methodused])
				end
			else
				RunLoops:UnbindFromRenderStep("NameTags")
				if nametagfuncs2[methodused] then
					for i,v in pairs(nametagsfolderdrawing) do
						nametagfuncs2[methodused](i)
					end
				end
			end
		end,
		HoverText = "Renders nametags on entities through walls."
	})
	for i,v in pairs(Enum.Font:GetEnumItems()) do
		if v.Name ~= "SourceSans" then
			table.insert(fontitems, v.Name)
		end
	end
	NameTagsFont = NameTags.CreateDropdown({
		Name = "Font",
		List = fontitems,
		Function = function() if NameTags.Enabled then NameTags.ToggleButton(false) NameTags.ToggleButton(false) end end,
	})
	NameTagsColor = NameTags.CreateColorSlider({
		Name = "Player Color",
		Function = function(hue, sat, val)
			if NameTags.Enabled and nametagcolorfuncs[methodused] then
				nametagcolorfuncs[methodused](hue, sat, val)
			end
		end
	})
	NameTagsScale = NameTags.CreateSlider({
		Name = "Scale",
		Function = function() if NameTags.Enabled then NameTags.ToggleButton(false) NameTags.ToggleButton(false) end end,
		Default = 10,
		Min = 1,
		Max = 50
	})
	NameTagsBackground = NameTags.CreateToggle({
		Name = "Background",
		Function = function() if NameTags.Enabled then NameTags.ToggleButton(false) NameTags.ToggleButton(false) end end,
		Default = true
	})
	NameTagsDisplayName = NameTags.CreateToggle({
		Name = "Use Display Name",
		Function = function() if NameTags.Enabled then NameTags.ToggleButton(false) NameTags.ToggleButton(false) end end,
		Default = true
	})
	NameTagsHealth = NameTags.CreateToggle({
		Name = "Health",
		Function = function() if NameTags.Enabled then NameTags.ToggleButton(false) NameTags.ToggleButton(false) end end
	})
	NameTagsDistance = NameTags.CreateToggle({
		Name = "Distance",
		Function = function() if NameTags.Enabled then NameTags.ToggleButton(false) NameTags.ToggleButton(false) end end
	})
	NameTagsTeammates = NameTags.CreateToggle({
		Name = "Teammates",
		Function = function() if NameTags.Enabled then NameTags.ToggleButton(false) NameTags.ToggleButton(false) end end,
		Default = true
	})
	NameTagsDrawing = NameTags.CreateToggle({
		Name = "Drawing",
		Function = function() if NameTags.Enabled then NameTags.ToggleButton(false) NameTags.ToggleButton(false) end end,
	})
end)

run(function()
	local Search = {Enabled = false}
	local SearchTextList = {RefreshValues = function() end, ObjectList = {}}
	local SearchColor = {Value = 0.44}
	local SearchFolder = Instance.new("Folder")
	SearchFolder.Name = "SearchFolder"
	SearchFolder.Parent = GuiLibrary.MainGui
	local function searchFindBoxHandle(part)
		for i,v in pairs(SearchFolder:GetChildren()) do
			if v.Adornee == part then
				return v
			end
		end
		return nil
	end
	local searchRefresh = function()
		SearchFolder:ClearAllChildren()
		if Search.Enabled then
			for i,v in pairs(workspace:GetDescendants()) do
				if (v:IsA("BasePart") or v:IsA("Model")) and table.find(SearchTextList.ObjectList, v.Name) and searchFindBoxHandle(v) == nil then
					local highlight = Instance.new("Highlight")
					highlight.Name = v.Name
					highlight.DepthMode = Enum.HighlightDepthMode.AlwaysOnTop
					highlight.FillColor = Color3.fromHSV(SearchColor.Hue, SearchColor.Sat, SearchColor.Value)
					highlight.Adornee = v
					highlight.Parent = SearchFolder
				end
			end
		end
	end
	Search = GuiLibrary.ObjectsThatCanBeSaved.RenderWindow.Api.CreateOptionsButton({
		Name = "Search",
		Function = function(callback)
			if callback then
				searchRefresh()
				table.insert(Search.Connections, workspace.DescendantAdded:Connect(function(v)
					if (v:IsA("BasePart") or v:IsA("Model")) and table.find(SearchTextList.ObjectList, v.Name) and searchFindBoxHandle(v) == nil then
						local highlight = Instance.new("Highlight")
						highlight.Name = v.Name
						highlight.DepthMode = Enum.HighlightDepthMode.AlwaysOnTop
						highlight.FillColor = Color3.fromHSV(SearchColor.Hue, SearchColor.Sat, SearchColor.Value)
						highlight.Adornee = v
						highlight.Parent = SearchFolder
					end
				end))
				table.insert(Search.Connections, workspace.DescendantRemoving:Connect(function(v)
					if v:IsA("BasePart") or v:IsA("Model") then
						local boxhandle = searchFindBoxHandle(v)
						if boxhandle then
							boxhandle:Remove()
						end
					end
				end))
			else
				SearchFolder:ClearAllChildren()
			end
		end,
		HoverText = "Draws a box around selected parts\nAdd parts in Search frame"
	})
	SearchColor = Search.CreateColorSlider({
		Name = "new part color",
		Function = function(hue, sat, val)
			for i,v in pairs(SearchFolder:GetChildren()) do
				v.FillColor = Color3.fromHSV(hue, sat, val)
			end
		end
	})
	SearchTextList = Search.CreateTextList({
		Name = "SearchList",
		TempText = "part name",
		AddFunction = function(user)
			searchRefresh()
		end,
		RemoveFunction = function(num)
			searchRefresh()
		end
	})
end)

run(function()
	local Xray = {Enabled = false}
	Xray = GuiLibrary.ObjectsThatCanBeSaved.WorldWindow.Api.CreateOptionsButton({
		Name = "Xray",
		Function = function(callback)
			if callback then
				table.insert(Xray.Connections, workspace.DescendantAdded:Connect(function(v)
					if v:IsA("BasePart") and not v.Parent:FindFirstChild("Humanoid") and not v.Parent.Parent:FindFirstChild("Humanoid") then
						v.LocalTransparencyModifier = 0.5
					end
				end))
				for i, v in pairs(workspace:GetDescendants()) do
					if v:IsA("BasePart") and not v.Parent:FindFirstChild("Humanoid") and not v.Parent.Parent:FindFirstChild("Humanoid") then
						v.LocalTransparencyModifier = 0.5
					end
				end
			else
				for i, v in pairs(workspace:GetDescendants()) do
					if v:IsA("BasePart") and not v.Parent:FindFirstChild("Humanoid") and not v.Parent.Parent:FindFirstChild("Humanoid") then
						v.LocalTransparencyModifier = 0
					end
				end
			end
		end
	})
end)

run(function()
	local TracersColor = {Value = 0.44}
	local TracersTransparency = {Value = 1}
	local TracersStartPosition = {Value = "Middle"}
	local TracersEndPosition = {Value = "Head"}
	local TracersTeammates = {Enabled = true}
	local tracersfolderdrawing = {}
	local methodused

	local tracersfuncs1 = {
		Drawing = function(plr)
			if TracersTeammates.Enabled and (not plr.Targetable) and (not plr.Friend) then return end
			local newobj = Drawing.new("Line")
			newobj.Thickness = 1
			newobj.Transparency = 1 - (TracersTransparency.Value / 100)
			newobj.Color = getPlayerColor(plr.Player) or Color3.fromHSV(TracersColor.Hue, TracersColor.Sat, TracersColor.Value)
			tracersfolderdrawing[plr.Player] = {entity = plr, Main = newobj}
		end,
		DrawingV3 = function(plr)
			if TracersTeammates.Enabled and (not plr.Targetable) and (not plr.Friend) then return end
			local toppoint = PointInstance.new(plr[TracersEndPosition.Value == "Torso" and "RootPart" or "Head"])
			local bottompoint = TracersStartPosition.Value == "Mouse" and PointMouse.new() or Point2D.new(UDim2.new(0.5, 0, TracersStartPosition.Value == "Middle" and 0.5 or 1, 0))
			local newobj = LineDynamic.new(toppoint, bottompoint)
			newobj.Opacity = 1 - (TracersTransparency.Value / 100)
			newobj.Color = getPlayerColor(plr.Player) or Color3.fromHSV(TracersColor.Hue, TracersColor.Sat, TracersColor.Value)
			tracersfolderdrawing[plr.Player] = {entity = plr, Main = newobj}
		end,
	}
	local tracersfuncs2 = {
		Drawing = function(ent)
			local v = tracersfolderdrawing[ent]
			tracersfolderdrawing[ent] = nil
			if v then
				pcall(function() v.Main.Visible = false v.Main:Remove() end)
			end
		end,
	}
	local tracerscolorfuncs = {
		Drawing = function(hue, sat, value)
			local color = Color3.fromHSV(hue, sat, value)
			for i,v in pairs(tracersfolderdrawing) do
				v.Main.Color = getPlayerColor(v.entity.Player) or color
			end
		end
	}
	tracerscolorfuncs.DrawingV3 = tracerscolorfuncs.Drawing
	tracersfuncs2.DrawingV3 = tracersfuncs2.Drawing
	local tracersloop = {
		Drawing = function()
			for i,v in pairs(tracersfolderdrawing) do
				local rootPart = v.entity[TracersEndPosition.Value == "Torso" and "RootPart" or "Head"].Position
				local rootPos, rootVis = worldtoviewportpoint(rootPart)
				local screensize = gameCamera.ViewportSize
				local startVector = TracersStartPosition.Value == "Mouse" and inputService:GetMouseLocation() or Vector2.new(screensize.X / 2, (TracersStartPosition.Value == "Middle" and screensize.Y / 2 or screensize.Y))
				local endVector = Vector2.new(rootPos.X, rootPos.Y)
				v.Main.Visible = rootVis
				v.Main.From = startVector
				v.Main.To = endVector
			end
		end,
	}

	local Tracers = {Enabled = false}
	Tracers = GuiLibrary.ObjectsThatCanBeSaved.RenderWindow.Api.CreateOptionsButton({
		Name = "Tracers",
		Function = function(callback)
			if callback then
				methodused = "Drawing"..synapsev3
				if tracersfuncs2[methodused] then
					table.insert(Tracers.Connections, entityLibrary.entityRemovedEvent:Connect(tracersfuncs2[methodused]))
				end
				if tracersfuncs1[methodused] then
					local addfunc = tracersfuncs1[methodused]
					for i,v in pairs(entityLibrary.entityList) do
						if tracersfolderdrawing[v.Player] then tracersfuncs2[methodused](v.Player) end
						addfunc(v)
					end
					table.insert(Tracers.Connections, entityLibrary.entityAddedEvent:Connect(function(ent)
						if tracersfolderdrawing[ent.Player] then tracersfuncs2[methodused](ent.Player) end
						addfunc(ent)
					end))
				end
				if tracerscolorfuncs[methodused] then
					table.insert(Tracers.Connections, GuiLibrary.ObjectsThatCanBeSaved.FriendsListTextCircleList.Api.FriendColorRefresh.Event:Connect(function()
						tracerscolorfuncs[methodused](TracersColor.Hue, TracersColor.Sat, TracersColor.Value)
					end))
				end
				if tracersloop[methodused] then
					RunLoops:BindToRenderStep("Tracers", tracersloop[methodused])
				end
			else
				RunLoops:UnbindFromRenderStep("Tracers")
				for i,v in pairs(tracersfolderdrawing) do
					if tracersfuncs2[methodused] then
						tracersfuncs2[methodused](i)
					end
				end
			end
		end,
		HoverText = "Extra Sensory Perception\nRenders an Tracers on players."
	})
	TracersStartPosition = Tracers.CreateDropdown({
		Name = "Start Position",
		List = {"Middle", "Bottom", "Mouse"},
		Function = function() if Tracers.Enabled then Tracers.ToggleButton(true) Tracers.ToggleButton(true) end end
	})
	TracersEndPosition = Tracers.CreateDropdown({
		Name = "End Position",
		List = {"Head", "Torso"},
		Function = function() if Tracers.Enabled then Tracers.ToggleButton(true) Tracers.ToggleButton(true) end end
	})
	TracersColor = Tracers.CreateColorSlider({
		Name = "Player Color",
		Function = function(hue, sat, val)
			if Tracers.Enabled and tracerscolorfuncs[methodused] then
				tracerscolorfuncs[methodused](hue, sat, val)
			end
		end
	})
	TracersTransparency = Tracers.CreateSlider({
		Name = "Transparency",
		Min = 1,
		Max = 100,
		Function = function(val)
			for i,v in pairs(tracersfolderdrawing) do
				if v.Main then
					v.Main[methodused == "DrawingV3" and "Opacity" or "Transparency"] = 1 - (val / 100)
				end
			end
		end,
		Default = 0
	})
	TracersTeammates = Tracers.CreateToggle({
		Name = "Priority Only",
		Function = function() if Tracers.Enabled then Tracers.ToggleButton(true) Tracers.ToggleButton(true) end end,
		Default = true
	})
end)

run(function()
	Spring = {} do
		Spring.__index = Spring

		function Spring.new(freq, pos)
			local self = setmetatable({}, Spring)
			self.f = freq
			self.p = pos
			self.v = pos*0
			return self
		end

		function Spring:Update(dt, goal)
			local f = self.f*2*math.pi
			local p0 = self.p
			local v0 = self.v

			local offset = goal - p0
			local decay = math.exp(-f*dt)

			local p1 = goal + (v0*dt - offset*(f*dt + 1))*decay
			local v1 = (f*dt*(offset*f - v0) + v0)*decay

			self.p = p1
			self.v = v1

			return p1
		end

		function Spring:Reset(pos)
			self.p = pos
			self.v = pos*0
		end
	end

	local cameraPos = Vector3.zero
	local cameraRot = Vector2.new()
	local velSpring = Spring.new(5, Vector3.zero)
	local panSpring = Spring.new(5, Vector2.new())

	Input = {} do

		keyboard = {
			W = 0,
			A = 0,
			S = 0,
			D = 0,
			E = 0,
			Q = 0,
			Up = 0,
			Down = 0,
			LeftShift = 0,
		}

		mouse = {
			Delta = Vector2.new(),
		}

		NAV_KEYBOARD_SPEED = Vector3.new(1, 1, 1)
		PAN_MOUSE_SPEED = Vector2.new(3, 3)*(math.pi/64)
		NAV_ADJ_SPEED = 0.75
		NAV_SHIFT_MUL = 0.25

		navSpeed = 1

		function Input.Vel(dt)
			navSpeed = math.clamp(navSpeed + dt*(keyboard.Up - keyboard.Down)*NAV_ADJ_SPEED, 0.01, 4)

			local kKeyboard = Vector3.new(
				keyboard.D - keyboard.A,
				keyboard.E - keyboard.Q,
				keyboard.S - keyboard.W
			)*NAV_KEYBOARD_SPEED

			local shift = inputService:IsKeyDown(Enum.KeyCode.LeftShift)

			return (kKeyboard)*(navSpeed*(shift and NAV_SHIFT_MUL or 1))
		end

		function Input.Pan(dt)
			local kMouse = mouse.Delta*PAN_MOUSE_SPEED
			mouse.Delta = Vector2.new()
			return kMouse
		end

		do
			function Keypress(action, state, input)
				keyboard[input.KeyCode.Name] = state == Enum.UserInputState.Begin and 1 or 0
				return Enum.ContextActionResult.Sink
			end

			function MousePan(action, state, input)
				local delta = input.Delta
				mouse.Delta = Vector2.new(-delta.y, -delta.x)
				return Enum.ContextActionResult.Sink
			end

			function Zero(t)
				for k, v in pairs(t) do
					t[k] = v*0
				end
			end

			function Input.StartCapture()
				game:GetService("ContextActionService"):BindActionAtPriority("FreecamKeyboard",Keypress,false,Enum.ContextActionPriority.High.Value,
				Enum.KeyCode.W,
				Enum.KeyCode.A,
				Enum.KeyCode.S,
				Enum.KeyCode.D,
				Enum.KeyCode.E,
				Enum.KeyCode.Q,
				Enum.KeyCode.Up,
				Enum.KeyCode.Down
				)
				game:GetService("ContextActionService"):BindActionAtPriority("FreecamMousePan",MousePan,false,Enum.ContextActionPriority.High.Value,Enum.UserInputType.MouseMovement)
			end

			function Input.StopCapture()
				navSpeed = 1
				Zero(keyboard)
				Zero(mouse)
				game:GetService("ContextActionService"):UnbindAction("FreecamKeyboard")
				game:GetService("ContextActionService"):UnbindAction("FreecamMousePan")
			end
		end
	end

	local function GetFocusDistance(cameraFrame)
		local znear = 0.1
		local viewport = gameCamera.ViewportSize
		local projy = 2*math.tan(cameraFov/2)
		local projx = viewport.x/viewport.y*projy
		local fx = cameraFrame.rightVector
		local fy = cameraFrame.upVector
		local fz = cameraFrame.lookVector

		local minVect = Vector3.zero
		local minDist = 512

		for x = 0, 1, 0.5 do
			for y = 0, 1, 0.5 do
				local cx = (x - 0.5)*projx
				local cy = (y - 0.5)*projy
				local offset = fx*cx - fy*cy + fz
				local origin = cameraFrame.p + offset*znear
				local _, hit = workspace:FindPartOnRay(Ray.new(origin, offset.unit*minDist))
				local dist = (hit - origin).magnitude
				if minDist > dist then
					minDist = dist
					minVect = offset.unit
				end
			end
		end

		return fz:Dot(minVect)*minDist
	end

	local playerstate = {} do
		mouseBehavior = ""
		mouseIconEnabled = ""
		cameraType = ""
		cameraFocus = ""
		cameraCFrame = ""
		cameraFieldOfView = ""

		function playerstate.Push()
			cameraFieldOfView = gameCamera.FieldOfView
			gameCamera.FieldOfView = 70

			cameraType = gameCamera.CameraType
			gameCamera.CameraType = Enum.CameraType.Custom

			cameraCFrame = gameCamera.CFrame
			cameraFocus = gameCamera.Focus

			mouseBehavior = inputService.MouseBehavior
			inputService.MouseBehavior = Enum.MouseBehavior.Default

			mouseIconEnabled = inputService.MouseIconEnabled
			inputService.MouseIconEnabled = true
		end

		function playerstate.Pop()
			gameCamera.FieldOfView = cameraFieldOfView
			cameraFieldOfView = nil

			gameCamera.CameraType = cameraType
			cameraType = nil

			gameCamera.CFrame = cameraCFrame
			cameraCFrame = nil

			gameCamera.Focus = cameraFocus
			cameraFocus = nil

			inputService.MouseIconEnabled = mouseIconEnabled
			mouseIconEnabled = nil

			inputService.MouseBehavior = mouseBehavior
			mouseBehavior = nil
		end
	end

	local Freecam = GuiLibrary.ObjectsThatCanBeSaved.WorldWindow.Api.CreateOptionsButton({
		Name = "Freecam",
		Function = function(callback)
			if callback then
				local cameraCFrame = gameCamera.CFrame
				local pitch, yaw, roll = cameraCFrame:ToEulerAnglesYXZ()
				cameraRot = Vector2.new(pitch, yaw)
				cameraPos = cameraCFrame.p
				cameraFov = gameCamera.FieldOfView

				velSpring:Reset(Vector3.zero)
				panSpring:Reset(Vector2.new())

				playerstate.Push()
				RunLoops:BindToRenderStep("Freecam", function(dt)
					local vel = velSpring:Update(dt, Input.Vel(dt))
					local pan = panSpring:Update(dt, Input.Pan(dt))

					local zoomFactor = math.sqrt(math.tan(math.rad(70/2))/math.tan(math.rad(cameraFov/2)))

					cameraRot = cameraRot + pan*Vector2.new(0.75, 1)*8*(dt/zoomFactor)
					cameraRot = Vector2.new(math.clamp(cameraRot.x, -math.rad(90), math.rad(90)), cameraRot.y%(2*math.pi))

					local cameraCFrame = CFrame.new(cameraPos)*CFrame.fromOrientation(cameraRot.x, cameraRot.y, 0)*CFrame.new(vel*Vector3.new(1, 1, 1)*64*dt)
					cameraPos = cameraCFrame.p

					gameCamera.CFrame = cameraCFrame
					gameCamera.Focus = cameraCFrame*CFrame.new(0, 0, -GetFocusDistance(cameraCFrame))
					gameCamera.FieldOfView = cameraFov
				end)
				Input.StartCapture()
			else
				Input.StopCapture()
				RunLoops:UnbindFromRenderStep("Freecam")
				playerstate.Pop()
			end
		end,
		HoverText = "Lets you fly and clip through walls freely\nwithout moving your player server-sided."
	})
	Freecam.CreateSlider({
		Name = "Speed",
		Min = 1,
		Max = 150,
		Function = function(val) NAV_KEYBOARD_SPEED = Vector3.new(val / 75,  val / 75, val / 75) end,
		Default = 75
	})
end)

run(function()
	local Panic = GuiLibrary.ObjectsThatCanBeSaved.UtilityWindow.Api.CreateOptionsButton({
		Name = "Panic",
		Function = function(callback)
			if callback then
				for i,v in pairs(GuiLibrary.ObjectsThatCanBeSaved) do
					if v.Type == "OptionsButton" then
						if v.Api.Enabled then
							v.Api.ToggleButton()
						end
					end
				end
			end
		end
	})
end)

run(function()
	local ChatSpammer = {Enabled = false}
	local ChatSpammerDelay = {Value = 10}
	local ChatSpammerHideWait = {Enabled = true}
	local ChatSpammerMessages = {ObjectList = {}}
	local chatspammerfirstexecute = true
	local chatspammerhook = false
	local oldchanneltab
	local oldchannelfunc
	local oldchanneltabs = {}
	local waitnum = 0
	ChatSpammer = GuiLibrary.ObjectsThatCanBeSaved.UtilityWindow.Api.CreateOptionsButton({
		Name = "ChatSpammer",
		Function = function(callback)
			if callback then
				if textChatService.ChatVersion == Enum.ChatVersion.TextChatService then
					task.spawn(function()
						repeat
							if ChatSpammer.Enabled then
								pcall(function()
									textChatService.ChatInputBarConfiguration.TargetTextChannel:SendAsync((#ChatSpammerMessages.ObjectList > 0 and ChatSpammerMessages.ObjectList[math.random(1, #ChatSpammerMessages.ObjectList)] or "vxpe on top"))
								end)
							end
							if waitnum ~= 0 then
								task.wait(waitnum)
								waitnum = 0
							else
								task.wait(ChatSpammerDelay.Value / 10)
							end
						until not ChatSpammer.Enabled
					end)
				else
					task.spawn(function()
						if chatspammerfirstexecute then
							lplr.PlayerGui:WaitForChild("Chat", 10)
							chatspammerfirstexecute = false
						end
						if lplr.PlayerGui:FindFirstChild("Chat") and lplr.PlayerGui.Chat:FindFirstChild("Frame") and lplr.PlayerGui.Chat.Frame:FindFirstChild("ChatChannelParentFrame") and replicatedStorage:FindFirstChild("DefaultChatSystemChatEvents") then
							if not chatspammerhook then
								task.spawn(function()
									chatspammerhook = true
									for i,v in pairs(getconnections(replicatedStorage.DefaultChatSystemChatEvents.OnNewMessage.OnClientEvent)) do
										if v.Function and #debug.getupvalues(v.Function) > 0 and type(debug.getupvalues(v.Function)[1]) == "table" and getmetatable(debug.getupvalues(v.Function)[1]) and getmetatable(debug.getupvalues(v.Function)[1]).GetChannel then
											oldchanneltab = getmetatable(debug.getupvalues(v.Function)[1])
											oldchannelfunc = getmetatable(debug.getupvalues(v.Function)[1]).GetChannel
											getmetatable(debug.getupvalues(v.Function)[1]).GetChannel = function(Self, Name)
												local tab = oldchannelfunc(Self, Name)
												if tab and tab.AddMessageToChannel then
													local addmessage = tab.AddMessageToChannel
													if oldchanneltabs[tab] == nil then
														oldchanneltabs[tab] = tab.AddMessageToChannel
													end
													tab.AddMessageToChannel = function(Self2, MessageData)
														if MessageData.MessageType == "System" then
															if MessageData.Message:find("You must wait") and ChatSpammer.Enabled then
																return nil
															end
														end
														return addmessage(Self2, MessageData)
													end
												end
												return tab
											end
										end
									end
								end)
							end
							task.spawn(function()
								repeat
									pcall(function()
										replicatedStorage.DefaultChatSystemChatEvents.SayMessageRequest:FireServer((#ChatSpammerMessages.ObjectList > 0 and ChatSpammerMessages.ObjectList[math.random(1, #ChatSpammerMessages.ObjectList)] or "vxpe on top"), "All")
									end)
									if waitnum ~= 0 then
										task.wait(waitnum)
										waitnum = 0
									else
										task.wait(ChatSpammerDelay.Value / 10)
									end
								until not ChatSpammer.Enabled
							end)
						else
							warningNotification("ChatSpammer", "Default chat not found.", 3)
							if ChatSpammer.Enabled then ChatSpammer.ToggleButton(false) end
						end
					end)
				end
			else
				waitnum = 0
			end
		end,
		HoverText = "Spams chat with text of your choice (Default Chat Only)"
	})
	ChatSpammerDelay = ChatSpammer.CreateSlider({
		Name = "Delay",
		Min = 1,
		Max = 50,
		Default = 10,
		Function = function() end
	})
	ChatSpammerHideWait = ChatSpammer.CreateToggle({
		Name = "Hide Wait Message",
		Function = function() end,
		Default = true
	})
	ChatSpammerMessages = ChatSpammer.CreateTextList({
		Name = "Message",
		TempText = "message to spam",
		Function = function() end
	})
end)

run(function()
	local controlmodule
	local oldmove
	local SafeWalk = {Enabled = false}
	local SafeWalkRaycast = RaycastParams.new()
	SafeWalkRaycast.RespectCanCollide = true
	SafeWalkRaycast.FilterType = Enum.RaycastFilterType.Blacklist
	SafeWalk = GuiLibrary.ObjectsThatCanBeSaved.WorldWindow.Api.CreateOptionsButton({
		Name = "SafeWalk",
		Function = function(callback)
			if callback then
				if not controlmodule then
					local suc = pcall(function() controlmodule = require(lplr.PlayerScripts.PlayerModule).controls end)
					if not suc then controlmodule = {} end
				end
				oldmove = controlmodule.moveFunction
				controlmodule.moveFunction = function(Self, vec, facecam)
					if entityLibrary.isAlive then
						SafeWalkRaycast.FilterDescendantsInstances = {lplr.Character}
						local ray = workspace:Raycast(entityLibrary.character.HumanoidRootPart.Position + (vec * 0.5), Vector3.new(0, -1000, 0), SafeWalkRaycast)
						if not ray then
							if workspace:Raycast(entityLibrary.character.HumanoidRootPart.Position, Vector3.new(0, -((entityLibrary.character.Humanoid.HipHeight + (entityLibrary.character.HumanoidRootPart.Size.Y / 2)) + 1), 0), SafeWalkRaycast) then
								vec = Vector3.zero
							end
						end
					end
					return oldmove(Self, vec, facecam)
				end
			else
				controlmodule.moveFunction = oldmove
			end
		end,
		HoverText = "lets you not walk off because you are bad"
	})
end)

run(function()
	local function capeFunction(char, texture)
		for i,v in pairs(char:GetDescendants()) do
			if v.Name == "Cape" then
				v:Destroy()
			end
		end
		local hum = char:WaitForChild("Humanoid")
		local torso = nil
		if hum.RigType == Enum.HumanoidRigType.R15 then
			torso = char:WaitForChild("UpperTorso")
		else
			torso = char:WaitForChild("Torso")
		end
		local p = Instance.new("Part", torso.Parent)
		p.Name = "Cape"
		p.Anchored = false
		p.CanCollide = false
		p.TopSurface = 0
		p.BottomSurface = 0
		p.FormFactor = "Custom"
		p.Size = Vector3.new(0.2,0.2,0.08)
		p.Transparency = 1
		local decal
		local video = false
		if texture:find(".webm") then
			video = true
			local decal2 = Instance.new("SurfaceGui", p)
			decal2.Adornee = p
			decal2.CanvasSize = Vector2.new(1, 1)
			decal2.Face = "Back"
			decal = Instance.new("VideoFrame", decal2)
			decal.Size = UDim2.new(0, 9, 0, 17)
			decal.BackgroundTransparency = 1
			decal.Position = UDim2.new(0, -4, 0, -8)
			decal.Video = texture
			decal.Looped = true
			decal:Play()
		else
			decal = Instance.new("Decal", p)
			decal.Texture = texture
			decal.Face = "Back"
		end
		local msh = Instance.new("BlockMesh", p)
		msh.Scale = Vector3.new(9, 17.5, 0.5)
		local motor = Instance.new("Motor", p)
		motor.Part0 = p
		motor.Part1 = torso
		motor.MaxVelocity = 0.01
		motor.C0 = CFrame.new(0, 2, 0) * CFrame.Angles(0, math.rad(90), 0)
		motor.C1 = CFrame.new(0, 1, 0.45) * CFrame.Angles(0, math.rad(90), 0)
		local wave = false
		repeat task.wait(1/44)
			if video then
				decal.Visible = torso.LocalTransparencyModifier ~= 1
			else
				decal.Transparency = torso.Transparency
			end
			local ang = 0.1
			local oldmag = torso.Velocity.magnitude
			local mv = 0.002
			if wave then
				ang = ang + ((torso.Velocity.magnitude/10) * 0.05) + 0.05
				wave = false
			else
				wave = true
			end
			ang = ang + math.min(torso.Velocity.magnitude/11, 0.5)
			motor.MaxVelocity = math.min((torso.Velocity.magnitude/111), 0.04) --+ mv
			motor.DesiredAngle = -ang
			if motor.CurrentAngle < -0.2 and motor.DesiredAngle > -0.2 then
				motor.MaxVelocity = 0.04
			end
			repeat task.wait() until motor.CurrentAngle == motor.DesiredAngle or math.abs(torso.Velocity.magnitude - oldmag) >= (torso.Velocity.magnitude/10) + 1
			if torso.Velocity.magnitude < 0.1 then
				task.wait(0.1)
			end
		until not p or p.Parent ~= torso.Parent
	end

	local Cape = {Enabled = false}
	local CapeBox = {Value = ""}
	Cape = GuiLibrary.ObjectsThatCanBeSaved.RenderWindow.Api.CreateOptionsButton({
		Name = "Cape",
		Function = function(callback)
			if callback then
				local successfulcustom
				if CapeBox.Value ~= "" then
					if (tonumber(CapeBox.Value)) then
						local suc, id = pcall(function() return string.match(game:GetObjects("rbxassetid://"..CapeBox.Value)[1].Texture, "%?id=(%d+)") end)
						if not suc then
							id = CapeBox.Value
						end
						successfulcustom = "rbxassetid://"..id
					elseif (not isfile(CapeBox.Value)) then
						warningNotification("Cape", "Missing file", 5)
					else
						successfulcustom = CapeBox.Value:find(".") and getcustomasset(CapeBox.Value) or CapeBox.Value
					end
				end
				table.insert(Cape.Connections, lplr.CharacterAdded:Connect(function(char)
					task.spawn(function()
						pcall(function()
							capeFunction(char, (successfulcustom or downloadVapeAsset("vape/assets/VapeCape.png")))
						end)
					end)
				end))
				if lplr.Character then
					task.spawn(function()
						pcall(function()
							capeFunction(lplr.Character, (successfulcustom or downloadVapeAsset("vape/assets/VapeCape.png")))
						end)
					end)
				end
			else
				if lplr.Character then
					for i,v in pairs(lplr.Character:GetDescendants()) do
						if v.Name == "Cape" then
							v:Destroy()
						end
					end
				end
			end
		end
	})
	CapeBox = Cape.CreateTextBox({
		Name = "File",
		TempText = "File (link)",
		FocusLost = function(enter)
			if enter then
				if Cape.Enabled then
					Cape.ToggleButton(false)
					Cape.ToggleButton(false)
				end
			end
		end
	})
end)

run(function()
	local ChinaHat = {Enabled = false}
	local ChinaHatColor = {Hue = 1, Sat=1, Value=0.33}
	local chinahattrail
	local chinahatattachment
	local chinahatattachment2
	ChinaHat = GuiLibrary.ObjectsThatCanBeSaved.RenderWindow.Api.CreateOptionsButton({
		Name = "ChinaHat",
		Function = function(callback)
			if callback then
				RunLoops:BindToHeartbeat("ChinaHat", function()
					if entityLibrary.isAlive then
						if chinahattrail == nil or chinahattrail.Parent == nil then
							chinahattrail = Instance.new("Part")
							chinahattrail.CFrame = entityLibrary.character.Head.CFrame * CFrame.new(0, 1.1, 0)
							chinahattrail.Size = Vector3.new(3, 0.7, 3)
							chinahattrail.Name = "ChinaHat"
							chinahattrail.Material = Enum.Material.Neon
							chinahattrail.Color = Color3.fromHSV(ChinaHatColor.Hue, ChinaHatColor.Sat, ChinaHatColor.Value)
							chinahattrail.CanCollide = false
							chinahattrail.Transparency = 0.3
							local chinahatmesh = Instance.new("SpecialMesh")
							chinahatmesh.Parent = chinahattrail
							chinahatmesh.MeshType = "FileMesh"
							chinahatmesh.MeshId = "http://www.roblox.com/asset/?id=1778999"
							chinahatmesh.Scale = Vector3.new(3, 0.6, 3)
							chinahattrail.Parent = workspace.Camera
						end
						chinahattrail.CFrame = entityLibrary.character.Head.CFrame * CFrame.new(0, 1.1, 0)
						chinahattrail.Velocity = Vector3.zero
						chinahattrail.LocalTransparencyModifier = ((gameCamera.CFrame.Position - gameCamera.Focus.Position).Magnitude <= 0.6 and 1 or 0)
					else
						if chinahattrail then
							chinahattrail:Destroy()
							chinahattrail = nil
						end
					end
				end)
			else
				RunLoops:UnbindFromHeartbeat("ChinaHat")
				if chinahattrail then
					chinahattrail:Destroy()
					chinahattrail = nil
				end
			end
		end,
		HoverText = "Puts a china hat on your character (mastadawn ty for)"
	})
	ChinaHatColor = ChinaHat.CreateColorSlider({
		Name = "Hat Color",
		Function = function(h, s, v)
			if chinahattrail then
				chinahattrail.Color = Color3.fromHSV(h, s, v)
			end
		end
	})
end)

run(function()
	local FieldOfView = {Enabled = false}
	local FieldOfViewZoom = {Enabled = false}
	local FieldOfViewValue = {Value = 70}
	local oldfov
	FieldOfView = GuiLibrary.ObjectsThatCanBeSaved.RenderWindow.Api.CreateOptionsButton({
		Name = "FOVChanger",
		Function = function(callback)
			if callback then
				oldfov = gameCamera.FieldOfView
				if FieldOfViewZoom.Enabled then
					task.spawn(function()
						repeat
							task.wait()
						until inputService:IsKeyDown(Enum.KeyCode[FieldOfView.Keybind ~= "" and FieldOfView.Keybind or "C"]) == false
						if FieldOfView.Enabled then
							FieldOfView.ToggleButton(false)
						end
					end)
				end
				task.spawn(function()
					repeat
						gameCamera.FieldOfView = FieldOfViewValue.Value
						task.wait()
					until (not FieldOfView.Enabled)
				end)
			else
				gameCamera.FieldOfView = oldfov
			end
		end
	})
	FieldOfViewValue = FieldOfView.CreateSlider({
		Name = "FOV",
		Min = 30,
		Max = 120,
		Function = function(val) end
	})
	FieldOfViewZoom = FieldOfView.CreateToggle({
		Name = "Zoom",
		Function = function() end,
		HoverText = "optifine zoom lol"
	})
end)

run(function()
	local Swim = {Enabled = false}
	local SwimVertical = {Value = 1}
	local swimconnection
	local oldgravity

	Swim = GuiLibrary.ObjectsThatCanBeSaved.BlatantWindow.Api.CreateOptionsButton({
		Name = "Swim",
		Function = function(callback)
			if callback then
				oldgravity = workspace.Gravity
				if entityLibrary.isAlive then
					GravityChangeTick = tick() + 0.1
					workspace.Gravity = 0
					local enums = Enum.HumanoidStateType:GetEnumItems()
					table.remove(enums, table.find(enums, Enum.HumanoidStateType.None))
					for i,v in pairs(enums) do
						entityLibrary.character.Humanoid:SetStateEnabled(v, false)
					end
					entityLibrary.character.Humanoid:ChangeState(Enum.HumanoidStateType.Swimming)
					RunLoops:BindToHeartbeat("Swim", function()
						local rootvelo = entityLibrary.character.HumanoidRootPart.Velocity
						local moving = entityLibrary.character.Humanoid.MoveDirection ~= Vector3.zero
						entityLibrary.character.HumanoidRootPart.Velocity = ((moving or inputService:IsKeyDown(Enum.KeyCode.Space)) and Vector3.new(moving and rootvelo.X or 0, inputService:IsKeyDown(Enum.KeyCode.Space) and SwimVertical.Value or rootvelo.Y, moving and rootvelo.Z or 0) or Vector3.zero)
					end)
				end
			else
				GravityChangeTick = tick() + 0.1
				workspace.Gravity = oldgravity
				RunLoops:UnbindFromHeartbeat("Swim")
				if entityLibrary.isAlive then
					local enums = Enum.HumanoidStateType:GetEnumItems()
					table.remove(enums, table.find(enums, Enum.HumanoidStateType.None))
					for i,v in pairs(enums) do
						entityLibrary.character.Humanoid:SetStateEnabled(v, true)
					end
				end
			end
		end
	})
	SwimVertical = Swim.CreateSlider({
		Name = "Y Speed",
		Min = 1,
		Max = 50,
		Default = 50,
		Function = function() end
	})
end)


run(function()
	local Breadcrumbs = {Enabled = false}
	local BreadcrumbsLifetime = {Value = 20}
	local BreadcrumbsThickness = {Value = 7}
	local BreadcrumbsFadeIn = {Value = 0.44}
	local BreadcrumbsFadeOut = {Value = 0.44}
	local breadcrumbtrail
	local breadcrumbattachment
	local breadcrumbattachment2
	Breadcrumbs = GuiLibrary.ObjectsThatCanBeSaved.RenderWindow.Api.CreateOptionsButton({
		Name = "Breadcrumbs",
		Function = function(callback)
			if callback then
				task.spawn(function()
					repeat
						if entityLibrary.isAlive then
							if not breadcrumbtrail then
								breadcrumbattachment = Instance.new("Attachment")
								breadcrumbattachment.Position = Vector3.new(0, 0.07 - 2.7, 0)
								breadcrumbattachment2 = Instance.new("Attachment")
								breadcrumbattachment2.Position = Vector3.new(0, -0.07 - 2.7, 0)
								breadcrumbtrail = Instance.new("Trail")
								breadcrumbtrail.Attachment0 = breadcrumbattachment
								breadcrumbtrail.Attachment1 = breadcrumbattachment2
								breadcrumbtrail.Color = ColorSequence.new(Color3.fromHSV(BreadcrumbsFadeIn.Hue, BreadcrumbsFadeIn.Sat, BreadcrumbsFadeIn.Value), Color3.fromHSV(BreadcrumbsFadeOut.Hue, BreadcrumbsFadeOut.Sat, BreadcrumbsFadeOut.Value))
								breadcrumbtrail.FaceCamera = true
								breadcrumbtrail.Lifetime = BreadcrumbsLifetime.Value / 10
								breadcrumbtrail.Enabled = true
							else
								local suc = pcall(function()
									breadcrumbattachment.Parent = entityLibrary.character.HumanoidRootPart
									breadcrumbattachment2.Parent = entityLibrary.character.HumanoidRootPart
									breadcrumbtrail.Parent = gameCamera
								end)
								if not suc then
									if breadcrumbtrail then breadcrumbtrail:Destroy() breadcrumbtrail = nil end
									if breadcrumbattachment then breadcrumbattachment:Destroy() breadcrumbattachment = nil end
									if breadcrumbattachment2 then breadcrumbattachment2:Destroy() breadcrumbattachment2 = nil end
								end
							end
						end
						task.wait(0.3)
					until not Breadcrumbs.Enabled
				end)
			else
				if breadcrumbtrail then breadcrumbtrail:Destroy() breadcrumbtrail = nil end
				if breadcrumbattachment then breadcrumbattachment:Destroy() breadcrumbattachment = nil end
				if breadcrumbattachment2 then breadcrumbattachment2:Destroy() breadcrumbattachment2 = nil end
			end
		end,
		HoverText = "Shows a trail behind your character"
	})
	BreadcrumbsFadeIn = Breadcrumbs.CreateColorSlider({
		Name = "Fade In",
		Function = function(hue, sat, val)
			if breadcrumbtrail then
				breadcrumbtrail.Color = ColorSequence.new(Color3.fromHSV(hue, sat, val), Color3.fromHSV(BreadcrumbsFadeOut.Hue, BreadcrumbsFadeOut.Sat, BreadcrumbsFadeOut.Value))
			end
		end
	})
	BreadcrumbsFadeOut = Breadcrumbs.CreateColorSlider({
		Name = "Fade Out",
		Function = function(hue, sat, val)
			if breadcrumbtrail then
				breadcrumbtrail.Color = ColorSequence.new(Color3.fromHSV(BreadcrumbsFadeIn.Hue, BreadcrumbsFadeIn.Sat, BreadcrumbsFadeIn.Value), Color3.fromHSV(hue, sat, val))
			end
		end
	})
	BreadcrumbsLifetime = Breadcrumbs.CreateSlider({
		Name = "Lifetime",
		Min = 1,
		Max = 100,
		Function = function(val)
			if breadcrumbtrail then
				breadcrumbtrail.Lifetime = val / 10
			end
		end,
		Default = 20,
		Double = 10
	})
	BreadcrumbsThickness = Breadcrumbs.CreateSlider({
		Name = "Thickness",
		Min = 1,
		Max = 30,
		Function = function(val)
			if breadcrumbattachment then
				breadcrumbattachment.Position = Vector3.new(0, (val / 100) - 2.7, 0)
			end
			if breadcrumbattachment2 then
				breadcrumbattachment2.Position = Vector3.new(0, -(val / 100) - 2.7, 0)
			end
		end,
		Default = 7,
		Double = 10
	})
end)

run(function()
	local AutoReport = {Enabled = false}
	local AutoReportList = {ObjectList = {}}
	local AutoReportNotify = {Enabled = false}
	local alreadyreported = {}

	local function removerepeat(str)
		local newstr = ""
		local lastlet = ""
		for i,v in pairs(str:split("")) do
			if v ~= lastlet then
				newstr = newstr..v
				lastlet = v
			end
		end
		return newstr
	end

	local reporttable = {
		gay = "Bullying",
		gae = "Bullying",
		gey = "Bullying",
		hack = "Scamming",
		exploit = "Scamming",
		cheat = "Scamming",
		hecker = "Scamming",
		haxker = "Scamming",
		hacer = "Scamming",
		report = "Bullying",
		fat = "Bullying",
		black = "Bullying",
		getalife = "Bullying",
		fatherless = "Bullying",
		report = "Bullying",
		fatherless = "Bullying",
		disco = "Offsite Links",
		yt = "Offsite Links",
		dizcourde = "Offsite Links",
		retard = "Swearing",
		bad = "Bullying",
		trash = "Bullying",
		nolife = "Bullying",
		nolife = "Bullying",
		loser = "Bullying",
		killyour = "Bullying",
		kys = "Bullying",
		hacktowin = "Bullying",
		bozo = "Bullying",
		kid = "Bullying",
		adopted = "Bullying",
		linlife = "Bullying",
		commitnotalive = "Bullying",
		vape = "Offsite Links",
		futureclient = "Offsite Links",
		download = "Offsite Links",
		youtube = "Offsite Links",
		die = "Bullying",
		lobby = "Bullying",
		ban = "Bullying",
		wizard = "Bullying",
		wisard = "Bullying",
		witch = "Bullying",
		magic = "Bullying",
	}
	local reporttableexact = {
		L = "Bullying",
	}


	local function findreport(msg)
		local checkstr = removerepeat(msg:gsub("%W+", ""):lower())
		for i,v in pairs(reporttable) do
			if checkstr:find(i) then
				return v, i
			end
		end
		for i,v in pairs(reporttableexact) do
			if checkstr == i then
				return v, i
			end
		end
		for i,v in pairs(AutoReportList.ObjectList) do
			if checkstr:find(v) then
				return "Bullying", v
			end
		end
		return nil
	end

	AutoReport = GuiLibrary.ObjectsThatCanBeSaved.UtilityWindow.Api.CreateOptionsButton({
		Name = "AutoReport",
		Function = function(callback)
			if callback then
				if textChatService.ChatVersion == Enum.ChatVersion.TextChatService then
					table.insert(AutoReport.Connections, textChatService.MessageReceived:Connect(function(tab)
						if tab.TextSource then
							local plr = playersService:GetPlayerByUserId(tab.TextSource.UserId)
							local args = tab.Text:split(" ")
							if plr and plr ~= lplr and whitelist:get(plr) == 0 then
								local reportreason, reportedmatch = findreport(tab.Text)
								if reportreason then
									if alreadyreported[plr] then return end
									task.spawn(function()
										if syn == nil or reportplayer then
											if reportplayer then
												reportplayer(plr, reportreason, "he said a bad word")
											else
												playersService:ReportAbuse(plr, reportreason, "he said a bad word")
											end
										end
									end)
									if AutoReportNotify.Enabled then
										warningNotification("AutoReport", "Reported "..plr.Name.." for "..reportreason..' ('..reportedmatch..')', 15)
									end
									alreadyreported[plr] = true
								end
							end
						end
					end))
				else
					if replicatedStorage:FindFirstChild("DefaultChatSystemChatEvents") then
						table.insert(AutoReport.Connections, replicatedStorage.DefaultChatSystemChatEvents.OnMessageDoneFiltering.OnClientEvent:Connect(function(tab, channel)
							local plr = playersService:FindFirstChild(tab.FromSpeaker)
							local args = tab.Message:split(" ")
							if plr and plr ~= lplr and whitelist:get(plr) == 0 then
								local reportreason, reportedmatch = findreport(tab.Message)
								if reportreason then
									if alreadyreported[plr] then return end
									task.spawn(function()
										if syn == nil or reportplayer then
											if reportplayer then
												reportplayer(plr, reportreason, "he said a bad word")
											else
												playersService:ReportAbuse(plr, reportreason, "he said a bad word")
											end
										end
									end)
									if AutoReportNotify.Enabled then
										warningNotification("AutoReport", "Reported "..plr.Name.." for "..reportreason..' ('..reportedmatch..')', 15)
									end
									alreadyreported[plr] = true
								end
							end
						end))
					else
						warningNotification("AutoReport", "Default chat not found.", 5)
						AutoReport.ToggleButton(false)
					end
				end
			end
		end
	})
	AutoReportNotify = AutoReport.CreateToggle({
		Name = "Notify",
		Function = function() end
	})
	AutoReportList = AutoReport.CreateTextList({
		Name = "Report Words",
		TempText = "phrase (to report)"
	})
end)

run(function()
	local targetstrafe = {Enabled = false}
	local targetstraferange = {Value = 0}
	local oldmove
	local controlmodule
	targetstrafe = GuiLibrary.ObjectsThatCanBeSaved.BlatantWindow.Api.CreateOptionsButton({
		Name = "TargetStrafe",
		Function = function(callback)
			if callback then
				if not controlmodule then
					local suc = pcall(function() controlmodule = require(lplr.PlayerScripts.PlayerModule).controls end)
					if not suc then controlmodule = {} end
				end
				oldmove = controlmodule.moveFunction
				controlmodule.moveFunction = function(Self, vec, facecam, ...)
					if entityLibrary.isAlive then
						local plr = EntityNearPosition(targetstraferange.Value, {
							WallCheck = false,
							AimPart = "RootPart"
						})
						if plr then
							facecam = false
							--code stolen from roblox since the way I tried to make it apparently sucks
							local c, s
							local plrCFrame = CFrame.lookAt(entityLibrary.character.HumanoidRootPart.Position, Vector3.new(plr.RootPart.Position.X, 0, plr.RootPart.Position.Z))
							local _, _, _, R00, R01, R02, _, _, R12, _, _, R22 = plrCFrame:GetComponents()
							if R12 < 1 and R12 > -1 then
								c = R22
								s = R02
							else
								c = R00
								s = -R01*math.sign(R12)
							end
							local norm = math.sqrt(c*c + s*s)
							local cameraRelativeMoveVector = controlmodule:GetMoveVector()
							vec = Vector3.new(
								(c*cameraRelativeMoveVector.X + s*cameraRelativeMoveVector.Z)/norm,
								0,
								(c*cameraRelativeMoveVector.Z - s*cameraRelativeMoveVector.X)/norm
							)
						end
					end
					return oldmove(Self, vec, facecam, ...)
				end
			else
				controlmodule.moveFunction = oldmove
			end
		end
	})
	targetstraferange = targetstrafe.CreateSlider({
		Name = "Range",
		Function = function() end,
		Min = 0,
		Max = 100,
		Default = 14
	})
end)

run(function()
	local AutoLeave = {Enabled = false}
	local AutoLeaveMode = {Value = "UnInject"}
	local AutoLeaveGroupId = {Value = "0"}
	local AutoLeaveRank = {Value = "1"}
	local getrandomserver
	local alreadyjoining = false
	getrandomserver = function(pointer)
		alreadyjoining = true
		local decodeddata = game:GetService("HttpService"):JSONDecode(game:HttpGet("https://games.roblox.com/v1/games/"..game.PlaceId.."/servers/Public?sortOrder=Desc&limit=100"..(pointer and "&cursor="..pointer or "")))
		local chosenServer
		for i, v in pairs(decodeddata.data) do
			if (tonumber(v.playing) < tonumber(playersService.MaxPlayers)) and tonumber(v.ping) < 300 and v.id ~= game.JobId then
				chosenServer = v.id
				break
			end
		end
		if chosenServer then
			alreadyjoining = false
			game:GetService("TeleportService"):TeleportToPlaceInstance(game.PlaceId, chosenServer, lplr)
		else
			if decodeddata.nextPageCursor then
				getrandomserver(decodeddata.nextPageCursor)
			else
				alreadyjoining = false
			end
		end
	end

	local function getRole(plr, id)
		local suc, res = pcall(function() return plr:GetRankInGroup(id) end)
		if not suc then
			repeat
				suc, res = pcall(function() return plr:GetRankInGroup(id) end)
				task.wait()
			until suc
		end
		return res
	end

	local function autoleaveplradded(plr)
		task.spawn(function()
			pcall(function()
				if AutoLeaveGroupId.Value == "" or AutoLeaveRank.Value == "" then return end
				if getRole(plr, tonumber(AutoLeaveGroupId.Value) or 0) >= (tonumber(AutoLeaveRank.Value) or 1) then
					local _, ent = entityLibrary.getEntityFromPlayer(plr)
					if ent then
						entityLibrary.entityUpdatedEvent:Fire(ent)
					end
					if AutoLeaveMode.Value == "UnInject" then
						task.spawn(function()
							if not shared.VapeFullyLoaded then
								repeat task.wait() until shared.VapeFullyLoaded
							end
							GuiLibrary.SelfDestruct()
						end)
						game:GetService("StarterGui"):SetCore("SendNotification", {
							Title = "AutoLeave",
							Text = "Staff Detected\n"..(plr.DisplayName and plr.DisplayName.." ("..plr.Name..")" or plr.Name),
							Duration = 60,
						})
					elseif AutoLeaveMode.Value == "Rejoin" then
						getrandomserver()
					else
						createwarning("AutoLeave", "Staff Detected : "..(plr.DisplayName and plr.DisplayName.." ("..plr.Name..")" or plr.Name), 60)
					end
				end
			end)
		end)
	end

	local function autodetect(roles)
		local highest = 9e9
		for i,v in pairs(roles) do
			local low = v.Name:lower()
			if (low:find("admin") or low:find("mod") or low:find("dev")) and v.Rank < highest then
				highest = v.Rank
			end
		end
		return highest
	end

	AutoLeave = GuiLibrary.ObjectsThatCanBeSaved.BlatantWindow.Api.CreateOptionsButton({
		Name = "AutoLeave",
		Function = function(callback)
			if callback then
				if AutoLeaveGroupId.Value == "" or AutoLeaveRank.Value == "" then
					task.spawn(function()
						local placeinfo = {Creator = {CreatorTargetId = tonumber(AutoLeaveGroupId.Value)}}
						if AutoLeaveGroupId.Value == "" then
							placeinfo = game:GetService("MarketplaceService"):GetProductInfo(game.PlaceId)
							if placeinfo.Creator.CreatorType ~= "Group" then
								local desc = placeinfo.Description:split("\n")
								for i, str in pairs(desc) do
									local _, begin = str:find("roblox.com/groups/")
									if begin then
										local endof = str:find("/", begin + 1)
										placeinfo = {Creator = {CreatorType = "Group", CreatorTargetId = str:sub(begin + 1, endof - 1)}}
									end
								end
							end
							if placeinfo.Creator.CreatorType ~= "Group" then
								warningNotification("AutoLeave", "Automatic Setup Failed (no group detected)", 60)
								return
							end
						end
						local groupinfo = game:GetService("GroupService"):GetGroupInfoAsync(placeinfo.Creator.CreatorTargetId)
						AutoLeaveGroupId.SetValue(placeinfo.Creator.CreatorTargetId)
						AutoLeaveRank.SetValue(autodetect(groupinfo.Roles))
						if AutoLeave.Enabled then
							AutoLeave.ToggleButton(false)
							AutoLeave.ToggleButton(false)
						end
					end)
					table.insert(AutoLeave.Connections, playersService.PlayerAdded:Connect(autoleaveplradded))
					for i, plr in pairs(playersService:GetPlayers()) do
						autoleaveplradded(plr)
					end
				end
			end
		end,
		HoverText = "Leaves if a staff member joins your game."
	})
	AutoLeaveMode = AutoLeave.CreateDropdown({
		Name = "Mode",
		List = {"UnInject", "Rejoin", "Notify"},
		Function = function() end
	})
	AutoLeaveGroupId = AutoLeave.CreateTextBox({
		Name = "Group Id",
		TempText = "0 (group id)",
		Function = function() end
	})
	AutoLeaveRank = AutoLeave.CreateTextBox({
		Name = "Rank Id",
		TempText = "1 (rank id)",
		Function = function() end
	})
end)

run(function()
	GuiLibrary.ObjectsThatCanBeSaved.WorldWindow.Api.CreateOptionsButton({
		Name = "AntiVoid",
		Function = function(callback)
			if callback then
				local rayparams = RaycastParams.new()
				rayparams.RespectCanCollide = true
				local lastray
				RunLoops:BindToHeartbeat("AntiVoid", function()
					if entityLibrary.isAlive then
						rayparams.FilterDescendantsInstances = {gameCamera, lplr.Character}
						lastray = entityLibrary.character.Humanoid.FloorMaterial ~= Enum.Material.Air and entityLibrary.character.HumanoidRootPart.CFrame or lastray
						if (entityLibrary.character.HumanoidRootPart.Position.Y + (entityLibrary.character.HumanoidRootPart.Velocity.Y * 0.016)) <= (workspace.FallenPartsDestroyHeight + 5) then
							local comp = {entityLibrary.character.HumanoidRootPart.CFrame:GetComponents()}
							comp[2] = (workspace.FallenPartsDestroyHeight + 20)
							if lastray then
								comp[1] = lastray.Position.X
								comp[2] = lastray.Position.Y + (entityLibrary.character.Humanoid.HipHeight + (entityLibrary.character.HumanoidRootPart.Size.Y / 2))
								comp[3] = lastray.Position.Z
							end
							entityLibrary.character.HumanoidRootPart.CFrame = CFrame.new(unpack(comp))
							entityLibrary.character.HumanoidRootPart.Velocity = Vector3.new(entityLibrary.character.HumanoidRootPart.Velocity.X, 0, entityLibrary.character.HumanoidRootPart.Velocity.Z)
						end
					end
				end)
			else
				RunLoops:UnbindFromHeartbeat("AntiVoid")
			end
		end
	})
end)

run(function()
	local Blink = {Enabled = false}
	Blink = GuiLibrary.ObjectsThatCanBeSaved.BlatantWindow.Api.CreateOptionsButton({
		Name = "Blink",
		Function = function(callback)
			if callback then
				if sethiddenproperty then
					RunLoops:BindToHeartbeat("Blink", function()
						if entityLibrary.isAlive then
							sethiddenproperty(entityLibrary.character.HumanoidRootPart, "NetworkIsSleeping", true)
						end
					end)
				else
					warningNotification("Blink", "missing function", 5)
					Blink.ToggleButton(false)
				end
			else
				RunLoops:UnbindFromHeartbeat("Blink")
			end
		end
	})
end)

run(function()
	local AnimationPlayer = {Enabled = false}
	local AnimationPlayerBox = {Value = ""}
	local AnimationPlayerSpeed = {Speed = 1}
	local playedanim
	AnimationPlayer = GuiLibrary.ObjectsThatCanBeSaved.UtilityWindow.Api.CreateOptionsButton({
		Name = "AnimationPlayer",
		Function = function(callback)
			if callback then
				if entityLibrary.isAlive then
					if playedanim then
						playedanim:Stop()
						playedanim.Animation:Destroy()
						playedanim = nil
					end
					local anim = Instance.new("Animation")
					local suc, id = pcall(function() return string.match(game:GetObjects("rbxassetid://"..AnimationPlayerBox.Value)[1].AnimationId, "%?id=(%d+)") end)
                    if not suc then
                        id = AnimationPlayerBox.Value
                    end
                    anim.AnimationId = "rbxassetid://"..id
					local suc, res = pcall(function() playedanim = entityLibrary.character.Humanoid.Animator:LoadAnimation(anim) end)
					if suc then
						playedanim.Priority = Enum.AnimationPriority.Action4
						playedanim.Looped = true
						playedanim:Play()
						playedanim:AdjustSpeed(AnimationPlayerSpeed.Value / 10)
						table.insert(AnimationPlayer.Connections, playedanim.Stopped:Connect(function()
							if AnimationPlayer.Enabled then
								AnimationPlayer.ToggleButton(false)
								AnimationPlayer.ToggleButton(false)
							end
						end))
					else
						warningNotification("AnimationPlayer", "failed to load anim : "..(res or "invalid animation id"), 5)
					end
				end
				table.insert(AnimationPlayer.Connections, lplr.CharacterAdded:Connect(function()
					repeat task.wait() until entityLibrary.isAlive or not AnimationPlayer.Enabled
					task.wait(0.5)
					if not AnimationPlayer.Enabled then return end
					if playedanim then
						playedanim:Stop()
						playedanim.Animation:Destroy()
						playedanim = nil
					end
					local anim = Instance.new("Animation")
					local suc, id = pcall(function() return string.match(game:GetObjects("rbxassetid://"..AnimationPlayerBox.Value)[1].AnimationId, "%?id=(%d+)") end)
                    if not suc then
                        id = AnimationPlayerBox.Value
                    end
                    anim.AnimationId = "rbxassetid://"..id
					local suc, res = pcall(function() playedanim = entityLibrary.character.Humanoid.Animator:LoadAnimation(anim) end)
					if suc then
						playedanim.Priority = Enum.AnimationPriority.Action4
						playedanim.Looped = true
						playedanim:Play()
						playedanim:AdjustSpeed(AnimationPlayerSpeed.Value / 10)
						playedanim.Stopped:Connect(function()
							if AnimationPlayer.Enabled then
								AnimationPlayer.ToggleButton(false)
								AnimationPlayer.ToggleButton(false)
							end
						end)
					else
						warningNotification("AnimationPlayer", "failed to load anim : "..(res or "invalid animation id"), 5)
					end
				end))
			else
				if playedanim then playedanim:Stop() playedanim = nil end
			end
		end
	})
	AnimationPlayerBox = AnimationPlayer.CreateTextBox({
		Name = "Animation",
		TempText = "anim (num only)",
		Function = function(enter)
			if enter and AnimationPlayer.Enabled then
				AnimationPlayer.ToggleButton(false)
				AnimationPlayer.ToggleButton(false)
			end
		end
	})
	AnimationPlayerSpeed = AnimationPlayer.CreateSlider({
		Name = "Speed",
		Function = function(val)
			if playedanim then
				playedanim:AdjustSpeed(val / 10)
			end
		end,
		Min = 1,
		Max = 20,
		Double = 10
	})
end)

run(function()
	local GamingChair = {Enabled = false}
	local GamingChairColor = {Value = 1}
	local chair
	local chairanim
	local chairhighlight
	local movingsound
	local flyingsound
	local wheelpositions = {
		Vector3.new(-0.8, -0.6, -0.18),
		Vector3.new(0.1, -0.6, -0.88),
		Vector3.new(0, -0.6, 0.7)
	}
	local currenttween
	GamingChair = GuiLibrary.ObjectsThatCanBeSaved.RenderWindow.Api.CreateOptionsButton({
		Name = "GamingChair",
		Function = function(callback)
			if callback then
				chair = Instance.new("MeshPart")
				chair.Color = Color3.fromRGB(21, 21, 21)
				chair.Size = Vector3.new(2.16, 3.6, 2.3) / Vector3.new(12.37, 20.636, 13.071)
				chair.CanCollide = false
				chair.MeshId = "rbxassetid://12972961089"
				chair.Material = Enum.Material.SmoothPlastic
				chair.Parent = workspace
				movingsound = Instance.new("Sound")
				movingsound.SoundId = downloadVapeAsset("vape/assets/ChairRolling.mp3")
				movingsound.Volume = 0.4
				movingsound.Looped = true
				movingsound.Parent = workspace
				flyingsound = Instance.new("Sound")
				flyingsound.SoundId = downloadVapeAsset("vape/assets/ChairFlying.mp3")
				flyingsound.Volume = 0.4
				flyingsound.Looped = true
				flyingsound.Parent = workspace
				local chairweld = Instance.new("WeldConstraint")
				chairweld.Part0 = chair
				chairweld.Parent = chair
				if entityLibrary.isAlive then
					chair.CFrame = entityLibrary.character.HumanoidRootPart.CFrame * CFrame.Angles(0, math.rad(-90), 0)
					chairweld.Part1 = entityLibrary.character.HumanoidRootPart
				end
				chairhighlight = Instance.new("Highlight")
				chairhighlight.FillTransparency = 1
				chairhighlight.OutlineColor = Color3.fromHSV(GamingChairColor.Hue, GamingChairColor.Sat, GamingChairColor.Value)
				chairhighlight.DepthMode = Enum.HighlightDepthMode.Occluded
				chairhighlight.OutlineTransparency = 0.2
				chairhighlight.Parent = chair
				local chairarms = Instance.new("MeshPart")
				chairarms.Color = chair.Color
				chairarms.Size = Vector3.new(1.39, 1.345, 2.75) / Vector3.new(97.13, 136.216, 234.031)
				chairarms.CFrame = chair.CFrame * CFrame.new(-0.169, -1.129, -0.013)
				chairarms.MeshId = "rbxassetid://12972673898"
				chairarms.CanCollide = false
				chairarms.Parent = chair
				local chairarmsweld = Instance.new("WeldConstraint")
				chairarmsweld.Part0 = chairarms
				chairarmsweld.Part1 = chair
				chairarmsweld.Parent = chair
				local chairlegs = Instance.new("MeshPart")
				chairlegs.Color = chair.Color
				chairlegs.Name = "Legs"
				chairlegs.Size = Vector3.new(1.8, 1.2, 1.8) / Vector3.new(10.432, 8.105, 9.488)
				chairlegs.CFrame = chair.CFrame * CFrame.new(0.047, -2.324, 0)
				chairlegs.MeshId = "rbxassetid://13003181606"
				chairlegs.CanCollide = false
				chairlegs.Parent = chair
				local chairfan = Instance.new("MeshPart")
				chairfan.Color = chair.Color
				chairfan.Name = "Fan"
				chairfan.Size = Vector3.zero
				chairfan.CFrame = chair.CFrame * CFrame.new(0, -1.873, 0)
				chairfan.MeshId = "rbxassetid://13004977292"
				chairfan.CanCollide = false
				chairfan.Parent = chair
				local trails = {}
				for i,v in pairs(wheelpositions) do
					local attachment = Instance.new("Attachment")
					attachment.Position = v
					attachment.Parent = chairlegs
					local attachment2 = Instance.new("Attachment")
					attachment2.Position = v + Vector3.new(0, 0, 0.18)
					attachment2.Parent = chairlegs
					local trail = Instance.new("Trail")
					trail.Texture = "http://www.roblox.com/asset/?id=13005168530"
					trail.TextureMode = Enum.TextureMode.Static
					trail.Transparency = NumberSequence.new(0.5)
					trail.Color = ColorSequence.new(Color3.new(0.5, 0.5, 0.5))
					trail.Attachment0 = attachment
					trail.Attachment1 = attachment2
					trail.Lifetime = 20
					trail.MaxLength = 60
					trail.MinLength = 0.1
					trail.Parent = chairlegs
					table.insert(trails, trail)
				end
				chairanim = {Stop = function() end}
				local oldmoving = false
				local oldflying = false
				task.spawn(function()
					repeat
						task.wait()
						if not GamingChair.Enabled then break end
						if entityLibrary.isAlive and entityLibrary.character.Humanoid.Health > 0 then
							if not chairanim.IsPlaying then
								local temp2 = Instance.new("Animation")
								temp2.AnimationId = entityLibrary.character.Humanoid.RigType == Enum.HumanoidRigType.R15 and "http://www.roblox.com/asset/?id=2506281703" or "http://www.roblox.com/asset/?id=178130996"
								chairanim = entityLibrary.character.Humanoid:LoadAnimation(temp2)
								chairanim.Priority = Enum.AnimationPriority.Movement
								chairanim.Looped = true
								chairanim:Play()
							end
							--welds didn't work for these idk why so poop code :troll:
							chair.CFrame = entityLibrary.character.HumanoidRootPart.CFrame * CFrame.Angles(0, math.rad(-90), 0)
							chairweld.Part1 = entityLibrary.character.HumanoidRootPart
							chairlegs.Velocity = Vector3.zero
							chairlegs.CFrame = chair.CFrame * CFrame.new(0.047, -2.324, 0)
							chairfan.Velocity = Vector3.zero
							chairfan.CFrame = chair.CFrame * CFrame.new(0.047, -1.873, 0) * CFrame.Angles(0, math.rad(tick() * 180 % 360), math.rad(180))
							local moving = entityLibrary.character.Humanoid:GetState() == Enum.HumanoidStateType.Running and entityLibrary.character.Humanoid.MoveDirection ~= Vector3.zero
							local flying = GuiLibrary.ObjectsThatCanBeSaved.FlyOptionsButton.Api.Enabled or GuiLibrary.ObjectsThatCanBeSaved.LongJumpOptionsButton and GuiLibrary.ObjectsThatCanBeSaved.LongJumpOptionsButton.Api.Enabled or GuiLibrary.ObjectsThatCanBeSaved.InfiniteFlyOptionsButton and GuiLibrary.ObjectsThatCanBeSaved.InfiniteFlyOptionsButton.Api.Enabled
							if movingsound.TimePosition > 1.9 then
								movingsound.TimePosition = 0.2
							end
							movingsound.PlaybackSpeed = (entityLibrary.character.HumanoidRootPart.Velocity * Vector3.new(1, 0, 1)).Magnitude / 16
							for i,v in pairs(trails) do
								v.Enabled = not flying and moving
								v.Color = ColorSequence.new(movingsound.PlaybackSpeed > 1.5 and Color3.new(1, 0.5, 0) or Color3.new())
							end
							if moving ~= oldmoving then
								if movingsound.IsPlaying then
									if not moving then movingsound:Stop() end
								else
									if not flying and moving then movingsound:Play() end
								end
								oldmoving = moving
							end
							if flying ~= oldflying then
								if flying then
									if movingsound.IsPlaying then
										movingsound:Stop()
									end
									if not flyingsound.IsPlaying then
										flyingsound:Play()
									end
									if currenttween then currenttween:Cancel() end
									tween = tweenService:Create(chairlegs, TweenInfo.new(0.15), {Size = Vector3.zero})
									tween.Completed:Connect(function(state)
										if state == Enum.PlaybackState.Completed then
											chairfan.Transparency = 0
											chairlegs.Transparency = 1
											tween = tweenService:Create(chairfan, TweenInfo.new(0.15), {Size = Vector3.new(1.534, 0.328, 1.537) / Vector3.new(791.138, 168.824, 792.027)})
											tween:Play()
										end
									end)
									tween:Play()
								else
									if flyingsound.IsPlaying then
										flyingsound:Stop()
									end
									if not movingsound.IsPlaying and moving then
										movingsound:Play()
									end
									if currenttween then currenttween:Cancel() end
									tween = tweenService:Create(chairfan, TweenInfo.new(0.15), {Size = Vector3.zero})
									tween.Completed:Connect(function(state)
										if state == Enum.PlaybackState.Completed then
											chairfan.Transparency = 1
											chairlegs.Transparency = 0
											tween = tweenService:Create(chairlegs, TweenInfo.new(0.15), {Size = Vector3.new(1.8, 1.2, 1.8) / Vector3.new(10.432, 8.105, 9.488)})
											tween:Play()
										end
									end)
									tween:Play()
								end
								oldflying = flying
							end
						else
							chair.Anchored = true
							chairlegs.Anchored = true
							chairfan.Anchored = true
							repeat task.wait() until entityLibrary.isAlive and entityLibrary.character.Humanoid.Health > 0
							chair.Anchored = false
							chairlegs.Anchored = false
							chairfan.Anchored = false
							chairanim:Stop()
						end
					until not GamingChair.Enabled
				end)
			else
				if chair then chair:Destroy() end
				if chairanim then chairanim:Stop() end
				if movingsound then movingsound:Destroy() end
				if flyingsound then flyingsound:Destroy() end
			end
		end
	})
	GamingChairColor = GamingChair.CreateColorSlider({
		Name = "Color",
		Function = function(h, s, v)
			if chairhighlight then
				chairhighlight.OutlineColor = Color3.fromHSV(h, s, v)
			end
		end
	})
end)

run(function()
	local SongBeats = {Enabled = false}
	local SongBeatsList = {ObjectList = {}}
	local SongTween
	local SongAudio
	local SongFOV

	local function PlaySong(arg)
		local args = arg:split(":")
		local song = isfile(args[1]) and getcustomasset(args[1]) or tonumber(args[1]) and "rbxassetid://"..args[1]
		if not song then
			warningNotification("SongBeats", "missing music file "..args[1], 5)
			SongBeats.ToggleButton(false)
			return
		end
		local bpm = 1 / (args[2] / 60)
		SongAudio = Instance.new("Sound")
		SongAudio.SoundId = song
		SongAudio.Parent = workspace
		SongAudio:Play()
		repeat
			repeat task.wait() until SongAudio.IsLoaded or (not SongBeats.Enabled)
			if (not SongBeats.Enabled) then break end
			gameCamera.FieldOfView = SongFOV - 5
			if SongTween then SongTween:Cancel() end
			SongTween = tweenService:Create(gameCamera, TweenInfo.new(0.2), {FieldOfView = SongFOV})
			SongTween:Play()
			task.wait(bpm)
		until (not SongBeats.Enabled) or SongAudio.IsPaused
	end

	SongBeats = GuiLibrary.ObjectsThatCanBeSaved.RenderWindow.Api.CreateOptionsButton({
		Name = "SongBeats",
		Function = function(callback)
			if callback then
				SongFOV = gameCamera.FieldOfView
				task.spawn(function()
					if #SongBeatsList.ObjectList <= 0 then
						warningNotification("SongBeats", "no songs", 5)
						SongBeats.ToggleButton(false)
						return
					end
					local lastChosen
					repeat
						local newSong
						repeat newSong = SongBeatsList.ObjectList[Random.new():NextInteger(1, #SongBeatsList.ObjectList)] task.wait() until newSong ~= lastChosen or #SongBeatsList.ObjectList <= 1
						lastChosen = newSong
						PlaySong(newSong)
						if not SongBeats.Enabled then break end
						task.wait(2)
					until (not SongBeats.Enabled)
				end)
			else
				if SongAudio then SongAudio:Destroy() end
				if SongTween then SongTween:Cancel() end
				gameCamera.FieldOfView = SongFOV
			end
		end
	})
	SongBeatsList = SongBeats.CreateTextList({
		Name = "SongList",
		TempText = "songpath:bpm"
	})
end)

run(function()
	local Atmosphere = {Enabled = false}
	local SkyUp = {Value = ""}
	local SkyDown = {Value = ""}
	local SkyLeft = {Value = ""}
	local SkyRight = {Value = ""}
	local SkyFront = {Value = ""}
	local SkyBack = {Value = ""}
	local SkySun = {Value = ""}
	local SkyMoon = {Value = ""}
	local SkyColor = {Value = 1}
	local skyobj
	local skyatmosphereobj
	local oldobjects = {}
	Atmosphere = GuiLibrary.ObjectsThatCanBeSaved.RenderWindow.Api.CreateOptionsButton({
		Name = "Atmosphere",
		Function = function(callback)
			if callback then
				for i,v in pairs(lightingService:GetChildren()) do
					if v:IsA("PostEffect") or v:IsA("Sky") then
						table.insert(oldobjects, v)
						v.Parent = game
					end
				end
				skyobj = Instance.new("Sky")
				skyobj.SkyboxBk = tonumber(SkyBack.Value) and "rbxassetid://"..SkyBack.Value or SkyBack.Value
				skyobj.SkyboxDn = tonumber(SkyDown.Value) and "rbxassetid://"..SkyDown.Value or SkyDown.Value
				skyobj.SkyboxFt = tonumber(SkyFront.Value) and "rbxassetid://"..SkyFront.Value or SkyFront.Value
				skyobj.SkyboxLf = tonumber(SkyLeft.Value) and "rbxassetid://"..SkyLeft.Value or SkyLeft.Value
				skyobj.SkyboxRt = tonumber(SkyRight.Value) and "rbxassetid://"..SkyRight.Value or SkyRight.Value
				skyobj.SkyboxUp = tonumber(SkyUp.Value) and "rbxassetid://"..SkyUp.Value or SkyUp.Value
				skyobj.SunTextureId = tonumber(SkySun.Value) and "rbxassetid://"..SkySun.Value or SkySun.Value
				skyobj.MoonTextureId = tonumber(SkyMoon.Value) and "rbxassetid://"..SkyMoon.Value or SkyMoon.Value
				skyobj.Parent = lightingService
				skyatmosphereobj = Instance.new("ColorCorrectionEffect")
				skyatmosphereobj.TintColor = Color3.fromHSV(SkyColor.Hue, SkyColor.Sat, SkyColor.Value)
				skyatmosphereobj.Parent = lightingService
			else
				if skyobj then skyobj:Destroy() end
				if skyatmosphereobj then skyatmosphereobj:Destroy() end
				for i,v in pairs(oldobjects) do
					v.Parent = lightingService
				end
				table.clear(oldobjects)
			end
		end
	})
	SkyUp = Atmosphere.CreateTextBox({
		Name = "SkyUp",
		TempText = "Sky Top ID",
		FocusLost = function(enter)
			if Atmosphere.Enabled then
				Atmosphere.ToggleButton(false)
				Atmosphere.ToggleButton(false)
			end
		end
	})
	SkyDown = Atmosphere.CreateTextBox({
		Name = "SkyDown",
		TempText = "Sky Bottom ID",
		FocusLost = function(enter)
			if Atmosphere.Enabled then
				Atmosphere.ToggleButton(false)
				Atmosphere.ToggleButton(false)
			end
		end
	})
	SkyLeft = Atmosphere.CreateTextBox({
		Name = "SkyLeft",
		TempText = "Sky Left ID",
		FocusLost = function(enter)
			if Atmosphere.Enabled then
				Atmosphere.ToggleButton(false)
				Atmosphere.ToggleButton(false)
			end
		end
	})
	SkyRight = Atmosphere.CreateTextBox({
		Name = "SkyRight",
		TempText = "Sky Right ID",
		FocusLost = function(enter)
			if Atmosphere.Enabled then
				Atmosphere.ToggleButton(false)
				Atmosphere.ToggleButton(false)
			end
		end
	})
	SkyFront = Atmosphere.CreateTextBox({
		Name = "SkyFront",
		TempText = "Sky Front ID",
		FocusLost = function(enter)
			if Atmosphere.Enabled then
				Atmosphere.ToggleButton(false)
				Atmosphere.ToggleButton(false)
			end
		end
	})
	SkyBack = Atmosphere.CreateTextBox({
		Name = "SkyBack",
		TempText = "Sky Back ID",
		FocusLost = function(enter)
			if Atmosphere.Enabled then
				Atmosphere.ToggleButton(false)
				Atmosphere.ToggleButton(false)
			end
		end
	})
	SkySun = Atmosphere.CreateTextBox({
		Name = "SkySun",
		TempText = "Sky Sun ID",
		FocusLost = function(enter)
			if Atmosphere.Enabled then
				Atmosphere.ToggleButton(false)
				Atmosphere.ToggleButton(false)
			end
		end
	})
	SkyMoon = Atmosphere.CreateTextBox({
		Name = "SkyMoon",
		TempText = "Sky Moon ID",
		FocusLost = function(enter)
			if Atmosphere.Enabled then
				Atmosphere.ToggleButton(false)
				Atmosphere.ToggleButton(false)
			end
		end
	})
	SkyColor = Atmosphere.CreateColorSlider({
		Name = "Color",
		Function = function(h, s, v)
			if skyatmosphereobj then
				skyatmosphereobj.TintColor = Color3.fromHSV(SkyColor.Hue, SkyColor.Sat, SkyColor.Value)
			end
		end
	})
end)

run(function()
	local Disabler = {Enabled = false}
	local DisablerAntiKick = {Enabled = false}
	local disablerhooked = false

	local hookmethod = function(self)
		if (not Disabler.Enabled) then return end
		if type(self) == "userdata" and self == lplr then
			return true
		end
	end


	Disabler = GuiLibrary.ObjectsThatCanBeSaved.UtilityWindow.Api.CreateOptionsButton({
		Name = "ClientKickDisabler",
		Function = function(callback)
			if callback then
				if not disablerhooked then
					disablerhooked = true
					local oldnamecall
					oldnamecall = hookmetamethod(game, "__namecall", function(self, ...)
						local method = getnamecallmethod()
						if method ~= "Kick" and method ~= "kick" then return oldnamecall(self, ...) end
						if not Disabler.Enabled then
							return oldnamecall(self, ...)
						end
						if not hookmethod(self) then return oldnamecall(self, ...) end
						return
					end)
					local antikick
					antikick = hookfunction(lplr.Kick, function(self, ...)
						if not Disabler.Enabled then return antikick(self, ...) end
						if type(self) == "userdata" and self == lplr then
							return
						end
						return antikick(self, ...)
					end)
				end
			else
				if restorefunction then
					restorefunction(lplr.Kick)
					restorefunction(getrawmetatable(game).__namecall)
					disablerhooked = false
				end
			end
		end
	})
end)

run(function()
	local FPS = {}
	local FPSLabel
	FPS = GuiLibrary.CreateLegitModule({
		Name = "FPS",
		Function = function(callback)
			if callback then
				local frames = {}
				local framerate = 0
				local startClock = os.clock()
				local updateTick = tick()
				RunLoops:BindToHeartbeat("FPS", function()
					-- https://devforum.roblox.com/t/get-client-fps-trough-a-script/282631, annoying math, I thought either adding dt to a table or doing 1 / dt would work, but this is just better lol
					local updateClock = os.clock()
					for i = #frames, 1, -1 do
						frames[i + 1] = frames[i] >= updateClock - 1 and frames[i] or nil
					end
					frames[1] = updateClock
					if updateTick < tick() then
						updateTick = tick() + 1
						FPSLabel.Text = math.floor(os.clock() - startClock >= 1 and #frames or #frames / (os.clock() - startClock)).." FPS"
					end
				end)
			else
				RunLoops:UnbindFromHeartbeat("FPS")
			end
		end
	})
	FPSLabel = Instance.new("TextLabel")
	FPSLabel.Size = UDim2.new(0, 100, 0, 41)
	FPSLabel.BackgroundTransparency = 0.5
	FPSLabel.TextSize = 15
	FPSLabel.Font = Enum.Font.Gotham
	FPSLabel.Text = "inf FPS"
	FPSLabel.TextColor3 = Color3.new(1, 1, 1)
	FPSLabel.BackgroundColor3 = Color3.new()
	FPSLabel.Parent = FPS.GetCustomChildren()
	local ReachCorner = Instance.new("UICorner")
	ReachCorner.CornerRadius = UDim.new(0, 4)
	ReachCorner.Parent = FPSLabel
end)


run(function()
	local Ping = {}
	local PingLabel
	Ping = GuiLibrary.CreateLegitModule({
		Name = "Ping",
		Function = function(callback)
			if callback then
				task.spawn(function()
					repeat
						PingLabel.Text = math.floor(tonumber(game:GetService("Stats"):FindFirstChild("PerformanceStats").Ping:GetValue())).." ms"
						task.wait(1)
					until false
				end)
			end
		end
	})
	PingLabel = Instance.new("TextLabel")
	PingLabel.Size = UDim2.new(0, 100, 0, 41)
	PingLabel.BackgroundTransparency = 0.5
	PingLabel.TextSize = 15
	PingLabel.Font = Enum.Font.Gotham
	PingLabel.Text = "0 ms"
	PingLabel.TextColor3 = Color3.new(1, 1, 1)
	PingLabel.BackgroundColor3 = Color3.new()
	PingLabel.Parent = Ping.GetCustomChildren()
	local PingCorner = Instance.new("UICorner")
	PingCorner.CornerRadius = UDim.new(0, 4)
	PingCorner.Parent = PingLabel
end)

run(function()
	local Keystrokes = {}
	local keys = {}
	local keystrokesframe
	local keyconnection1
	local keyconnection2

	local function createKeystroke(keybutton, pos, pos2)
		local key = Instance.new("Frame")
		key.Size = keybutton == Enum.KeyCode.Space and UDim2.new(0, 110, 0, 24) or UDim2.new(0, 34, 0, 36)
		key.BackgroundColor3 = Color3.new()
		key.BackgroundTransparency = 0.5
		key.Position = pos
		key.Name = keybutton.Name
		key.Parent = keystrokesframe
		local keytext = Instance.new("TextLabel")
		keytext.BackgroundTransparency = 1
		keytext.Size = UDim2.new(1, 0, 1, 0)
		keytext.Font = Enum.Font.Gotham
		keytext.Text = keybutton == Enum.KeyCode.Space and "______" or keybutton.Name
		keytext.TextXAlignment = Enum.TextXAlignment.Left
		keytext.TextYAlignment = Enum.TextYAlignment.Top
		keytext.Position = pos2
		keytext.TextSize = keybutton == Enum.KeyCode.Space and 18 or 15
		keytext.TextColor3 = Color3.new(1, 1, 1)
		keytext.Parent = key
		local keycorner = Instance.new("UICorner")
		keycorner.CornerRadius = UDim.new(0, 4)
		keycorner.Parent = key
		keys[keybutton] = {Key = key}
	end

	Keystrokes = GuiLibrary.CreateLegitModule({
		Name = "Keystrokes",
		Function = function(callback)
			if callback then
				keyconnection1 = inputService.InputBegan:Connect(function(inputType)
					local key = keys[inputType.KeyCode]
					if key then
						if key.Tween then key.Tween:Cancel() end
						if key.Tween2 then key.Tween2:Cancel() end
						key.Tween = tweenService:Create(key.Key, TweenInfo.new(0.1), {BackgroundColor3 = Color3.new(1, 1, 1), BackgroundTransparency = 0})
						key.Tween:Play()
						key.Tween2 = tweenService:Create(key.Key.TextLabel, TweenInfo.new(0.1), {TextColor3 = Color3.new()})
						key.Tween2:Play()
					end
				end)
				keyconnection2 = inputService.InputEnded:Connect(function(inputType)
					local key = keys[inputType.KeyCode]
					if key then
						if key.Tween then key.Tween:Cancel() end
						if key.Tween2 then key.Tween2:Cancel() end
						key.Tween = tweenService:Create(key.Key, TweenInfo.new(0.1), {BackgroundColor3 = Color3.new(), BackgroundTransparency = 0.5})
						key.Tween:Play()
						key.Tween2 = tweenService:Create(key.Key.TextLabel, TweenInfo.new(0.1), {TextColor3 = Color3.new(1, 1, 1)})
						key.Tween2:Play()
					end
				end)
			else
				if keyconnection1 then keyconnection1:Disconnect() end
				if keyconnection2 then keyconnection2:Disconnect() end
			end
		end
	})
	keystrokesframe = Instance.new("Frame")
	keystrokesframe.Size = UDim2.new(0, 110, 0, 176)
	keystrokesframe.BackgroundTransparency = 1
	keystrokesframe.Parent = Keystrokes.GetCustomChildren()
	createKeystroke(Enum.KeyCode.W, UDim2.new(0, 38, 0, 0), UDim2.new(0, 6, 0, 5))
	createKeystroke(Enum.KeyCode.S, UDim2.new(0, 38, 0, 42), UDim2.new(0, 8, 0, 5))
	createKeystroke(Enum.KeyCode.A, UDim2.new(0, 0, 0, 42), UDim2.new(0, 7, 0, 5))
	createKeystroke(Enum.KeyCode.D, UDim2.new(0, 76, 0, 42), UDim2.new(0, 8, 0, 5))
	createKeystroke(Enum.KeyCode.Space, UDim2.new(0, 0, 0, 83), UDim2.new(0, 25, 0, -10))
end)
