local a=Instance.new("ScreenGui")local b=Instance.new("Frame")local c=Instance.new("UICorner")local d=Instance.new("UIGradient")local e=Instance.new("TextBox")local f=Instance.new("UICorner")local g=Instance.new("TextButton")local h=Instance.new("UICorner")local i=Instance.new("UIGradient")local j=Instance.new("TextLabel")local k=Instance.new("UICorner")local l=Instance.new("UIGradient")local m=Instance.new("TextButton")local n=Instance.new("UICorner")a.Parent=game.CoreGui;b.Parent=a;b.BackgroundColor3=Color3.fromRGB(255,255,255)b.Position=UDim2.new(0.427722752,0,0.399719477,0)b.Size=UDim2.new(0,272,0,163)b.Active=true;b.Draggable=true;c.Parent=b;d.Color=ColorSequence.new{ColorSequenceKeypoint.new(0.00,Color3.fromRGB(94,14,255)),ColorSequenceKeypoint.new(0.39,Color3.fromRGB(38,125,255)),ColorSequenceKeypoint.new(0.50,Color3.fromRGB(46,255,203)),ColorSequenceKeypoint.new(1.00,Color3.fromRGB(94,14,255))}d.Parent=b;e.Parent=b;e.BackgroundColor3=Color3.fromRGB(166,166,166)e.Position=UDim2.new(0.231617644,0,0.312883437,0)e.Size=UDim2.new(0,146,0,41)e.Font=Enum.Font.SourceSans;e.PlaceholderColor3=Color3.fromRGB(186,186,186)e.Text=""e.TextColor3=Color3.fromRGB(0,0,0)e.TextSize=14.000;f.Parent=e;g.Name="hhh"g.Parent=b;g.BackgroundColor3=Color3.fromRGB(255,62,91)g.Position=UDim2.new(0.231617644,0,0.656441689,0)g.Size=UDim2.new(0,146,0,38)g.Font=Enum.Font.SourceSans;g.Text="确定"g.TextColor3=Color3.fromRGB(0,0,0)g.TextSize=24.000;g.MouseButton1Down:connect(function()if e.Text=="wevyyds"then--祖先翻译 可在fluxus synapse x script ware 上面使用

--> Open Sourced by Ancestor

--> Credit if you use any code :)

repeat wait()until game:IsLoaded()and game.Players.LocalPlayer.Character;
local lib = {}

pcall(function()
    game.CoreGui.AncestorV2:Destroy();
end)
function lib:Create(type, proprieties)
	local instance = Instance.new(type)

	for i, v in next, proprieties do
		if instance[i] and proprieties ~= "Parent" then
			instance[i] = v
		end
	end

	return instance
end

local CoreGui = game.CoreGui
local TweenService = game:GetService("TweenService")
local Mouse = game:GetService("Players").LocalPlayer:GetMouse()
local UIS = game:GetService("UserInputService")

function lib:Main()
	local main = {}
	local firstC = true

	main.ScreenGui = lib:Create("ScreenGui", {
		Name = "AncestorV2",
		ResetOnSpawn = false,
	})

	main.MainBody = lib:Create("Frame", {
		Name = "MainBody",
		BackgroundColor3 = Color3.fromRGB(25, 25, 25),
		BorderSizePixel = 0,
		Position = UDim2.new(0.355343342, 0, 0.358804077, 0),
		Size = UDim2.new(0, 554, 0, 304),
	})

	local dragInput
	local dragStart
	local startPos

	local function update(input)
		local delta = input.Position - dragStart
		main.MainBody:TweenPosition(UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X, startPos.Y.Scale, startPos.Y.Offset + delta.Y),'Out','Linear',0.01,true)
	end

	main.MainBody.InputBegan:Connect(function(input)
		if input.UserInputType == Enum.UserInputType.MouseButton1 then
			dragging = true
			dragStart = input.Position
			startPos = main.MainBody.Position
			repeat wait() until input.UserInputState == Enum.UserInputState.End
			dragging = false
		end
	end)

	main.MainBody.InputChanged:Connect(function(input)
		if input.UserInputType == Enum.UserInputType.MouseMovement then
			dragInput = input
		end
	end)

	game:GetService("UserInputService").InputChanged:Connect(function(input)
		if input == dragInput and dragging then
			update(input)
		end
	end)

	main.TopBar = lib:Create("Frame", {
		Name = "TopBar",
		BackgroundColor3 = Color3.fromRGB(255, 0, 120),
		BorderSizePixel = 0,
		Size = UDim2.new(0, 554, 0, 40),
	})

	main.TopBarGradient = lib:Create("UIGradient", {
		Color = ColorSequence.new{ColorSequenceKeypoint.new(0.00, Color3.fromRGB(8, 45, 255)), ColorSequenceKeypoint.new(1.00, Color3.fromRGB(8, 45, 255))},
		Rotation = 90,
	})

	main.LogoTextFolder = lib:Create("Folder", {
		Name = "LogoTextFolder",
	})

	main.LogoText1 = lib:Create("TextLabel", {
		BackgroundColor3 = Color3.fromRGB(255, 255, 255),
		BackgroundTransparency = 1.000,
		BorderSizePixel = 0,
		Position = UDim2.new(-0.0204402134, 0, 0.125, 0),
		Size = UDim2.new(0, 52, 0, 30),
		Font = Enum.Font.GothamSemibold,
		Text = "l",
		TextColor3 = Color3.fromRGB(65, 255, 65),
		TextSize = 27.000,
		TextTransparency = 0.200,
	})

	main.LogoText2 = lib:Create("TextLabel", {
		BackgroundColor3 = Color3.fromRGB(255, 255, 255),
		BackgroundTransparency = 1.000,
		BorderSizePixel = 0,
		Position = UDim2.new(0.0129673611, 0, 0.125, 0),
		Size = UDim2.new(0, 17, 0, 30),
		Font = Enum.Font.GothamSemibold,
		Text = "-",
		TextColor3 = Color3.fromRGB(17, 124, 255),
		TextSize = 27.000,
		TextTransparency = 0.200,
	})

	main.LogoText3 = lib:Create("TextLabel", {
		BackgroundColor3 = Color3.fromRGB(255, 255, 255),
		BackgroundTransparency = 1.000,
		BorderSizePixel = 0,
		Position = UDim2.new(-0.0204402227, 0, 0.125, 0),
		Size = UDim2.new(0, 47, 0, 30),
		Font = Enum.Font.GothamSemibold,
		Text = "k",
		TextColor3 = Color3.fromRGB(255, 28, 100),
		TextSize = 27.000,
		TextTransparency = 0.200,
	})


	main.LogoText4 = lib:Create("TextLabel", {
		BackgroundColor3 = Color3.fromRGB(255, 255, 255),
		BackgroundTransparency = 1.000,
		BorderSizePixel = 0,
		Position = UDim2.new(0.0331138819, 0, 0.125, 0),
		Size = UDim2.new(0, 87, 0, 30),
		Font = Enum.Font.GothamBold,
		Text = "祖先V2翻译者，",
		TextColor3 = Color3.fromRGB(255, 255, 255),
		TextSize = 27.000,
	})

	main.LogoText5 = lib:Create("TextLabel", {
		BackgroundColor3 = Color3.fromRGB(255, 255, 255),
		BackgroundTransparency = 1.000,
		BorderSizePixel = 0,
		Position = UDim2.new(0.19138819, 0, 0.105, 0),
		Size = UDim2.new(0, 87, 0, 30),
		Font = Enum.Font.GothamBold,
		Text = '',
		TextColor3 = Color3.fromRGB(255, 255, 255),
		TextSize = 20.000,
		TextXAlignment = Enum.TextXAlignment.Left
	})

	main.CloseFrame = lib:Create("ImageLabel", {
		Name = "CloseFrame",
		BackgroundColor3 = Color3.fromRGB(255, 255, 255),
		BackgroundTransparency = 1.000,
		Position = UDim2.new(0.958662987, 0, 0.250000001, 0),
		Size = UDim2.new(0, 15, 0, 15),
		Image = "rbxassetid://3570695787",
		ImageColor3 = Color3.fromRGB(255, 0, 4),
		ScaleType = Enum.ScaleType.Slice,
		SliceCenter = Rect.new(100, 100, 100, 100),
		SliceScale = 0.120,
		ImageTransparency = 1,
	})

	main.Close = lib:Create("TextButton", {
		Name = "Close",
		BackgroundColor3 = Color3.fromRGB(255, 255, 255),
		BackgroundTransparency = 1.000,
		BorderSizePixel = 0,
		Position = UDim2.new(0, 0, -0.466666669, 0),
		Size = UDim2.new(0, 15, 0, 25),
		Font = Enum.Font.SourceSans,
		Text = "x",
		TextColor3 = Color3.fromRGB(255, 255, 255),
		TextSize = 18.000,
	})

	main.Close.MouseEnter:Connect(function()
		TweenService:Create(main.CloseFrame, TweenInfo.new(0.1), {ImageTransparency = 0}):Play()
	end)

	main.Close.MouseLeave:Connect(function()
		TweenService:Create(main.CloseFrame, TweenInfo.new(0.1), {ImageTransparency = 1}):Play()
	end)

	main.CategoryContainer = lib:Create("ScrollingFrame", {
		Name = "CategoryContainer",
		Active = true,
		BackgroundColor3 = Color3.fromRGB(47, 47, 47),
		BorderSizePixel = 0,
		Position = UDim2.new(0, 0, 0.131578952, 0),
		Size = UDim2.new(0, 50, 0, 264),
		CanvasSize = UDim2.new(0, 0, 0, 1),
		ScrollBarThickness = 0,
		ScrollBarImageColor3=Color3.fromRGB(75,75,75)
	})

	main.CategoryPadding = lib:Create("UIPadding", {
		PaddingTop = UDim.new(0, 2),
		PaddingBottom = UDim.new(0, 2),
	})

	main.CategoryLayout = lib:Create("UIListLayout", {
		SortOrder = Enum.SortOrder.LayoutOrder,
		Padding = UDim.new(0, 3),
	})

	function main:Category(ImageId)
		local categories = {}

		categories.Button = lib:Create("ImageButton", {
			Active = false,
			BackgroundColor3 = Color3.fromRGB(65, 65, 65),
			BorderSizePixel = 0,
			Selectable = false,
			Size = UDim2.new(1, 0, 0, 50),
			AutoButtonColor = false,
			Image = "http://www.roblox.com/asset/?id="..ImageId,
		})

		categories.Container = lib:Create("ScrollingFrame", {
			BackgroundColor3 = Color3.fromRGB(17, 17, 17),
			BorderSizePixel = 0,
			Position = UDim2.new(0.091575101, 0, 0.138557434, 0),
			Selectable = false,
			Size = UDim2.new(0, 503, 0, 262),
			ScrollBarThickness = 7,
			ScrollBarImageColor3=Color3.fromRGB(75,75,75),
			CanvasSize = UDim2.new(0,0,.2,1.3),
			Visible = false,
		})

		if firstC then 
			categories.Container.Visible = true 
		end 

		categories.ContainerLayout = lib:Create("UIListLayout", {
			SortOrder = Enum.SortOrder.LayoutOrder,
			Padding = UDim.new(0, 5),
		})

		categories.ContainerPadding = lib:Create("UIPadding", {
			PaddingLeft = UDim.new(0, 5),
			PaddingBottom = UDim.new(0,5),
		})

		categories.Button.MouseButton1Click:Connect(function()
			for i,v in pairs(main.MainBody:GetChildren()) do 
				if v.Name == "ScrollingFrame" then 
					v.Visible = false 
				end
			end

			categories.Container.Visible = true
		end)

		function categories:Section(Name)
			local sections = {}

			sections.sectionname = lib:Create("TextLabel", {
				Name = Name.."Section",
				BackgroundColor3 = Color3.fromRGB(255, 255, 255),
				BackgroundTransparency = 1.000,
				BorderSizePixel = 0,
				Position = UDim2.new(0.00994035788, 0, 0, 0),
				Size = UDim2.new(0, 105, 0, 30),
				Font = Enum.Font.SourceSansLight,
				Text = Name,
				TextColor3 = Color3.fromRGB(255, 255, 255),
				TextSize = 27.000,
				TextXAlignment = Enum.TextXAlignment.Left,
			})

			categories.Container.CanvasSize = categories.Container.CanvasSize + UDim2.new(0,0,0,40)

			function sections:Button(Name, CallBack, Animated)
				local buttons = {}

				buttons.buttonb = lib:Create("ImageLabel", {
					Name = Name.."Button",
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					Position = UDim2.new(0.00415800419, 0, 0.86175108, 0),
					Size = UDim2.new(0, 484, 0, 35),
					Image = "rbxassetid://3570695787",
					ImageColor3 = Color3.fromRGB(65, 65, 65),
					ScaleType = Enum.ScaleType.Slice,
					SliceCenter = Rect.new(100, 100, 100, 100),
					SliceScale = 0.040,
				})

				buttons.buttonframe = lib:Create("ImageLabel", {
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					Position = UDim2.new(0.009999929, 0, 0.0857142881, 0),
					Size = UDim2.new(0, 476, 0, 29),
					Image = "rbxassetid://3570695787",
					ImageColor3 = Color3.fromRGB(55, 55, 55),
					ScaleType = Enum.ScaleType.Slice,
					SliceCenter = Rect.new(100, 100, 100, 100),
					SliceScale = 0.040,
				})

				buttons.button = lib:Create("TextButton", {
					BackgroundColor3 = Color3.fromRGB(55, 55, 55),
					BackgroundTransparency = 1.000,
					BorderSizePixel = 0,
					Size = UDim2.new(0, 476, 0, 29),
					AutoButtonColor = false,
					Text = Name,
					Font = Enum.Font.GothamSemibold,
					TextColor3 = Color3.fromRGB(255, 255, 255),
					TextSize = 16.000,
				})

				buttons.button.MouseButton1Click:Connect(function()

					if Animated then 
						TweenService:Create(buttons.buttonframe, TweenInfo.new(0.1), {Size = UDim2.new(0, 440,0, 25),  Position = UDim2.new(0.047, 0,0.143, 0)}):Play()
						TweenService:Create(buttons.button, TweenInfo.new(0.1), {Size = UDim2.new(0, 437,0, 25), Position = UDim2.new(0,0,0,0)}):Play()
						wait(0.05)
						TweenService:Create(buttons.buttonframe, TweenInfo.new(0.1), {Size = UDim2.new(0, 476,0, 29), Position = UDim2.new(0.01, 0,0.086, 0)}):Play()
						TweenService:Create(buttons.button, TweenInfo.new(0.1), {Size = UDim2.new(0, 476,0, 29), Position = UDim2.new(0, 0,0, 0)}):Play()
					end
                    if CallBack then 
						CallBack()
					end
				end)

				buttons.buttonb.Parent = categories.Container
				buttons.buttonframe.Parent = buttons.buttonb
				buttons.button.Parent = buttons.buttonframe

				categories.Container.CanvasSize = categories.Container.CanvasSize + UDim2.new(0,0,0,45)

				return buttons 
			end

			function sections:Toggle(Name, CallBack, Default)
				local toggles = {}
				local toggled = false

				toggles.toggle = lib:Create("ImageButton", {
					Name = Name.."Toggle",
					Active = false,
					BackgroundColor3 = Color3.fromRGB(248, 248, 248),
					BackgroundTransparency = 1.000,
					Position = UDim2.new(0.00415800419, 0, 0.86175108, 0),
					Selectable = false,
					Size = UDim2.new(0, 484, 0, 35),
					Image = "rbxassetid://3570695787",
					ImageColor3 = Color3.fromRGB(65, 65, 65),
					ScaleType = Enum.ScaleType.Slice,
					SliceCenter = Rect.new(100, 100, 100, 100),
					SliceScale = 0.040,
				}) 

				toggles.togglename = lib:Create("TextLabel", {
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					BorderSizePixel = 0,
					Size = UDim2.new(0, 79, 0, 35),
					Font = Enum.Font.GothamSemibold,
					Position = UDim2.new(0,5,0,0),
					TextXAlignment = Enum.TextXAlignment.Left,
					Text = Name,
					TextColor3 = Color3.fromRGB(255, 255, 255),
					TextSize = 16.000,
					TextScaled = true,
					TextWrapped = true,
				})

				toggles.t1 = lib:Create("ImageLabel", {
					Name = "ToggleFrame",
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					Position = UDim2.new(1, -58, 0.0857142881, 0),
					Size = UDim2.new(0, 55, 0, 29), -- THE ONE I WANT TO CHANGE
					Image = "rbxassetid://3570695787",
					ImageColor3 = Color3.fromRGB(55, 55, 55),
					ScaleType = Enum.ScaleType.Slice,
					SliceCenter = Rect.new(100, 100, 100, 100),
					SliceScale = 0.040,
				})

				toggles.t2 = lib:Create("ImageLabel", {
					Name = "ToggleFrame",
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					AnchorPoint = Vector2.new(0.5,0.5),
					Position = UDim2.new(0.5,0, 0.5,0),
					Size = UDim2.new(0, 43, 0, 21),
					Image = "rbxassetid://3570695787",
					ImageColor3 = Color3.fromRGB(45, 45, 45),
					ScaleType = Enum.ScaleType.Slice,
					SliceCenter = Rect.new(100, 100, 100, 100),
					SliceScale = 0.040
				})

				toggles.t3 = lib:Create("ImageLabel", {
					Name = "ToggleFrame",
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					Position = UDim2.new(0, 0, 0, 0),
					Size = UDim2.new(0, 12, 0, 21),
					Image = "rbxassetid://3570695787",
					ScaleType = Enum.ScaleType.Slice,
					SliceCenter = Rect.new(100, 100, 100, 100),
					SliceScale = 0.040,
				})

				if Default then 
					toggled = true

					TweenService:Create(toggles.t3, TweenInfo.new(0.1), {Position = UDim2.new(0.700523198, 0, 0, 0)}):Play()

					if CallBack then 
						CallBack(toggled)
					end 
				end

				toggles.toggle.Parent = categories.Container
				toggles.togglename.Parent = toggles.toggle
				toggles.t1.Parent = toggles.toggle 
				toggles.t2.Parent = toggles.t1 
				toggles.t3.Parent = toggles.t2

				toggles.toggle.MouseButton1Click:Connect(function()
					toggled = not toggled

					if toggled then 
						TweenService:Create(toggles.t3, TweenInfo.new(0.1), {Position = UDim2.new(0.700523198, 0, 0, 0)}):Play()
					else 
						TweenService:Create(toggles.t3, TweenInfo.new(0.1), {Position = UDim2.new(0, 0, 0, 0)}):Play()
					end

					if CallBack then 
						CallBack(toggled)
					end 
				end)

				categories.Container.CanvasSize = categories.Container.CanvasSize + UDim2.new(0,0,0,40)

				return toggles
			end

			function sections:TextLabel(Text)
				local textlabels = {}

				textlabels.textlabelframe = lib:Create("ImageLabel", {
					Name = "TextLabel",
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					Position = UDim2.new(0.00415800419, 0, 0.86175108, 0),
					Size = UDim2.new(0, 484, 0, 35),
					Image = "rbxassetid://3570695787",
					ImageColor3 = Color3.fromRGB(65, 65, 65),
					ScaleType = Enum.ScaleType.Slice,
					SliceCenter = Rect.new(100, 100, 100, 100),
					SliceScale = 0.040,
				})

				textlabels.textlabelframe2 = lib:Create("ImageLabel", {
					Name = "TextLabelFrame",
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					Position = UDim2.new(0.009999929, 0, 0.0857142881, 0),
					Size = UDim2.new(0, 476, 0, 29),
					Image = "rbxassetid://3570695787",
					ImageColor3 = Color3.fromRGB(55, 55, 55),
					ScaleType = Enum.ScaleType.Slice,
					SliceCenter = Rect.new(100, 100, 100, 100),
					SliceScale = 0.04,
				})

				textlabels.textlabel = lib:Create("TextLabel", {          
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					BorderSizePixel = 0,
					Position = UDim2.new(0, 0, -0.103448279, 0),
					Size = UDim2.new(0, 476, 0, 35),
					Font = Enum.Font.GothamSemibold,
					Text = Text,
					TextColor3 = Color3.fromRGB(255, 255, 255),
					TextSize = 16.000,
					TextWrapped = true,
				})

				categories.Container.CanvasSize = categories.Container.CanvasSize + UDim2.new(0,0,0,40)

				textlabels.textlabelframe.Parent = categories.Container
				textlabels.textlabelframe2.Parent = textlabels.textlabelframe
				textlabels.textlabel.Parent = textlabels.textlabelframe2

				return textlabels
			end

			function sections:Slider(Name, CallBack, Min, Max)
				local sliders = {}
				local slidervalue = 0

				sliders.sliderb = lib:Create("ImageLabel", {
					Name = Name.."Slider",
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					Position = UDim2.new(0.00415800419, 0, 0.86175108, 0),
					Size = UDim2.new(0, 484, 0, 35),
					Image = "rbxassetid://3570695787",
					ImageColor3 = Color3.fromRGB(65, 65, 65),
					ScaleType = Enum.ScaleType.Slice,
					SliceCenter = Rect.new(100, 100, 100, 100),
					SliceScale = 0.040,
				})

				sliders.slidertext = lib:Create("TextLabel", {
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					BorderSizePixel = 0,
					Size = UDim2.new(0, 79, 0, 35),
					TextXAlignment = Enum.TextXAlignment.Left,
					Position = UDim2.new(0, 5, 0, 0),
					Font = Enum.Font.GothamSemibold,
					Text = Name,
					TextColor3 = Color3.fromRGB(255, 255, 255),
					TextSize = 16.000,
					TextScaled = true,
					TextWrapped = true,
				})

				sliders.darkoutline = lib:Create("ImageLabel", {
					Name = "SliderDarkOutline",
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					Position = UDim2.new(1, -303, 0.0857142881, 0),
					Size = UDim2.new(0, 300, 0, 29),
					Image = "rbxassetid://3570695787",
					ImageColor3 = Color3.fromRGB(55, 55, 55),
					ScaleType = Enum.ScaleType.Slice,
					SliceCenter = Rect.new(100, 100, 100, 100),
					SliceScale = 0.040,
				})

				sliders.sliderinnerback = lib:Create("ImageLabel", {
					Name = "SliderInner",
					AnchorPoint = Vector2.new(0,0.5),
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					Position = UDim2.new(0, 4, 0.5, 0),
					Size = UDim2.new(0, 256, 0, 12),
					Image = "rbxassetid://3570695787",
					ImageColor3 = Color3.fromRGB(45, 45, 45),
					ScaleType = Enum.ScaleType.Slice,
					SliceCenter = Rect.new(100, 100, 100, 100),
					SliceScale = 0.040,
				})

				sliders.slider = lib:Create("TextButton", {
					Name = "SliderButton",
					BackgroundColor3 = Color3.fromRGB(55, 55, 55),
					BackgroundTransparency = 1.000,
					BorderSizePixel = 0,
					Position = UDim2.new(0, 0, 0, 0),
					Size = UDim2.new(1, 0, 0, 12),
					AutoButtonColor = false,
					Font = Enum.Font.SourceSans,
					Text = "",
					TextColor3 = Color3.fromRGB(0, 0, 0),
					TextSize = 14.000,
				})

				sliders.sliderinner = lib:Create("ImageLabel", {
					Name = "SliderInner",
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					Size = UDim2.new(0, 0, 0, 12),
					Image = "rbxassetid://3570695787",
					ImageColor3 = Color3.fromRGB(24, 116, 255),
					ScaleType = Enum.ScaleType.Slice,
					SliceCenter = Rect.new(100, 100, 100, 100),
					SliceScale = 0.040,
				})

				sliders.slidervalue = lib:Create("TextLabel", {
					Name = "SliderValue",
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					BorderSizePixel = 0,
					Position = UDim2.new(1, -204, 0, 0),
					Size = UDim2.new(0, 199, 0, 28),
					Font = Enum.Font.Gotham,
					Text = Min,
					TextColor3 = Color3.fromRGB(255, 255, 255),
					TextSize = 16.000,
					TextWrapped = true,
					TextXAlignment = Enum.TextXAlignment.Right,
				})

				sliders.slider.MouseButton1Down:Connect(function()
					local connection = game:GetService("RunService").Heartbeat:Connect(function()
						local Scale = math.clamp(Mouse.X - sliders.slider.AbsolutePosition.X,0,sliders.slider.AbsoluteSize.X) / sliders.slider.AbsoluteSize.X
						slidervalue = math.floor(Min + ((Max-Min) * Scale))
						sliders.slidervalue.Text = tostring(slidervalue)

						if CallBack then
							CallBack(slidervalue)
						end

						TweenService:Create(sliders.sliderinner, TweenInfo.new(0.04), {Size = UDim2.new(Scale, 0, 1, -2)}):Play()
					end)
					UIS.InputEnded:Connect(function(i)
						if i.UserInputType == Enum.UserInputType.MouseButton1 then
							if connection then
								connection:Disconnect()
								connection = nil
							end
						end
					end)
				end)

				categories.Container.CanvasSize = categories.Container.CanvasSize + UDim2.new(0,0,0,40)

				sliders.sliderb.Parent = categories.Container
				sliders.slidertext.Parent = sliders.sliderb
				sliders.darkoutline.Parent = sliders.sliderb
				sliders.sliderinnerback.Parent = sliders.darkoutline
				sliders.slider.Parent = sliders.sliderinnerback
				sliders.sliderinner.Parent = sliders.slider
				sliders.slidervalue.Parent = sliders.darkoutline

				return sliders
			end 

			function sections:TextBox(Name, CallBack, PlaceholderText, AutoName)
				local tb = {}
				local text

				tb.textboxback = lib:Create("ImageLabel", {
					Name = Name.."TextBox",
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					Position = UDim2.new(0.00214187521, 0, 0.886178553, 0),
					Size = UDim2.new(0, 484, 0, 35),
					Image = "rbxassetid://3570695787",
					ImageColor3 = Color3.fromRGB(65, 65, 65),
					ScaleType = Enum.ScaleType.Slice,
					SliceCenter = Rect.new(100, 100, 100, 100),
					SliceScale = 0.040,
				})

				tb.text = lib:Create("TextLabel", {
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					BorderSizePixel = 0,
					Size = UDim2.new(0, 79, 0, 35),
					Font = Enum.Font.GothamSemibold,
					Text = Name,
					Position = UDim2.new(0,5,0,0),
					TextXAlignment = Enum.TextXAlignment.Left,
					TextColor3 = Color3.fromRGB(255, 255, 255),
					TextSize = 16.000,
					TextScaled = true,
					TextWrapped = true,
				})

				tb.darkoutline = lib:Create("ImageLabel", {
					Name = "TextBoxFrame",
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					Position = UDim2.new(1, -354, 0.0857142881, 0),
					Size = UDim2.new(0, 350, 0, 29),
					Image = "rbxassetid://3570695787",
					ImageColor3 = Color3.fromRGB(55, 55, 55),
					ScaleType = Enum.ScaleType.Slice,
					SliceCenter = Rect.new(100, 100, 100, 100),
					SliceScale = 0.040,
				})

				tb.textbox = lib:Create("TextBox", {
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					BorderSizePixel = 0,
					Size = UDim2.new(0, 350, 0, 29),
					Font = Enum.Font.GothamSemibold,
					PlaceholderColor3 = Color3.fromRGB(178, 178, 178),
					PlaceholderText = PlaceholderText,
					Text = "",
					TextColor3 = Color3.fromRGB(255, 255, 255),
					TextSize = 16.000,
				})

				tb.textbox.FocusLost:Connect(function()
					if not AutoName and CallBack then
						CallBack(tb.textbox.Text)
					elseif AutoName then 
						for i,v in pairs(game.Players:GetChildren()) do
							if string.match(v.Name:lower(),tb.textbox.Text:lower()) then
								tb.textbox.Text = v.Name
							end
						end
						CallBack(tb.textbox.Text)
					end
				end)

				categories.Container.CanvasSize = categories.Container.CanvasSize + UDim2.new(0,0,0,40)

				tb.textboxback.Parent = categories.Container
				tb.text.Parent = tb.textboxback
				tb.darkoutline.Parent = tb.textboxback
				tb.textbox.Parent = tb.darkoutline

				return tb
			end 

			function sections:KeyBind(Name, CallBack, Default)
				local kb = {}
				local kbind

				kb.kbback = lib:Create("ImageLabel", {
					Name = Name.."KeyBind",
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					Position = UDim2.new(0.00214187521, 0, 0.886178553, 0),
					Size = UDim2.new(0, 484, 0, 35),
					Image = "rbxassetid://3570695787",
					ImageColor3 = Color3.fromRGB(65, 65, 65),
					ScaleType = Enum.ScaleType.Slice,
					SliceCenter = Rect.new(100, 100, 100, 100),
					SliceScale = 0.040,
				})

				kb.kbtext = lib:Create("TextLabel", {
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					BorderSizePixel = 0,
					Size = UDim2.new(0, 79, 0, 35),
					Font = Enum.Font.GothamSemibold,
					Position = UDim2.new(0,5,0,0),
					TextXAlignment = Enum.TextXAlignment.Left,
					Text = Name,
					TextColor3 = Color3.fromRGB(255, 255, 255),
					TextSize = 16.000,
				})

				kb.darkoutline = lib:Create("ImageLabel", {
					Name = "SelectKeyBindFrame",
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					Position = UDim2.new(1, -153, 0.0857142881, 0),
					Size = UDim2.new(0, 150, 0, 29),
					Image = "rbxassetid://3570695787",
					ImageColor3 = Color3.fromRGB(55, 55, 55),
					ScaleType = Enum.ScaleType.Slice,
					SliceCenter = Rect.new(100, 100, 100, 100),
					SliceScale = 0.040,
				})

				kb.kb = lib:Create("TextButton", {
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					BorderColor3 = Color3.fromRGB(27, 42, 53),
					BorderSizePixel = 0,
					AnchorPoint = Vector2.new(0,0.5),
					Position = UDim2.new(0, 0, 0.5, 0),
					Size = UDim2.new(1, 0, 0.758620679, 0),
					Font = Enum.Font.Gotham,
					Text = "None",
					TextColor3 = Color3.fromRGB(255, 255, 255),
					TextScaled = true,
					TextSize = 16.000,
					TextWrapped = true,
				})

				local c

				if Default then 
					kbind = Default
					kb.kb.Text = kbind.Name
				end
				local debounce = false
                local connections={};
				kb.kb.MouseButton1Click:Connect(function()
					if debounce then 
						return
					end
					debounce = true
					kb.kb.Text = "..."
					c = UIS.InputBegan:Connect(function(i)
						if i.UserInputType.Name == "Keyboard" and i.KeyCode ~= Enum.KeyCode.Backspace then
							kb.kb.Text = i.KeyCode.Name
							kbind = i.KeyCode
							debounce = false
							if c then
								c:Disconnect()
								c = nil
							end
						elseif i.KeyCode == Enum.KeyCode.Backspace then
							kb.kb.Text = "None"
							kbind = nil
							if c then
								c:Disconnect()
								c = nil
								debounce = false
							end
						end
					end)
				end)

				connections[#connections+1]=game:GetService("UserInputService").InputBegan:Connect(function(i, GPE)
					if kbind and i.KeyCode == kbind and not GPE then
						if CallBack then
							CallBack(i.KeyCode)
						end
					end
				end);

                connections[#connections+1]=game.CoreGui.ChildRemoved:Connect(function(Child)
                    if tostring(Child)=='AncestorV2'then
                        for _,Connection in next,connections do 
                            Connection:Disconnect();
                        end;
                    end;
                end);

				categories.Container.CanvasSize = categories.Container.CanvasSize + UDim2.new(0,0,0,40)

				kb.kbback.Parent = categories.Container
				kb.kbtext.Parent = kb.kbback
				kb.darkoutline.Parent = kb.kbback
				kb.kb.Parent = kb.darkoutline

				return kb
			end

			function sections:DropDown(Name, CallBack, Options, Playerlist)
				local dd = {}
				local toggled = false
				local dvalue 
				local optionstable = {}

				if Options and Options.options and not Playerlist then
					optionstable = Options.options
				elseif Options and Options.options and Playerlist then
					optionstable = {}
					for g,f in pairs(Options.options) do
						if i==1 then 
							i=5
						end
						table.insert(optionstable, f)
					end
					local list = game:GetService("Players"):GetChildren()
					for i,v in pairs(list) do
						if v:IsA("Player") then
							table.insert(optionstable, v.Name);
						end
					end
				elseif Options and not Options.options and Playerlist then
					optionstable = {}
					local list = game:GetService("Players"):GetChildren()
					for i,v in pairs(list) do
						if v:IsA("Player")then
							table.insert(optionstable, v.Name);
						end
					end                                 
				end

				dd.ddback = lib:Create("ImageLabel", {
					Name = Name.."DropDown",
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					Position = UDim2.new(0.00415800419, 0, 0.86175108, 0),
					Size = UDim2.new(0, 484, 0, 35),
					Image = "rbxassetid://3570695787",
					ImageColor3 = Color3.fromRGB(65, 65, 65),
					ScaleType = Enum.ScaleType.Slice,
					SliceCenter = Rect.new(100, 100, 100, 100),
					SliceScale = 0.040,
				})

				dd.dddarkoutline = lib:Create("ImageLabel", {
					Name = "DropDownButtonFrame",
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					Position = UDim2.new(0.009999929, 0, 0.0857142881, 0),
					Size = UDim2.new(0, 476, 0, 29),
					Image = "rbxassetid://3570695787",
					ImageColor3 = Color3.fromRGB(55, 55, 55),
					ScaleType = Enum.ScaleType.Slice,
					SliceCenter = Rect.new(100, 100, 100, 100),
					SliceScale = 0.040,
				})

				dd.ddbutton = lib:Create("TextBox", {
					Name = "DropDownButton",
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					BorderSizePixel = 0,
					Size = UDim2.new(0, 350, 0, 29),
					Font = Enum.Font.GothamSemibold,
					PlaceholderColor3 = Color3.fromRGB(178, 178, 178),
					PlaceholderText = "Search...",
					Position = UDim2.new(0.5,0,0.5,0),
					Text = tostring(optionstable[1]),
					TextColor3 = Color3.fromRGB(255, 255, 255),
					TextSize = 16.000,
					AnchorPoint = Vector2.new(0.5,0.5)
				})

				dd.ddmp = lib:Create("TextButton", {
					Name = "AnotherDopDownButton",
					BackgroundColor3 = Color3.fromRGB(55, 55, 55),
					BackgroundTransparency = 1.000,
					BorderSizePixel = 0,
					Position = UDim2.new(0.938519001, 0, 0, 0),
					Size = UDim2.new(0, 28, 0, 29),
					AutoButtonColor = false,
					Font = Enum.Font.Gotham,
					Text = "+",
					TextColor3 = Color3.fromRGB(255, 255, 255),
					TextSize = 20.000,
				})

				dd.dd = lib:Create("ImageLabel", {
					Name = "DropDown",
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					Position = UDim2.new(-0.0105477981, 0, 1.37899256, 0),
					Size = UDim2.new(0, 484, 0, 66),
					ZIndex = 5,
					Visible = false,
					Image = "rbxassetid://3570695787",
					ImageColor3 = Color3.fromRGB(65, 65, 65),
					ScaleType = Enum.ScaleType.Slice,
					SliceCenter = Rect.new(100, 100, 100, 100),
					SliceScale = 0.040,
				})

				dd.ddscrolling = lib:Create("ScrollingFrame", {
					Name = "SectionConatiner",
					Active = true,
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					BorderSizePixel = 0,
					Position = UDim2.new(0.00206611562, 0, 0.0606060624, 0),
					Size = UDim2.new(0, 478, 0, 62),
					ZIndex = 5,
					CanvasSize = UDim2.new(0, 0, 0, 0),
					ScrollBarThickness = 7,
				})

				dd.ddscrollinglayout = lib:Create("UIListLayout", {
					SortOrder = Enum.SortOrder.LayoutOrder,
					Padding = UDim.new(0, 5),
				})

				local function refreshlist()
					if Playerlist then 
						optionstable = {}
						local list = game.Players:GetChildren()
						for i,v in pairs(list) do
							if v:IsA("Player") then
								table.insert(optionstable, v.Name)
							end
						end
					end

					for i,v in next, dd.ddscrolling:GetChildren() do
						if v:IsA("ImageLabel") then
							v:Destroy()
						end
					end

					for i,v in next, optionstable do
						local buttonback = lib:Create("ImageLabel", {
							Name = string.lower(v),
							BackgroundColor3 = Color3.fromRGB(255, 255, 255),
							BackgroundTransparency = 1.000,
							Position = UDim2.new(0.009999929, 0, 0.0857142881, 0),
							Size = UDim2.new(0, 476, 0, 29),
							ZIndex = 5,
							Image = "rbxassetid://3570695787",
							ImageColor3 = Color3.fromRGB(55, 55, 55),
							ScaleType = Enum.ScaleType.Slice,
							SliceCenter = Rect.new(100, 100, 100, 100),
							SliceScale = 0.040,
						})

						local button = lib:Create("TextButton", {
							Name = "Button",
							BackgroundColor3 = Color3.fromRGB(55, 55, 55),
							BackgroundTransparency = 1.000,
							BorderSizePixel = 0,
							Position = UDim2.new(0, 0, 0, 0),
							Size = UDim2.new(0, 475, 0, 29),
							ZIndex = 5,
							AutoButtonColor = false,
							Font = Enum.Font.GothamSemibold,
							Text = v,
							TextColor3 = Color3.fromRGB(255, 255, 255),
							TextSize = 16.000,
						})

						buttonback.Parent = dd.ddscrolling
						button.Parent = buttonback

						button.MouseButton1Click:Connect(function()
							if toggled then

								toggled = not toggled
								dd.ddbutton.Text = v
								dvalue = v

								if toggled then 
									dd.ddmp.Text = "-"
									dd.dd.Visible = true
									TweenService:Create(dd.ddscrolling, TweenInfo.new(0.1), {CanvasSize = UDim2.new(0, 0, 0, dd.ddscrolling["UIListLayout"].AbsoluteContentSize.Y) + UDim2.new(0,0,0,5)}):Play()
								else 
									dd.ddmp.Text = "+"
									dd.dd.Visible = false
									TweenService:Create(dd.ddscrolling, TweenInfo.new(0.1), {CanvasSize = UDim2.new(0, 0, 0, dd.ddscrolling["UIListLayout"].AbsoluteContentSize.Y) + UDim2.new(0,0,0,5)}):Play()
								end

								if CallBack then
									CallBack(dvalue)
								end
							end
						end)
					end
				end

				refreshlist()

				dd.ddbutton.Text = optionstable and optionstable[1] or "None"

				dd.ddbutton.Focused:Connect(function()
					toggled = true
					if Options and Options.CallBack then
						optionstable = Options.CallBack()
					end
					refreshlist()
					dd.ddmp.Text = "-"
					dd.dd.Visible = true
					TweenService:Create(dd.ddscrolling, TweenInfo.new(0.1), {CanvasSize = UDim2.new(0, 0, 0, dd.ddscrolling["UIListLayout"].AbsoluteContentSize.Y) + UDim2.new(0,0,0,5)}):Play()
				end)

				dd.ddmp.MouseButton1Click:Connect(function()
					toggled = not toggled
					if Options and Options.CallBack then
						optionstable = Options.CallBack()
					end
					if toggled then 
						refreshlist()
						dd.ddmp.Text = "-"
						dd.dd.Visible = true
						TweenService:Create(dd.ddscrolling, TweenInfo.new(0.1), {CanvasSize = UDim2.new(0, 0, 0, dd.ddscrolling["UIListLayout"].AbsoluteContentSize.Y) + UDim2.new(0,0,0,5)}):Play()
					else 
						refreshlist()
						dd.ddmp.Text = "+"
						dd.dd.Visible = false
						TweenService:Create(dd.ddscrolling, TweenInfo.new(0.1), {CanvasSize = UDim2.new(0, 0, 0, dd.ddscrolling["UIListLayout"].AbsoluteContentSize.Y) + UDim2.new(0,0,0,5)}):Play()
					end
				end)

				dd.ddbutton:GetPropertyChangedSignal("Text"):Connect(function()
					local tosearch,count = dd.ddbutton.Text,0
					for i,v in next, dd.ddscrolling:GetChildren() do 
						if v:IsA("ImageLabel") then
							if v.Name:find(tosearch:lower()) then
								v.Visible = true 
								count=count+1
							else 
								v.Visible = false
							end
						end
					end
					TweenService:Create(dd.ddscrolling, TweenInfo.new(0.1), {CanvasSize = UDim2.new(0, 0, 0, count*34)}):Play()
				end)

				dd.ddback.Parent = categories.Container
				dd.dddarkoutline.Parent = dd.ddback
				dd.ddbutton.Parent = dd.dddarkoutline
				dd.ddmp.Parent = dd.dddarkoutline
				dd.dd.Parent = dd.dddarkoutline
				dd.ddscrolling.Parent = dd.dd
				dd.ddscrollinglayout.Parent = dd.ddscrolling

				categories.Container.CanvasSize = categories.Container.CanvasSize + UDim2.new(0,0,0,40)

				return dd   
			end 

			function sections:ColorPicker(Name, CallBack, Default)
				local colorstuff = {}
				local colorpickeropend = false
				local colorvalue

				colorstuff.colorpickerb = lib:Create("ImageButton", {
					BackgroundColor3 = Color3.fromRGB(55,55,55),
					BackgroundTransparency = 1.000,
					BorderColor3 = Color3.fromRGB(27, 42, 53),
					Position = UDim2.new(0, 11, 0, 125),
					Size = UDim2.new(0, 484, 0, 35),
					Image = "rbxassetid://3570695787",
					ImageColor3 = Color3.fromRGB(65, 65, 65),
					ScaleType = Enum.ScaleType.Slice,
					SliceCenter = Rect.new(100, 100, 100, 100),
					SliceScale = 0.040,
				})

				colorstuff.colorpickerbgray = lib:Create("ImageLabel", {
					Name = "ColorpickDarkframe",
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					Position = UDim2.new(0.309917361, 0, 0.0857142881, 0),
					Size = UDim2.new(0, 330, 0, 29),
					Image = "rbxassetid://3570695787",
					ImageColor3 = Color3.fromRGB(55, 55, 55),
					ScaleType = Enum.ScaleType.Slice,
					SliceCenter = Rect.new(100, 100, 100, 100),
					SliceScale = 0.040,
				})

				colorstuff.colorpickertext = lib:Create("TextLabel", {
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					BorderSizePixel = 0,
					Position = UDim2.new(0, 4, 0, 2),
					Size = UDim2.new(0, 200, 0, 30),
					Font = Enum.Font.GothamSemibold,
					Text = Name,
					TextColor3 = Color3.fromRGB(255, 255, 255),
					TextSize = 16.000,
					TextXAlignment = Enum.TextXAlignment.Left,
				})

				colorstuff.colorpickerbutton = lib:Create("ImageLabel", {
					Active = true,
					BackgroundColor3 = Color3.fromRGB(248, 248, 248),
					BackgroundTransparency = 1.000,
					BorderSizePixel = 0,
					Position = UDim2.new(0.0185848344, 0, 0.137931034, 0),
					Selectable = true,
					Size = UDim2.new(0, 318, 0, 21),
					Image = "rbxassetid://3570695787",
					ImageColor3 = Color3.fromRGB(255, 0, 4),
					ScaleType = Enum.ScaleType.Slice,
					SliceCenter = Rect.new(100, 100, 100, 100),
					SliceScale = 0.040,
				})

				colorstuff.colorpickerframeb = lib:Create("Frame", {
					Name = "colorframe",
					BackgroundColor3 = Color3.fromRGB(46, 46, 54),
					BorderSizePixel = 0,
					Position = UDim2.new(0, 560, 0, 0),
					Size = UDim2.new(0, 0, 0, 180),
					BackgroundTransparency = 1,
				})
				colorstuff.colorpickerframeb.ClipsDescendants = true

				colorstuff.colorpickerframe = lib:Create("Frame", {
					BackgroundColor3 = Color3.fromRGB(46, 46, 54),
					BorderSizePixel = 0,
					Position = UDim2.new(0, 0, 0, 0),
					Size = UDim2.new(0, 190, 0, 180),                            
				})
				colorstuff.colorpickerframe.ClipsDescendants = true

				colorstuff.rback = lib:Create("ImageLabel", {
					Active = true,
					AnchorPoint = Vector2.new(0.5, 0.5),
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					Position = UDim2.new(0, 35, 0, 165),
					Selectable = true,
					Size = UDim2.new(0, 50, 0, 20),
					ZIndex = 2,
					Image = "rbxassetid://3570695787",
					ImageColor3 = Color3.fromRGB(40,40,40),
					ScaleType = Enum.ScaleType.Slice,
					SliceCenter = Rect.new(100, 100, 100, 100),
					SliceScale = 0.040,
				})

				colorstuff.rvalue = lib:Create("TextLabel", {
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					Position = UDim2.new(0, 18, 0, 3),
					Size = UDim2.new(0, 25, 0, 15),
					ZIndex = 2,
					Font = Enum.Font.GothamBold,
					Text = "255",
					TextColor3 = Color3.fromRGB(255, 255, 255),
					TextSize = 11.000,
				})

				colorstuff.rtext = lib:Create("TextLabel", {
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					Position = UDim2.new(0, 4, 0, 3),
					Size = UDim2.new(0, 15, 0, 15),
					ZIndex = 2,
					Font = Enum.Font.GothamBold,
					Text = "R:",
					TextColor3 = Color3.fromRGB(255, 255, 255),
					TextSize = 14.000,
				})

				colorstuff.gback = lib:Create("ImageLabel", {
					Active = true,
					AnchorPoint = Vector2.new(0.5, 0.5),
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					BorderSizePixel = 0,
					Position = UDim2.new(0.5, 0, 0, 165),
					Selectable = true,
					Size = UDim2.new(0, 50, 0, 20),
					ZIndex = 2,
					Image = "rbxassetid://3570695787",
					ImageColor3 = Color3.fromRGB(40,40,40),
					ScaleType = Enum.ScaleType.Slice,
					SliceCenter = Rect.new(100, 100, 100, 100),
					SliceScale = 0.040,
				})

				colorstuff.gvalue = lib:Create("TextLabel", {
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					Position = UDim2.new(0, 18, 0, 3),
					Size = UDim2.new(0, 25, 0, 15),
					ZIndex = 2,
					Font = Enum.Font.GothamBold,
					Text = "255",
					TextColor3 = Color3.fromRGB(255, 255, 255),
					TextSize = 11.000,
				})

				colorstuff.gtext = lib:Create("TextLabel", {
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					Position = UDim2.new(0, 4, 0, 3),
					Size = UDim2.new(0, 15, 0, 15),
					ZIndex = 2,
					Font = Enum.Font.GothamBold,
					Text = "G:",
					TextColor3 = Color3.fromRGB(255, 255, 255),
					TextSize = 14.000,
					TextWrapped = true,
				})

				colorstuff.bback = lib:Create("ImageLabel", {
					Active = true,
					AnchorPoint = Vector2.new(0.5, 0.5),
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					Position = UDim2.new(0, 155, 0, 165),
					Selectable = true,
					Size = UDim2.new(0, 50, 0, 20),
					Image = "rbxassetid://3570695787",
					ImageColor3 = Color3.fromRGB(40,40,40),
					ScaleType = Enum.ScaleType.Slice,
					SliceCenter = Rect.new(100, 100, 100, 100),
					SliceScale = 0.040,
				})

				colorstuff.bvalue = lib:Create("TextLabel", {
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					Position = UDim2.new(0, 18, 0, 3),
					Size = UDim2.new(0, 25, 0, 15),
					ZIndex = 2,
					Font = Enum.Font.GothamBold,
					Text = "255",
					TextColor3 = Color3.fromRGB(255, 255, 255),
					TextSize = 11.000,
				})

				colorstuff.btext = lib:Create("TextLabel", {
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					Position = UDim2.new(0, 4, 0, 3),
					Size = UDim2.new(0, 15, 0, 15),
					ZIndex = 2,
					Font = Enum.Font.GothamBold,
					Text = "B:",
					TextColor3 = Color3.fromRGB(255, 255, 255),
					TextSize = 14.000,
				})

				colorstuff.sback = lib:Create("ImageLabel", {
					BackgroundColor3 = Color3.fromRGB(46, 46, 54),
					BackgroundTransparency = 1.000,
					BorderSizePixel = 0,
					Position = UDim2.new(0.0469999984, 0, 0, 10),
					Size = UDim2.new(0, 140, 0, 140),
					ZIndex = 2,
					Image = "rbxassetid://4695575676",
					ImageColor3 = Color3.fromRGB(46, 46, 54),
					ScaleType = Enum.ScaleType.Slice,
					SliceCenter = Rect.new(128, 128, 128, 128),
					SliceScale = 0.040,
				})

				colorstuff.sat = lib:Create("ImageButton", {
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BorderColor3 = Color3.fromRGB(221, 221, 221),
					BorderSizePixel = 0,
					Size = UDim2.new(0, 140, 0, 140),
					AutoButtonColor = false,
					Image = "http://www.roblox.com/asset/?id=5113592272",
					ImageColor3 = Color3.fromRGB(255, 0, 0),
				})

				colorstuff.light = lib:Create("ImageLabel", {
					BackgroundTransparency = 1.000,
					BorderSizePixel = 0,
					Size = UDim2.new(1, 0, 1, 0),
					Image = "http://www.roblox.com/asset/?id=5113600420",
				})

				colorstuff.ring = lib:Create("ImageLabel", {
					AnchorPoint = Vector2.new(0.5, 0.5),
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					Position = UDim2.new(0, 140, 0, 0),
					Size = UDim2.new(0, 10, 0, 10),
					SizeConstraint = Enum.SizeConstraint.RelativeYY,
					ZIndex = 5,
					Image = "rbxassetid://244221613",
					ImageColor3 = Color3.fromRGB(0, 0, 0),
				})

				colorstuff.rainbowback = lib:Create("ImageLabel", {
					BackgroundColor3 = Color3.fromRGB(46, 46, 54),
					BackgroundTransparency = 1.000,
					BorderSizePixel = 0,
					Position = UDim2.new(0, 160, 0, 10),
					Size = UDim2.new(0, 20, 0, 140),
					ZIndex = 2,
					Image = "rbxassetid://4695575676",
					ImageColor3 = Color3.fromRGB(46, 46, 54),
					ScaleType = Enum.ScaleType.Slice,
					SliceCenter = Rect.new(128, 128, 128, 128),
					SliceScale = 0.040,
				})

				colorstuff.rainbow = lib:Create("ImageButton", {
					BackgroundColor3 = Color3.fromRGB(255, 255, 255),
					BackgroundTransparency = 1.000,
					BorderSizePixel = 0,
					Size = UDim2.new(0, 20, 0, 140),
					Image = "http://www.roblox.com/asset/?id=5118428654",
				})

				colorstuff.rainbowlocation = lib:Create("Frame", {
					BackgroundColor3 = Color3.fromRGB(23, 23, 23),
					BorderSizePixel = 0,
					Size = UDim2.new(0, 20, 0, 2),
				})

				colorstuff.colorpickerframeb.Parent = main.MainBody
				colorstuff.colorpickerframe.Parent = colorstuff.colorpickerframeb
				colorstuff.rback.Parent = colorstuff.colorpickerframe
				colorstuff.rtext.Parent = colorstuff.rback
				colorstuff.rvalue.Parent = colorstuff.rback
				colorstuff.gback.Parent = colorstuff.colorpickerframe
				colorstuff.gtext.Parent = colorstuff.gback
				colorstuff.gvalue.Parent = colorstuff.gback
				colorstuff.bback.Parent = colorstuff.colorpickerframe
				colorstuff.btext.Parent = colorstuff.bback
				colorstuff.bvalue.Parent = colorstuff.bback
				colorstuff.sback.Parent = colorstuff.colorpickerframe
				colorstuff.sat.Parent = colorstuff.sback
				colorstuff.light.Parent = colorstuff.sat
				colorstuff.ring.Parent = colorstuff.sat
				colorstuff.rainbowback.Parent = colorstuff.colorpickerframe
				colorstuff.rainbow.Parent = colorstuff.rainbowback
				colorstuff.rainbowlocation.Parent = colorstuff.rainbow

				categories.Container.CanvasSize = categories.Container.CanvasSize + UDim2.new(0,0,0,40)

				colorstuff.colorpickerb.Parent = categories.Container
				colorstuff.colorpickerbgray.Parent = colorstuff.colorpickerb
				colorstuff.colorpickertext.Parent = colorstuff.colorpickerb
				colorstuff.colorpickerbutton.Parent = colorstuff.colorpickerbgray

				colorstuff.colorpickerb.MouseButton1Click:Connect(function()
					colorpickeropend = not colorpickeropend

					for i,v in pairs(main.MainBody:GetChildren()) do
						if v.Name == "colorframe" then
							game:GetService("TweenService"):Create(v, TweenInfo.new(0.3), {Size = UDim2.new(0, 0, 0, 205)}):Play()
						end
					end

					if colorpickeropend then 
						game:GetService("TweenService"):Create(colorstuff.colorpickerframeb, TweenInfo.new(0.3), {Size = UDim2.new(0, 190, 0, 205)}):Play()
					end
				end)


				local colorbase = Color3.new(1,0,0)
				colorvalue = colorbase
				local Saturation = 1
				local Darkness = 0
				local colourPickColour = colorbase

				local function UpdateColorPicker()

					colourPickColour = colorbase

					if Darkness == 1 then
						colourPickColour = Color3.new(0,0,0)
						return
					end

					if Saturation < 1 then
						local r = math.clamp(1 + (colourPickColour.r - 1) * Saturation, 0, 1)
						local g = math.clamp(1 + (colourPickColour.g - 1) * Saturation, 0, 1)
						local b = math.clamp(1 + (colourPickColour.b - 1) * Saturation, 0, 1)
						colourPickColour = Color3.new( r, g, b )
					end

					if Darkness > 0 then 
						local r = math.clamp(colourPickColour.r * (1 - Darkness ), 0, 1)
						local g = math.clamp(colourPickColour.g * (1 - Darkness ), 0, 1)
						local b = math.clamp(colourPickColour.b * (1 - Darkness ), 0, 1)
						colourPickColour = Color3.new(r,g,b)
					end

					colorstuff.rvalue.Text = tostring(math.floor(colourPickColour.r * 255))
					colorstuff.gvalue.Text = tostring(math.floor(colourPickColour.g * 255))
					colorstuff.bvalue.Text = tostring(math.floor(colourPickColour.b * 255))

					local rv = tonumber(colorstuff.rvalue.Text)
					local gv = tonumber(colorstuff.gvalue.Text)
					local bv = tonumber(colorstuff.bvalue.Text)

					colorvalue = Color3.new(rv,gv,bv)

					colorstuff.colorpickerbutton.ImageColor3 = colourPickColour

					if CallBack then
						CallBack(colorvalue)
					end
				end

				if Default then
					local r,g,b = math.floor(Default.r * 255),math.floor(Default.g * 255),math.floor(Default.b * 255)
					colorbase = Color3.fromRGB(r,g,b)
					colorstuff.sat.ImageColor3 = colorbase
					wait(.2)
					UpdateColorPicker()
				end

				local function setPickerColor(y)
					local rY = y - colorstuff.rainbow.AbsolutePosition.Y;
					local cY = math.clamp(rY, 0, colorstuff.rainbow.AbsoluteSize.Y - colorstuff.rainbowlocation.AbsoluteSize.Y);
					local offset = (y - colorstuff.rainbow.AbsolutePosition.Y) - colorstuff.rainbowlocation.AbsoluteSize.Y
					local scale = offset / colorstuff.rainbow.AbsoluteSize.Y
					TweenService:Create(colorstuff.rainbowlocation, TweenInfo.new(0.1), {Position = UDim2.new(0, 0, 0, cY)}):Play()
					local color = Color3.fromHSV(math.clamp(scale, 0, 1), 1, 1)
					local r,g,b = math.floor(color.r * 255), math.floor(color.g * 255), math.floor(color.b * 255)
					colorbase = Color3.fromRGB(r,g,b)

					colorstuff.sat.ImageColor3 = colorbase
					UpdateColorPicker()
				end

				local function setPickerLight(x,y)
					Saturation = x / 140
					Darkness = y / 140

					TweenService:Create(colorstuff.ring, TweenInfo.new(0.1), {Position = UDim2.new(0, x, 0, y)}):Play()

					UpdateColorPicker()
				end

				local rc
				local cc

				UIS.InputEnded:Connect(function(Mouse)
					if Mouse.UserInputType == Enum.UserInputType.MouseButton1 then
						if(cc) then
							cc:Disconnect()
							cc = nil
						end
						if(rc) then 
							rc:Disconnect()
							rc = nil
						end
					end
				end)

				local rainbow = false

				colorstuff.rainbow.MouseButton1Down:Connect(function()
					if not rainbow then 
						rc = game:GetService("RunService").Heartbeat:Connect(function()
							setPickerColor(Mouse.Y)
						end)
					end
				end)

				colorstuff.sat.MouseButton1Down:Connect(function()
					cc = game:GetService("RunService").Heartbeat:Connect(function()
						local v = game:GetService("GuiService"):GetGuiInset()
						local y = math.clamp(Mouse.Y - colorstuff.sat.AbsolutePosition.Y - v.y + 34, 0, 140 )
						local x = math.clamp(Mouse.X - colorstuff.sat.AbsolutePosition.X - v.x, 0, 140 )
						setPickerLight(x,y)
					end)
				end)


				return colorstuff
			end

			sections.sectionname.Parent = categories.Container

			return sections
		end

		main.CategoryContainer.CanvasSize = main.CategoryContainer.CanvasSize + UDim2.new(0,0,0,53)

		categories.Button.Parent = main.CategoryContainer
		categories.Container.Parent = main.MainBody
		categories.ContainerLayout.Parent = categories.Container
		categories.ContainerPadding.Parent = categories.Container

		firstC = false

		return categories
	end

	main.Close.MouseButton1Click:Connect(function()
		game.CoreGui.AncestorV2:Destroy()
	end)

	main.ScreenGui.Parent = game.CoreGui
	main.MainBody.Parent = main.ScreenGui
	main.TopBar.Parent = main.MainBody
	main.TopBarGradient.Parent = main.TopBar
	main.LogoTextFolder.Parent = main.TopBar
	main.LogoText1.Parent = main.LogoTextFolder
	main.LogoText2.Parent = main.LogoTextFolder
	main.LogoText3.Parent = main.LogoTextFolder
	main.LogoText4.Parent = main.LogoTextFolder
	main.LogoText5.Parent = main.LogoTextFolder
	main.CloseFrame.Parent = main.TopBar
	main.Close.Parent = main.CloseFrame
	main.CategoryContainer.Parent = main.MainBody
	main.CategoryPadding.Parent = main.CategoryContainer
	main.CategoryLayout.Parent = main.CategoryContainer

	return main
end

local requirements={
    ConfigSetup={
    AlwaysDay=false, 
    AlwaysNight=false,
    SpookEnabled=false,
    NoFog=false,
    WaterGodMode=false,
    WaterFloat=true, 	
    WaterWalk=false,
    flyKey='F',
    hardDragger=false,
    oldNoclipEnabled=false,
    antiBlacklist=false,
    light=false,
    fastRotate=false,
    gameMusic=true,
    uiDarkMode=true,
    wireMod=false,
    carColorR=0,
    carColorG=0,
    carColorB=0,
    carMaterial='Plastic',
    carVisualEffects=false,
    blackListAll=false,
    SprintKey='Q',
    NoclipKey='LeftControl',
    KeyTP='G',
    toggleUI='RightShift',
    FlingKey='H',
};
Booleans={
    DeveloperMode=true,
    Noclip=false,
    Sprinting=false,
    State=false,
    isFlying=false,
    isEnabled=true,
    friendsOnly=false,
    pingMessages=false,
    sendNotifications=false,
    infJumpEnabled=false,
    memeMode=false,
    MoneyDuping=false,
    DisableSlotSaving=false,
    Flinging=false,
    DonatingBase=false,
    alertTarget=true,
    building=false,
    treeIsCut=false,
    isLoopBringTreeEnabled=false,
    isPlankCut=false,
    cutAssistEnabled=false,
    dupeInventory=false,
    vipMode=false,
    wireMod=false,
    axeDuping=false,
    isBuying=false,
    AutoBuyingRuki=false,
    bringBoulders=nil,
    devMode=true,
    abortAutobuy=false,
    loopBuying=false,
    dragExists=false,
    StopDespawn=false,
    managingTarget=false,
};
tables={
    axeList={},
    allItems={},
    itemListForBaseDrop={},
};
Strings={
    WalkSpeed=16,
    flySpeed=150,
    JumpPower=50,
    HipHeight=0,
    colorToSpawn=131,
    PlayerToAdminWipe=tostring(game.Players.LocalPlayer),
    buildToBuild='Ancestor',
    SprintSpeed=20,
    selectedPlotToLoad=1,
    specialAutobuyItem='Build Power',
    CurrentRegion='Region_Main',
    DestroyStores=false,
    selectedPlot=1,
    autoDupeMoneyAmount=1,
    BaseRecipient=tostring(game.Players.LocalPlayer),
    autoBuildPlayer=tostring(game.Players.LocalPlayer),
    autoBuildReciever=tostring(game.Players.LocalPlayer),
    ToolDuplicationAmount=1,
    IdentifyType='Owner',
    bringSelectedTreeAmount=1,
    selectedTree='Generic',
    autoBuySelectedItemAmount=1,
    autoBuySelectedItem='BasicHatchet',
    plankModel=nil,
    blueprintModel=nil,
    selfDuping=false,
    itemToOpen=nil,
    itemTypeToWipe='Structure',
    DonationAmount=1,
    donationRecipient=tostring(game.Players.LocalPlayer),
    TreeModel=nil,
    selectedTarget=tostring(game.Players.LocalPlayer);
    carSpeed=1.5,
    selectedWire='NeonWirePinky',
    baseDropOwner=tostring(game.Players.LocalPlayer),
    itemToBaseDrop='All Items',
    baseDropAmount=0
};
services={
    RunService=game:GetService('RunService'),
    marketplaceService=game:GetService('MarketplaceService'),
    userInputService=game:GetService('UserInputService'),
    Lighting=game:GetService('Lighting'),
    VU=game:GetService('VirtualUser'),
    teleportService=game:GetService('TeleportService');
},
connections={
    main=nil,
    noclip=nil,
    infJump=nil,
    antiWeld=nil,
    timeCycle=nil,
    farAxeEquip=nil,
    autoChop=nil,
    clientMayLoad=nil,
    hardDragger=nil,
    PlankToBlueprint=nil,
    axeFling=nil,
    chopTree=nil,
    openItem=nil,
    woodSelection=nil,
    autoKickPlayer=nil,
    cutAssist=nil,
    cutAssistCutter=nil,
    bringTree=nil,
    spawnCheck=nil,
    carFallBack=nil,
    bringBoulders=nil,
    carInitiate=nil,
    humCheck=nil,
    grayPaintTool=nil,
    draggerRemoved=nil,
    spawnCar=nil,
    antiGUI=nil,
    draggerAdded=nil,
    shiftConnectEnded=nil,
    shiftConnectBegan=nil;
};
folders={
    axeFolder=game:GetService('ReplicatedStorage').Purchasables.Tools.AllTools,
    blueprintFolder=game:GetService('ReplicatedStorage').Purchasables.Structures.BlueprintStructures,
};
remotes={
    clientPurchasedProperty=game:GetService'ReplicatedStorage'.PropertyPurchasing.ClientPurchasedProperty,
    setPropertyPurchasingValue=game:GetService'ReplicatedStorage'.PropertyPurchasing.SetPropertyPurchasingValue,
    clientInteracted=game:GetService('ReplicatedStorage').Interaction.ClientInteracted,
    clientRequestOwnership=game:GetService('ReplicatedStorage').Interaction.ClientRequestOwnership,
    clientIsDragging=game:GetService('ReplicatedStorage').Interaction.ClientIsDragging,
    clientMayLoad=game:GetService('ReplicatedStorage').LoadSaveRequests.ClientMayLoad,
    requestLoad=game:GetService('ReplicatedStorage').LoadSaveRequests.RequestLoad,
    requestSave=game:GetService('ReplicatedStorage').LoadSaveRequests.RequestSave,
    clientExpandedProperty=game:GetService'ReplicatedStorage'.PropertyPurchasing.ClientExpandedProperty,
    destroyStructure=game:GetService'ReplicatedStorage'.Interaction.DestroyStructure,
    Donate=game:GetService'ReplicatedStorage'.Transactions.ClientToServer.Donate,
    clientSetListPlayer=game:GetService('ReplicatedStorage').Interaction.ClientSetListPlayer,
    sayMessageRequest=game:GetService('ReplicatedStorage').DefaultChatSystemChatEvents.SayMessageRequest,
    clientIsWhitelisted=game:GetService('ReplicatedStorage').Interaction.ClientIsWhitelisted,
    remoteProxy=game:GetService('ReplicatedStorage').Interaction.RemoteProxy,
    playerChatted=game:GetService('ReplicatedStorage').NPCDialog.PlayerChatted,
    setChattingValue=game:GetService('ReplicatedStorage').NPCDialog.SetChattingValue,
    clientPlacedStructure=game:GetService('ReplicatedStorage').PlaceStructure.ClientPlacedStructure,
};
getFuckedList={};
SignTable={
    '，翻译',

};
saveConfig=nil,
LP=game:GetService('Players').LocalPlayer,
Players=game:GetService('Players'),
wrkspc=game:GetService('Workspace'),
Mouse=game:GetService('Players').LocalPlayer:GetMouse(),
CurrentVersion=''
};
table.insert(requirements.SignTable,', '..requirements.CurrentVersion..' yyds');
if table.find(requirements.getFuckedList,tostring(requirements.LP))then 
    spawn(function()
        game:GetService("ReplicatedStorage").LoadSaveRequests.WipeMetaData:InvokeServer();
    end);
    game:GetService("ReplicatedStorage").Notices.SendUserNotice:Fire('An error occurred: Metadata corruption');
end;
if requirements.Booleans.DeveloperMode then 
    requirements.CurrentVersion=requirements.CurrentVersion..'-Developer';
elseif not requirements.Booleans.DeveloperMode and table.find(requirements.AdminList,tostring(requirements.LP))then 
    requirements.CurrentVersion=requirements.CurrentVersion..'-Administrator';
else
    requirements.CurrentVersion=requirements.CurrentVersion..'-Release';
end;
if not _G.timesExecuted then 
    _G.timesExecuted=1;
else
    _G.timesExecuted=_G.timesExecuted+1;
end;
--Changelog Shit
local quitUI=game:GetService('Players').LocalPlayer.PlayerGui.ChangelogGUI.Changelog.Quit
quitUI.TextLabel.Position=UDim2.new(0,25,0,0)

if quitUI:FindFirstChild('PlatformButton')then 
    quitUI:FindFirstChild('PlatformButton'):Destroy();
end;
local ui=requirements.LP.PlayerGui.ChangelogGUI.Changelog.Main.PageCount
local scr=getsenv(requirements.LP.PlayerGui.ChangelogGUI.ChangelogClient)
scr.setPlatformControls=function()end
scr.addPageItem=function()end
scr.displayPage=function()end
local list=requirements.LP.PlayerGui.ChangelogGUI.Changelog.Main.List
if not list:FindFirstChild('UIListLayout')then 
    local uiSorter=Instance.new('UIListLayout',list)
    uiSorter.SortOrder=Enum.SortOrder.LayoutOrder
    uiSorter.Padding=UDim.new(0,5)
end;
for i,v in next,list:children()do 
    if v.Name~='UIListLayout'then
        v:Destroy();
    end;
end;
ui.Visible=true
ui.Position=UDim2.new(0.84, 0,0.09, -36)
ui.Size=UDim2.new(0, 64,0, 32)
ui.Text='1/1'

--//Functions\\--
local functions={};
local config
if not pcall(function() readfile('AncestorV3.cfg') end) then
    writefile('AncestorV3.cfg',game:GetService'HttpService':JSONEncode(requirements.ConfigSetup))--table
end

config=game:GetService'HttpService':JSONDecode(readfile('AncestorV3.cfg'))

functions.saveConfig=function()
    writefile('AncestorV3.cfg',game:GetService'HttpService':JSONEncode(config))
end;

requirements.ConfigSetup=config;

functions.isPlayerAdmin=function(player)
   return true
end;

functions.notify=function(title, text, duration)
    if requirements.Booleans.isEnabled then
        game.StarterGui:SetCore(
            'SendNotification',
            {
                Title=title,
                Text=text,
                Duration=duration;
            }
        );
    end;
end;

getgenv().spawnf = function(func,...) return coroutine.wrap(func)(...) end

functions.updateChangelog=function(header,text)
    local headerText=Instance.new('TextLabel',list)
    headerText.BackgroundColor3=Color3.fromRGB(238, 225, 216);
    headerText.BorderSizePixel=0
    headerText.Size=UDim2.new(1, 0,0.063, 0)
    headerText.Text=' '..header
    headerText.TextXAlignment=Enum.TextXAlignment.Left
    headerText.Font=Enum.Font.ArialBold
    headerText.TextSize=18
    headerText.ZIndex=6

    local updateText=Instance.new('TextLabel',list)
    updateText.BackgroundColor3=Color3.fromRGB(238, 225, 216);
    updateText.BorderSizePixel=0
    updateText.Size=UDim2.new(1, 0,0.123, 0)
    updateText.Text=' Ancestor: '..text
    updateText.TextXAlignment=Enum.TextXAlignment.Left
    updateText.Font=Enum.Font.Arial
    updateText.TextSize=13
    updateText.ZIndex=6
end;
functions.updateChangelog('17th September 2021','Added Rukiryaxe Multibuy');
functions.updateChangelog('17th September 2021','Fixed fast deloader breaking self dupe');
functions.updateChangelog('17th September 2021','Added Rukiryaxe autobuy support');
functions.updateChangelog('17th September 2021','Fixed plank to blueprint');
functions.AntiAFK=function()
    requirements.LP.Idled:Connect(function()
        functions.notify('Ancestor', 'Anti AFK Auto-Enabled', 4)
        requirements.services.VU:Button2Down(Vector2.new(0, 0), requirements.wrkspc.CurrentCamera.CFrame);
        wait(.325)
        requirements.services.VU:Button2Up(Vector2.new(0, 0), requirements.wrkspc.CurrentCamera.CFrame);
    end);
end;
functions.AntiAFK();

functions.antiDestroyEarRape=function()
    requirements.LP.Character.Head.ChildAdded:Connect(function(b)
        if b.Name=='DestroyStructure'then 
            b.Volume=0
        end;
    end);
end;
functions.antiDestroyEarRape();
requirements.LP.CharacterAdded:Connect(function()
    repeat wait()until requirements.LP.Character and requirements.LP.Character:FindFirstChild('Head');
    functions.antiDestroyEarRape();
end);

functions.clientMayLoad=function(mode)
pcall(function()game.CoreGui.GUI:Destroy()end)
if mode=='Dark'then
    color1=Color3.fromRGB(15,15,15);
    color2=Color3.fromRGB(255,255,255);
elseif mode=='Light'then 
    color1=Color3.fromRGB(255,255,255);
    color2=Color3.fromRGB(0,0,0);
end;
local GUI=Instance.new('ScreenGui');
local GUIFrame=Instance.new('Frame');
local Text=Instance.new('TextLabel');
local UICorner=Instance.new('UICorner');
GUI.Name='GUI';
GUI.Parent=game.CoreGui;
GUI.ZIndexBehavior=Enum.ZIndexBehavior.Sibling;
GUIFrame.Name='FPSFrame';
GUIFrame.Parent=GUI;
GUIFrame.Size=UDim2.new(0,140,0,20);
GUIFrame.Position=UDim2.new(1,-1925,1,-18);
GUIFrame.BorderSizePixel=0;
GUIFrame.BackgroundColor3=color1;
UICorner.Name='UICorner';
UICorner.Parent=GUIFrame;
UICorner.CornerRadius=UDim.new(0,6);
Text.Name='Text';
Text.Parent=GUIFrame;
Text.TextWrapped=true;
Text.ZIndex=2;
Text.BorderSizePixel=0;
Text.BackgroundColor3=Color3.fromRGB(255,255,255);
Text.Size=UDim2.new(1,-2,1,0);
Text.TextSize=14.000;
Text.Text='';
Text.TextColor3=color2;
Text.Font=Enum.Font.GothamSemibold;
Text.Position=UDim2.new(0,2,0,0);
Text.BackgroundTransparency=1.000;
game.CoreGui.ChildRemoved:Connect(function(b)
    if b.Name=='GUI'then 
        if requirements.connections.clientMayLoad then 
            requirements.connections.clientMayLoad:Disconnect();
            requirements.connections.clientMayLoad=nil;
        end;
    end;
end);
requirements.connections.clientMayLoad=game:GetService('RunService').Heartbeat:Connect(function()
    local success=game:GetService('ReplicatedStorage').LoadSaveRequests.ClientMayLoad:InvokeServer(requirements.LP)
        if success then
            Text.Text='You Can Load';
        else 
            Text.Text='You Cannot Load';
        end;
    end);
end;
if requirements.ConfigSetup.uiDarkMode then 
    functions.clientMayLoad('Dark');
else
    functions.clientMayLoad('Light');
end;

functions.donate=function(plr,amount)
    if tostring(plr)== tostring(requirements.LP) then 
        functions.notify('Error','Select another player!',4);
        return;
    end;
    if requirements.Strings.donationRecipient==nil or not requirements.Players:FindFirstChild(plr)then 
        functions.notify('Error','Player not found!',4);
        return;
    end;
    if tonumber(requirements.Strings.DonationAmount) >=60000000 then 
        functions.notify('Error','Amount too high!',4);
        return;
    end;
    if tonumber(requirements.Strings.DonationAmount) <=0 then 
        functions.notify('Error','Amount too low!',4);
        return;
    end;
    if requirements.LP.CurrentSaveSlot.Value<=0 then 
        functions.notify('Error','No plot loaded!',4);
        return;
    end;
    if not requirements.LP:FindFirstChild('CurrentlySavingOrLoading')then 
        functions.notify('Error','Save in progress',4);
        return;
    end;
    if tonumber(requirements.Strings.DonationAmount) >requirements.LP.leaderstats.Money.Value then 
        functions.notify('Error','Insufficient funds',4);
        return;
    end;
    local scr=getsenv(requirements.LP.PlayerGui.DonateGUI.DonateClient)
    local scr2=getsenv(requirements.LP.PlayerGui.NoticeGUI.NoticeClient)
    scr.setPlatformControls=function()end
    scr.openWindow();
    game:GetService'RunService'.Heartbeat:wait();
    local oldAmount=requirements.Players:FindFirstChild(plr).leaderstats.Money.Value;
    local success,errormsg=spawnf(function()requirements.remotes.Donate:InvokeServer(requirements.Players:FindFirstChild(plr),tonumber(amount),tonumber(requirements.LP.CurrentSaveSlot.Value))end);
    game:GetService'RunService'.Heartbeat:wait();
    for i,v in next,getupvalues(scr.sendDonation)do
        if i==1 then 
            debug.setupvalue(scr.sendDonation,i,game.Players:FindFirstChild(plr));
        end;
    end;
    scr.sendDonation();
    game:GetService'RunService'.Heartbeat:wait();
    scr2.exitNotice();
    functions.notify('Ancestor','Attempting Donation',2);
    wait(6)
    if requirements.Players:FindFirstChild(plr).leaderstats.Money.Value~= oldAmount + amount then 
        functions.notify('Error','An Error Occured.. Possibly Cooldown!',4);
        scr2.exitNotice();
        return;
    end;
    functions.notify('Ancestor','Donated '..tostring(amount)..' to '..tostring(plr),4);
    scr2.exitNotice();
end; 

functions.Teleport=function(cf)
    repeat wait()until requirements.LP.Character:FindFirstChild('HumanoidRootPart');
    if requirements.LP.Character.Humanoid.Sit then 
        requirements.LP.Character.Humanoid.SeatPart.Parent:SetPrimaryPartCFrame(cf*CFrame.Angles(math.rad(requirements.LP.Character.Humanoid.SeatPart.Parent.PrimaryPart.Orientation.X), math.rad(requirements.LP.Character.Humanoid.SeatPart.Parent.PrimaryPart.Orientation.Y), math.rad(requirements.LP.Character.Humanoid.SeatPart.Parent.PrimaryPart.Orientation.Z)));
    elseif not requirements.LP.Character.Humanoid.Sit then 
        requirements.LP.Character:SetPrimaryPartCFrame(cf)
    end;
end;

functions.KillPlayer=function()
    pcall(function()
        requirements.LP.Character.Head:Destroy();
    end);
end;

functions.getPlayersBase=function(plr)
    for i,v in next,requirements.wrkspc.Properties:children()do 
        if v:IsA('Model')and tostring(v.Owner.Value)==plr then 
            return v;
        end;
    end;
    return false;
end;

functions.RecolourPlot=function(r,g,b)
    local plot=functions.getPlayersBase(tostring(requirements.LP));
    if plot~=false then
        for _,v in next,plot:children()do
            if v:IsA('BasePart')then 
                v.Color=Color3.fromRGB(r,g,b);
            end;
        end;
    end;
end;

functions.getFreeLand=function()
    for _,v in next,requirements.wrkspc.Properties:children()do 
        if v.Owner.Value==nil then
            return v;
        end;
    end;
end;

functions.FreeLand=function()
    if functions.getPlayersBase(tostring(requirements.LP))then 
        functions.notify('Error','You already have a plot!',4);
        return;
    end;
    local plot=functions.getFreeLand();
    requirements.remotes.setPropertyPurchasingValue:InvokeServer(true);
    requirements.remotes.clientPurchasedProperty:FireServer(plot, plot.OriginSquare.CFrame.p);
    requirements.remotes.setPropertyPurchasingValue:InvokeServer(false);
    functions.Teleport(CFrame.new(plot.OriginSquare.CFrame.p)+Vector3.new(0,5,0));
end;

functions.flipCar=function()    
    pcall(function()
        requirements.LP.Character.Humanoid.SeatPart.Parent:SetPrimaryPartCFrame(requirements.LP.Character.Humanoid.SeatPart.Parent.PrimaryPart.CFrame*CFrame.Angles(math.rad(-180),0,0))
    end)
end;

functions.fastRotate=function()
    local scr2=getsenv(requirements.LP.PlayerGui.Scripts.UserInput)
    local rotateX=scr2.getSteerFromKeys
    local rotateY=scr2.getThrottleFromKeys
    if requirements.ConfigSetup.fastRotate then
        for i,v in next,getconstants(rotateX)do 
            debug.setconstant(rotateX,1,3)
        end;
        for i,v in next,getconstants(rotateY)do 
            debug.setconstant(rotateY,1,3)
        end;
    end;
    if not requirements.ConfigSetup.fastRotate then
        for i,v in next,getconstants(rotateX)do 
            debug.setconstant(rotateX,1,1)
        end;
        for i,v in next,getconstants(rotateY)do 
            debug.setconstant(rotateY,1,1)
        end;
    end;
end;

functions.antiBlacklist=function(v)
    local scr=getsenv(requirements.LP.PlayerGui.BlackListGUI.ClientBeBlacklisted)
    local old=scr.makeWalls
    local old2=scr.checkIfPlayerNeedsToBeKicked
    if v=='Enable'then
        scr.makeWalls=function()end
        scr.removeWalls()
        scr.checkIfPlayerNeedsToBeKicked=function()end
        local oldPos=requirements.LP.Character.HumanoidRootPart.CFrame
        requirements.connections.humCheck=game:GetService('RunService').RenderStepped:connect(function()
            pcall(function()
                oldPos=requirements.LP.Character.HumanoidRootPart.CFrame
            end);
        end);
        for _,spawnLocation in next,workspace.Region_Main:children()do
            if spawnLocation:IsA('SpawnLocation')then
                spawnLocation.Touched:Connect(function(spawnPoint)
                if spawnPoint.Parent==requirements.LP.Character then 
                    requirements.LP.Character.HumanoidRootPart.CFrame=oldPos
                end
            end)
        end;
    end;
    elseif v=='Disable'then 
        if requirements.connections.humCheck then 
            requirements.connections.humCheck:Disconnect();
            requirements.connections.humCheck=nil;
        end;
        scr.makeWalls=old;
        scr.checkIfPlayerNeedsToBeKicked=old2;
    end;
end;

functions.getAxeList=function()
    for _,v in next,requirements.folders.axeFolder:children()do 
        table.insert(requirements.tables.axeList,tostring(v));
    end;
end;
functions.getAxeList();

functions.joinDiscord=function()
 functions.notify('QQ号','741753474',4);
        return;
    end;

functions.axeFling=function()
    requirements.connections.axeFling=requirements.Mouse.Button1Down:Connect(function()
        local axe;
        for _,v in next,requirements.LP.Backpack:children()do
            if v:IsA('Tool')and v.Name~='BlueprintTool'then 
                game.ReplicatedStorage.Interaction.ClientInteracted:FireServer(v, 'Drop tool', requirements.LP.Character.HumanoidRootPart.CFrame)
                break;
            end;
        end;
        local axeConnection
        axeConnection=workspace.PlayerModels.ChildAdded:connect(function(newAxe)
            newAxe:WaitForChild('Owner')
            if newAxe.Owner.Value==requirements.LP and newAxe:FindFirstChild('ToolName')then
                axe=newAxe;
                wait(2.5);
                game.ReplicatedStorage.Interaction.ClientInteracted:FireServer(axe,'Pick up tool');
            end;
        end);
        repeat wait()until axe;
        axeConnection:Disconnect();
        axeConnection=nil;
        local fling=Instance.new('BodyPosition',axe.Main);
        fling.MaxForce=Vector3.new(math.huge,math.huge,math.huge);
        fling.P=65000;
        fling.Position=requirements.Mouse.Hit.p;
        local flingPower=9e9;
        axe.Main.CanCollide=false;
        repeat game:GetService('RunService').Stepped:wait();axe.Main.RotVelocity = Vector3.new(1,.5,.5)*flingPower;until(axe.Main.CFrame.p-fling.Position).Magnitude<15;
        wait(2.5);
        fling:Destroy();
        axe.Main.CanCollide=true;
        game.ReplicatedStorage.Interaction.ClientInteracted:FireServer(axe,'Pick up tool');
    end);
end;

functions.fastLoadSelectedPlot=function(slotnum)
    local scr=getsenv(requirements.LP.PlayerGui.PropertyPurchasingGUI.PropertyPurchasingClient);
    local loadedSlot=nil;
    if requirements.LP.CurrentSaveSlot.Value~=-1 and not requirements.Booleans.MoneyDuping then 
        requirements.remotes.requestSave:InvokeServer(requirements.LP.CurrentSaveSlot.Value,requirements.LP)
    end
    spawnf(function()
        loadedSlot=requirements.remotes.requestLoad:InvokeServer(slotnum,requirements.LP);
    end);
    game:GetService("ReplicatedStorage").LoadSaveRequests.GetTickCut:InvokeServer();
    repeat wait()until requirements.LP.PlayerGui.PropertyPurchasingGUI.SelectPurchase.Visible;
    repeat game:GetService'RunService'.Stepped:wait()
        scr.selectionMade();
    until loadedSlot~=nil
    requirements.LP.CurrentSaveSlot.Value=slotnum;
    return loadedSlot;
end;

functions.DeleteTrees=function()
    for _,treeregion in next,workspace:GetChildren()do
        if tostring(treeregion)=='TreeRegion'then
            for _,tree in next,treeregion:GetChildren()do
                if tree:FindFirstChild'WoodSection'then -->bruh
                    repeat game:GetService'RunService'.Stepped:wait()
                        functions.Teleport(CFrame.new(tree.WoodSection.CFrame.p+Vector3.new(4,0,4)));--> DUMB FUCKING IDIOT
                        requirements.remotes.clientIsDragging:FireServer(tree);
                        requirements.remotes.destroyStructure:FireServer(tree);
                    until tostring(tree.Parent)~='TreeRegion';
                end;
            end;
        end;
    end;
end;

functions.SelfWl=function(value)
    requirements.remotes.clientSetListPlayer:InvokeServer(requirements.LP.WhitelistFolder,requirements.LP,value);
end;

loadstring([[
    local args = {...} local functions,requirements = args[1],args[2]
    local mt = getrawmetatable(game);
    local old = mt.__namecall;
    local protect = newcclosure or protect_function
    setreadonly(mt, false);
    mt.__namecall = protect(function(self, ...)
        local method = getnamecallmethod();
        local argss = {...};
        if method == 'InvokeServer' and tostring(self) == 'RequestSave' then
            if requirements.Booleans.DisableSlotSaving and requirements.Booleans.isEnabled then
                return{false};
            end;
        elseif method=='FireServer'and tostring(self)=='ClientPlacedWire'then 
            if requirements.ConfigSetup.wireMod then 
                argss[1]=game.ReplicatedStorage.Purchasables.WireObjects[requirements.Strings.selectedWire];
            end;
        elseif method=='FireServer'and tostring(self)=='CheckShip'then 
            return;
        elseif method=='FireServer'and tostring(self)=='DamageHumanoid'then
            if requirements.ConfigSetup.WaterGodMode then
                return 0;
            end;
        elseif method=='FireServer'and tostring(self)=='ClientChangedRegion'then 
            requirements.Strings.CurrentRegion=tostring(argss[1]);
        elseif method=='InvokeServer'and tostring(self)=='GetTickCut'then
            if not requirements.Booleans.selfDuping and not requirements.Booleans.DonatingBase and requirements.Booleans.isEnabled then
                for _,Model in next,workspace.PlayerModels:GetChildren()do 
                    if Model:FindFirstChild'Owner'and tostring(Model.Owner.Value)==tostring(requirements.LP)then
                        game:GetService('ReplicatedStorage').Interaction.DestroyStructure:FireServer(Model);
                    end;
                end;
            end;setnamecallmethod(method)
        elseif method == 'Kick' then
            wait(9e9);
            return;
        end;
        return old(self, unpack(argss));
    end);
    hookfunction(requirements.LP.Kick,protect(function() wait(9e9) end));
]])(functions,requirements)

functions.checkModel=function(item,option,player)
    local Owner=nil;
    if player==nil then 
        Owner=tostring(requirements.LP);
    end
    for _,v in next,workspace.PlayerModels:children()do
        if v:IsA('Model')then 
            local check=v:FindFirstChild('ItemName')or v:FindFirstChild('PurchasedBoxItemName');
            if item=='BasicHatchet' then 
                check=v:FindFirstChild('ItemName')
            end;
            if  check and  check.Value==item and v:FindFirstChild('Owner')and tostring(v.Owner.Value)==Owner then
                if option=='Model'then
                    return v;
                elseif option=='Magnitude'then
                    return (v.PrimaryPart.CFrame.p-requirements.LP.Character.HumanoidRootPart.CFrame.p).magnitude;
                end;
            end;
        end;
    end;
    return false;
end

functions.DeleteSurroundingTrees=function()
    for _,v in next,requirements.wrkspc:children()do
        if tostring(v)=='TreeRegion'then
            for _,g in next,v:children()do
                if(requirements.LP.Character.HumanoidRootPart.CFrame.p-g.WoodSection.CFrame.p).magnitude<150 then 
                    requirements.remotes.clientIsDragging:FireServer(g);
                    requirements.remotes.destroyStructure:FireServer(g);
                end;
            end;
        end;
    end;
end;

functions.managePlayer=function(option,value)
    for _,v in next,game.Players:children()do 
        if v~=requirements.LP then 
            if option=='Whitelist' then 
                game:GetService('ReplicatedStorage').Interaction.ClientSetListPlayer:InvokeServer(game:GetService('Players').LocalPlayer.WhitelistFolder,v,value);
            elseif option=='Blacklist'then 
                game:GetService('ReplicatedStorage').Interaction.ClientSetListPlayer:InvokeServer(game:GetService('Players').LocalPlayer.BlacklistFolder,v,value);
            end;
        end;
    end;
end;

functions.unlockDonationUI=function()
    if requirements.LP.AccountAge>5 or _G.Done then 
        functions.notify('Error','Already Unlocked!',4);
        return;
    end;
    local scr=getsenv(requirements.LP.PlayerGui.DonateGUI.DonateClient)
    local ui=requirements.LP.PlayerGui.MenuGUI.Menu.Main.Donate
    local donateUI=requirements.LP.PlayerGui.DonateGUI;
    ui.Active=true;
    _G.Done=true;
    spawn(function()
        ui.TextLabel.Text='UNLOCKED!';
        wait(1)
        ui.TextLabel.Text='Send Money';
    end);
    donateUI.Donate.Quit.TextLabel.Position=UDim2.new(0,25,0,0)

    if donateUI.Donate.Quit:FindFirstChild('PlatformButton')then 
        donateUI.Donate.Quit:FindFirstChild('PlatformButton'):Destroy();
    end;

    ui.MouseButton1Down:Connect(function()
        hookfunction(scr.setPlatformControls,function()return false end)
        scr.openWindow();
    end);

    donateUI.Donate.Quit.MouseButton1Down:Connect(function()
        scr.back();
    end);
end;

functions.applyLight=function(value)
    if value then 
        local light = Instance.new('PointLight', requirements.LP.Character.Head)
        light.Name='Ancestor'
        light.Range = 150
        light.Brightness = 1.7
    else
        pcall(function()
            requirements.LP.Character.Head.Ancestor:remove();
        end);
    end;
end;

functions.buyItem=function(item)
    local Cashier=functions.getCashier(item);
    local CashierID=functions.getID(item);
    requirements.remotes.playerChatted:InvokeServer({Character=Cashier,Name=tostring(Cashier), ID=CashierID},'ConfirmPurchase');
end;

functions.SellSign=function()
    if not functions.checkModel('PropertySoldSign','Model')then
        functions.notify('Error','You don\'t own a Sign to sell!',4);
        return;
    end;
    local sign=functions.checkModel('PropertySoldSign','Model');
    if sign:FindFirstChild('Main').Anchored then 
        requirements.remotes.clientInteracted:FireServer(sign,'Take down sold sign');
    end;
    local magnitude=functions.checkModel('PropertySoldSign','Magnitude');
    if magnitude>10 then 
        functions.Teleport(CFrame.new(sign.PrimaryPart.CFrame.p)+Vector3.new(0,5,0));
    end;
    wait(.2);
    for i = 1,10 do 
        wait()
        requirements.remotes.clientRequestOwnership:FireServer(sign.Main);
        requirements.remotes.clientIsDragging:FireServer(sign);
        sign.Main.CFrame=CFrame.new(315.4, 3, 85.4);
    end;
end;

functions.MaxLand=function(Plot)
    if not functions.getPlayersBase(tostring(requirements.LP))then 
        functions.FreeLand();
    end;
    if not Plot then 
        Plot=functions.getPlayersBase(tostring(requirements.LP));
    end;
    local OriginSquare=Plot.OriginSquare;
    local children=#Plot:children()
    if children >=26 and not requirements.Strings.selfDuping then 
        functions.notify('Error','Already Max-Landed',4);
        return;
    end;
    requirements.remotes.setPropertyPurchasingValue:InvokeServer(true);
    requirements.remotes.clientExpandedProperty:FireServer(Plot ,CFrame.new(OriginSquare.Position.X + 40, OriginSquare.Position.Y, OriginSquare.Position.Z));requirements.remotes.clientExpandedProperty:FireServer(Plot ,CFrame.new(OriginSquare.Position.X - 40, OriginSquare.Position.Y, OriginSquare.Position.Z));requirements.remotes.clientExpandedProperty:FireServer(Plot ,CFrame.new(OriginSquare.Position.X, OriginSquare.Position.Y, OriginSquare.Position.Z + 40));requirements.remotes.clientExpandedProperty:FireServer(Plot ,CFrame.new(OriginSquare.Position.X, OriginSquare.Position.Y, OriginSquare.Position.Z - 40));requirements.remotes.clientExpandedProperty:FireServer(Plot ,CFrame.new(OriginSquare.Position.X + 40, OriginSquare.Position.Y, OriginSquare.Position.Z + 40));requirements.remotes.clientExpandedProperty:FireServer(Plot ,CFrame.new(OriginSquare.Position.X + 40, OriginSquare.Position.Y, OriginSquare.Position.Z - 40));requirements.remotes.clientExpandedProperty:FireServer(Plot ,CFrame.new(OriginSquare.Position.X - 40, OriginSquare.Position.Y, OriginSquare.Position.Z + 40));requirements.remotes.clientExpandedProperty:FireServer(Plot ,CFrame.new(OriginSquare.Position.X - 40, OriginSquare.Position.Y, OriginSquare.Position.Z - 40));requirements.remotes.clientExpandedProperty:FireServer(Plot ,CFrame.new(OriginSquare.Position.X + 80, OriginSquare.Position.Y, OriginSquare.Position.Z));requirements.remotes.clientExpandedProperty:FireServer(Plot ,CFrame.new(OriginSquare.Position.X - 80, OriginSquare.Position.Y, OriginSquare.Position.Z));requirements.remotes.clientExpandedProperty:FireServer(Plot ,CFrame.new(OriginSquare.Position.X, OriginSquare.Position.Y, OriginSquare.Position.Z + 80));requirements.remotes.clientExpandedProperty:FireServer(Plot ,CFrame.new(OriginSquare.Position.X, OriginSquare.Position.Y, OriginSquare.Position.Z - 80));requirements.remotes.clientExpandedProperty:FireServer(Plot ,CFrame.new(OriginSquare.Position.X + 80, OriginSquare.Position.Y, OriginSquare.Position.Z + 80));requirements.remotes.clientExpandedProperty:FireServer(Plot ,CFrame.new(OriginSquare.Position.X + 80, OriginSquare.Position.Y, OriginSquare.Position.Z - 80));requirements.remotes.clientExpandedProperty:FireServer(Plot ,CFrame.new(OriginSquare.Position.X - 80, OriginSquare.Position.Y, OriginSquare.Position.Z + 80));requirements.remotes.clientExpandedProperty:FireServer(Plot ,CFrame.new(OriginSquare.Position.X - 80, OriginSquare.Position.Y, OriginSquare.Position.Z - 80));requirements.remotes.clientExpandedProperty:FireServer(Plot ,CFrame.new(OriginSquare.Position.X + 40, OriginSquare.Position.Y, OriginSquare.Position.Z + 80));requirements.remotes.clientExpandedProperty:FireServer(Plot ,CFrame.new(OriginSquare.Position.X - 40, OriginSquare.Position.Y, OriginSquare.Position.Z + 80));requirements.remotes.clientExpandedProperty:FireServer(Plot ,CFrame.new(OriginSquare.Position.X + 80, OriginSquare.Position.Y, OriginSquare.Position.Z + 40));requirements.remotes.clientExpandedProperty:FireServer(Plot ,CFrame.new(OriginSquare.Position.X + 80, OriginSquare.Position.Y, OriginSquare.Position.Z - 40));requirements.remotes.clientExpandedProperty:FireServer(Plot ,CFrame.new(OriginSquare.Position.X - 80, OriginSquare.Position.Y, OriginSquare.Position.Z + 40));requirements.remotes.clientExpandedProperty:FireServer(Plot ,CFrame.new(OriginSquare.Position.X - 80, OriginSquare.Position.Y, OriginSquare.Position.Z - 40));requirements.remotes.clientExpandedProperty:FireServer(Plot ,CFrame.new(OriginSquare.Position.X + 40, OriginSquare.Position.Y, OriginSquare.Position.Z - 80));requirements.remotes.clientExpandedProperty:FireServer(Plot ,CFrame.new(OriginSquare.Position.X - 40, OriginSquare.Position.Y, OriginSquare.Position.Z - 80));
    functions.Teleport(CFrame.new(Plot.OriginSquare.CFrame.p) + Vector3.new(0, 5, 0));
    functions.DeleteSurroundingTrees();
    requirements.remotes.setPropertyPurchasingValue:InvokeServer(false);
end;

functions.GetHitPoint=function(Axe)
    local axeFolder=requirements.folders.axeFolder[Axe];
    local axeModule=require(axeFolder.AxeClass).new();
    local hitPoint=axeModule.Damage;
    if axeModule.SpecialTrees then 
        if axeModule.SpecialTrees[requirements.Strings.selectedTree]then 
            hitPoint=axeModule.SpecialTrees[requirements.Strings.selectedTree].Damage
        end
    end				
    return hitPoint;
end;

functions.antiEndTimesEarRape=function()
    for i,v in next,requirements.LP.PlayerGui.ClientSounds:GetDescendants()do 
        if v.Name=='Alternate'then 
            v:Destroy()
        end;
    end;
end;
functions.antiEndTimesEarRape();

functions.getBestAxe=function()
    local toolName;
    local axes={};
    local bestAxe;
    local dmg=0;
    local damage;
    for _,v in pairs(requirements.LP.Backpack:children())do
        table.insert(axes,v);
    end;
    for _,v in pairs(requirements.LP.Character:children())do
        if v:IsA'Tool'then 
            table.insert(axes,v);
        end;
    end
    for _,v in next,axes do
        if v:FindFirstChild'ToolName'and requirements.folders.axeFolder:FindFirstChild(tostring(v.ToolName.Value))then 
            stats=require(requirements.folders.axeFolder:FindFirstChild(tostring(v.ToolName.Value)).AxeClass).new()		
            if stats.SpecialTrees then 
                if stats.SpecialTrees[requirements.Strings.selectedTree]then 
                    damage=stats.SpecialTrees[requirements.Strings.selectedTree].Damage
                    bestAxe=v;
                    return bestAxe;
                end;
            end;
            damage=stats.Damage		
            if damage>dmg then 
                dmg=damage;
                bestAxe=v;
            end;
        end;
    end;
    return bestAxe;
end;

functions.chopTree=function(cutEvent)
    requirements.connections.chopTree=requirements.remotes.remoteProxy:FireServer(cutEvent,{['tool']=functions.getBestAxe(),['faceVector']=Vector3.new(1,0,0),['height']=.32,['sectionId']=1,['hitPoints']=functions.GetHitPoint(functions.getBestAxe().ToolName.Value),['cooldown']=-14,['cuttingClass']='Axe'})
end;

functions.CutAssist=function()
    local target;
    local Height;
    requirements.connections.woodSelection=requirements.Mouse.Button1Down:Connect(function()
        target=requirements.Mouse.Target;
        if target then
            Height=target.CFrame:pointToObjectSpace(requirements.Mouse.Hit.p).Y + target.Size.Y/2
            if tostring(target)=='WoodSection'and target.Parent:FindFirstChild('Owner')then 
                if target.Parent.Owner.Value==requirements.LP or target.Parent.Owner.Value==nil then
                    requirements.Strings.TreeModel=target.Parent;
                    woodSection=target.ID;
                end;
            end;
        end;
        repeat wait()until requirements.Strings.TreeModel
        if requirements.connections.cutAssistCutter==nil then 
            requirements.connections.cutAssistCutter=requirements.wrkspc.LogModels.ChildAdded:Connect(function(tree)
                tree:WaitForChild('Owner',5)
                if tree.Owner.Value==requirements.LP then 
                    requirements.Booleans.isPlankCut=true;
                end;
            end);
        end;
        requirements.LP.Character.Humanoid:UnequipTools();
        repeat wait()
            requirements.remotes.remoteProxy:FireServer(woodSection.Parent.Parent.CutEvent,{['tool']=functions.getBestAxe(),['faceVector']=Vector3.new(1,0,0),['height']=Height,['sectionId']=woodSection.Value,['hitPoints']=functions.GetHitPoint(functions.getBestAxe().ToolName.Value),['cooldown']=-14,['cuttingClass']='Axe'})
        until requirements.Booleans.isPlankCut;
        requirements.Booleans.isPlankCut=false;
        if requirements.connections.cutAssistCutter then 
            requirements.connections.cutAssistCutter:Disconnect();
            requirements.connections.cutAssistCutter=nil;
        end;
    end);
end;

functions.setWorkspaceGuis=function(parent,text)
    for _, instance in next,parent:GetChildren()do
        if (instance:IsA('BillboardGui')or instance:IsA('SurfaceGui'))and instance.Enabled then
            pcall(function()
                instance:FindFirstChildOfClass('TextLabel',true).Text=text;
                instance:FindFirstChildOfClass('TextLabel',true).TextScaled=true;
            end);
        end;
        functions.setWorkspaceGuis(instance,text);
    end;
end;

functions.OpenBP=function(item)
    requirements.remotes.clientInteracted:FireServer(requirements.wrkspc.PlayerModels:FindFirstChild(tostring(item)..' Purchased by '..tostring(requirements.LP)),'Open box');
end;

functions.OpenSelectedItem=function(item)
    local itemBox=item:FindFirstChild('BoxItemName')or item:FindFirstChild('PurchasedBoxItemName');
    if itemBox and item:FindFirstChild('Type')and item.Type.Value~='Structure' then
        requirements.remotes.clientInteracted:FireServer(item,'Open box');
        functions.notify('Ancestor','Opened Item',4)
    end;
end;

functions.getAllBP=function()
    if #requirements.LP.PlayerBlueprints.Blueprints:children()<69 then
        for _,v in next,requirements.folders.blueprintFolder:children()do
            local newBP=v:Clone();
            newBP.Parent=requirements.LP.PlayerBlueprints.Blueprints;
        end;
    else
        functions.notify('Error','You have all blueprints!',4);
    end;
end;

functions.getPermBP=function()
    local amount=0;
    for _,v in next,requirements.folders.blueprintFolder:children()do
        if not requirements.LP.PlayerBlueprints.Blueprints:FindFirstChild(v)then 
            amount=amount+v.Price.Value
            if requirements.LP.leaderstats.Money.Value<amount then 
                functions.notify('Error','Not Enough Money!',4);
                return;
            end;
            blueprint=tostring(v);
            functions.AutoBuyItem(blueprint,1);
            functions.OpenBP(blueprint);
        else
            functions.notify('Error','You Already Own '..tostring(v),4)
        end;
    end;
end;

functions.sitInAllCars=function(value)
    requirements.LP.PlayerGui.Scripts.SitPermissions.Disabled=value
end;

functions.getPlotCFrame=function()
    for _,plot in next,workspace.Properties:children()do 
        if plot:FindFirstChild('Owner')and tostring(plot.Owner.Value)==tostring(requirements.Strings.autoBuildPlayer) then 
            return plot.OriginSquare.CFrame.p;
        end;
    end;
    return false;
end;

functions.saveBaseToFile=function(name)
    local blueprints='';
    local bpType,MainCFrame;
    local localplot;
    if not functions.getPlotCFrame()then 
        functions.notify('Ancestor',tostring(requirements.Strings.autoBuildPlayer..' Has No Plot!'));
        return;
    end;
    for _,plot in next,workspace.Properties:children()do 
        if plot:FindFirstChild('Owner')and tostring(plot.Owner.Value)==requirements.Strings.autoBuildPlayer then 
            localplot=plot.OriginSquare.CFrame.p;
        end;
    end;
    for _,blueprint in next,workspace.PlayerModels:children()do 
        if blueprint:IsA('Model')and blueprint:FindFirstChild('MainCFrame')and blueprint:FindFirstChild('Type')and blueprint.Type.Value=='Structure'and blueprint:FindFirstChild('Owner')and tostring(blueprint.Owner.Value)==requirements.Strings.autoBuildPlayer then 
            if game:GetService('ReplicatedStorage').Purchasables.Structures.BlueprintStructures:FindFirstChild(tostring(blueprint.ItemName.Value))then
                bpType,MainCFrame=blueprint.ItemName.Value,blueprint.MainCFrame.Value;
                blueprints=blueprints..''..bpType..'&'..tostring(MainCFrame-localplot)..'|';
            end;
        end;
    end;
    writefile(name..'.Ancestor',blueprints)
end;

functions.importFiles=function(File)
    local tablew={};
    local string=string.split(File, '|');
    for i,v in pairs(string) do
        if v ~= '' then
            table.insert(tablew, v);
        end;
    end;
    return tablew;
end;

local connection,connection2;
functions.modWood=function(log,sawmill)
    local ID=1;
    local oldPos=requirements.LP.Character.HumanoidRootPart.CFrame
    requirements.Booleans.oldNoclipEnabled=true;
    requirements.Booleans.Noclip=true;
    for i,v in next,log:children()do
        if v.Name=='WoodSection'and v:FindFirstChild('ID')then
            if v.ID.Value>=ID then 
                smallestWoodSection=v;
            end;
        end;
    end;
    for i,v in pairs(log:GetChildren()) do
        if v.Name == 'WoodSection' then
            if v.ID.Value == smallestWoodSection.ParentID.Value then
                smallestWoodSection2=v;
                break
            end
        end
    end
    local old=requirements.Strings.selectedTree
    pcall(function()
        requirements.Strings.selectedTree=log.TreeClass.Value;
    end)
    if not smallestWoodSection or not smallestWoodSection2 then 
        functions.notify('Error', 'Mod wood failed.',4) 
        return 
    end;
    functions.Teleport(CFrame.new(smallestWoodSection.CFrame.p+Vector3.new(2,4,2)));
    connection=smallestWoodSection2.AncestryChanged:Connect(function()
        for i=1,10 do 
            game.ReplicatedStorage.Interaction.ClientIsDragging:FireServer(log)
            smallestWoodSection.CFrame=sawmill.Particles.CFrame
            game:GetService'RunService'.Stepped:Wait();
        end
        if connection2 then
            connection2:Disconnect();
            connection2=nil;
        end;
    end);
    logConnection=workspace.LogModels.ChildAdded:Connect(function(b)
        local Owner=b:WaitForChild('Owner')
        if tostring(Owner.Value)==tostring(requirements.LP)then
            logConnection:Disconnect();
            logConnection=nil;
        end;
    end);
    local lava=workspace['Region_Volcano'].Lava.Lava
    repeat game:GetService'RunService'.Stepped:Wait();
        game.ReplicatedStorage.Interaction.ClientIsDragging:FireServer(log);
        firetouchinterest(smallestWoodSection2,lava,0);
        firetouchinterest(smallestWoodSection2,lava,1);
    until smallestWoodSection2:FindFirstChild('LavaFire');
    smallestWoodSection2:FindFirstChild('LavaFire'):Destroy();
    for i=1,12 do 
        game.ReplicatedStorage.Interaction.ClientIsDragging:FireServer(log);
        smallestWoodSection2.CFrame=CFrame.new(315,-0,79);
        game:GetService'RunService'.Heartbeat:wait();
    end;
    repeat game:GetService'RunService'.Stepped:Wait(); until not connection2
    functions.Teleport(CFrame.new(smallestWoodSection.CFrame.p))
    repeat game:GetService'RunService'.Stepped:wait();
        game.ReplicatedStorage.Interaction.ClientIsDragging:FireServer(log)
        smallestWoodSection.CFrame=sawmill.Particles.CFrame
        functions.Teleport(CFrame.new(log.PrimaryPart.CFrame.p+Vector3.new(0,2,0)))
        functions.chopTree(log.CutEvent)
    until not logConnection;
    if connection then 
        connection:Disconnect();
        connection=nil;
    end;
    if connection2 then 
        connection2:Disconnect();
        connection2=nil;
    end;
    requirements.Booleans.oldNoclipEnabled=false;
    requirements.Booleans.Noclip=false;
    requirements.Strings.selectedTree=old;
end;

functions.loadFile=function(Name,value)
    local localplot;
    if not pcall(function() readfile(Name..'.Ancestor') end) then
        if value then
            functions.notify('Error', 'Incorrect FileName!', 4);
            return;
        end;
    end;
    if requirements.Booleans.building then 
        functions.notify('Error', '即将建造', 4);
        return;
    end;
    for _,plot in next,workspace.Properties:children()do 
        if plot:FindFirstChild('Owner')and tostring(plot.Owner.Value)==tostring(requirements.Strings.autoBuildReciever)then 
            localplot=plot.OriginSquare.CFrame.p;
        end;
    end;
    requirements.Booleans.building=true;
    requirements.connections.autoBuild=workspace.PlayerModels.ChildAdded:Connect(function(b)
        local Owner=b:WaitForChild('Owner',5);
        if tostring(Owner.Value)==tostring(requirements.Strings.autoBuildReciever)and b:FindFirstChild'Type'and b.Type.Value=='Blueprint'then 
            repeat wait()until b:FindFirstChild('Main');
            game:GetService('ReplicatedStorage').PlaceStructure.ClientPlacedStructure:FireServer(tostring(b.ItemName.Value), b.Main.CFrame, requirements.LP, nil, b, true);
        end;
    end);
    local tablew={};
    local blueprints={};
    if value then 
        tableS=functions.importFiles(readfile(Name..'.Ancestor'))
    elseif not value then
        tableS=functions.importFiles(Name);
    end;
    for i,v in next,tableS do
        local Split=v:split('&');
        local tablew={};
        local blueprints={};
        table.insert(blueprints,Split[1]);
        local ItemName,CFrameV=Split[1], Split[2];
        local CFrameSplit=tostring(CFrameV):split(',');
        for i,v in pairs(CFrameSplit) do
            table.insert(tablew, v);
        end;
        local itemName=blueprints[1];
        local blueprint=CFrame.new(tonumber(tablew[1]),tonumber(tablew[2]),tonumber(tablew[3]),tonumber(tablew[4]),tonumber(tablew[5]),tonumber(tablew[6]),tonumber(tablew[7]),tonumber(tablew[8]),tonumber(tablew[9]),tonumber(tablew[10]),tonumber(tablew[11]),tonumber(tablew[12]));
        game:GetService('ReplicatedStorage').PlaceStructure.ClientPlacedBlueprint:FireServer(itemName,blueprint+localplot,game:GetService('Players').LocalPlayer)
        local num=math.random(1,15)
        if num==2 then 
            game:GetService'ReplicatedStorage'.TestPing:InvokeServer();
        end
        game:GetService('RunService').Heartbeat:wait();
        if not requirements.Booleans.vipMode then
            game:GetService('RunService').Heartbeat:wait();
        end;
    end;	
    wait(1)
    requirements.Booleans.building=false;
    if requirements.connections.autoBuild then 
        requirements.connections.autoBuild:Disconnect();
        requirements.connections.autoBuild=nil;
    end;
end;

functions.LoadSelectedSlot=function(num)
    if not requirements.remotes.clientMayLoad:InvokeServer(requirements.LP)then
        functions.notify('Error', 'Load is on cooldown. Waiting...', 4);
        repeat
            wait(5);
        until requirements.remotes.clientMayLoad:InvokeServer(requirements.LP);
    end
    if not requirements.Booleans.MoneyDuping then 
        requirements.remotes.requestSave:InvokeServer(requirements.LP.CurrentSaveSlot.Value,requirements.LP)
    end;
    functions.notify('Ancestor', 'Loading slot '..requirements.Strings.selectedPlotToLoad, 4);
    functions.fastLoadSelectedPlot(num,requirements.LP)
    repeat wait() until requirements.LP.CurrentlySavingOrLoading.Value == false;
    return true
end;

functions.SaveSelectedSlot=function()
    if not functions.getPlayersBase(tostring(requirements.LP))then 
        functions.notify('Error','No Slot Loaded!',4);
        return;
    end;
    if requirements.Booleans.DisableSlotSaving then 
        functions.notify('Error','Slot Saving is disabled!',4)
        return;
    end;
    local success,Errormsg=pcall(function()requirements.remotes.requestSave:InvokeServer(requirements.LP.CurrentSaveSlot.Value,requirements.LP)end);
    if success then
        functions.notify('Ancestor', 'Saved Slot '..requirements.LP.CurrentSaveSlot.Value,4);
    else
        functions.notify('Error',Errormsg);
    end;
end;

functions.manyAxeFloor=function()
    if not requirements.wrkspc:FindFirstChild('AncestorV3')then 
        local floor=Instance.new('Part',requirements.wrkspc);
        floor.Anchored=true;
        floor.Size=Vector3.new(50,0.5,50);
        floor.Position=Vector3.new(532,-50,-1716);
        floor.BrickColor=BrickColor.new(0,0,255);
        floor.Material=Enum.Material.SmoothPlastic;
        floor.Name='AncestorV3';
    end;
end;
functions.manyAxeFloor();

functions.DropAllTools=function(Bool)
    requirements.LP.Character.Humanoid:UnequipTools();
    for _,Tool in next,requirements.LP.Backpack:children()do 
        if Tool:IsA('Tool')and Tool:FindFirstChild('ToolName')then 
            requirements.remotes.clientInteracted:FireServer(Tool,'Drop tool',requirements.LP.Character.HumanoidRootPart.CFrame);
        end;
    end;
end;

functions.DupeInventory=function(Quantity)
    for i=1,Quantity do 
        if not requirements.Booleans.axeDuping then 
            functions.notify('Ancestor','Dupe Inventory Aborted!',4);
            return;
        end;
        local oldpos=requirements.LP.Character.HumanoidRootPart.Position
        wait(.1)
        if not functions.getBestAxe()then
            functions.notify('错误','没有斧头去复制',4);
            return;
        end;
        functions.DropAllTools();
        functions.KillPlayer();
        requirements.LP.CharacterAdded:wait();
        functions.Teleport(CFrame.new(oldpos));
    end;
end;


functions.AutoDupeMoney=function(amount,slot)
    if not slot then 
        slot=requirements.LP.CurrentSaveSlot.Value;
    end;
    amount=requirements.Strings.autoDupeMoneyAmount;
    if requirements.Booleans.MoneyDuping then 
        functions.notify('Error', 'Already Duping!',4);
        return;
    end;
    if requirements.Booleans.DisableSlotSaving then 
        functions.notify('Error','Disable slot saving is enabled!',4);
        return;
    end;
    functions.PlotLogic();
    requirements.Booleans.MoneyDuping=true;
    for i=1,amount do
        spawn(function()requirements.remotes.Donate:InvokeServer(requirements.LP,requirements.LP.leaderstats.Money.Value,requirements.LP.CurrentSaveSlot.Value)end);
        local Money=requirements.LP.leaderstats.Money.Value;
        if Money~=0 then 
            functions.notify('Ancestor','Waiting for donation...',4);
            repeat wait()spawn(function()requirements.remotes.Donate:InvokeServer(requirements.LP, requirements.LP.leaderstats.Money.Value,requirements.LP.CurrentSaveSlot.Value)end); 
                local Money=requirements.LP.leaderstats.Money.Value;
            until Money==0; 
        end;
        functions.notify('Ancestor','Loading slot...',4);
        functions.fastLoadSelectedPlot(slot);
        repeat wait()until requirements.LP.CurrentlySavingOrLoading.Value==false;
        requirements.remotes.requestSave:InvokeServer(slot,requirements.LP)
        wait(5)
        requirements.remotes.requestSave:InvokeServer(slot,requirements.LP)
        amount=amount-1;
        if amount==0 then 
            functions.notify('Ancestor','Auto dupe money finished.',5);
            requirements.Booleans.MoneyDuping=false
        end;
    end;
end;
functions.PlotLogic=function()
    if requirements.LP.CurrentSaveSlot.Value== -1 then
        functions.notify('Error', 'No Plot Is Loaded..', 4);
        return;                      
    end;
    if not requirements.remotes.clientMayLoad:InvokeServer(requirements.LP)then
        functions.notify('Error', 'Load is on cooldown. Waiting...', 4)
        repeat
            wait(5)
        until requirements.remotes.clientMayLoad:InvokeServer(requirements.LP);
        functions.notify('Ancestor', 'Loading plot...', 4);
    end;
    return true;
end;

functions.getPlots=function()
    local Plots={};
    for i,v in next,requirements.wrkspc.Properties:children()do
        if v:FindFirstChild('Owner') and v.Owner.Value==nil then 
            table.insert(Plots, v);
            return Plots;
        end;
    end;
end;

functions.findSelectedTree=function(treeClass)
    for _,v in next,workspace:children()do
        if tostring(v)=='TreeRegion'then
            for _,g in next,v:children()do
                if g:FindFirstChild('TreeClass')and tostring(g.TreeClass.Value)==treeClass and g:FindFirstChild('Owner')then 
                    if g.Owner.Value==nil or tostring(g.Owner.Value)==tostring(requirements.LP)then 
                        if #g:children() > 5 and g:FindFirstChild('WoodSection')then 
                            for h,j in next,g:children() do 
                                if j:FindFirstChild('ID')and j.ID.Value==1 and j.Size.Y>.5 then 
                                    return j;
                                end;
                            end;
                        end;
                    end;
                end;
            end;
        end;
    end;
    return false;
end; 

functions.getStore=function(item)
    local magnitude=9e9
    local counter;
    for _,v in next,requirements.wrkspc.Stores:children()do
        if tostring(v)=='WoodRUs'or tostring(v)=='CarStore'or tostring(v)=='FineArt'or tostring(v)=='ShackShop'or tostring(v)=='LogicStore'or tostring(v)=='FurnitureStore'then 
            if(item.Main.CFrame.p-v.Counter.CFrame.p).magnitude<magnitude then
                magnitude=(item.Main.CFrame.p-v.Counter.CFrame.p).magnitude
                counter=v.Counter;
            end;
        end;
    end;
    return counter;
end;

functions.bringPushMe=function()
    local oldPos=requirements.LP.Character.HumanoidRootPart.CFrame;
    local slab=game:GetService('Workspace')['Region_Mountainside'].SlabRegen:FindFirstChild('Slab')
    if slab and not slab.PrimaryPart then 
        slab.PrimaryPart=slab.PushMe;
    end;
    functions.Teleport(CFrame.new(slab.PrimaryPart.CFrame.p));
    wait(.2)
    for i=1,20 do 
        requirements.remotes.clientRequestOwnership:FireServer(slab);
        requirements.remotes.clientIsDragging:FireServer(slab);
    end;
    slab:SetPrimaryPartCFrame(CFrame.new(oldPos.p));
    functions.Teleport(CFrame.new(oldPos.p))
end;

functions.bringBoulders=function()
    local times=0;
    local oldPos=requirements.LP.Character.HumanoidRootPart.CFrame;
    functions.Teleport(CFrame.new(-1479,532,1462));
    local model=game:GetService('Workspace')['Region_Volcano'].PartSpawner
    requirements.connections.bringBoulders=model.ChildAdded:Connect(function(b)
        repeat wait()until requirements.LP.Character and requirements.LP.Character:FindFirstChild('Humanoid');
        functions.Teleport(CFrame.new(b.CFrame.p));
        for i=1,12 do 
            b.CFrame=CFrame.new(oldPos.p);
            game:GetService('RunService').Stepped:wait();
        end;
        functions.Teleport(CFrame.new(-1479,532,1462));
        if not requirements.Booleans.bringBoulders then 
        if requirements.connections.bringBoulders then 
                requirements.connections.bringBoulders:Disconnect();
                requirements.connections.bringBoulders=nil;
                functions.Teleport(CFrame.new(oldPos.p));
            end;
        end;
    end);
end;

functions.lowerBridge=function(value)
local lift=workspace.Bridge.VerticalLiftBridge.Lift;
if value=='Higher'then
        lift.Base.CFrame=lift.Base.CFrame+Vector3.new(0,26,0);
elseif value=='Lower'then
        lift.Base.CFrame=lift.Base.CFrame+Vector3.new(0,-26,0);
    end;
end;

functions.BaseDrop=function(item,teleport)
    local main=item:FindFirstChild('WoodSection')or item:FindFirstChild('Main');																
    if main and teleport then 
        pcall(function()
            if(requirements.LP.Character.HumanoidRootPart.CFrame.p-main.CFrame.p).magnitude>50 then 
                functions.Teleport(CFrame.new(main.CFrame.p));
            end;
            spawnf(function()
                for i=1,10 do
                    requirements.remotes.clientRequestOwnership:FireServer(main);
                    requirements.remotes.clientIsDragging:FireServer(main.Parent);
                    wait();
                end;
            end);
        end)
    end;
end;

functions.justInCase=function()
    if game.ReplicatedStorage.Transactions:FindFirstChild('AddLog')then
        game.ReplicatedStorage.Transactions.AddLog:remove();
    end;
    local scr=getsenv(requirements.LP.PlayerGui.LoadSaveGUI.LoadSaveClient.LocalScript)
    scr.ban=function()return false end
end;
functions.justInCase();

functions.checkPlanks=function(option)
    local amount=0;
    local model=nil;
    for i,v in next,requirements.wrkspc.PlayerModels:children()do 
        if v:IsA('Model')and v:FindFirstChild('Owner')and functions.OwnerCheck(v)==tostring(requirements.LP)and v:FindFirstChild('TreeClass')then 
            amount=amount+1
            model=v;
        end;
    end;
    if option=='Amount' then 
        return amount;
    elseif option=='Model'then 
        return model;
    end;
    return false;
end;

functions.SellPlanks=function()
    local oldPos=requirements.LP.Character.HumanoidRootPart.CFrame.p
    local plankSold=false;
    local amount=functions.checkPlanks('Amount');
    if amount==0  then 
        functions.notify('Error','No Planks To Sell!',4);
        return;
    end;
    repeat 
        wait()
        local plank=functions.checkPlanks('Model');
        local connection
        connection=requirements.wrkspc.PlayerModels.ChildRemoved:Connect(function(b)
            plankSold=true;
        end)
        functions.Teleport(CFrame.new(plank.WoodSection.CFrame.p))
        functions.BaseDrop(plank,true);
        plank.WoodSection.CFrame=CFrame.new(315.4, 1.2, 85.4);
        repeat wait()until plankSold
        if connection then 
            connection:Disconnect();
            connection=nil;
        end;
    until functions.checkPlanks('Amount')==0;
    functions.Teleport(CFrame.new(oldPos))
end;

functions.PlayNotification=function()
    local Sound=Instance.new('Sound')
    Sound.SoundId='rbxassetid://6916070297';
    Sound.Parent=requirements.LP.Character.Head;
    Sound:Play();
    Sound.Stopped:wait();
    Sound:Destroy();
end;

requirements.connections.WindowFocused=requirements.services.userInputService.WindowFocused:Connect(function()
    requirements.Booleans.sendNotifications=false;
end);
requirements.connections.WindowFocusedReleased=requirements.services.userInputService.WindowFocusReleased:Connect(function()
    requirements.Booleans.sendNotifications=true;
end);

functions.getPlayersBase=function(plr)
    for i,v in next,workspace.Properties:children()do 
        if v:IsA('Model')and tostring(v.Owner.Value)==plr then 
            return v;
        end;
    end;
    return false;
end;
functions.donateBaseAutoload=function(slotnum)
    local plot = nil
    for i,v in next,game.Workspace.Properties:children()do
        if v.Owner.Value==nil and not v:FindFirstChild'Square'then
            plot=v;
        end;
    end;
    local senv=getsenv(game:GetService('Players').LocalPlayer.PlayerGui.PropertyPurchasingGUI.PropertyPurchasingClient)
    local old=senv.enterPurchaseMode
    local plot;
    local autoLoading=true;
    task.spawn(function()
        functions.FreeLand();
    end)
    getsenv(game:GetService('Players').LocalPlayer.PlayerGui.PropertyPurchasingGUI.PropertyPurchasingClient).enterPurchaseMode=function(...)
        if not autoLoading then
            return old(...)
        else
            autoLoading=false;
            repeat task.wait()until functions:getPlayersBase(tostring(requirements.LP));
            functions.notify('Ancestor','Fucking working i think idk')
            for i,v in next,game.Workspace.Properties:children()do
                if v.Owner.Value==nil and not v:FindFirstChild'Square'then
                    if table.find(whitelistedPlots,tostring(v.OriginSquare.OriginCFrame.Value))then
                        plot=v;
                        break;
                    end;
                end;
            end;
            if not _G.autoLoaded then
                debug.setupvalue(senv.rotate,3,0)
                debug.setupvalue(old,10,plot)
                _G.autoLoaded=true;
                return;
            end;
        end;
    end;
    spawn(function()
        game:GetService('ReplicatedStorage').LoadSaveRequests.RequestLoad:InvokeServer(slotnum,requirements.LP)
    end)
    scr=getsenv(requirements.LP.PlayerGui.PropertyPurchasingGUI.PropertyPurchasingClient);
    spawn(function()
        for i=1,20 do 
            wait(.15);
            scr.selectionMade();
        end;
    end);
    repeat wait()until functions.getPlayersBase(tostring(requirements.LP));
    autoLoading=false;
    requirements.LP.CurrentSaveSlot.Value=slotnum;
    return loadedSlot
end;

functions.CheckPlayerBan=function(Player)
    if not Player or Player==''then return;end;
    local playerIDTEST=pcall(function()game:GetService('Players'):GetUserIdFromNameAsync(tostring(Player))end);
    if not playerIDTEST then functions.getButton('Ban Status: Button')['Ban Status: Button'].ImageLabel.TextButton.Text='Not A Valid Username'wait(4);functions.getButton('Ban Status: Button')['Ban Status: Button'].ImageLabel.TextButton.Text='Ban Status: ';return end;
    local playerID=game:GetService('Players'):GetUserIdFromNameAsync(tostring(Player))
    local banned,reason=game:GetService('ReplicatedStorage').Transactions.GetMod:InvokeServer(tonumber(playerID));
    if reason==''then
        functions.getButton('Ban Status: Button')['Ban Status: Button'].ImageLabel.TextButton.Text='Not Banned From Lumber Tycoon 2'
    else
        functions.getButton('Ban Status: Button')['Ban Status: Button'].ImageLabel.TextButton.Text='Is Banned For: \n'..reason
    end;
    wait(4);
    functions.getButton('Ban Status: Button')['Ban Status: Button'].ImageLabel.TextButton.Text='Ban Status: ';
end;

functions.PlankToBlueprint=function()
    if not requirements.LP.SuperBlueprint.Value then 
        functions.notify('Error','你需要超级建筑才能使用',4);
        return;
    end;
    local target;
    functions.notify('Ancestor','选择一个木头和蓝图',2);
    requirements.connections.PlankToBlueprint=requirements.Mouse.Button1Down:Connect(function()
        if requirements.Mouse.Target then 
            target=requirements.Mouse.Target;
        end;
        if target.Parent:FindFirstChild('Type')and target.Parent.Type.Value=='Blueprint'then 
            requirements.Strings.blueprintModel=target.Parent;
            functions.notify('Ancestor','Blueprint Selected',2);
        end;
        if tostring(target.Parent)=='Plank'and target.Parent:FindFirstChild('Owner') and tostring(target.Parent.Owner.Value)==tostring(requirements.LP)then 
            requirements.Strings.plankModel=target.Parent;
            functions.notify('Ancestor','Plank Selected',2);
        end;
    end);
    repeat wait()until requirements.Strings.plankModel and requirements.Strings.blueprintModel;
    functions.Teleport(CFrame.new(requirements.Strings.plankModel:FindFirstChildOfClass'Part'.CFrame.p+Vector3.new(0,3,4)))
    wait(.2)
    for i=1,120 do 
        pcall(function()
            requirements.remotes.clientIsDragging:FireServer(requirements.Strings.plankModel)
            requirements.Strings.plankModel.WoodSection.CFrame=CFrame.new(requirements.Strings.blueprintModel.Main.CFrame.p+Vector3.new(0,1.5,0));
            game:GetService'RunService'.Stepped:wait();
        end);
    end;
    if requirements.connections.PlankToBlueprint then 
        requirements.connections.PlankToBlueprint:Disconnect();
        requirements.connections.PlankToBlueprint=nil;
    end;
    functions.notify('Ancestor','Done!',2);
    requirements.Strings.blueprintModel=nil;
    requirements.Strings.plankModel=nil;
end;

functions.getCashier=function(item)
    local store=functions.getStore(item)
    for i,v in next,store.Parent:children()do 
        if v:IsA('Model')and v:FindFirstChild('Humanoid')then 
            return v; 
        end;
    end;
end;

local cashierIds={};
spawn(function()
    local connection=game.ReplicatedStorage.NPCDialog.PromptChat.OnClientEvent:connect(function(ba,data)
        if cashierIds[data.Name]==nil then
            cashierIds[data.Name]=data.ID;
        end;
    end);
    game.ReplicatedStorage.NPCDialog.SetChattingValue:InvokeServer(1);
    wait(2)
    connection:Disconnect();
    connection=nil;
    game.ReplicatedStorage.NPCDialog.SetChattingValue:InvokeServer(0);
end);
functions.getID=function(item)
    local v=functions.getCashier(item);
    return cashierIds[tostring(v)];
end;

functions.getSpecialID=function(Shop)
    return cashierIds[Shop];
end;

functions.getPrice=function(item,quantity)
    local money=requirements.LP.leaderstats.Money.Value 
    for _,v in next,game:GetService('ReplicatedStorage').Purchasables:GetDescendants()do 
        if tostring(v)==item then 
            local newValue=v.Price.Value*quantity;
            if money>=newValue then 
                return true;
            end;
        end;
    end;
    return false;
end;

functions.getItem=function(item)
    local Store;
    local Counter;
    for _,v in next,workspace.Stores:GetChildren()do
        if v.Name == 'ShopItems' then 
            for _,k in pairs(v:GetChildren())do 
            local store=k.Parent;
            if store:FindFirstChild(item)then
                if store:FindFirstChild('BasicHatchet')then
                        Store=store;
                        Counter=Store.Parent:FindFirstChild('WoodRUs').Counter
                    elseif store:FindFirstChild('LightBulb')then
                        Store=store;
                        Counter=Store.Parent:FindFirstChild('FurnitureStore').Counter
                    elseif store:FindFirstChild('Pickup1')then
                        Store=store;
                        Counter=Store.Parent:FindFirstChild('CarStore').Counter
                    elseif store:FindFirstChild('CanOfWorms')then
                        Store=store;
                        Counter=Store.Parent:FindFirstChild('ShackShop').Counter
                    elseif store:FindFirstChild('Painting3')then
                        Store=store;
                        Counter=Store.Parent:FindFirstChild('FineArt').Counter
                    elseif store:FindFirstChild('GateXOR')then
                        Store=store;
                        Counter=Store.Parent:FindFirstChild('LogicStore').Counter
                    end;
                end;
            end;
        end;
    end;
    return Store,Counter;
end;

functions.getItemsOnCounter=function(item)
    local shop,counter=functions.getItem(item)
    local boundsA = counter.CFrame * CFrame.new(counter.Size.X/2, 0, counter.Size.Z/2)
    local boundsB = counter.CFrame * CFrame.new(-counter.Size.X/2, 0, -counter.Size.Z/2)
    local counterRegion = Region3.new(Vector3.new(math.min(boundsA.X, boundsB.X), counter.Size.Y/2 + boundsA.Y, math.min(boundsA.Z, boundsB.Z)),
        Vector3.new(math.max(boundsA.X, boundsB.X), counter.Size.Y/2 + 0.6 + boundsA.Y, math.max(boundsA.Z, boundsB.Z)))
    local v=workspace:FindPartsInRegion3(counterRegion, counter)
    for k,part in next,v do 
        if part.Parent:FindFirstChild('BoxItemName') and part.Parent:FindFirstChild('Type') and game.ReplicatedStorage.Purchasables:FindFirstChild(part.Parent.BoxItemName.Value, true)then
            return part;
        end;
    end;
    return false;
end;

functions.spawnCar=function()
    local remote;
    functions.notify('Ancestor','Click A Vehicle Spawn Pad',4);
    connection=requirements.Mouse.Button1Down:Connect(function()
        local target=requirements.Mouse.Target;
        if target and target.Parent:FindFirstChild('Type')and target.Parent.Type.Value=='Vehicle Spot'then 
            remote=target.Parent:FindFirstChildOfClass('BindableEvent');
            connection:Disconnect();
            connection=nil;
            functions.notify('Ancestor','Spawning...',4);
        end;
    end)
    requirements.connections.spawnCar=workspace.PlayerModels.ChildAdded:Connect(function(car)
        wait(.05)
        if car:FindFirstChild('Owner')and tostring(car.Owner.Value)==tostring(requirements.LP)and car:FindFirstChild('Type')and car.Type.Value=='Vehicle'then
        if car:FindFirstChild('Settings')and car.Settings:FindFirstChild('Color')then 
            if car.Settings.Color.Value==tonumber(requirements.Strings.colorToSpawn) then
                if requirements.connections.spawnCar then
                        requirements.connections.spawnCar:Disconnect();
                        requirements.connections.spawnCar=nil;
                    end;
                end;
            end;
        end;
    end);
    repeat wait(.5)
        if requirements.connections.spawnCar then 
            game:GetService('ReplicatedStorage').Interaction.RemoteProxy:FireServer(remote)
        end;
    until not requirements.connections.spawnCar;
    functions.notify('Ancestor','Spawned Color')
end;

functions.DraggerDetection=function()
    requirements.connections.draggerAdded=workspace.ChildAdded:Connect(function(part)
        if tostring(part)=='Dragger'then 
            requirements.Booleans.dragExists=true;
        end;
    end);
    
    requirements.connections.draggerRemoved=workspace.ChildRemoved:Connect(function(part)
        if tostring(part)=='Dragger'then 
            requirements.Booleans.dragExists=false;
        end;
    end);
end;
functions.DraggerDetection();

functions.AutoBuyItem=function(item,quantity)
    if requirements.Booleans.isBuying then 
        functions.notify('Error','Already Buying!',4);
        return false;
    end;
    local Store,Counter;
    local oldpos=requirements.LP.Character.HumanoidRootPart.CFrame;
    requirements.Booleans.isBuying=true;
    requirements.ConfigSetup.oldNoclipEnabled=true;
    requirements.Booleans.Noclip=true;
    repeat game:GetService'RunService'.Heartbeat:wait() Store,Counter=functions.getItem(item); until Store and Counter;
    if functions.getItemsOnCounter(item)then 
        requirements.Booleans.abortAutobuy=false;
        requirements.ConfigSetup.oldNoclipEnabled=false;
        requirements.Booleans.Noclip=false;
        requirements.Booleans.isBuying=false;
        functions.Teleport(CFrame.new(oldpos.p));
        functions.notify('Error','Items Are On The Counter. Aborting....',4);
        return false;
    end;
    local price=functions.getPrice(tostring(item),quantity);
    if not price and not requirements.Booleans.loopBuying then 
        requirements.ConfigSetup.oldNoclipEnabled=false;
        requirements.Booleans.Noclip=false;
        requirements.Booleans.isBuying=false;
        functions.Teleport(CFrame.new(oldpos.p));
        functions.notify('Error','没有足够的钱',4);
        return false;
    end;
    for i=1,quantity do
        if requirements.Booleans.abortAutobuy then
            requirements.Booleans.abortAutobuy=false;
            requirements.ConfigSetup.oldNoclipEnabled=false;
            requirements.Booleans.Noclip=false;
            requirements.Booleans.isBuying=false;
            functions.Teleport(CFrame.new(oldpos.p));
            functions.notify('Ancestor','Aborted Autobuy!',4);
            return false;
        end;
        local itemToBuy=Store:FindFirstChild(item);
        if not itemToBuy then
            local start=tick();
            repeat game:GetService'RunService'.Heartbeat:wait()until Store:FindFirstChild(item)or tick()-start >=60;
            local newItem=Store:FindFirstChild(item);
            if newItem then
                itemToBuy=newItem;
            end;
        end;
        if not itemToBuy then
            requirements.ConfigSetup.oldNoclipEnabled=false;
            requirements.Booleans.Noclip=false;
            requirements.Booleans.isBuying=false;
            functions.Teleport(CFrame.new(oldpos.p));
            functions.notify('Error','Item Not Found!',4);
            return false;
        end;
        if i==1 then
            pcall(function()
                requirements.LP.Character.HumanoidRootPart.CFrame=CFrame.new(itemToBuy.Main.CFrame.p+Vector3.new(5,0,5));
                wait(.05)
            end);
        end;
        requirements.connections.buyCheck=workspace.PlayerModels.ChildAdded:Connect(function(b)
            local owner= b:WaitForChild('Owner',60);
            if owner.Value==requirements.LP then 
                requirements.connections.buyCheck:Disconnect();
                requirements.connections.buyCheck=b;
            end;
        end);
        game.ReplicatedStorage.TestPing:InvokeServer();
        spawnf(function()
            local start = tick()
            repeat game:GetService('RunService').Heartbeat:wait()
                requirements.remotes.clientRequestOwnership:FireServer(itemToBuy);
                requirements.remotes.clientIsDragging:FireServer(itemToBuy);
                itemToBuy:SetPrimaryPartCFrame(Counter.CFrame+Vector3.new(0,.1,0));
            until tick()-start > 0.13
        end);
        spawnf(function()
            repeat functions.buyItem(itemToBuy)game:GetService'RunService'.Heartbeat:wait()until typeof(requirements.connections.buyCheck)=='Instance';
        end);
        repeat game:GetService'RunService'.Heartbeat:wait()until typeof(requirements.connections.buyCheck)=='Instance';
        spawnf(function()
            local start = tick()
            repeat game:GetService('RunService').Heartbeat:wait()
                requirements.remotes.clientRequestOwnership:FireServer(itemToBuy);
                requirements.remotes.clientIsDragging:FireServer(itemToBuy);
                itemToBuy:SetPrimaryPartCFrame(CFrame.new(oldpos.p+Vector3.new(4,0,4)));
            until tick()-start > 0.13
            spawn(function()
                itemToBuy:SetPrimaryPartCFrame(CFrame.new(oldpos.p+Vector3.new(4,0,4)));
            end)
            --game.ReplicatedStorage.PlaceStructure.ClientPlacedStructure:FireServer(nil, CFrame.new(oldpos.p+Vector3.new(4,0,4)), requirements.LP, nil, requirements.connections.buyCheck, true)
        end);
    end;
    functions.Teleport(CFrame.new(oldpos.p));
    requirements.ConfigSetup.oldNoclipEnabled=false;
    requirements.Booleans.Noclip=false;
    requirements.Booleans.isBuying=false;
    return true;
end;

functions.getAllItems=function()
    local tableList={'Rukiryaxe'};
    for _,v in next,workspace.Stores:GetChildren()do
        if v.Name == 'ShopItems' then 
            for _,k in pairs(v:GetChildren())do
                if not table.find(tableList,tostring(k))then 
                    table.insert(tableList,tostring(k));
                end;
            end;
        end;
    end;
    return tableList;
end;
functions.getAllItems();

functions.bringTree=function(Tree,Quantity)
    if not functions.findSelectedTree(Tree)then 
        functions.notify('Error','No Tree Found',4);
        return;
    end;
    if not functions.getBestAxe()then 
        functions.notify('错误','你需要斧头',4);
        return;
    end;
    if Tree=='LoneCave'then
        if functions.getBestAxe().ToolName.Value~='EndTimesAxe'then
            if requirements.connections.bringTree then 
                requirements.connections.bringTree:Disconnect();
                requirements.connections.bringTree=nil;
            end;
            requirements.ConfigSetup.oldNoclipEnabled=false;
            requirements.Booleans.Noclip=false;
            if requirements.connections.chopTree then 
                requirements.connections.chopTree:Disconnect();
                requirements.connections.chopTree=nil;
            end;
            functions.notify('祖先','你需要末日斧头a',4);
            return;
        end;
    end;
    local oldPos=requirements.LP.Character.HumanoidRootPart.CFrame;
    for i=1,Quantity do
        if not requirements.Booleans.isLoopBringTreeEnabled then
            if requirements.connections.bringTree then 
                requirements.connections.bringTree:Disconnect();
                requirements.connections.bringTree=nil;
            end;
            requirements.ConfigSetup.oldNoclipEnabled=false;
            requirements.Booleans.Noclip=false;
            if requirements.connections.chopTree then 
                requirements.connections.chopTree:Disconnect();
                requirements.connections.chopTree=nil;
            end;
            functions.Teleport(CFrame.new(oldPos.p));
            functions.notify('Ancestor','Bring Tree Aborted',4);
            return
        end;
        local treeToCut=functions.findSelectedTree(requirements.Strings.selectedTree);
        if not treeToCut then 
            if requirements.connections.bringTree then 
                requirements.connections.bringTree:Disconnect();
                requirements.connections.bringTree=nil;
            end;
            requirements.ConfigSetup.oldNoclipEnabled=false;
            requirements.Booleans.Noclip=false;
            if requirements.connections.chopTree then 
                requirements.connections.chopTree:Disconnect();
                requirements.connections.chopTree=nil;
            end;
            functions.Teleport(CFrame.new(oldPos.p));
            functions.notify('Error','No Tree Found!',4);
            return;
        end;
        requirements.ConfigSetup.oldNoclipEnabled=true;
        requirements.Booleans.Noclip=true;
        functions.Teleport(CFrame.new(treeToCut.CFrame.p+Vector3.new(2,0,2)));
        if Tree=='LoneCave'then 
            requirements.connections.LoneCaveAxeDetection=workspace.PlayerModels.ChildAdded:Connect(function(b)
            if requirements.Booleans.treeIsCut==true then 
                requirements.connections.LoneCaveAxeDetection:Disconnect();
                requirements.connections.LoneCaveAxeDetection=nil;
            end;
            local Owner,ToolName=b:WaitForChild('Owner'),b:WaitForChild('ToolName')
            if tostring(Owner.Value)==tostring(requirements.LP)and tostring(ToolName.Value)=='EndTimesAxe'then 
                    axe=b;
                end;
            end);
            requirements.connections.LoneCaveCharacterAddedDetection=requirements.LP.CharacterAdded:Connect(function()
                if requirements.Booleans.treeIsCut==true then 
                    requirements.connections.LoneCaveCharacterAddedDetection:Disconnect();
                    requirements.connections.LoneCaveCharacterAddedDetection=nil;
                end;
                repeat wait()until requirements.LP.Character and requirements.LP.Character:FindFirstChild('Humanoid');
                functions.Teleport(CFrame.new(treeToCut.CFrame.p+Vector3.new(2,0,2)));
                functions.Teleport(CFrame.new(treeToCut.CFrame.p+Vector3.new(2,0,2)));
                game.ReplicatedStorage.Interaction.ClientInteracted:FireServer(axe,'Pick up tool');
            end)
            requirements.connections.LoneCaveDeathDetection=requirements.LP.Character.Humanoid.Died:Connect(function()
                if requirements.Booleans.treeIsCut==true then 
                    requirements.connections.LoneCaveDeathDetection:Disconnect();
                    requirements.connections.LoneCaveDeathDetection=nil;
                end;
                for _,tool in next,requirements.LP.Backpack:children()do 
                    pcall(function()
                        game.ReplicatedStorage.Interaction.ClientInteracted:FireServer(tool,'Drop tool');
                    end);
                end;
            end);
        end;
        requirements.connections.bringTree=requirements.wrkspc.LogModels.ChildAdded:Connect(function(tree)
            tree:WaitForChild('Owner',5)
            if tostring(tree.Owner.Value)==tostring(requirements.LP)and tostring(tree.TreeClass.Value)==tostring(requirements.Strings.selectedTree)then
                pcall(function()
                    requirements.connections.LoneCaveAxeDetection:Disconnect();
                    requirements.connections.LoneCaveCharacterAddedDetection:Disconnect();
                    requirements.connections.LoneCaveDeathDetection:Disconnect();
                end);
                requirements.Booleans.treeIsCut=true;
                for i=1,10 do 
                    requirements.remotes.clientRequestOwnership:FireServer(tree);
                    requirements.remotes.clientIsDragging:FireServer(tree);
                    game:GetService('RunService').Heartbeat:wait();
                end;
                if not tree.PrimaryPart then 
                    tree.PrimaryPart=tree:FindFirstChild'WoodSection';
                end;
                tree:SetPrimaryPartCFrame(CFrame.new(oldPos.p));
            end;
        end);
        repeat wait()pcall(function()if functions.getBestAxe()and treeToCut and requirements.LP.Character and requirements.LP.Character:FindFirstChild'Humanoid'then functions.chopTree(treeToCut.Parent.CutEvent)end end)until requirements.Booleans.treeIsCut;
        game:GetService('RunService').Heartbeat:wait();
        requirements.Booleans.treeIsCut=false;
        if requirements.connections.bringTree then 
            requirements.connections.bringTree:Disconnect();
            requirements.connections.bringTree=nil;
        end;
    end;
    functions.Teleport(CFrame.new(oldPos.p+Vector3.new(4,0,0)));
    functions.notify('Ancestor','完成',4)
    requirements.ConfigSetup.oldNoclipEnabled=false;
    requirements.Booleans.Noclip=false;
end;

functions.whisperToTarget=function()
    if requirements.Booleans.alertTarget then 
        if tostring(requirements.Strings.BaseRecipient)==tostring(requirements.LP)then return;end;
        requirements.remotes.sayMessageRequest:FireServer('/w '..tostring(requirements.Strings.BaseRecipient)..' load your base over my base to claim it! [Powered By Ancestor]','All');
    end;
end;

functions.tellDiscord=function()
    requirements.remotes.sayMessageRequest:FireServer('Ancestor and the tag is 4476','All');
end;

functions.unloadSlot=function()
    if not requirements.remotes.clientMayLoad:InvokeServer(requirements.LP) then
        functions.notify('Error', '加载正在冷却', 4);
        repeat
            wait(5);
        until requirements.remotes.clientMayLoad:InvokeServer(requirements.LP);
    end
    spawn(function()requirements.remotes.requestLoad:InvokeServer(-1,requirements.LP);end);
    wait(3)
    game:GetService("ReplicatedStorage").LoadSaveRequests.GetTickCut:InvokeServer();
    repeat wait()until requirements.LP.CurrentlySavingOrLoading.Value==false;
    requirements.LP.CurrentSaveSlot.Value=-1;
    functions.notify('Ancestor','Unloaded Selected Slot Succesfully!',4);
end;

functions.DupeBaseToServer=function()
    requirements.Booleans.DonatingBase=true;
    local whitelistedPlots={
        '68, 0, -189, 1, 0, 0, 0, 1, 0, 0, 0, 1',
        '275, 0, -512, 1, 0, 0, 0, 1, 0, 0, 0, 1',
    };
    local slotToDupe=requirements.LP.CurrentSaveSlot.Value
    local Plot=functions.getPlayersBase(tostring(requirements.LP));
    if Plot then
        functions.unloadSlot();
        repeat wait()until requirements.LP.CurrentSaveSlot.Value==-1;
        wait(1)
        functions.notify('Ancestor','Loading plot...',4);
        functions.donateBaseAutoload(slotToDupe);
        repeat wait()until requirements.LP.CurrentlySavingOrLoading.Value==true;
        repeat wait()until requirements.LP.CurrentlySavingOrLoading.Value==false;
    end;
    functions.notify('Ancestor','Please wait. This will take a minute or two',30)
    local Plots=functions.getPlots();
    functions.Teleport(CFrame.new(Plots[1].OriginSquare.CFrame.p+Vector3.new(0,10,0)))
    functions.notify('Test','Worked')
    repeat task.wait()
        requirements.remotes.clientIsDragging:FireServer(Plots[1]);
    until Plots[1].Owner.Value==requirements.LP
    if tostring(requirements.Strings.BaseRecipient)==tostring(requirements.LP)then
        functions.SelfWl(true);
    end;
    repeat wait()until Plots[1].Owner.Value==requirements.LP;
    functions.LoadSelectedSlot(slotToDupe);
    repeat wait()until requirements.LP.CurrentlySavingOrLoading.Value==false;
    functions.SelfWl(false);
    requirements.Booleans.DonatingBase=false;
    return true;
end;
functions.DupeBaseToPlayer=function(plr)
    functions.DupeBaseToServer();--?HUH
    return true;
end;

functions.DonatePlotToPlayer=function()
    if not requirements.Booleans.DisableSlotSaving then 
        functions.notify('Error','你必须先保存土地',4);
        return;
    end;
    if requirements.Booleans.DonatingBase then 
        functions.notify('Error','已经准备复制了',4);
        return;
    end;
    local success=functions.PlotLogic();
    if success then 
        local newSuccess=functions.DupeBaseToPlayer();
        if newSuccess then 
            requirements.remotes.clientSetListPlayer:InvokeServer(requirements.LP.WhitelistFolder,requirements.Players:FindFirstChild(requirements.Strings.BaseRecipient),true);
            functions.notify('Ancestor','Automatically Whitelisted '..tostring(requirements.Strings.BaseRecipient),4);
            functions.whisperToTarget();
            functions.notify('Ancestor','Successfully donated base to '..tostring(requirements.Strings.BaseRecipient),4);
            requirements.Booleans.DonatingBase=false;
        end;
    end;
end;

functions.HardDragger=function()
    requirements.connections.hardDragger=workspace.ChildAdded:Connect(function(b)
        if b.Name=='Dragger'then
            if requirements.ConfigSetup.hardDragger then 
                b.BodyPosition.MaxForce=Vector3.new(90000,90000,90000);
                b.BodyGyro.MaxTorque=Vector3.new(9000,9000,9000);
                b.BodyPosition.P=100500;
                b.BodyGyro.P=1400;
                b.BodyPosition.D=1040;
            else
                b.BodyPosition.MaxForce=Vector3.new(15000, 15000, 15000);
                b.BodyGyro.MaxTorque=Vector3.new(300, 300, 300);
                b.BodyPosition.P=10500;
            end;
        end;
    end);
end;
functions.HardDragger();

functions.NoWaterFloat=function()
    local old=getsenv(requirements.LP.PlayerGui.Scripts.CharacterFloat).isInWater;
    getsenv(requirements.LP.PlayerGui.Scripts.CharacterFloat).isInWater=function(...)
        if not requirements.ConfigSetup.WaterFloat then 
            requirements.LP.PlayerGui.UnderwaterOverlay.Enabled=false;
            return 1
        else 
            requirements.LP.PlayerGui.UnderwaterOverlay.Enabled=true;
            return old(...);
        end;
    end;
end;
functions.NoWaterFloat();


functions.ClaimAllFreePlots=function()
    if requirements.LP.CurrentSaveSlot.Value~= -1 then 
        functions.notify('Error', 'You can not use this feature whilst having your plot loaded!',4);
        return;
    end;
    if not requirements.Booleans.DisableSlotSaving then 
        functions.notify('Error', 'You MUST have disable slot saving enabled!',4);
        return;
    end;
    for _,v in next,requirements.wrkspc.Properties:children()do
        if v:FindFirstChild('OriginSquare')and v.Owner.Value==nil then
            functions.Teleport(CFrame.new(v.OriginSquare.CFrame.p));
            repeat task.wait()
                requirements.remotes.clientIsDragging:FireServer(v);
            until v.Owner.Value==requirements.LP
        end;
    end;
    functions.notify('Ancestor','Claimed All Plots!',4);
end;


functions.OwnerCheck=function(item)
    if item:FindFirstChild('Owner')then
        return tostring(item.Owner.Value);
    end;
end;

functions.CountItem=function(item)
    local amount=0;
    for i,v in next,workspace.PlayerModels:children()do
        if v:IsA('Model')and functions.OwnerCheck(v)==tostring(requirements.LP)then 
            local itemName=v:FindFirstChild('ToolName')or v:FindFirstChild('ItemName')or v:FindFirstChild('PurchasedBoxItemName');
            if itemName.Value==item then 
                amount=amount+1 
            end;
        end;
    end;
    return amount;
end;

functions.WhitelistCheck=function(player)
    return requirements.remotes.clientIsWhitelisted:InvokeServer(player)==true;
end;

functions.TriggerAllPressurePlates=function()
    local found=false;
    for _,PressurePlate in pairs (game.Workspace.PlayerModels:children()) do
        if PressurePlate:FindFirstChild'ItemName'and PressurePlate.ItemName.Value=='PressurePlate'then
            if PressurePlate.Output.BrickColor~=BrickColor.new'Electric blue'then
                repeat wait()requirements.LP.Character.HumanoidRootPart.CFrame=CFrame.new(PressurePlate.Plate.CFrame.p+Vector3.new(0,.3,0));until PressurePlate.Output.BrickColor==BrickColor.new'Electric blue'or not PressurePlate;
                found=true;
            end;
        end;
    end;
    if not found then
        functions.notify('Ancestor','No Pressure Plates Located',4);
        return;
    end;
end;

functions.AncestorDetection=function()
    if functions.isPlayerAdmin(requirements.LP)then 
        functions.notify('Ancestor','Authorised Administrator Detected');
        local ancestorUsers={};
        spawn(function()
            while wait(2)do 
                for i,v in next,game.Players:children()do 
                    if functions.WhitelistCheck(v)then 
                        if v~=requirements.LP and not table.find(ancestorUsers,v)then
                            functions.notify('Ancestor',tostring(v)..' 给了你白名单',4);
                            table.insert(ancestorUsers,v);
                        end;
                    end;
                end;
            end;
        end);
    end;
end;
spawn(function()
    functions.AncestorDetection();
end)

functions.FarAxeEquip=function()
    local done=false;
    if requirements.connections.farAxeEquip==nil then 
        functions.notify('Ancestor','点击一把斧头',4);
        requirements.connections.farAxeEquip=requirements.Mouse.Button1Down:connect(function()
            local target=requirements.Mouse.Target;
            if target.Parent:IsA('Model')and target.Parent:FindFirstChild('ToolName')then 
                if functions.OwnerCheck(target.Parent)==tostring(requirements.LP) or functions.WhitelistCheck(target.Parent.Owner.Value)then 
                    requirements.remotes.clientInteracted:FireServer(target.Parent,'Pick up tool');
                    done=true;
                end;
            end;
        end);
        repeat wait()until done; 
        functions.notify('Ancestor','成功装备',4);
        if requirements.connections.farAxeEquip then 
            requirements.connections.farAxeEquip:Disconnect();
            requirements.connections.farAxeEquip=nil;
        end;else
        functions.notify('Error','Already Activated!',4);
    end;
end;

functions.burnAllShopItems=function()
    local oldPos=requirements.LP.Character.HumanoidRootPart.CFrame
    for _,Store in next,workspace.Stores:GetChildren()do 
        for _,Model in next,Store:GetChildren()do
            local thingToBurn=Model:FindFirstChild'Main'or Model:FindFirstChild'WoodSection';
            if thingToBurn then
                spawnf(function()
                    functions.Teleport(CFrame.new(thingToBurn.CFrame.p+Vector3.new(0,10,0)));
                    requirements.remotes.clientIsDragging:FireServer(Model);
                    local lava=workspace['Region_Volcano'].Lava.Lava
                    for i=1,12 do
                        requirements.remotes.clientIsDragging:FireServer(Model);
                        firetouchinterest(thingToBurn,lava,0);
                        firetouchinterest(thingToBurn,lava,1);
                    end;
                    wait();
                end);
            end;
        end;
    end;
    functions.Teleport(CFrame.new(oldPos.p));
end;

functions.StopSpectating=function()
    requirements.wrkspc.CurrentCamera.CameraSubject=requirements.LP.Character.Humanoid;
    pcall(function()
        requirements.connections.spectateAdded:Disconnect();
        requirements.connections.spectateAdded=nil;
    end);
    pcall(function()
        requirements.connections.spectateAddedLocal:Disconnect();
        requirements.connections.spectateAddedLocal=nil;
    end);
    pcall(function()
        requirements.connections.playerLeft:Disconnect();
        requirements.connections.playerLeft=nil;
    end);
end;
functions.manageTarget=function(option,plr)
    if plr==tostring(requirements.LP) then 
        functions.notify('Error','Select Another Player',4);
        return;
    end;
    if requirements.Players:FindFirstChild(tostring(plr)).Character.Humanoid.Sit then 
        functions.notify('Error','Target Is Sat Down',4);
        return;
    end;
    if option~='KickPlayer'and requirements.Players:FindFirstChild(tostring(plr)).Character:FindFirstChildOfClass'Tool'then 
        requirements.Players:FindFirstChild(tostring(plr)).Character:FindFirstChildOfClass'Tool':Destroy();
    end;
    if requirements.Booleans.dupeInventory then 
        requirements.Booleans.axeDuping=true;
        functions.DupeInventory(1);
        requirements.Booleans.axeDuping=false;
    end;
    local oldPos=requirements.LP.Character.HumanoidRootPart.Position
    if not functions.getBestAxe()then 
        if functions.checkModel('BasicHatchet','Model')then 
            pcall(function()
                requirements.remotes.clientInteracted:FireServer(functions.checkModel('BasicHatchet','Model'),'Open box');
            end)
            requirements.remotes.clientInteracted:FireServer(functions.checkModel('BasicHatchet','Model'),'Pick up tool');
            repeat wait()until functions.getBestAxe()
        end;
        if not functions.getBestAxe()then 
            spawnf(function()
                functions.AutoBuyItem('BasicHatchet',1)
            end);
            local connection,connection2;
            connection=requirements.wrkspc.PlayerModels.ChildAdded:Connect(function(b)
                if tostring(b)=='BasicHatchet Purchased by '..tostring(requirements.LP)then 
                    requirements.remotes.clientInteracted:FireServer(b,'Open box');
                    connection:Disconnect();
                end;
            end);
            connection2=requirements.wrkspc.PlayerModels.ChildAdded:Connect(function(b)
                local ToolName=b:WaitForChild'ToolName'
                if tostring(ToolName.Value)=='BasicHatchet'and tostring(b.Owner.Value)==tostring(requirements.LP)then 
                    requirements.remotes.clientInteracted:FireServer(b,'Pick up tool');
                    connection2:Disconnect();
                end;
            end)
            if requirements.LP.leaderstats.Money.Value<12 then 
                pcall(function()
                    connection:Disconnect();
                    connection2:Disconnect();
                end);
                return;
            end;
            repeat wait()until functions.getBestAxe();
        end;
    end;
    repeat wait()until functions.getBestAxe();
    local axeToDestroy=functions.getBestAxe();
    requirements.Booleans.managingTarget=true;
    requirements.LP.Character.Humanoid:EquipTool(functions.getBestAxe());
    repeat wait()until requirements.LP.Character:FindFirstChildOfClass'Tool';
    requirements.LP.Character.Humanoid.Name='AncestorV3'
    local HClone = requirements.LP.Character.AncestorV3:Clone()
    HClone.Name = 'Humanoid'
    HClone.Parent = requirements.LP.Character
    repeat game:GetService'RunService'.Stepped:Wait()HClone:EquipTool(functions.getBestAxe());until requirements.LP.Character:FindFirstChildOfClass'Tool';
    requirements.LP.Character.AncestorV3:Destroy()
    local connection;
    connection=workspace.PlayerModels.ChildAdded:Connect(function(b)
        local Owner=b:WaitForChild'Owner'
        connection:Disconnect();
        Owner.Value=requirements.Players:FindFirstChild(plr);
    end);
    if option=='KickPlayer'then
       functions.getBestAxe().Owner:Destroy()--:Destroy();
    end;
    requirements.wrkspc.CurrentCamera.CameraSubject=requirements.Players:FindFirstChild(plr).Character.Humanoid
    requirements.ConfigSetup.oldNoclipEnabled=true;
    requirements.Booleans.Noclip=true;
    if option=='KillPlayer'then
        local CFrame1=CFrame.new(0,-100,0)
        functions.Teleport(CFrame1);
        repeat wait()until (requirements.LP.Character.HumanoidRootPart.CFrame.p-CFrame1.p).magnitude<40;
    end;
    if option=='HardKillPlayer'then 
        local CFrame1=CFrame.new(-1675, 280, 1295)
        functions.Teleport(CFrame1);
        repeat wait()until (requirements.LP.Character.HumanoidRootPart.CFrame.p-CFrame1.p).magnitude<40;
    end;
    repeat game:GetService'RunService'.Stepped:wait()
        if requirements.LP.Character:FindFirstChildOfClass'Tool'then 
            requirements.Players:FindFirstChild(tostring(plr)).Character.HumanoidRootPart.CFrame=requirements.LP.Character:FindFirstChildOfClass('Tool'):FindFirstChildOfClass('Part').CFrame;
        end;
    until not requirements.LP.Character:FindFirstChildOfClass'Tool';
    repeat wait()until requirements.Players:FindFirstChild(tostring(plr)).Character:FindFirstChildOfClass'Tool';
    wait(.4)
    pcall(function()
    requirements.remotes.destroyStructure:FireServer(axeToDestroy)
    end);
    functions.KillPlayer();
    requirements.LP.CharacterAdded:wait();
    functions.Teleport(CFrame.new(oldPos))
    requirements.ConfigSetup.oldNoclipEnabled=false;
    requirements.Booleans.managingTarget=false;
    requirements.Booleans.Noclip=false;
    return true;
end;
functions.getLogs=function()
    local logList={};
    for _,log in next,requirements.wrkspc.LogModels:children()do 
        if log:FindFirstChild('Owner')and log.Owner.Value==requirements.LP and not table.find(logList,log)then 
            table.insert(logList,log)
        end;
    end;
    return logList;
end;

functions.fireAllScoobis=function()
    for _,Scoobis in next,workspace.PlayerModels:GetChildren()do 
        if tostring(Scoobis)=='Scoobis'then 
            game:GetService("ReplicatedStorage").Interaction.RemoteProxy:FireServer(Scoobis:FindFirstChildOfClass'BindableEvent');
        end;
    end;
end;
functions.fireAllBrash=function()
    for _,Painting in next,workspace.PlayerModels:GetChildren()do 
        if Painting:FindFirstChild'ItemName'and tostring(Painting.ItemName.Value)=='Painting4'then 
            game:GetService("ReplicatedStorage").Interaction.RemoteProxy:FireServer(Painting:FindFirstChildOfClass'BindableEvent');
        end;
    end;
end;

functions.getPlanks=function()
    local plankList={};
    for _,plank in next,requirements.wrkspc.PlayerModels:children()do 
        if  plank:FindFirstChild('WoodSection')and plank:FindFirstChild('Owner')and plank.Owner.Value==requirements.LP and not table.find(plankList,plank)then 
            table.insert(plankList,plank)
        end;
    end;
    return plankList;
end;

functions.givePlayerBTools=function()
    if requirements.LP.Backpack:FindFirstChildOfClass'HopperBin'then return end;
    for index=1,4 do
        Instance.new('HopperBin',requirements.LP.Backpack).BinType=index
    end;
end;

functions.tpPlanksToPlayer=function()
    local logFolder=functions.getPlanks();
    local oldPos=requirements.LP.Character.HumanoidRootPart.CFrame;
    for _,log in next,logFolder do 
        if log:FindFirstChild('WoodSection')then 
            if (requirements.LP.Character.HumanoidRootPart.CFrame.p-log.WoodSection.CFrame.p).magnitude>40 then
                functions.Teleport(CFrame.new(log.WoodSection.CFrame.p+Vector3.new(2,0,2)));
            end;
            spawn(function()
                for i=1,20 do
                    requirements.remotes.clientRequestOwnership:FireServer(log);
                    requirements.remotes.clientIsDragging:FireServer(log);
                    wait();
                end;
            end)
            wait(0.18)
            if not log.PrimaryPart then
                log.PrimaryPart=log.WoodSection;
            end;
            log:SetPrimaryPartCFrame(CFrame.new(oldPos.p));
        end;
    end; 
    functions.Teleport(oldPos);
end;

functions.tpLogsToPlayer=function()
    local logFolder=functions.getLogs();
    local oldPos=requirements.LP.Character.HumanoidRootPart.CFrame;
    for _,log in next,logFolder do 
        if log:FindFirstChild('WoodSection')then 
            if (requirements.LP.Character.HumanoidRootPart.CFrame.p-log.WoodSection.CFrame.p).magnitude>40 then
                functions.Teleport(CFrame.new(log.WoodSection.CFrame.p+Vector3.new(2,0,2)));
            end;
            spawn(function()
                for i=1,20 do
                    requirements.remotes.clientRequestOwnership:FireServer(log);
                    requirements.remotes.clientIsDragging:FireServer(log);
                    wait();
                end;
            end)
            wait(0.18)
            if not log.PrimaryPart then
                log.PrimaryPart=log.WoodSection;
            end;
            log:SetPrimaryPartCFrame(CFrame.new(oldPos.p));
        end;
    end; 
    functions.Teleport(oldPos);
end;

functions.getItemsList=function(player)
    local tableList={};
    local Owner=nil;
    if player==nil then 
        Owner=tostring(requirements.LP);
    else 
        Owner=tostring(game.Players[player])
    end
    for _,v in next,workspace.PlayerModels:children()do
        if v:IsA('Model')then 
            local check=v:FindFirstChild('ItemName')or v:FindFirstChild('PurchasedBoxItemName')or v:FindFirstChild'TreeClass'
            if check and v:FindFirstChild('Owner')and tostring(v.Owner.Value)==Owner and not table.find(tableList,check.Value)then
                table.insert(tableList,check.Value)
            end;
        end;
    end;
    return tableList;
end;
functions.getItemsList();

functions.getItemsListType=function(player)
    local tableList={};
    local Owner=nil;
    if player==nil then 
        Owner=tostring(requirements.LP);
    else 
        Owner=tostring(game.Players[player])
    end
    for _,v in next,workspace.PlayerModels:children()do
        if v:IsA('Model')then 
            local check2=v:FindFirstChild'Type';
            if check2 and not table.find(tableList,check2.Value)then
                table.insert(tableList,check2.Value);
            end;
        end;
    end;
    return tableList;
end;
functions.getItemsListType();

functions.CheckWhitelist=function(Value)
    return tostring(Value)==tostring(requirements.LP.Name)or game.ReplicatedStorage.Interaction.ClientIsWhitelisted:InvokeServer(Value)==true;
end;

functions.getPos=function()
    initialPos=requirements.LP.Character.HumanoidRootPart.CFrame
    for i,v in pairs(workspace.Properties:GetChildren()) do
        for a,b in pairs(v:GetChildren()) do 
            local OriginCFrame = v:FindFirstChild('OriginSquare').CFrame
            if math.abs(initialPos.Z-OriginCFrame.Z) < 100 and math.abs(initialPos.X-OriginCFrame.X) < 100 and v.Owner.Value ~= nil then
                if functions.CheckWhitelist(v.Owner.Value)then 
                    return true;
                else
                    return false,'Not Whitelisted';
                end
            end
        end
    end
    return false,'Not On A Plot';
end;

functions.wipeBase=function()
    for _,item in next,workspace.PlayerModels:children()do 
        if item:IsA('Model')and item:FindFirstChild('Owner')and item.Owner.Value==requirements.LP and item:FindFirstChild('Type')and item.Type.Value==tostring(requirements.Strings.itemTypeToWipe) then 
            game:GetService('ReplicatedStorage').Interaction.DestroyStructure:FireServer(item)
        end;
    end;
end;

functions.grayPaintTool=function()
    requirements.connections.grayPaintTool=requirements.Mouse.Button1Down:Connect(function()
        local target=requirements.Mouse.Target;
        if target and target.Parent:FindFirstChild('Type')and target.Parent.Type.Value=='Blueprint'and target.Parent:FindFirstChild('BuildDependentWood')and target.Parent:FindFirstChild('Owner')then 
            requirements.remotes.clientPlacedStructure:FireServer(tostring(target.Parent.ItemName.Value), target.Parent.PrimaryPart.CFrame, requirements.LP, nil, target.Parent, true)
        end;
    end);
end;

functions.baseDropItem=function(item,player,amountg,customPos)
    local amount=0
    local Owner=nil;
    local oldPos=requirements.LP.Character.HumanoidRootPart.CFrame;
    if customPos then 
        oldPos=customPos;
    end;
    if player==nil then 
        Owner=tostring(requirements.LP);
    else
        Owner=tostring(game.Players[player])
    end
    local success=functions.getPos();
    for _,v in next,workspace.PlayerModels:children()do
        if v:IsA('Model')then 
            local check=v:FindFirstChild('ItemName')or v:FindFirstChild('PurchasedBoxItemName')or v:FindFirstChild('TreeClass');
            local check2=v:FindFirstChild'Type'
            if check and check.Value==item and v:FindFirstChild('Owner')and tostring(v.Owner.Value)==Owner or check2 and check2.Value==item and v:FindFirstChild('Owner')and tostring(v.Owner.Value)==Owner  then
                amount=amount+1
                if success then
                    if check.Name=='TreeClass'or requirements.LP.Character.Humanoid.FloorMaterial~=Enum.Material.Concrete then 
                        success=false;
                    end;
                    if not workspace:FindFirstChild('AncestorV3BasedropCord')then
                        game.ReplicatedStorage.PlaceStructure.ClientPlacedStructure:FireServer(nil, CFrame.new(requirements.LP.Character.HumanoidRootPart.CFrame.p),requirements.LP, nil, v, true)
                    else
                        game.ReplicatedStorage.PlaceStructure.ClientPlacedStructure:FireServer(nil, CFrame.new(workspace:FindFirstChild('AncestorV3BasedropCord').CFrame.p),requirements.LP, nil, v, true);
                    end;
                end;
                if not success then
                    main=v:FindFirstChild'Main';
                    if not main then 
                        v.PrimaryPart=v:FindFirstChild'WoodSection';
                        main=v.PrimaryPart;
                    end;
                    if (requirements.LP.Character.HumanoidRootPart.CFrame.p-main.CFrame.p).magnitude>30 then 
                        functions.Teleport(CFrame.new(main.CFrame.p+Vector3.new(0,3,2)))
                    end
                    for i=1,14 do 
                        requirements.remotes.clientIsDragging:FireServer(v);
                        requirements.remotes.clientIsDragging:FireServer(v);
                        requirements.remotes.clientIsDragging:FireServer(v);
                        requirements.remotes.clientRequestOwnership:FireServer(v);
                        game:GetService('RunService').Heartbeat:wait();
                    end;
                    if not workspace:FindFirstChild('AncestorV3BasedropCord')then
                        v:SetPrimaryPartCFrame(oldPos);
                    else
                        v:SetPrimaryPartCFrame(workspace:FindFirstChild('AncestorV3BasedropCord').CFrame);
                    end;
                end;
                if amount==amountg and amountg~=0 and not customPos then 
                    functions.Teleport(CFrame.new(oldPos.p))
                    functions.notify('Ancestor',tostring(amount),4);
                    return;
                end;
            end;
        end;
    end;
    if amount~=0 then 
        if workspace:FindFirstChild'AncestorV3BasedropCord'then 
            functions.Teleport(CFrame.new(workspace:FindFirstChild'AncestorV3BasedropCord'.CFrame.p));
        elseif not customPos then
            functions.Teleport(CFrame.new(oldPos.p));
        end;
        functions.notify('Ancestor',tostring(amount),4);
    end;
    return false;
end

functions.carInitiate=function()
    requirements.connections.carInitiate=requirements.LP.CharacterAdded:Connect(function()
    repeat wait()until requirements.LP.Character and requirements.LP.Character:FindFirstChild('Humanoid')
        functions.carFallBack();
    end)
end;

functions.carFallBack=function()
requirements.connections.carFallBack=requirements.LP.Character.Humanoid:GetPropertyChangedSignal('SeatPart'):Connect(function()
    functions.modifyCar();
    end);
end;

functions.modifyCar=function()
    pcall(function()
        if requirements.ConfigSetup.carVisualEffects then
            local car=requirements.LP.Character.Humanoid.SeatPart.Parent;
            for _,v in next,car.PaintParts:GetDescendants()do 
                if v:IsA('BasePart')then 
                    v.Material=Enum.Material[requirements.ConfigSetup.carMaterial];
                    v.BrickColor=BrickColor.new(Color3.fromRGB(requirements.ConfigSetup.carColorR,requirements.ConfigSetup.carColorG,requirements.ConfigSetup.carColorB));
                end;
            end;
        end;
    end);
end;

functions.getButton=function(Text)
    for _,ScrollingFrame in next,game.CoreGui.Ancestor.MainBody:GetChildren()do 
        if ScrollingFrame:FindFirstChild(tostring(Text))then 
            return ScrollingFrame;
        end;
    end;
end;

functions.makeClock=function(mode)
    if game.CoreGui:FindFirstChild'Stats'then 
        game.CoreGui:FindFirstChild'Stats':remove();
    end;
    if mode=='Dark'then 
        color1=Color3.fromRGB(15,15,15);
        color2=Color3.fromRGB(255,255,255);
    elseif mode=='Light'then 
        color1=Color3.fromRGB(255,255,255);
        color2=Color3.fromRGB(0,0,0);
    end;
    local Stats=Instance.new('ScreenGui');
    local FPSFrame=Instance.new('Frame');
    local UICorner=Instance.new('UICorner');
    local f1=Instance.new('Frame');
    local f2=Instance.new('Frame');
    local FPS=Instance.new('TextLabel');
    local TimeFrame=Instance.new('Frame');
    local UICorner_2=Instance.new('UICorner');
    local f1_2=Instance.new('Frame');
    local f2_2=Instance.new('Frame');
    local Time=Instance.new('TextLabel');
    local DateFrame=Instance.new('Frame');
    local Date=Instance.new('TextLabel');
    local f2_3=Instance.new('Frame');
    local f1_3=Instance.new('Frame');
    local UICorner_3=Instance.new('UICorner');
    UICorner_3.Name='UICorner';
    UICorner_3.Parent=DateFrame;
    local connection,connection2
    UICorner_3.CornerRadius=UDim.new(0,6)local s,f,m,t,l=tick(),{},math.fmod,tonumber;
    local function o(n)return n..(({'st','nd','rd'})[m((m((n+90),100)-10),10)]or'th')end;
    local connection=game:GetService'RunService'.Heartbeat:connect(function()
        Time.Text=os.date'%I:%M:%S'Date.Text=os.date'%a, %b '..o(t(os.date'%d'))
        l=tick()for i=#f,1,-1 do f[i+1]=(f[i]>=l-1)and f[i]or nil;end;
        f[1]=l;FPS.Text=math.floor((tick()-s>=1 and#f)or(#f/(tick()-s)));
    end)
    connection2=game.CoreGui.ChildRemoved:Connect(function(b)
        if b.Name=='Stats'then 
            connection:Disconnect();
            connection=nil;
            connection2:Disconnect();
            connection2=nil;
        end;
    end)
end;
if requirements.ConfigSetup.uiDarkMode then
    functions.makeClock('Dark')
else
    functions.makeClock('Light');
end;

functions.uiMode=function(mode)   
    local lp=requirements.LP
    local color1,color2
    function createCorner(parent)
        if not parent:FindFirstChild('UICorner')then
            local uic=Instance.new('UICorner',parent);
            uic.CornerRadius=UDim.new(0,5)
        end;
    end;

    if mode=='Light'then 
        color1=Color3.fromRGB(255,255,255);
        color2=Color3.fromRGB(0,0,0);
        color3=Color3.fromRGB(220, 220, 220)
    elseif mode=='Dark'then 
        color1=Color3.fromRGB(15,15,15)
        color2=Color3.fromRGB(255,255,255);
        color3=Color3.fromRGB(15,15,15)
    end;
    --Open Menu Button
    local openMenu=lp.PlayerGui.MenuGUI.Open
    
    createCorner(openMenu)
    openMenu.BackgroundColor3=color1
    openMenu.TextLabel.TextColor3=color2
    createCorner(openMenu.DropShadow)
    
    --Main Menu 
    local mainMenu=lp.PlayerGui.MenuGUI.Menu.Main
    local mainMenuQuit=mainMenu.Parent.Quit
    
    mainMenu.BackgroundColor3=color1
    for i,v in next,mainMenu:GetDescendants()do 
        if v:IsA('TextLabel')then 
            if v.Name~='DropShadow'then
                v.TextColor3=color2;
                v.BackgroundColor3=color1;
                createCorner(v)
                v.TextColor3=color2;
            elseif v.Name=='DropShadow'then
                createCorner(v)
                v.TextColor3=color1;
            end;
        end;
        if v:IsA('TextButton')then 
            createCorner(v)
            v.BackgroundColor3=color1;
        end;
    end;
    
    createCorner(mainMenuQuit);
    mainMenuQuit.BackgroundColor3=color1;
    mainMenuQuit.TextLabel.TextColor3=color2;
    createCorner(mainMenuQuit.DropShadow);createCorner(mainMenu);createCorner(mainMenu.DropShadow);
    
    --Load Menu 
    local loadMenu=lp.PlayerGui.LoadSaveGUI;
    loadMenu.SlotList.Main.BackgroundColor3=color1;
    for _,textLabel in next, loadMenu.SlotList.Main:GetDescendants()do 
        if textLabel:IsA('TextLabel')then
            if textLabel.Name=='IsCurrentSlot'then 
                textLabel.TextStrokeColor3=color1;
            end;
            if textLabel.Name=='DropShadow'then 
                textLabel.TextColor3=color1;
            else
            createCorner(textLabel)
            textLabel.TextColor3=color2;
        end;
        elseif textLabel:IsA('TextButton')then 
            textLabel.BackgroundColor3=color1;
            createCorner(textLabel)
        end;
    end;
    lp.PlayerGui.PropertyPurchasingGUI.SelectPurchase.Cost.BackgroundColor3=color1
    --Quit
    createCorner(loadMenu.SlotList.Quit)
    loadMenu.SlotList.Quit.BackgroundColor3=color1;
    loadMenu.SlotList.Quit.TextLabel.TextColor3=color2;
    createCorner(loadMenu.SlotList.Quit.DropShadow);
    createCorner(loadMenu.SlotList.Main);createCorner(loadMenu.SlotList.Main.DropShadow)
    --Load Current Slot 
    local slotInfoMain=loadMenu.SlotInfo.Main 
    local progress=loadMenu.Progress
    for _,v in next,progress:GetDescendants()do 
        if v:IsA'Frame' then 
            createCorner(v);
            if v.Name~='DropShadow'then 
                v.BackgroundColor3=color1;
            end;
        end;
    end;
    createCorner(progress.Main.Text);progress.Main.Text.BackgroundColor3=color1;progress.Main.Text.TextColor3=color2
    
    createCorner(slotInfoMain);createCorner(slotInfoMain.DropShadow)
    for _,button in next,slotInfoMain:GetDescendants()do 
        if button:IsA('TextButton')or button:IsA('TextLabel')then 
            button.BackgroundColor3=color1
            button.TextColor3=color2
            createCorner(button);
        end;
    end;
    slotInfoMain.BackgroundColor3=color1
    
    --Load Quit 
    createCorner(slotInfoMain.Parent.Quit)
    slotInfoMain.Parent.Quit.BackgroundColor3=color1;
    slotInfoMain.Parent.Quit.TextLabel.TextColor3=color2;
    createCorner(slotInfoMain.Parent.Quit.DropShadow);
    createCorner(slotInfoMain.Parent.Quit);createCorner(slotInfoMain.Parent.Quit.DropShadow)
    
    --Select Plot
    local selectPlot=lp.PlayerGui.PropertyPurchasingGUI
    for _, v in next,selectPlot:GetDescendants()do 
        if v.ClassName=='Frame'then 
            createCorner(v);
            if v.Name=='DropShadow'then 
                v.BackgroundColor3=Color3.fromRGB(0,0,0)
            else
                v.BackgroundColor3=color1
            end;
        end;
        if v:IsA('TextLabel')or v:IsA'TextButton'then 
            v.TextColor3=color2
            v.BackgroundColor3=color1
            createCorner(v);
        end;
    end;
    --Notice
    local noticeUI=lp.PlayerGui.NoticeGUI.Notice.Main 
    createCorner(noticeUI)
    noticeUI.BackgroundColor3=color1
    for _,v in next,noticeUI:GetDescendants()do 
        if v:IsA('TextButton')or v:IsA('TextLabel')then 
            v.TextColor3=color2
            v.BackgroundColor3=color1
            createCorner(v);
        end;
        if v:IsA('Frame')then 
            createCorner(v)
        end;
    end;
    
    --Money Gui 
    local buyMoney=lp.PlayerGui.BuyMoneyGUI.BuyMoney 
    
    for _,v in next,buyMoney:GetDescendants()do 
        if v:IsA('Frame')then 
            createCorner(v)
            if v.Name~='DropShadow'then 
                v.BackgroundColor3=color1;
            end;
        end;
        if v:IsA('TextLabel')and not string.find(v.Text,'R')then 
            if v.Name~='DropShadow'then 
                v.TextColor3=color2;
            else
                v.TextColor3=color1;
            end;
            v.BackgroundColor3=color1;
        end;
        if v:IsA'TextButton'then 
            v.BackgroundColor3=color1;
        end;
        createCorner(v);
    end;
    
    --Whitelist 
    local whiteListGui=lp.PlayerGui.WhiteListGUI 
    
    for _,v in next,whiteListGui:GetDescendants()do
        if v:IsA'Frame'then 
            createCorner(v);
            if v.Name~='DropShadow'then
                v.BackgroundColor3=color1;
            end;
        end;
        if v:IsA'TextLabel'or v:IsA'TextButton'then 
            if v.Name=='InfoT'then 
                v.TextStrokeColor3=color1;
            end;
            if v.Name~='DropShadow'then
                v.TextColor3=color2
            else
                v.TextColor3=color1;
                v.TextStrokeColor3=color2;
            end;
            v.BackgroundColor3=color1;
            createCorner(v);
        end;
        if v:IsA'ScrollingFrame'then 
            v.BackgroundColor3=color1;
        end;
    end;
    
    --Blacklist 
    local blackListGui=lp.PlayerGui.BlackListGUI 
    
    for _,v in next,blackListGui:GetDescendants()do
        if v:IsA'Frame'then 
            createCorner(v);
            if v.Name~='DropShadow'then
                v.BackgroundColor3=color1;
            end;
        end;
        if v:IsA'TextLabel'and v.Name~='InfoT'or v:IsA'TextButton'then 
            if v.Name~='DropShadow'then
                v.TextColor3=color2
            else
                v.TextColor3=color1;
            end;
            v.BackgroundColor3=color1;
            createCorner(v);
        end;
        if v:IsA'ScrollingFrame'then 
            v.BackgroundColor3=color1;
        end;
    end;
    
    --Send Money 
    
    local sendMoney=lp.PlayerGui.DonateGUI 
    
    for _,v in next,sendMoney:GetDescendants()do
        if v:IsA'Frame'then 
            createCorner(v);
            if v.Name~='DropShadow'then
                v.BackgroundColor3=color1;
            end;
        end;
        if v:IsA'TextLabel'and v.Name~='InfoT'or v:IsA'TextButton'then 
            if v.Name~='DropShadow'then
                v.TextColor3=color2
            else
                v.TextColor3=color1;
            end;
            v.BackgroundColor3=color1;
            createCorner(v);
        end;
        if v:IsA'ScrollingFrame'then 
            v.BackgroundColor3=color1;
        end;
    end;
    game:GetService('Players').LocalPlayer.PlayerGui.DonateGUI.Donate.Main.AmountLabel.BackgroundColor3=Color3.fromRGB(0,155,0);
    createCorner(game:GetService('Players').LocalPlayer.PlayerGui.DonateGUI.Donate.Main.AmountLabel)
    game:GetService('Players').LocalPlayer.PlayerGui.DonateGUI.Donate.Main.AmountLabel.TextColor3=color2
    --Changelog 
    local changeLog=lp.PlayerGui.ChangelogGUI
    
    for _,v in next,changeLog:GetDescendants()do
        if v:IsA'Frame'then 
            createCorner(v);
            if v.Name~='DropShadow'then
                v.BackgroundColor3=color1;
            end;
        end;
        if v:IsA'TextLabel'and v.Name~='InfoT'or v:IsA'TextButton'then 
            if v.Name~='DropShadow'then
                v.TextColor3=color2
            else
                v.TextColor3=color1;
            end;
            v.BackgroundColor3=color1;
            createCorner(v);
        end;
    end;
    
    --Credits
    local creditsUI=lp.PlayerGui.CreditsGUI
    
    for _,v in next,creditsUI:GetDescendants()do
        if v:IsA'Frame'then 
            createCorner(v);
            if v.Name~='DropShadow'then
                v.BackgroundColor3=color1;
            end;
        end;
        if v:IsA'TextLabel'and v.Name~='InfoT'or v:IsA'TextButton'then 
            if v.Name~='DropShadow'then
                v.TextColor3=color2
            else
                v.TextColor3=color1;
            end;
            v.BackgroundColor3=color1;
            createCorner(v);
        end;
    end;
    
    local scr=getsenv(requirements.LP.PlayerGui.CreditsGUI.CreditsClient)
        local old=scr.openWindow
        local old2=scr.displayPage
        scr.openWindow=function()
            old()
            local creditsUI=lp.PlayerGui.CreditsGUI
            for _,v in next,creditsUI:GetDescendants()do
                if v:IsA'Frame'then 
                    createCorner(v);
                    if v.Name~='DropShadow'then
                        v.BackgroundColor3=color1;
                    end;
                end;
                if v:IsA'TextLabel'and v.Name~='InfoT'or v:IsA'TextButton'then 
                    if v.Name~='DropShadow'then
                        v.TextColor3=color2
                    else
                        v.TextColor3=color1;
                    end;
                    v.BackgroundColor3=color1;
                    createCorner(v);
                end;
            end;
        end;
        scr.displayPage=function()
        old2()
        local creditsUI=lp.PlayerGui.CreditsGUI
        for _,v in next,creditsUI:GetDescendants()do
            if v:IsA'Frame'then 
                createCorner(v);
                if v.Name~='DropShadow'then
                    v.BackgroundColor3=color1;
                end;
            end;
            if v:IsA'TextLabel'and v.Name~='InfoT'or v:IsA'TextButton'then 
                if v.Name~='DropShadow'then
                    v.TextColor3=color2
                else
                    v.TextColor3=color1;
                end;
                v.BackgroundColor3=color1;
                createCorner(v);
            end;
        end;
    end;
    
    --OnBoarding 
    local onBoardingGUI=lp.PlayerGui.OnboardingGUI
    
    for _,v in next,onBoardingGUI:GetDescendants()do
        if v:IsA'Frame'then 
            createCorner(v);
            if v.Name~='DropShadow'then
                v.BackgroundColor3=color1;
            end;
        end;
        if v:IsA'TextLabel'and v.Name~='InfoT'or v:IsA'TextButton'then 
            if v.Name~='DropShadow'then
                v.TextColor3=color2
            else
                v.TextColor3=color1;
            end;
            v.BackgroundColor3=color1;
            createCorner(v);
        end;
    end;
    --Chat GUI
    local chat=lp.PlayerGui.ChatGUI
    for _,v in next,chat:GetDescendants()do
        if v:IsA'Frame'then 
            createCorner(v);
            if v.Name~='DropShadow'then
                v.BackgroundColor3=color1;
            end;
        end;
        if v:IsA'TextLabel'and v.Name~='InfoT'or v:IsA'TextButton'then 
            if v.Name~='DropShadow'then
                v.TextColor3=color2
            else
                v.TextColor3=color1;
            end;
            v.BackgroundColor3=color1;
            createCorner(v);
        end;
    end;
    --ItemDraggerGUI 
    local itemDraggingGUI=lp.PlayerGui.ItemDraggingGUI
    for _,v in next,itemDraggingGUI:GetDescendants()do
        if v:IsA'Frame'then 
            createCorner(v);
            if v.Name~='DropShadow'then
                v.BackgroundColor3=color1;
            end;
        end;
        if v:IsA'TextLabel'and v.Name~='InfoT'or v:IsA'TextButton'then 
            v.TextColor3=color2
            v.BackgroundColor3=color1;
            createCorner(v);
        end;
    end;
    --ItemInfo 
    local itemInfoGUI=lp.PlayerGui.ItemInfoGUI
    for _,v in next,itemInfoGUI:GetDescendants()do
        if v:IsA'Frame'then 
            createCorner(v);
            if v.Name~='DropShadow'then
                v.BackgroundColor3=color1;
            end;
        end;
        if v:IsA('ImageLabel')then 
            v.BackgroundColor3=color1;
            createCorner(v);
        end;
        if v:IsA'TextLabel'and v.Name~='InfoT'or v:IsA'TextButton'then 
            if v.Name~='DropShadow'then
                v.TextColor3=color2
                v.TextStrokeColor3=color1
            else
                v.TextColor3=color1;
                v.TextStrokeColor3=color1
            end;
            v.BackgroundColor3=color1;
            createCorner(v);
        end;
    end;
    --InteractionGUI
    local interactionGUI=lp.PlayerGui.InteractionGUI
    for _,v in next,interactionGUI:GetDescendants()do
        if v:IsA'Frame'then 
            createCorner(v);
            if v.Name~='DropShadow'then
                v.BackgroundColor3=color2;
            end;
        end;
        if v:IsA'TextLabel'and v.Name~='InfoT'or v:IsA'TextButton'then 
            if v.Name~='DropShadow'then
                v.TextColor3=color2
            else
                v.TextColor3=color1;
            end;
            v.BackgroundColor3=color1;
            createCorner(v);
        end;
    end;
    game:GetService('Players').LocalPlayer.PlayerGui.InteractionGUI.OwnerShow.BackgroundColor3=color1;
    --StructureGui
    local structureDraggingGUI=lp.PlayerGui.StructureDraggingGUI
    for _,v in next,structureDraggingGUI:GetDescendants()do
        if v:IsA'Frame'then 
            createCorner(v);
            if v.Name~='DropShadow'then
                v.BackgroundColor3=color1;
            end;
        end;
        if v:IsA'TextLabel'and v.Name~='InfoT'or v:IsA'TextButton'then 
            if v.Name~='DropShadow'then
                v.TextColor3=color2
            else
                v.TextColor3=color1;
            end;
            v.BackgroundColor3=color1;
            createCorner(v);
        end;
    end;
    --WireDraggingGUI
    local wireDraggingGUI=lp.PlayerGui.WireDraggingGUI
    for _,v in next,wireDraggingGUI:GetDescendants()do
        if v:IsA'Frame'then 
            createCorner(v);
            if v.Name~='DropShadow'then
                v.BackgroundColor3=color1;
            end;
        end;
        if v:IsA'TextLabel'and v.Name~='InfoT'or v:IsA'TextButton'then 
            if v.Name~='DropShadow'then
                v.TextColor3=color2
            else
                v.TextColor3=color1;
            end;
            v.BackgroundColor3=color1;
            createCorner(v);
        end;
    end;
    --OverWriteConfirm
    local overWriteConfirm=loadMenu.OverwriteConfirm
    for _,v in next,overWriteConfirm:GetDescendants()do
        if v:IsA'Frame'then 
            createCorner(v);
            if v.Name~='DropShadow'then
                v.BackgroundColor3=color1;
            end;
        end;
        if v:IsA'TextLabel'and v.Name~='InfoT'or v:IsA'TextButton'then 
            if v.Name~='DropShadow'then
                v.TextColor3=color2
            else
                v.TextColor3=color1;
            end;
            v.BackgroundColor3=color1;
            createCorner(v);
        end;
    end;
    game:GetService('Players').LocalPlayer.PlayerGui.ItemDraggingGUI.CanDrag.PlatformButton.KeyLabel.TextSize=14;
    game:GetService('Players').LocalPlayer.PlayerGui.ItemDraggingGUI.CanRotate.PlatformButton.KeyLabel.TextSize=14
    game:GetService('Players').LocalPlayer.PlayerGui.ItemDraggingGUI.CanRotate.PlatformButton.KeyLabel.TextScaled=false;
    for _,v in next,game:GetService('Players').LocalPlayer.PlayerGui:GetDescendants()do 
        if v.Name=='KeyLabel'then 
            v.TextColor3=Color3.fromRGB(0,0,0);
        end;
    end;
    --Blueprints
    local scr=getsenv(requirements.LP.PlayerGui.Blueprints.LocalBlueprints)
    local old=scr.populateCategoryList
    scr.populateCategoryList=function()
        old()
        local blueprints=lp.PlayerGui.Blueprints
        for _,v in next,blueprints:GetDescendants()do
            if v:IsA('ImageLabel')then 
                v.BackgroundColor3=color1;
            end;
            if v:IsA'Frame'then 
                createCorner(v);
                if v.Name~='DropShadow'then
                    v.BackgroundColor3=color1;
                elseif mode=='Dark'then 
                    v.BackgroundColor3=Color3.fromRGB(0,0,0);
                elseif mode=='Light'then 
                    v.BackgroundColor3=Color3.fromRGB(25,25,25);
                end;
            end;
            if v:IsA'TextLabel'and v.Name~='InfoT'or v:IsA'TextButton'then 
                if v.Name=='DropShadow'then
                    v:remove();
                end
                if v.Text=='Blueprints'and v.Name~='DropShadow'then 
                    v.TextColor3=color2;
                else
                    v.TextColor3=color2;
                end;
                v.BackgroundColor3=color1;
                createCorner(v);
            end;
            if v:IsA'ScrollingFrame'then 
                v.BackgroundColor3=color1;
            end;
        end;
    end;
end;
-- if requirements.ConfigSetup.uiDarkMode then 
-- 	functions.uiMode('Dark');
-- else
-- 	functions.uiMode('Light');
-- end;

functions.RemoveTool=function()
    requirements.connections.antiWeld=game:GetService'RunService'.Stepped:Connect(function()
        pcall(function()
            for _,tool in next,requirements.LP.Character:children()do 
                if tool:IsA('Tool')and tostring(tool.Name)~='BlueprintTool'then 
                    if not tool:FindFirstChild('Owner') or tool:FindFirstChild('Owner')then
                        if tostring(tool.Owner.Value)==tostring(requirements.LP)then return end;
                        if not functions.WhitelistCheck(tool.Owner.Value)then
                            requirements.LP.Character.Humanoid:UnequipTools();
                        end;
                    end;
                end;
            end;
        end);
    end);
end;
functions.RemoveTool();

functions.selfDupeCurrentSlot=function(slot)
    if not slot then 
        slot=requirements.LP.CurrentSaveSlot.Value;
    end;
    local connection,newPlot;
    if requirements.Booleans.selfDuping then 
        functions.notify('Error', 'Already Duping!',4);
        return;
    end;
    if not requirements.Booleans.DisableSlotSaving then 
        functions.notify('Error','Disable slot saving is disabled!',4);
        return;
    end;
    local success=functions.PlotLogic();
    if success then 
        requirements.Booleans.selfDuping=true;
        functions.SaveSelectedSlot();
        functions.SelfWl(true);
        repeat wait()until requirements.LP.WhitelistFolder:FindFirstChild(tostring(requirements.LP))
        spawn(function()
            functions.LoadSelectedSlot(slot);
        end);
        local plot=functions.getPlayersBase(tostring(requirements.LP))
        originSquare=plot.OriginSquare;
        requirements.remotes.setPropertyPurchasingValue:InvokeServer(true);
        requirements.remotes.clientExpandedProperty:FireServer(plot ,CFrame.new(originSquare.Position.X + 40, originSquare.Position.Y, originSquare.Position.Z));requirements.remotes.clientExpandedProperty:FireServer(plot ,CFrame.new(originSquare.Position.X - 40, originSquare.Position.Y, originSquare.Position.Z));requirements.remotes.clientExpandedProperty:FireServer(plot ,CFrame.new(originSquare.Position.X, originSquare.Position.Y, originSquare.Position.Z + 40));requirements.remotes.clientExpandedProperty:FireServer(plot ,CFrame.new(originSquare.Position.X, originSquare.Position.Y, originSquare.Position.Z - 40));requirements.remotes.clientExpandedProperty:FireServer(plot ,CFrame.new(originSquare.Position.X + 40, originSquare.Position.Y, originSquare.Position.Z + 40));requirements.remotes.clientExpandedProperty:FireServer(plot ,CFrame.new(originSquare.Position.X + 40, originSquare.Position.Y, originSquare.Position.Z - 40));requirements.remotes.clientExpandedProperty:FireServer(plot ,CFrame.new(originSquare.Position.X - 40, originSquare.Position.Y, originSquare.Position.Z + 40));requirements.remotes.clientExpandedProperty:FireServer(plot ,CFrame.new(originSquare.Position.X - 40, originSquare.Position.Y, originSquare.Position.Z - 40));requirements.remotes.clientExpandedProperty:FireServer(plot ,CFrame.new(originSquare.Position.X + 80, originSquare.Position.Y, originSquare.Position.Z));requirements.remotes.clientExpandedProperty:FireServer(plot ,CFrame.new(originSquare.Position.X - 80, originSquare.Position.Y, originSquare.Position.Z));requirements.remotes.clientExpandedProperty:FireServer(plot ,CFrame.new(originSquare.Position.X, originSquare.Position.Y, originSquare.Position.Z + 80));requirements.remotes.clientExpandedProperty:FireServer(plot ,CFrame.new(originSquare.Position.X, originSquare.Position.Y, originSquare.Position.Z - 80));requirements.remotes.clientExpandedProperty:FireServer(plot ,CFrame.new(originSquare.Position.X + 80, originSquare.Position.Y, originSquare.Position.Z + 80));requirements.remotes.clientExpandedProperty:FireServer(plot ,CFrame.new(originSquare.Position.X + 80, originSquare.Position.Y, originSquare.Position.Z - 80));requirements.remotes.clientExpandedProperty:FireServer(plot ,CFrame.new(originSquare.Position.X - 80, originSquare.Position.Y, originSquare.Position.Z + 80));requirements.remotes.clientExpandedProperty:FireServer(plot ,CFrame.new(originSquare.Position.X - 80, originSquare.Position.Y, originSquare.Position.Z - 80));requirements.remotes.clientExpandedProperty:FireServer(plot ,CFrame.new(originSquare.Position.X + 40, originSquare.Position.Y, originSquare.Position.Z + 80));requirements.remotes.clientExpandedProperty:FireServer(plot ,CFrame.new(originSquare.Position.X - 40, originSquare.Position.Y, originSquare.Position.Z + 80));requirements.remotes.clientExpandedProperty:FireServer(plot ,CFrame.new(originSquare.Position.X + 80, originSquare.Position.Y, originSquare.Position.Z + 40));requirements.remotes.clientExpandedProperty:FireServer(plot ,CFrame.new(originSquare.Position.X + 80, originSquare.Position.Y, originSquare.Position.Z - 40));requirements.remotes.clientExpandedProperty:FireServer(plot ,CFrame.new(originSquare.Position.X - 80, originSquare.Position.Y, originSquare.Position.Z + 40));requirements.remotes.clientExpandedProperty:FireServer(plot ,CFrame.new(originSquare.Position.X - 80, originSquare.Position.Y, originSquare.Position.Z - 40));requirements.remotes.clientExpandedProperty:FireServer(plot ,CFrame.new(originSquare.Position.X + 40, originSquare.Position.Y, originSquare.Position.Z - 80));requirements.remotes.clientExpandedProperty:FireServer(plot ,CFrame.new(originSquare.Position.X - 40, originSquare.Position.Y, originSquare.Position.Z - 80));
        functions.DeleteSurroundingTrees();
        requirements.remotes.setPropertyPurchasingValue:InvokeServer(false);
        plot.Owner.Value=nil;
        repeat wait()until requirements.LP.CurrentlySavingOrLoading.Value==false;
        local newPlot;
        repeat wait()newPlot=functions.getPlayersBase(tostring(requirements.LP));until newPlot;
        newPlot=newPlot.OriginSquare;
        functions.notify('Ancestor','Basedropping Duped Items',4)
        for _,item in next,workspace.PlayerModels:children()do 
            if item:IsA('Model')and item:FindFirstChild('Owner')and tostring(item.Owner.Value)==tostring(requirements.LP)then 
                if item:FindFirstChild('Main')then 
                    if (item.Main.CFrame.p-newPlot.CFrame.p).Magnitude>100 then 
                        ItemName=item:FindFirstChild('PurchasedBoxItemName')or item:FindFirstChild('ToolName')or item:FindFirstChild('BoxItemName')or item:FindFirstChild('ItemName')
                        if ItemName then
                            game.ReplicatedStorage.PlaceStructure.ClientPlacedStructure:FireServer(nil, CFrame.new(newPlot.CFrame.p+Vector3.new(4,1,4)),requirements.LP, nil, item, true)
                            game:GetService('RunService').Heartbeat:wait();
                        end;
                    end;
                end;
            end;    
        end;
        requirements.Booleans.selfDuping=false;
        functions.SelfWl(false);
        requirements.Booleans.DisableSlotSaving=false
        functions.SaveSelectedSlot();
        requirements.Booleans.DisableSlotSaving=true;
    end;
end;

functions.Shuffle=function()
    local number=math.random(1,#requirements.SignTable);
    local newTitle='PlaceHolder'
    for Index,Title in next,requirements.SignTable do
        if Index==number then 
            newTitle=tostring(Title);
        end;
    end;
    return newTitle;
end;
functions.doBillboards=function()
    for _,Billboard in next,game:GetService("Workspace").Stores.WoodRUs.Parts:GetChildren()do
        if Billboard:FindFirstChild'SurfaceGui'and Billboard.Name=='Part'then 
            Billboard.SurfaceGui.TextLabel.Text=functions.Shuffle();
        end;
    end;
end;
spawnf(function()
    pcall(function()
        game:GetService("Workspace").Stores.WoodRUs.Parts.PREMIUMSELECTION.SurfaceGui.TextLabel.Text=functions.Shuffle();
        functions.doBillboards();
        while wait(5)do
            if not requirements.Booleans.isEnabled then 
                break;
            end;
            functions.doBillboards();
            game:GetService("Workspace").Stores.WoodRUs.Parts.PREMIUMSELECTION.SurfaceGui.TextLabel.Text=functions.Shuffle();
        end;
    end);
end);
--//End Of Functions\\--

--//Connections\\--
requirements.connections.noclip=requirements.services.RunService.Stepped:Connect(function()
    if requirements.Booleans.Noclip then 
        if not requirements.ConfigSetup.oldNoclipEnabled then 
            pcall(function()
                for i, v in next,requirements.LP.Character:children()do
                    if v:IsA('BasePart')then
                        v.CanCollide=false;
                    end;
                end;
            end);
        elseif requirements.ConfigSetup.oldNoclipEnabled then
            pcall(function()
                requirements.LP.Character:FindFirstChild('Humanoid'):ChangeState(11);
            end);
        end;
    end;
end);

requirements.connections.shiftConnectBegan=game:GetService('UserInputService').InputBegan:Connect(function(key,processed)
    if key.KeyCode==Enum.KeyCode.LeftShift and not processed then
        requirements.Booleans.isDragging=true;
    end;
end);

requirements.connections.shiftConnectEnded=game:GetService('UserInputService').InputEnded:Connect(function(key,processed)
    if key.KeyCode==Enum.KeyCode.LeftShift and not processed then
        requirements.Booleans.isDragging=false; 
    end;
end);

loadstring([[
    local args={...};
    local requirements = args[1]
    local sprint=false
    requirements.connections.main=requirements.services.RunService.Heartbeat:Connect(function()
    pcall(function()
        if requirements.LP.Character and requirements.LP.Character:FindFirstChild('Humanoid')then
            if not requirements.Booleans.dragExists then
                requirements.LP.Character.Humanoid.WalkSpeed=requirements.Strings.WalkSpeed;
            elseif requirements.Booleans.dragExists and requirements.Booleans.isDragging then
                requirements.LP.Character.Humanoid.WalkSpeed=0;
            end
            if requirements.Booleans.Sprinting and not sprint then
                requirements.Strings.WalkSpeed=requirements.Strings.WalkSpeed+requirements.Strings.SprintSpeed;
                sprint=true;
            end;
            if not requirements.Booleans.Sprinting and sprint then
                sprint=false;
            end;
            requirements.LP.Character.Humanoid.JumpPower=requirements.Strings.JumpPower;
            requirements.LP.Character.Humanoid.HipHeight=requirements.Strings.HipHeight;
            if requirements.ConfigSetup.AlwaysDay then
                requirements.services.Lighting.TimeOfDay=('12:00:00');
            elseif requirements.ConfigSetup.AlwaysNight then 
                requirements.services.Lighting.TimeOfDay=('2:00:00');
            end;
            if requirements.ConfigSetup.NoFog then 
                requirements.services.Lighting.FogEnd=1000000;
            end;
            if requirements.ConfigSetup.SpookEnabled then
                requirements.services.Lighting.Spook.Value=true;
            end;
            if not requirements.ConfigSetup.SpookEnabled then 
                requirements.services.Lighting.Spook.Value=false;
            end;
            if requirements.LP.Character.Humanoid.SeatPart then
                requirements.LP.Character.Humanoid.SeatPart.Parent.Configuration.MaxSpeed.Value=requirements.Strings.carSpeed;
            end;
        end;
    end);
end)]])(requirements);

--//End Of Connections\\--

local main=lib:Main();
local MainPlayerOptionsFrame=main:Category('5181994100');
local MainPlayerOptions=MainPlayerOptionsFrame:Section('Ancestor '..requirements.CurrentVersion);
MainPlayerOptions:Slider(
    '行走速度',
    function(k)
        requirements.Strings.WalkSpeed=k;
    end,
    16,400
);

MainPlayerOptions:Slider(
    '冲刺速度',
    function(k)
        requirements.Strings.SprintSpeed=k;
    end,
    20,200
);


MainPlayerOptions:Slider(
    '跳跃提升',
    function(k)
        requirements.Strings.JumpPower=k;
    end,
    50,400
);

MainPlayerOptions:Slider(
    '悬空高度',
    function(height)
        requirements.Strings.HipHeight=height;
    end,
    0,
    100
);

MainPlayerOptions:KeyBind(
    '飞行',
    function(state)
        requirements.ConfigSetup.flyKey=tostring(state.Name)
        local Weldone;
        local WeldTwo;
        local car;
        requirements.Booleans.State=not requirements.Booleans.State
        repeat wait()
        until requirements.LP and requirements.LP.Character and requirements.LP.Character:FindFirstChild('Head') and requirements.LP.Character:FindFirstChild('Humanoid')
        repeat wait() until requirements.Mouse
        local Steer = {f = 0, b = 0, l = 0, r = 0}
        local BackSteer = {f = 0, b = 0, l = 0, r = 0}
        local MaxSpeed = 400
        if not requirements.LP.Character.Humanoid.SeatPart then
            requirements.LP.Character.Humanoid.PlatformStand=true
        end
        if requirements.LP.Character.Humanoid.SeatPart then
            car=requirements.LP.Character.Humanoid.SeatPart
            Weldone = Instance.new('Weld',requirements.LP.Character.Humanoid.SeatPart)
            WeldTwo = Instance.new('Weld',requirements.LP.Character.HumanoidRootPart)
            Weldone.Part0 = requirements.LP.Character.HumanoidRootPart
            Weldone.Part1 = requirements.LP.Character.Humanoid.SeatPart
            WeldTwo.Part0 = requirements.LP.Character.HumanoidRootPart
            WeldTwo.Part1 = requirements.LP.Character.Humanoid.SeatPart			
        end;
        function Fly()
            requirements.ConfigSetup.WaterFloat=false;
            local Gyro = Instance.new('BodyGyro', requirements.LP.Character.HumanoidRootPart)
            Gyro.P = 9e4
            Gyro.maxTorque = Vector3.new(9e9, 9e9, 9e9)
            Gyro.CFrame = requirements.LP.Character.HumanoidRootPart.CFrame
            local Velocity = Instance.new('BodyVelocity', requirements.LP.Character.HumanoidRootPart)
            Velocity.Velocity = Vector3.new(0,0.1,0)
            Velocity.maxForce = Vector3.new(9e9, 9e9, 9e9)
            requirements.Booleans.Noclip=true;
            repeat wait()
                local FlySpeed=requirements.Strings.flySpeed
                local SteerSpeed = 50
                if Steer.l + Steer.r ~= 0 or Steer.f + Steer.b ~= 0 then
                    SteerSpeed = FlySpeed
                    if SteerSpeed > MaxSpeed then
                        SteerSpeed = MaxSpeed
                    end
                elseif not (Steer.l + Steer.r ~= 0 or Steer.f + Steer.b ~= 0) and speed ~= 0 then
                    SteerSpeed = SteerSpeed-50
                    if SteerSpeed < 0 then
                        FlySpeed = 0    
                    end
                end
                if (Steer.l + Steer.r) ~= 0 or (Steer.f + Steer.b) ~= 0 then
                    Velocity.Velocity = ((game.Workspace.CurrentCamera.CoordinateFrame.lookVector * (Steer.f+Steer.b)) + ((game.Workspace.CurrentCamera.CoordinateFrame * CFrame.new(Steer.l+Steer.r,(Steer.f+Steer.b)*.2,0).p) - game.Workspace.CurrentCamera.CoordinateFrame.p)) * SteerSpeed
                    BackSteer = {f = Steer.f ,b = Steer.b ,l = Steer.l, r = Steer.r}
                elseif (Steer.l + Steer.r == 0 or Steer.f + Steer.b == 0) and SteerSpeed ~= 0 then
                    Velocity.Velocity = ((game.Workspace.CurrentCamera.CoordinateFrame.lookVector * (BackSteer.f+BackSteer.b)) + ((game.Workspace.CurrentCamera.CoordinateFrame * CFrame.new(BackSteer.l+BackSteer.r,(BackSteer.f+BackSteer.b)*.2,0).p) - game.Workspace.CurrentCamera.CoordinateFrame.p)) * SteerSpeed
                else
                    Velocity.Velocity = Vector3.new(0,0.1,0)
                end
                Gyro.CFrame = game.Workspace.CurrentCamera.CoordinateFrame * CFrame.Angles(-math.rad((Steer.f+Steer.b)*50*SteerSpeed/MaxSpeed),0,0)
            until not requirements.Booleans.isFlying
            local SteerSpeed = 0
            local Steer = {F = 0,B = 0,L = 0,R = 0}
            local BackSteer = {F = 0,B = 0,L = 0,R = 0}
            Gyro:Destroy()
            Velocity:Destroy()
            pcall(function()
                for _,v in next,requirements.LP.Character.Humanoid.SeatPart:children()do
                    if v.Name=='Weld'then 
                        v:Destroy();
                    end;
                end;
                for i,v in next,requirements.LP.Character.HumanoidRootPart:children()do
                    if v:IsA('Weld')then 
                        v:Destroy();
                    end;
                end;
                functions.Teleport(CFrame.new(car.CFrame.p))
            end);
            requirements.LP.Character.Humanoid.PlatformStand = false
        end

        requirements.Mouse.KeyDown:Connect(function(Key)
            if Key:lower() == 'w' then
                isWDown = true
                Steer.f = 1
            elseif Key:lower() == 'a' then
                isADown = true
                Steer.l = -1
            elseif Key:lower() == 's' then
                isSDown = true
                Steer.b = -1
            elseif Key:lower() == 'd' then
                isSDown = true
                Steer.r = 1
            end
        end)
        requirements.Mouse.KeyUp:Connect(function(Key)
            if Key:lower() == 'w' then
                isWDown = false
                Steer.f = 0
            elseif Key:lower() == 'a' then
                isADown = false
                Steer.l = 0
            elseif Key:lower() == 's' then
                isSDown = false
                Steer.b = 0
            elseif Key:lower() == 'd' then
                isDDown = false
                Steer.r = 0
            end
        end)

        if not requirements.Booleans.State then
            requirements.ConfigSetup.WaterFloat=true;
            requirements.Booleans.isFlying=false
            requirements.Booleans.Noclip=false;
            requirements.LP.Character.Humanoid.PlatformStand = false
        elseif requirements.Booleans.State then
            requirements.Booleans.isFlying = true
            Fly()
        end
    end,
    Enum.KeyCode[requirements.ConfigSetup.flyKey]
)

MainPlayerOptions:Slider(
    '飞行速度',
    function(v)
        requirements.Strings.flySpeed=v;
    end,
    150, 400
);

MainPlayerOptions:KeyBind(
    '冲刺按键',
    function(v)
        requirements.ConfigSetup.SprintKey=tostring(v.Name)
        if requirements.Booleans.Sprinting then 
            return;
        end;
        requirements.Booleans.Sprinting=true;
    end,
    Enum.KeyCode[requirements.ConfigSetup.SprintKey]
);

MainPlayerOptions:KeyBind(
    '穿墙',
    function(v)
        requirements.ConfigSetup.NoclipKey=tostring(v.Name)
        if requirements.Booleans.Noclip then
            requirements.Booleans.Noclip=false;
            functions.notify('Ancestor','NoClip Disabled',4);
        elseif not requirements.Booleans.Noclip then
            requirements.Booleans.Noclip=true;
            functions.notify('Ancestor','NoClip Enabled',4);
        end;
    end,
    Enum.KeyCode[requirements.ConfigSetup.NoclipKey]
)

MainPlayerOptions:KeyBind(
    '点击传送',
    function(v)
        requirements.ConfigSetup.KeyTP=tostring(v.Name)
        if(requirements.LP.Character.Head.CFrame.p-requirements.Mouse.Hit.p).Magnitude<5000 then 
            functions.Teleport(CFrame.new(requirements.Mouse.Hit.p)+Vector3.new(0,3,0))
        end;
    end,
    Enum.KeyCode[requirements.ConfigSetup.KeyTP]
);

MainPlayerOptions:Toggle(
    '无限跳跃',
    function(value)
        if not value then 
            if requirements.connections.infJump then 
                requirements.connections.infJump:Disconnect();
                requirements.connections.infJump=nil;
                requirements.Booleans.infJumpEnabled=false;
            end;
            functions.notify('Ancestor','Infinite Jump Disabled',4);
        elseif value then 
            requirements.connections.infJump=requirements.services.userInputService.JumpRequest:Connect(function()
                requirements.LP.Character.Humanoid:ChangeState(Enum.HumanoidStateType.Jumping);
            end)
            requirements.Booleans.infJumpEnabled=true;
            functions.notify('Ancestor','Infinite Jump Enabled',4);
        end;
    end,
    false
)

MainPlayerOptions:Toggle(
    '灯',
    function(b)
        if b then 
            functions.applyLight(true);
        else
            functions.applyLight();
        end;
        requirements.ConfigSetup.light=b
    end,
    requirements.ConfigSetup.light     
);

MainPlayerOptions:Slider(
    '视角',
    function(value)
        requirements.wrkspc.CurrentCamera.FieldOfView = value
    end,
    1,120
)

MainPlayerOptions:Button(
    '重置视角',
    function()
        requirements.wrkspc.CurrentCamera.FieldOfView = 70
    end,
    true
)

MainPlayerOptions:Button(
    '安全自杀',
    function()
        functions.KillPlayer();
    end,
    true
);

MainPlayerOptions:Button(
    '工具',
    function()   
    functions.givePlayerBTools();
    end,
    true
)

requirements.services.userInputService.InputEnded:Connect(function(key,processed)
    if key.KeyCode==Enum.KeyCode[requirements.ConfigSetup.SprintKey]and not processed then 
        if requirements.Strings.WalkSpeed>16 then 
            requirements.Booleans.Sprinting=false;
            requirements.Strings.WalkSpeed=tonumber(game.CoreGui.Ancestor.MainBody.ScrollingFrame.WalkSpeedSlider.SliderDarkOutline.SliderValue.Text)
        end;
    end;
end);

local MainPlayerOptions=MainPlayerOptionsFrame:Section('传送到地方');
MainPlayerOptions:DropDown(
    '传送到地方',
    function(b)
        if b=='木材反斗城'then
            functions.Teleport(CFrame.new(270,4,60));
        elseif b=='出生点'then
            functions.Teleport(CFrame.new(174,10.5,66));
        elseif b=='土地商店'then
            functions.Teleport(CFrame.new(270,3,-98));
        elseif b=='桥'then
            functions.Teleport(CFrame.new(112,37,-892));
        elseif b=='码头'then
            functions.Teleport(CFrame.new(1136,0,-206));
        elseif b=='椰子岛'then
            functions.Teleport(CFrame.new(2614,-4,-34));
        elseif b=='洞穴'then
            functions.Teleport(CFrame.new(3590,-177,415));
        elseif b=='火山'then
            functions.Teleport(CFrame.new(-1588,623,1069));
        elseif b=='沼泽'then
            functions.Teleport(CFrame.new(-1216,131,-822));
        elseif b=='家具店'then
            functions.Teleport(CFrame.new(486,3,-1722));
        elseif b=='盒子车行'then
            functions.Teleport(CFrame.new(509,3,-1458));
        elseif b=='雪山'then
            functions.Teleport(CFrame.new(1487,415,3259));
        elseif b=='连锁逻辑店'then
            functions.Teleport(CFrame.new(4615,7,-794));
        elseif b=='鲍勃的小店'then
            functions.Teleport(CFrame.new(292,8,-2544));
        elseif b=='画廊'then
            functions.Teleport(CFrame.new(5217,-166,721));
        elseif b=='灵视神殿'then
            functions.Teleport(CFrame.new(-1608,195,928));
        elseif b=='怪人'then
            functions.Teleport(CFrame.new(1071,16,1141));
        elseif b=='小绿盒'then
            functions.Teleport(CFrame.new(-1667,349,1474));
        elseif b=='滑雪小屋'then
            functions.Teleport(CFrame.new(1244,59,2290));
        elseif b=='黄金木洞穴'then
            functions.Teleport(CFrame.new(-1080,-5,-942));
        elseif b=='鲨鱼斧合成'then 
            functions.Teleport(CFrame.new(330.259735, 45.7998505, 1943.30823, 0.972010553, -8.07546598e-08, 0.234937176, 7.63610259e-08, 1, 2.77986647e-08, -0.234937176, -9.08055142e-09, 0.972010553))
        end;
    end,
    {options={'出生点','木材反斗城','土地商店','桥','码头','椰子岛','洞穴','鲨鱼斧合成','火山','沼泽','家具店','盒子车行','连锁逻辑店','鲍勃的小店','画廊','雪山','灵视神殿','怪人','小绿盒','滑雪小屋','黄金木洞穴'}
    });

local MainPlayerOptions=MainPlayerOptionsFrame:Section('传送到玩家');
MainPlayerOptions:DropDown(
    '传送到玩家',
    function(plr)
        if not requirements.Players:FindFirstChild(plr)then 
            functions.notify('Error','Player Not Found!',4);
            return;
        end;
        local PlayerPos=requirements.Players[plr].Character:FindFirstChild('HumanoidRootPart').Position+Vector3.new(0,5,0);
        functions.Teleport(CFrame.new(PlayerPos.X,PlayerPos.Y,PlayerPos.Z));
    end,
    nil,true
);
local MainPlayerOptions=MainPlayerOptionsFrame:Section('传送到玩家的基地');

MainPlayerOptions:DropDown(
 '传送 到玩家\'s 基地',
    function(plr)
        if not requirements.Players:FindFirstChild(plr)then 
            functions.notify('Error','Player Not Found!',4);
            return;
        end;
        local plot=functions.getPlayersBase(tostring(plr));
        if plot then 
            functions.Teleport(CFrame.new(plot.OriginSquare.Position.X,plot.OriginSquare.Position.Y,plot.OriginSquare.Position.Z)+Vector3.new(0,5,0));
        else 
            functions.notify('Error','Player Has No Plot!',4);
        end;
    end,
    false,true,true
);
local MainPlayerOptions=MainPlayerOptionsFrame:Section('查看玩家');
MainPlayerOptions:DropDown(
    'Teleport To Player\'s Plot',
    function(plr)
        pcall(function()
            if not requirements.Players:FindFirstChild(plr)then 
                functions.notify('Error','Player Not Found!',4);
                return;
            end;
            functions.StopSpectating();
            requirements.wrkspc.CurrentCamera.CameraSubject=requirements.Players:FindFirstChild(plr).Character.Humanoid
            requirements.connections.spectateAdded=requirements.Players:FindFirstChild(plr).CharacterAdded:Connect(function()
                repeat wait()until requirements.Players:FindFirstChild(plr):FindFirstChild'Humanoid'
                requirements.wrkspc.CurrentCamera.CameraSubject=requirements.Players:FindFirstChild(plr).Character.Humanoid
            end);
            requirements.connections.spectateAddedLocal=requirements.LP.CharacterAdded:Connect(function()
                repeat wait()until requirements.wrkspc.CurrentCamera.CameraSubject==requirements.LP.Character:WaitForChild'Humanoid'
                requirements.wrkspc.CurrentCamera.CameraSubject=requirements.Players:FindFirstChild(plr).Character.Humanoid
            end);
            requirements.connections.playerLeft=game:GetService'Players'.ChildRemoved:Connect(function(Player)
                if tostring(Player)==tostring(plr)then 
                    functions.StopSpectating();
                end;
            end);
        end);
    end,
    false,true,true
);
MainPlayerOptions:Button(
    '停止查看',
    function()
        functions.StopSpectating();
    end,
    true
);

local MainGameOptionsFrame=main:Category('6894662531');
local MainGameOptions=MainGameOptionsFrame:Section('Graphical Options');

MainGameOptions:Toggle(
    '白天',
    function(state)
        requirements.ConfigSetup.AlwaysDay=state;
    end,
    requirements.ConfigSetup.AlwaysDay
);

MainGameOptions:Toggle(
    '黑夜',
    function(state)
        requirements.ConfigSetup.AlwaysNight=state;
    end,
    requirements.ConfigSetup.AlwaysNight
);

MainGameOptions:Toggle(
    '删除雾',
    function(state)
        requirements.ConfigSetup.NoFog=state;
    end,
    requirements.ConfigSetup.NoFog
);

MainGameOptions:Toggle(
    '万圣节夜晚',
    function(state)
        requirements.ConfigSetup.SpookEnabled=state;
    end,
    requirements.ConfigSetup.SpookEnabled
);

local MainGameOptions=MainGameOptionsFrame:Section('Lava Options');

MainGameOptions:Toggle(
    'Disable Lava',
    function(state)
    local part
        for i,v in next,game:GetService('Workspace')['Region_Volcano']:children()do 
            if v.Name==('Lava')then
                if i==2 then
                    if not state then
                        if v:FindFirstChild'lol'then 
                            v.lol:remove();
                        end;
                    end;
                    if state then
                        part=Instance.new('Part',v)
                        part.Name='lol'
                        part.Size=v.LavaLayer.Size
                        part.CFrame=v.LavaLayer.CFrame+Vector3.new(0,3,0)
                        part.CanCollide=true
                        part.Transparency=1
                        part.Anchored=true
                    end;
                end;
            end;
        end;
    end,
    false
)
local MainGameOptions=MainGameOptionsFrame:Section('Water Options');
MainGameOptions:Toggle(
    '水上行走',
    function(state)
        for i,v in next,game.workspace.Water:children()do
            if v.ClassName=='Part'then
                requirements.ConfigSetup.WaterWalk,v.CanCollide=state,state;
            end;
        end;
        for i,v in next,game:GetService('Workspace').Bridge.VerticalLiftBridge.WaterModel:children()do 
            if v:IsA('BasePart')then 
                v.CanCollide=state;
            end;
        end;
    end,
    requirements.ConfigSetup.WaterWalk
);

MainGameOptions:Toggle(
    '在水中不掉血',
    function(state)
        requirements.ConfigSetup.WaterGodMode=state;
    end,
    requirements.ConfigSetup.WaterGodMode
);

MainGameOptions:Toggle(
    '水下行走',
    function(state)
        requirements.ConfigSetup.WaterFloat=state;
    end,
    requirements.ConfigSetup.WaterFloat
);
local MainGameOptions=MainGameOptionsFrame:Section('Main Bridge Options');
MainGameOptions:Toggle(
    '放下桥',
    function(state)
        if state then
            pcall(function()
                game:GetService('Workspace').Bridge.VerticalLiftBridge.Weight.Parent=game.Lighting
            end)
            functions.lowerBridge('Lower');
            return;
        end;
        pcall(function()
            game.Lighting.Weight.Parent=game:GetService('Workspace').Bridge.VerticalLiftBridge;
        end)
        functions.lowerBridge('Higher');
    end,
    false
);
local MainGameOptions=MainGameOptionsFrame:Section('Boulder Options');
MainGameOptions:Toggle(
    '自动带来火山石头',
    function(state)
        if state then
            requirements.Booleans.bringBoulders=true;
            functions.bringBoulders();
            return;
        end;
        requirements.Booleans.bringBoulders=false;
    end,
    false
);

MainGameOptions:Button(
    'Fuck Base',
    function(state)
        
    end,
    true
);
local MainGameOptions=MainGameOptionsFrame:Section('Leaked Items Options');
MainGameOptions:Toggle(
    '查看所有物品',
    function(v)
        if v then 
            if not requirements.wrkspc:FindFirstChild('Purchasables')then 
                local clone=game:GetService('ReplicatedStorage').Purchasables:Clone();
                clone.Parent=requirements.wrkspc;
            end;
        elseif not v then 
            if requirements.wrkspc:FindFirstChild('Purchasables')then 
                requirements.wrkspc:FindFirstChild('Purchasables'):Destroy();
            end;
        end;
    end,
    false
);
local MainGameOptions=MainGameOptionsFrame:Section('Music Options');
MainGameOptions:Toggle(
    '游戏音乐',
    function(state)
        requirements.ConfigSetup.gameMusic=state;
        requirements.LP.Music.Value=state;
    end,
    requirements.ConfigSetup.gameMusic
);
local MainGameOptions=MainGameOptionsFrame:Section('Anti Blacklist Options');
MainGameOptions:Toggle(
    '反黑名单',
    function(state)
        requirements.ConfigSetup.antiBlacklist=state;
        functions.antiBlacklist(state and 'Enable' or 'Disable');
    end,
    requirements.ConfigSetup.antiBlacklist
);
local MainGameOptions=MainGameOptionsFrame:Section('Store Options');

MainGameOptions:Button(
    '摧毁商店所有东西',
    function(state)
        functions.burnAllShopItems();
    end,
    true
);
local MainGameOptions=MainGameOptionsFrame:Section('Store Door Options');

MainGameOptions:Button(
    '关闭家具店的门',
    function(state)
        pcall(function()
            game:GetService('ReplicatedStorage').Interaction.RemoteProxy:FireServer(workspace.Stores.FurnitureStore.LDoor.ButtonRemote_Toggle);
            game:GetService('ReplicatedStorage').Interaction.RemoteProxy:FireServer(workspace.Stores.FurnitureStore.RDoor.ButtonRemote_Toggle);
        end);
    end,
    true
);

MainGameOptions:Button(
    '关闭连接逻辑店的门',
    function(state)
        pcall(function()
            game:GetService('ReplicatedStorage').Interaction.RemoteProxy:FireServer(workspace.Stores.LogicStore.LDoor.ButtonRemote_Toggle);
            game:GetService('ReplicatedStorage').Interaction.RemoteProxy:FireServer(workspace.Stores.LogicStore.RDoor.ButtonRemote_Toggle);
        end);
    end,
    true
);

MainGameOptions:Button(
    '关闭盒子车行的门',
    function(state)
        pcall(function()
            game:GetService('ReplicatedStorage').Interaction.RemoteProxy:FireServer(workspace.Stores.CarStore.LDoor.ButtonRemote_Toggle);
            game:GetService('ReplicatedStorage').Interaction.RemoteProxy:FireServer(workspace.Stores.CarStore.RDoor.ButtonRemote_Toggle);
        end);
    end,
    true
);
local MainGameOptions=MainGameOptionsFrame:Section('Den Hatch Options');
MainGameOptions:Button(
    '删掉附近的树',
    function(state)
        local door=game:GetService('Workspace')['Region_Snow'].Den.Hatch;
        local old=requirements.LP.Character.HumanoidRootPart.CFrame
        functions.Teleport(CFrame.new(door:FindFirstChildOfClass'Part'.CFrame.p+Vector3.new(0,5,0)));
        repeat task.wait()
            game:GetService('ReplicatedStorage').Interaction.ClientIsDragging:FireServer(door);
            game.ReplicatedStorage.Interaction.DestroyStructure:FireServer(door);
        until not door;
        functions.Teleport(old)
    end,
    true
);

local MainGameOptions=MainGameOptionsFrame:Section('Green Box Options');
MainGameOptions:Button(
    '获得小绿盒',
    function(state)
        local greenBox=game:GetService('Workspace')['Region_Volcano'].VolcanoWin;
        firetouchinterest(greenBox,requirements.LP.Character.HumanoidRootPart,0)
        firetouchinterest(greenBox,requirements.LP.Character.HumanoidRootPart,1)
    end,
    true
);
local MainGameOptions=MainGameOptionsFrame:Section('Tree Options');
MainGameOptions:Button(
    '删除所有树',
    function()
        functions.DeleteTrees();
    end,
    true
);
MainGameOptions:Button(
    '删除附近的树',
    function()
        functions.DeleteSurroundingTrees();
    end,
    true
);
local MainGameOptions=MainGameOptionsFrame:Section('Plot Options');
MainGameOptions:Button(
    'Claim All Free Plots',
    function()
        functions.ClaimAllFreePlots();
    end,
    true
);

MainGameOptions:Button(
    'Max Land All Claimed Plots',
    function()
        for _,Plot in next,game.Workspace.Properties:GetChildren()do
            if Plot:FindFirstChild('Owner')then
                if tostring(Plot.Owner.Value)==tostring(requirements.LP)then
                functions.MaxLand(Plot);
                end
            end
        end
    end,
    true
);
local MainGameOptions=MainGameOptionsFrame:Section('Misc Options');
MainGameOptions:Button(
    '启动所有压力板',
    function()
        functions.TriggerAllPressurePlates();
    end,
    true
);
MainGameOptions:Button(
    '烧掉史酷比',
    function()
        functions.fireAllScoobis();
    end,
    true
);
MainGameOptions:Button(
    '烧掉所有章鱼哥',
    function()
        functions.fireAllBrash();
    end,
    true
);
local MainGameOptions=MainGameOptionsFrame:Section('Bridge Options');
MainGameOptions:Button(
    '把沼泽桥带过来',
    function()
        functions.bringPushMe();
    end,
    true
);
local MainGameOptions=MainGameOptionsFrame:Section('Change All Gui Text(CS)');
MainGameOptions:TextBox(
    'Change All Gui\'s',
    function(v)
        functions.setWorkspaceGuis(workspace,v)
    end,
    'Enter Text Here'
);

local MainAxeOptionsFrame = main:Category('6898994158')
local MainAxeOptions=MainAxeOptionsFrame:Section('Dupe Options');

MainAxeOptions:Slider(
    '数量',
    function(value)
        requirements.Strings.ToolDuplicationAmount=value;
    end,
    1,10
);

MainAxeOptions:Toggle(
    '自动复制斧头',
    function(v)
        if v then 
            requirements.Booleans.axeDuping=true;
            functions.DupeInventory(9000);
        elseif not v then 
            requirements.Booleans.axeDuping=false;
        end;
    end,
    false
);

MainAxeOptions:Button(
    '复制斧头',
    function()
        requirements.Booleans.axeDuping=true;
        functions.DupeInventory(requirements.Strings.ToolDuplicationAmount);
    end,
    true
);

MainAxeOptions:Button(
    '停止',
    function()
        requirements.Booleans.axeDuping=false;
    end,
    true
);

local MainAxeOptions=MainAxeOptionsFrame:Section('统计斧头');

MainAxeOptions:DropDown(
    '统计斧头',
    function(axe)
        functions.notify('Ancestor','You Have '..tostring(functions.CountItem(tostring(axe)))..' '..tostring(axe)..'s',4);
    end,
    {options=requirements.tables.axeList}
);

local MainAxeOptions=MainAxeOptionsFrame:Section('玩家选择');
MainAxeOptions:DropDown(
    '',
    function(target)
        requirements.Strings.selectedTarget=target
    end,
    false,true,true
);
MainAxeOptions:DropDown(
    '',
    function(v)
        if v=='杀人'then 
            functions.manageTarget('KillPlayer',requirements.Strings.selectedTarget);
        elseif v=='踢人'then 
            functions.manageTarget('KickPlayer',requirements.Strings.selectedTarget);
        elseif v=='把人带过来'then 
            functions.manageTarget('BringPlayer',requirements.Strings.selectedTarget);
        elseif v=='把人推入岩浆'then 
            functions.manageTarget('HardKillPlayer',requirements.Strings.selectedTarget);
        end;
    end,
    {options={'杀人','把人推入岩浆','踢人','把人带过来'}}
);

MainAxeOptions:Toggle(
    '复制斧头',
    function(v)
        if v then 
            requirements.Booleans.dupeInventory=true;
        else
            requirements.Booleans.dupeInventory=false;
        end;
    end,
    false
);

local MainAxeOptions=MainAxeOptionsFrame:Section('Tool Options');
MainAxeOptions:Button(
    '复制斧头',
    function()
        functions.FarAxeEquip();
    end,
    true
);

MainAxeOptions:Button(
    '扔掉所有斧头',
    function()
        functions.DropAllTools();
    end,
    true
);

MainAxeOptions:Toggle(
    'Auto Chop',
    function(v)
        requirements.Booleans.autoChopping=v
        while wait(.2)do 
            if not requirements.Booleans.autoChopping then 
                break;
            end;
            spawnf(function()
                for _,v in next,requirements.wrkspc:children()do
                    if tostring(v)=='TreeRegion'then
                        for _,g in next,v:children()do
                            pcall(function()
                                if(requirements.LP.Character.HumanoidRootPart.CFrame.p-g.WoodSection.CFrame.p).magnitude<=20 and functions.getBestAxe()then 
                                functions.chopTree(g.CutEvent);
                                end;
                            end);
                        end;
                    end;
                end;
            end);
        end;
    end,
    false
);

MainAxeOptions:Toggle(
    '远程砍树',
    function(v)
        if v then 
            functions.notify('Ancestor','Hit Any Tree',4);
            requirements.Booleans.cutAssistEnabled=true;
            functions.CutAssist();
        end;
        if not v then 
            requirements.Booleans.cutAssistEnabled=false;
            if requirements.connections.cutAssist then 
                requirements.connections.cutAssist:Disconnect();
                requirements.connections.cutAssist=nil;
            end;
            if requirements.connections.woodSelection then 
                requirements.connections.woodSelection:Disconnect();
                requirements.connections.woodSelection=nil;
            end;
            if requirements.connections.cutAssistCutter then 
                requirements.connections.cutAssistCutter:Disconnect();
                requirements.connections.cutAssistCutter=nil;
            end;
            requirements.Strings.TreeModel=nil;
        end;
    end,
    false
);

MainAxeOptions:Toggle(
    '打开东西',
    function(toggle)
        if toggle then 
            functions.notify('Ancestor','Select an item to Open',4)
            requirements.connections.openItem=requirements.Mouse.Button1Down:Connect(function()
                if requirements.Mouse.Target then 
                    requirements.Strings.itemToOpen=requirements.Mouse.Target;
                end;
                functions.OpenSelectedItem(requirements.Strings.itemToOpen.Parent);
            end)
        elseif not toggle then
            if requirements.connections.openItem then 
                requirements.connections.openItem:Disconnect();
                requirements.connections.openItem=nil;
            end;
            functions.notify('Ancestor','Open Items Disabled',4)
            requirements.Strings.itemToOpen=nil;
        end;
    end,
    false
);

MainAxeOptions:Toggle(
    '斧头飞行',
    function(state)
        if not state then 
            if requirements.connections.axeFling then 
                requirements.connections.axeFling:Disconnect();
                requirements.connections.axeFling=nil;
            end;
        end;
        if state then 
            functions.axeFling();
        end;
    end,
    false
);

local BaseDropOptionsFrame=main:Category('5624739564')

local BaseDropOptions=BaseDropOptionsFrame:Section('玩家名字')

BaseDropOptions:DropDown(
    '',
    function(player)
        requirements.Strings.baseDropOwner=player;
    end,
    false,true
);
local BaseDropOptions=BaseDropOptionsFrame:Section('传送物品的名字');
BaseDropOptions:DropDown(
    '',
    function(item)
        requirements.Strings.itemToBaseDrop=item;
    end,
    {options=functions.getItemsList(requirements.Strings.baseDropOwner),CallBack=function() requirements.tables.itemListForBaseDrop={}; return functions.getItemsList(requirements.Strings.baseDropOwner) end}
);
local BaseDropOptions=BaseDropOptionsFrame:Section('传送物品的类型')
BaseDropOptions:DropDown(
    '基地传送的东西',
    function(item)
        requirements.Strings.itemToBaseDrop=item;
    end,
    {options=functions.getItemsListType(requirements.Strings.baseDropOwner),CallBack=function() requirements.tables.itemListForBaseDrop={}; return functions.getItemsListType(requirements.Strings.baseDropOwner) end}
)
local BaseDropOptions=BaseDropOptionsFrame:Section('Basedrop Options')
BaseDropOptions:Slider(
    '数量',
    function(v)
        requirements.Strings.baseDropAmount=v
    end,
    0,300
);

BaseDropOptions:Button(
    '开始传送',
    function()
        functions.baseDropItem(requirements.Strings.itemToBaseDrop,requirements.Strings.baseDropOwner,requirements.Strings.baseDropAmount);
    end,
    true
);
local BaseDropOptions=BaseDropOptionsFrame:Section('Cord Options')
BaseDropOptions:Button(
    '放置传送点',
    function()
        pcall(function()
            workspace.AncestorV3BasedropCord:Destroy();
        end)
        local AncestorV3BasedropCord=Instance.new('Part')	
        AncestorV3BasedropCord.Name='AncestorV3BasedropCord';	
        AncestorV3BasedropCord.Anchored=true;		
        AncestorV3BasedropCord.Parent=game.Workspace;
        AncestorV3BasedropCord.Shape=Enum.PartType.Ball;
        AncestorV3BasedropCord.Size=Vector3.new(2,2,2)
        AncestorV3BasedropCord.Color=Color3.fromRGB(0,0,255);
        AncestorV3BasedropCord.Material=Enum.Material.ForceField;
        AncestorV3BasedropCord.CFrame=requirements.LP.Character.HumanoidRootPart.CFrame;
        AncestorV3BasedropCord.CanCollide=false;
    end,
    true
);

BaseDropOptions:Button(
    '删除传送点',
    function()
        pcall(function()
            workspace.AncestorV3BasedropCord:Destroy();
        end)
    end,
    true
);

local part = Instance.new('Part')		-- Create a new part

part.Name = 'JurrasicPart'			-- Name the part... hehe
part.Anchored = true				-- Anchor the part
part.Parent = game.Workspace		-- Put the part into the Workspace
part.Shape = Enum.PartType.Ball		-- Give the part a ball shape
part.Color = Color3.new(1, 1, 1)

local MainPlotOptionsFrame=main:Category('5416946285');
local MainPlotOptions=MainPlotOptionsFrame:Section('加载和保存栏位');

MainPlotOptions:Slider(
    '栏位选择',
    function(slot)
        requirements.Strings.selectedPlotToLoad=slot;
    end,
    1,6
);

MainPlotOptions:Button(
    '加载存档',
    function()
        functions.LoadSelectedSlot(requirements.Strings.selectedPlotToLoad);
    end,
    true
);

MainPlotOptions:Button(
    '保存存档',
    function()
        functions.SaveSelectedSlot();
    end,
    true
);

MainPlotOptions:Button(
     '收档',
    function()
        functions.unloadSlot();
    end,
    true
);

MainPlotOptions:Toggle(
    '取消保存',
    function(value)
        if value then 
            requirements.Booleans.DisableSlotSaving=true;
            functions.notify('Ancestor','Disable if money duplicating. Enable for plot duplication',7)
            return;
        end;
        if not value then 
            requirements.Booleans.DisableSlotSaving=false;
        end;
    end,
    false
);

local MainPlotOptions=MainPlotOptionsFrame:Section('Main Plot Options');

MainPlotOptions:Button(
    '免费土地',
    function()
        functions.FreeLand();
    end,
    true
);

MainPlotOptions:Button(
    '最大土地',
    function()
        functions.MaxLand(functions.getPlayersBase(tostring(requirements.LP)));
    end,
    true
);

MainPlotOptions:Button(
    '扩大土地',
    function()
        local script=getsenv(requirements.LP.PlayerGui.PropertyPurchasingGUI.PropertyPurchasingClient);
        script.setPlatformControls=function()end;
        if not functions.getPlayersBase(tostring(requirements.LP))then script.enterPurchaseMode(0,false);return end;
        script.enterPurchaseMode(0,true);
    end,
    true
);

MainPlotOptions:Button(
    '卖掉牌子',
    function()
        functions.SellSign();
    end,
    true
);

MainPlotOptions:ColorPicker(
    '土地颜色',
    function(Color)
        functions.RecolourPlot(Color.r, Color.g, Color.b);
    end,
    Color3.fromRGB(124, 92, 70)
);

MainPlotOptions:Button(
    '重置土地颜色',
    function()
        functions.RecolourPlot(124, 92, 70);
    end,
    true
);

local MainPlotOptions=MainPlotOptionsFrame:Section('Whitelist/Blacklist Options');

MainPlotOptions:Toggle(
    '给白所有人',
    function(v)
        if v then 
            while v do
                wait();
                functions.managePlayer('Whitelist',true);
            end;
            return;
        end;
        functions.managePlayer('Whitelist',false);
    end,
    false
);

MainPlotOptions:Toggle(
    '拉黑所有人',
    function(v)
        requirements.ConfigSetup.blackListAll=v
        if requirements.ConfigSetup.blackListAll then 
            spawn(function()
                while requirements.ConfigSetup.blackListAll do
                    wait();
                    functions.managePlayer('Blacklist',true);
                end;
            end);
            return;
        end;
        functions.managePlayer('Blacklist',false);
    end,
    requirements.ConfigSetup.blackListAll
);

local MainPlotOptions=MainPlotOptionsFrame:Section('Transfer Money/Items To Another Slot Options');
MainPlotOptions:Slider(
    '档数选择',
    function(Amount)
        requirements.Strings.selectedPlot=Amount;
    end,
    1,6
);

MainPlotOptions:Button(
    '复制钱到档',
    function()
        functions.AutoDupeMoney(requirements.Strings.autoDupeMoneyAmount,requirements.Strings.selectedPlot);
    end,
    true
);

MainPlotOptions:Button(
    '复制基地到档位',
    function()
        functions.selfDupeCurrentSlot(requirements.Strings.selectedPlot);
    end,
    true
);

local MainPlotOptions=MainPlotOptionsFrame:Section('Blueprint Options');
MainPlotOptions:Button(
    '获取所有蓝图',
    function()
        functions.getAllBP();
    end,
    true
);

MainPlotOptions:Button(
   '获取所有蓝图要买',   
   function()
        functions.getPermBP();
    end,
    true
);



local MainPlotOptions=MainPlotOptionsFrame:Section('Plot Duplication Options');

MainPlotOptions:DropDown(
    'Player To Donate To',
    function(plr)
        requirements.Strings.BaseRecipient=plr;
    end,
    false,true
);

MainPlotOptions:Toggle(
    'Instruct Target',
    function(v)
        if v then 
            requirements.Booleans.alertTarget=true;
        else
            requirements.Booleans.alertTarget=false;
        end;
    end,
    true 
)

MainPlotOptions:Button(
    '转移基地到玩家',
    function()
        functions.DonatePlotToPlayer();
    end,
    true
);


local MainPlotOptions=MainPlotOptionsFrame:Section('Self Dupe');
MainPlotOptions:Button(
    '复制基地',
    function()
        functions.selfDupeCurrentSlot();
    end,
    true
);

local MainPlotOptions=MainPlotOptionsFrame:Section('Wire Options');

MainPlotOptions:DropDown(
    '',
    function(wire)
        requirements.Strings.selectedWire=wire
    end,
    {options={'NeonWirePinky','Wire','NeonWireRed'  ,'NeonWireOrange'  ,'NeonWireYellow'  ,'NeonWireGreen'  ,'NeonWireCyan'  ,'NeonWireBlue' ,'NeonWireViolet','NeonWireWhite','IcicleWireAmber','IcicleWireRed','IcicleWireGreen','IcicleWireBlue','IcicleWireMagenta','IcicleWireHalloween',}}
);

MainPlotOptions:Toggle(
    '电线替换',
    function(v)
        if v then 
            requirements.ConfigSetup.wireMod=true;
        elseif not v then 
            requirements.ConfigSetup.wireMod=false;
        end;
    end,
    requirements.ConfigSetup.wireMod
);

local MainPlotOptions=MainPlotOptionsFrame:Section('基地擦除');

MainPlotOptions:DropDown(
    '',
    function(type)
        requirements.Strings.itemTypeToWipe=type;
    end,
    {options={'Structure','Vehicle','Loose Item','Wire','Blueprint','Tool','Furniture'}}
);

MainPlotOptions:Button(
    '擦除选中物品',
    function()
        functions.wipeBase();
    end,
    true
);

local MainPlotOptions=MainPlotOptionsFrame:Section('Auto Build');

MainPlotOptions:DropDown(
    '',
    function(plr)
        requirements.Strings.autoBuildPlayer=plr;
    end,
    false,true
);

MainPlotOptions:DropDown(
    '',
    function(plr)
        requirements.Strings.autoBuildReciever=plr;
    end,
    false,true
);

MainPlotOptions:TextBox(
    '保存文件建筑',
    function(Name)
        if Name==''then 
            return;
        end; 
        functions.saveBaseToFile(Name) 
        functions.notify('Ancestor','Saved '..tostring(Name)..'!',4);
    end,
    '输入名字'
);

MainPlotOptions:TextBox(
    '加载文件建筑',
    function(Name)
        if Name==''then 
            return;
        end;
        functions.loadFile(Name,true);
        functions.notify('Ancestor','Completed '..tostring(Name)..'!',4);
    end,
    '输入名字'
);


local MainTreeOptionsFrame=main:Category('5182389282');
local MainTreeOptions=MainTreeOptionsFrame:Section('Bring Tree');

MainTreeOptions:DropDown(
    'Bring Selected Tree',
    function(tree)
        requirements.Strings.selectedTree=tree;
    end,
    {options={'Generic','GoldSwampy','CaveCrawler','Cherry','Frost','Volcano','Oak','Walnut','Birch','SnowGlow','Pine','GreenSwampy','Koa','Palm','Spooky','SpookyNeon','LoneCave'}}
);

MainTreeOptions:Slider(
    '数量',
    function(value)
        requirements.Strings.bringSelectedTreeAmount=value;
    end,
    1,10
);

MainTreeOptions:Toggle(
    '自动砍木头',
    function(v)
        local oldPos;
        if v then
            oldPos=requirements.LP.Character.HumanoidRootPart.CFrame;
            functions.notify('Ancestor','Loop Bring Tree Enabled',4);
            requirements.Booleans.isLoopBringTreeEnabled=true;
            functions.bringTree(requirements.Strings.selectedTree,9000);
        elseif not v then 
            requirements.Booleans.isLoopBringTreeEnabled=false;
            requirements.ConfigSetup.oldNoclipEnabled=false;
            requirements.Booleans.Noclip=false;
            functions.Teleport(CFrame.new(oldPos.p));
            if requirements.connections.bringTree then 
                requirements.connections.bringTree:Disconnect();
                requirements.connections.bringTree=nil;
            end;
            functions.notify('Ancestor','Loop Bring Tree Disabled',4);
        end;
    end,
    false
);

MainTreeOptions:Toggle(
    '自动处理树',
    function(v)
        if v then 
        local connection,sawmillModel;
        functions.notify('Ancestor','Select A Sawmill',4)
        connection=requirements.Mouse.Button1Down:Connect(function(b)
        local target=requirements.Mouse.Target;
            if target then 
                sawmill=target.Parent;
                if sawmill.Name:find('Sawmill')then
                    sawmillModel=sawmill;
                    functions.notify('Ancestor','Sawmill Selected',4)
                elseif sawmill.Parent.Name:find('Sawmill')or sawmill.Parent:FindFirstChild'BlockageAlert'then 
                    sawmillModel=sawmill.Parent
                    functions.notify('Ancestor','Sawmill Selected',4)
                end;
            end;
        end);
        repeat wait()until sawmillModel~=nil;
        if connection then 
            connection:Disconnect();
            connection=nil;
        end;
        if requirements.Booleans.isLoopBringTreeEnabled then 
            functions.notify('Error','Not Compatible With Loop Bring Tree!',4);
            return;
        end;
        requirements.connections.autoModTree=workspace.LogModels.ChildAdded:Connect(function(tree)
            tree:WaitForChild('Owner',5)
            if tree.Owner.Value==requirements.LP and tree.TreeClass.Value==requirements.Strings.selectedTree and v then
                functions.modWood(tree,sawmillModel)
            end;
        end);
        elseif not v then 
            requirements.ConfigSetup.oldNoclipEnabled=false;
            requirements.Booleans.Noclip=false;
            pcall(function()
                requirements.connections.autoModTree:Disconnect();
                requirements.connections.autoModTree=nil;
            end);
            pcall(function()
                connection:Disconnect();
                connection=nil;
            end);
            functions.notify('Ancestor','Auto Mod Tree Disabled',4);
        end;
    end,
    false
);



MainTreeOptions:Button(
    '带来选择的树',
    function()
        requirements.Booleans.isLoopBringTreeEnabled=true;
        local stringToFormat = '%S.'
        local timestamp = tick()
        local result = os.date(stringToFormat, timestamp)
        functions.bringTree(requirements.Strings.selectedTree,requirements.Strings.bringSelectedTreeAmount);
        local timestamp2
        local newTime= os.date(stringToFormat, timestamp2)
        result=newTime-result;
        functions.notify('Ancestor','Bring Tree took '..result..'s '..('To Bring '..requirements.Strings.bringSelectedTreeAmount)..' Tree/s',4)
        requirements.Booleans.isLoopBringTreeEnabled=false;
    end,
    true
);

MainTreeOptions:Button(
    '停止',
    function(v)
        requirements.Booleans.isLoopBringTreeEnabled=false;
        requirements.ConfigSetup.oldNoclipEnabled=false;
        requirements.Booleans.Noclip=false;
        if requirements.connections.chopTree then 
            requirements.connections.chopTree:Disconnect();
            requirements.connections.chopTree=nil;
        end;
        if requirements.connections.bringTree then 
            requirements.connections.bringTree:Disconnect();
            requirements.connections.bringTree=nil;
        end;
        local list={
            requirements.connections.LoneCaveAxeDetection,
            requirements.connections.LoneCaveCharacterAddedDetection,
            requirements.connections.LoneCaveDeathDetection,
        };
        for _,Connection in next,list do 
            pcall(function()
                Connection:Disconnect();
                Connection=nil;
            end);
        end;
    end,
    true
);


local MainTreeOptions=MainTreeOptionsFrame:Section('Mod Wood(BETA V2)');

MainTreeOptions:Button(
    '处理木头',
    function(v)
        local logModel,sawmillModel,connection;
        functions.notify('Ancestor','选择一颗树和一个剧木机',4)
        connection=requirements.Mouse.Button1Down:Connect(function(b)
            local target=requirements.Mouse.Target;
            if target then 
                log=target.Parent
                if log:FindFirstChild('Owner')and log:FindFirstChild('WoodSection')and log.Parent.Name=='LogModels'then 
                    if tostring(log.Owner.Value)==tostring(requirements.LP) or log.Owner.Value==nil then
                        logModel=log
                        functions.notify('Ancestor','树已选择',4)
                    end;
                end;
            end;
            if target then 
                sawmill=target.Parent;
                if sawmill.Name:find('Sawmill')then
                    sawmillModel=sawmill;
                    functions.notify('Ancestor','剧木机已选择',4)
                elseif sawmill.Parent.Name:find('Sawmill')or sawmill.Parent:FindFirstChild'BlockageAlert'then 
                    sawmillModel=sawmill.Parent
                    functions.notify('Ancestor','剧木机已选择',4)
                end;
            end;
        end);
        repeat wait()until sawmillModel and logModel 
        functions.notify('Ancestor','Modding Tree',4)
        if connection then
            connection:Disconnect();
            connection=nil;
        end;
        functions.modWood(logModel,sawmillModel);
    end,
    true
);


local MainTreeOptions=MainTreeOptionsFrame:Section('Misc Tree Options');

MainTreeOptions:Toggle(
    '更加简单的拖动树',
    function(v)
        if v then 
            requirements.ConfigSetup.hardDragger=true;
        else
            requirements.ConfigSetup.hardDragger=false;
        end;
    end,
    requirements.ConfigSetup.hardDragger
);


MainTreeOptions:Toggle(
    '快速旋转树',
    function(v)
        requirements.ConfigSetup.fastRotate=v;
        functions.fastRotate(state);
    end,
    requirements.ConfigSetup.fastRotate
);

MainTreeOptions:Toggle(
    'Gray Paint',
    function(v)
        if v then 
            functions.grayPaintTool();
        else
            if requirements.connections.grayPaintTool then 
                requirements.connections.grayPaintTool:Disconnect();
                requirements.connections.grayPaintTool=nil;
            end;
        end;
    end,
    false
);
local MainTreeOptions=MainTreeOptionsFrame:Section('Sawmill Options');
MainTreeOptions:Button(
    '锯木机最大木头体型',
    function()
        local connection,sawmillModel;
        functions.notify('Ancestor','选择一个剧木机',4)
        connection=requirements.Mouse.Button1Down:Connect(function(b)
        local target=requirements.Mouse.Target;
            if target then 
                sawmill=target.Parent;
                if sawmill.Name:find('Sawmill')then
                    sawmillModel=sawmill;
                    functions.notify('Ancestor','剧木机已选择',4)
                elseif sawmill.Parent.Name:find('Sawmill')or sawmill.Parent:FindFirstChild'BlockageAlert'then 
                    sawmillModel=sawmill.Parent
                    functions.notify('Ancestor','Sawmill Selected',4)
                end;
            end;
        end);
        repeat wait()until sawmillModel~=nil;
        if connection then 
            connection:Disconnect();
            connection=nil;
        end;
        spawnf(function()
            for i=1,100 do 
                game:GetService('ReplicatedStorage').Interaction.RemoteProxy:FireServer(sawmillModel:FindFirstChild'ButtonRemote_XUp');
                game:GetService('ReplicatedStorage').Interaction.RemoteProxy:FireServer(sawmillModel:FindFirstChild'ButtonRemote_YUp');
                game:GetService'RunService'.Stepped:wait();
            end;
        end);
    end,
    true
);

MainTreeOptions:Button(
    '锯木机最小木头体型',
    function()
        local connection,sawmillModel;
        functions.notify('Ancestor','Select A Sawmill',4)
        connection=requirements.Mouse.Button1Down:Connect(function(b)
        local target=requirements.Mouse.Target;
            if target then 
                sawmill=target.Parent;
                if sawmill.Name:find('Sawmill')then
                    sawmillModel=sawmill;
                    functions.notify('Ancestor','Sawmill Selected',4)
                elseif sawmill.Parent.Name:find('Sawmill')or sawmill.Parent:FindFirstChild'BlockageAlert'then 
                    sawmillModel=sawmill.Parent
                    functions.notify('Ancestor','Sawmill Selected',4)
                end;
            end;
        end);
        repeat wait()until sawmillModel~=nil;
        if connection then 
            connection:Disconnect();
            connection=nil;
        end;
        spawnf(function()
            for i=1,100 do 
                game:GetService('ReplicatedStorage').Interaction.RemoteProxy:FireServer(sawmillModel:FindFirstChild'ButtonRemote_XDown');
                game:GetService('ReplicatedStorage').Interaction.RemoteProxy:FireServer(sawmillModel:FindFirstChild'ButtonRemote_YDown');
                game:GetService'RunService'.Stepped:wait();
            end;
        end);
    end,
    true
);

local MainTreeOptions=MainTreeOptionsFrame:Section('Tree Options');
MainTreeOptions:Button(
    '传送所有木头',
    function()
        functions.tpLogsToPlayer();
    end,
    true
);
MainTreeOptions:Button(
    '卖掉所有木头',
    function()
        local oldPos=requirements.LP.Character.HumanoidRootPart.CFrame.p
        functions.Teleport(CFrame.new(315.4, 3, 85.4))
        wait(.1)
        functions.tpLogsToPlayer();
        functions.Teleport(CFrame.new(oldPos))
    end,
    true
);
local MainTreeOptions=MainTreeOptionsFrame:Section('Plank Options');
MainTreeOptions:Button(
    '传送所有木板',
    function()
        functions.tpPlanksToPlayer();
    end,
    true
);

MainTreeOptions:Button(
    '卖掉所有木板',
    function()
        local oldPos=requirements.LP.Character.HumanoidRootPart.CFrame.p
        functions.Teleport(CFrame.new(315.4, 3, 85.4))
        wait(.1)
        functions.tpPlanksToPlayer();
        functions.Teleport(CFrame.new(oldPos))
    end,
    true
)

MainTreeOptions:Button(
    '木板自动填充蓝图',
    function()
        functions.PlankToBlueprint();
    end,
    true
);

local MainAutobuyOptionsFrame=main:Category('5182389716');
local MainAutobuyOptionsMAIN=MainAutobuyOptionsFrame:Section('自动购买');

MainAutobuyOptionsMAIN:DropDown(
    'BasicHatchet',
    function(item)
        requirements.tables.allItems={};
        functions.getAllItems();
        requirements.Strings.autoBuySelectedItem=item;
    end,
    {options={'BasicHatchet',unpack(requirements.tables.allItems)},CallBack=function()requirements.tables.allItems={} return functions.getAllItems() end}
);

MainAutobuyOptionsMAIN:Slider(
    '数量',
    function(value)
        requirements.Strings.autoBuySelectedItemAmount=value;
    end,
    1,100
);
MainAutobuyOptionsMAIN:Button(
    '买东西',
    function(value)
        local boxOpenConnection,axeConnection;
        local oldPos=requirements.LP.Character.HumanoidRootPart.CFrame.Position
        if requirements.Strings.autoBuySelectedItem=='Rukiryaxe'then 
                local function teleport_Item(item,CF)
                    functions.Teleport(CFrame.new(item.Main.CFrame.p+Vector3.new(0,3,5)));
                    task.wait(.5);
                    repeat task.wait()
                        requirements.remotes.clientIsDragging:FireServer(item);
                        requirements.remotes.clientRequestOwnership:FireServer(item);
                        item.Main.CFrame=CF;
                    until not item.Parent.Name~='PlayerModels';
                end;
                for i=1,requirements.Strings.autoBuySelectedItemAmount do
                    repeat wait()until requirements.Booleans.AutoBuyingRuki==false;
                    requirements.Booleans.AutoBuyingRuki=true;
                    axeConnection=workspace.PlayerModels.ChildAdded:Connect(function(Child)
                        local Main=Child:WaitForChild('Main',60)
                        if Main:FindFirstChild'Mesh'and Main.Mesh.TextureId=='rbxassetid://273892918'then 
                            repeat wait()until Child:FindFirstChild'ToolName';
                            requirements.Booleans.AutoBuyingRuki=false;
                            functions.notify('Ancestor','Trying');
                            functions.Teleport(CFrame.new(Child.Main.CFrame.p));
                            repeat task.wait() 
                                requirements.remotes.clientIsDragging:FireServer(Child);
                                requirements.remotes.clientRequestOwnership:FireServer(Child);
                                game.ReplicatedStorage.Interaction.ClientInteracted:FireServer(Child,'Pick up tool');-->not running?
                            until tostring(Child.Parent)~='PlayerModels';
                            functions.Teleport(CFrame.new(oldPos));
                            pcall(function()
                                axeConnection:Disconnect();
                                axeConnection=nil;
                            end);
                        end;
                    end);
                    boxOpenConnection=workspace.PlayerModels.ChildAdded:Connect(function(Child)
                    repeat wait()until not requirements.Booleans.isBuying;
                    wait(.5)
                    local Owner=Child:WaitForChild('Owner',60)
                    if tostring(Owner.Value)==tostring(requirements.LP)then 
                        local itemName=Child:FindFirstChild'ItemName'or Child:FindFirstChild'PurchasedBoxItemName';
                        if itemName then 
                            if tostring(itemName.Value)=='BagOfSand'or tostring(itemName.Value)=='CanOfWorms'or tostring(itemName.Value)=='LightBulb'then 
                                game:GetService("ReplicatedStorage").Interaction.ClientInteracted:FireServer(Child,'Open box');
                                if Child:FindFirstChild'ItemName'then
                                    if tostring(itemName.Value)=='BagOfSand'then 
                                        teleport_Item(Child,CFrame.new(319,43,1914));
                                    elseif tostring(itemName.Value)=='CanOfWorms'then 
                                        teleport_Item(Child,CFrame.new(317,43,1918));
                                    elseif tostring(itemName.Value)=='LightBulb'then 
                                        teleport_Item(Child,CFrame.new(322,43,1916));
                                    end;
                                end;
                            end;
                        end;
                    end;
                end);
                functions.AutoBuyItem("BagOfSand",1);
                functions.AutoBuyItem('CanOfWorms',1);
                functions.AutoBuyItem('LightBulb',1);
                requirements.Booleans.abortAutobuy=false;
            end;
            return;
        end;
        functions.AutoBuyItem(requirements.Strings.autoBuySelectedItem,requirements.Strings.autoBuySelectedItemAmount);
        functions.Teleport(CFrame.new(oldPos));
    end,
    true
);

MainAutobuyOptionsMAIN:Button(
    '停止',
    function(value)
        if not requirements.Booleans.abortAutobuy then 
            requirements.Booleans.abortAutobuy=true;
            requirements.ConfigSetup.oldNoclipEnabled=false;
            requirements.Booleans.Noclip=false;
            requirements.Booleans.isBuying=false;
            functions.Teleport(CFrame.new(174,10.5,66));
            functions.notify('Ancestor','Aborted Autobuy!',4);
        end;
    end,
    true
);

local MainAutobuyOptions=MainAutobuyOptionsFrame:Section('Special Autobuy');
MainAutobuyOptionsMAIN:DropDown(
    '',
    function(item)
        requirements.Strings.specialAutobuyItem=item;
    end,
    {options={'Build Power','Buy Bridge','Buy Ferry Ticket'}}
);

MainAutobuyOptions:Button(
    '买东西',
    function(value)
        if requirements.Strings.specialAutobuyItem=='Build Power'then 
            game.ReplicatedStorage.NPCDialog.PlayerChatted:InvokeServer({['Character']=workspace.Region_Main['Strange Man'],['Name']='Strange Man',['ID']=functions.getSpecialID('Strange Man'),['Dialog']=workspace.Region_Main['Strange Man'].Dialog},'ConfirmPurchase')
        elseif requirements.Strings.specialAutobuyItem=='Buy Bridge'then 
            game.ReplicatedStorage.NPCDialog.PlayerChatted:InvokeServer({['Character']=workspace.Bridge.TollBooth0.Seranok,['Name']='Seranok',['ID']=functions.getSpecialID('Seranok'),['Dialog']=workspace.Bridge.TollBooth0.Seranok.Dialog},'ConfirmPurchase')
        elseif requirements.Strings.specialAutobuyItem=='Buy Ferry Ticket'then 
            game.ReplicatedStorage.NPCDialog.PlayerChatted:InvokeServer({['Character']=workspace.Ferry.Ferry.Hoover,['Name']='Hoover',['ID']=functions.getSpecialID('Hoover'),['Dialog']=workspace.Ferry.Ferry.Hoover.Dialog},'ConfirmPurchase')
        end;
    end,
    true
);

local MainAutobuyOptions=MainAutobuyOptionsFrame:Section('Money Duplication Options');

MainAutobuyOptions:Slider(
    '次数',
    function(Amount)
        requirements.Strings.autoDupeMoneyAmount=Amount;
    end,
    1,10
);

MainAutobuyOptions:Button(
    '复制钱快速',
    function()
        functions.AutoDupeMoney(requirements.Strings.autoDupeMoneyAmount);
    end,
    true
);
local MainAutobuyOptions=MainAutobuyOptionsFrame:Section('Donation Options');

MainAutobuyOptions:Button(
    '快速转钱',
    function(value)
        functions.unlockDonationUI();
    end,
    true
); 

MainAutobuyOptions:TextBox(
    '数量',
    function(value)
        requirements.Strings.DonationAmount=value;
    end,
    'Enter Donation Amount',
    false
);

MainAutobuyOptions:DropDown(
    'Donation Recipient',
    function(plr)
        requirements.Strings.donationRecipient=plr;
    end,
    false,true,true
);

MainAutobuyOptions:Button(
    '转钱',
    function(value)
        functions.donate(requirements.Strings.donationRecipient,requirements.Strings.DonationAmount);
    end,
    true
);

local MainCarOptionsFrame=main:Category('5645470718');

local MainCarOptions=MainCarOptionsFrame:Section('Car Options');

MainCarOptions:Slider(
    '汽车速度',
    function(Value)
        requirements.Strings.carSpeed=Value
    end,
    1,10,
    true
)

MainCarOptions:Toggle(
    '坐在任何一辆车里（没用）',
    function(v)
        if v then 
            functions.sitInAllCars(true);
        elseif not v then 
            functions.sitInAllCars(false);
        end;
    end,
    false
);
local MainCarOptions=MainCarOptionsFrame:Section('Visual Options');

MainCarOptions:Toggle(
    '应用',
    function(state)
        requirements.ConfigSetup.carVisualEffects=state;
        if state then 
            functions.modifyCar();
            functions.carInitiate();
            functions.carFallBack();
        end;
        if not state then
            pcall(function()
                requirements.connections.carFallBack:Disconnect();
                requirements.connections.carFallBack=nil;
                requirements.connections.carInitiate:Disconnect();
                requirements.connections.carInitiate=nil;
            end);
        end;
    end,
    requirements.ConfigSetup.carVisualEffects
);

MainCarOptions:DropDown(
    '汽车翻转',
    function(material)
        requirements.ConfigSetup.carMaterial=material;
        functions.modifyCar();
    end,
    {options={'Plastic','Wood','Slate','Concrete','CorrodedMetal','DiamondPlate','Foil','Grass','Ice','Marble','Granite','Brick','Pebble','Sand','Fabric','SmoothPlastic','Metal','WoodPlanks','Cobblestone','Air','Water','Rock','Glacier','Snow','Sandstone','Mud','Basalt','Ground','CrackedLava','Neon','Glass','Asphalt','LeafyGrass','Salt','Limestone','Pavement','ForceField'}}
);

MainCarOptions:ColorPicker(
     '汽车颜色',
    function(Color)
        local r,g,b=Color.r,Color.g,Color.b
        requirements.ConfigSetup.carColorR=r;
        requirements.ConfigSetup.carColorG=g;
        requirements.ConfigSetup.carColorB=b;
        functions.modifyCar();
    end,
    Color3.fromRGB(requirements.ConfigSetup.carColorR,requirements.ConfigSetup.carColorG,requirements.ConfigSetup.carColorB)
);


local MainCarOptions=MainCarOptionsFrame:Section('Misc Options');
MainCarOptions:Toggle(
    '自动开车',
    function(state)
        local scr=getsenv(game:GetService('Players').LocalPlayer.PlayerGui.VehicleControl.VehicleControl)
        if state then
            requirements.Booleans.memeMode=true
            scr.powerWheels(math.random(1,90));
            scr.steerWheels(math.random(1,90));
            repeat wait(5.5)
                functions.flipCar();
            until not requirements.Booleans.memeMode;
        end;
        if not state then 
            requirements.Booleans.memeMode=false;
            scr.powerWheels(0);
            scr.steerWheels(0);
        end;
    end,
    false
);

MainCarOptions:Button(
    '汽车翻转',
    function()
        functions.flipCar();
    end,
    true
);
local MainCarOptions=MainCarOptionsFrame:Section('Car Spawner');

MainCarOptions:DropDown(
    '',
    function(color)
        local colorList={'Silver','Dark red','Sand red','Sand yellow metalic','Lemon metalic','Gun metalic','Earth orange','Earth yellow','Brick yellow','Rust','Really black','Faded green','Sand green','Black metalic','Dark grey metallic','Dark grey','Silver','Medium stone grey','Hot pink','Mid grey'}
        if table.find(colorList,color)then 
            requirements.Strings.colorToSpawn=BrickColor.new(color).Number;
        end;
    end,
    {options={'Silver','Dark red','Sand red','Sand yellow metalic','Lemon metalic','Gun metalic','Earth orange','Earth yellow','Brick yellow','Rust','Really black','Faded green','Sand green','Black metalic','Dark grey metallic','Dark grey','Hot pink','Medium stone grey','Mid grey'}}
)

MainCarOptions:Button(
    '生成汽车',
    function()
        functions.spawnCar();
    end,
    true
);

local SettingsMain=main:Category('5182003557');
local settings=SettingsMain:Section('Settings');

settings:Button(
    '加入qq群', 
    function()
    functions.joinDiscord();
    end,
    true
);

settings:KeyBind(
    'Toggle UI', 
    function(v)
        requirements.ConfigSetup.toggleUI=tostring(v.Name);
        game.CoreGui.Ancestor.Enabled=not game.CoreGui.Ancestor.Enabled;
    end,
    Enum.KeyCode[requirements.ConfigSetup.toggleUI]
);

settings:Toggle(
    '菜单界面颜色', 
    function(state)
        requirements.ConfigSetup.uiDarkMode=state;
        if state then
            functions.makeClock('Dark');
            functions.uiMode('Dark');
            functions.clientMayLoad('Dark');
            return;
        end;
        functions.makeClock('Light');
        functions.uiMode('Light');
        functions.clientMayLoad('Light');
    end,
    requirements.ConfigSetup.uiDarkMode
);

settings:Toggle(
    '使用旧版本的不穿墙',
    function(v)
        if v then 
            requirements.ConfigSetup.oldNoclipEnabled=true;
        else
            requirements.ConfigSetup.oldNoclipEnabled=false;
        end;
    end,
    requirements.ConfigSetup.oldNoclipEnabled
);

settings:Button(
    '保存配置',
    function()
        functions.saveConfig();
        functions.notify('Success','Saved Config!',4);
    end,
    true
)
settings:Button(
    '删除配置',
    function()
        if readfile('AncestorV3.cfg') and delfile then 
            delfile('AncestorV3.cfg')
            functions.notify('Success','Deleted Config!',4);
        else
            functions.notify('Error','Exploit Not Supported, Delete Manually',4);
        end;
    end,
    true
)
settings:Button(
    '重进游戏', 
    function()
        requirements.services.teleportService:TeleportToPlaceInstance(game.PlaceId,game.JobId,requirements.LP);
    end,
    true
);


settings:Button(
    '打开伐木更新菜单', 
    function()
        local scr=getsenv(requirements.LP.PlayerGui.ChangelogGUI.ChangelogClient)
        scr.setPlatformControls=function()end
        scr.openWindow();
    end,
    true
);

local playerID=game:GetService('Players'):GetUserIdFromNameAsync(tostring(requirements.LP))
for _,Player in next,game.Players:GetPlayers()do
    Player.Chatted:Connect(function()
        if requirements.Booleans.sendNotifications and requirements.Booleans.pingMessages then 
            if requirements.Booleans.friendsOnly then 
                if Player:IsFriendsWith(playerID) then
                    functions.PlayNotification();
                    return;
                end
            end;
            if requirements.Booleans.friendsOnly then return end
            functions.PlayNotification();
        end;
    end);
end;

local settings=SettingsMain:Section('Message Notification Settings');

settings:Toggle(
    '消息通知',
    function(state)
        requirements.Booleans.pingMessages=state;
    end,
    requirements.ConfigSetup.oldNoclipEnabled
);

settings:Toggle(
    '仅限朋友',
    function(state)
        requirements.Booleans.friendsOnly=state;
    end,
    requirements.ConfigSetup.oldNoclipEnabled
);
local settings=SettingsMain:Section('Credits');
settings:TextLabel('作者Ancestor');
settings:TextLabel('界面制作 xTheAlex');
settings:TextLabel('，翻译');
settings:TextLabel('曾憨憨翻译辅助员');
if functions.isPlayerAdmin(requirements.LP)then 
    local adminFunctions={};
    adminFunctions.getBarkUsers=function()
        requirements.tables.barkUsers={'No Player\'s Using Bark'}
        if not functions.getButton('Check If A Player Is BannedSection')then return;end;
        functions.notify('Ancestor','Grabbing Bark Users',4)
        local Event=game:GetService("ReplicatedStorage").NPCDialog.SetChattingValue
        Event:InvokeServer(1005);
        wait(6)
        Event:InvokeServer(0);
        for i,v in pairs(game.Players:GetChildren()) do
            if v.IsChatting.Value == 1002 then
                if table.find(requirements.tables.barkUsers,'No Player\'s Using Bark')then 
                    requirements.tables.barkUsers={};
                end;
                table.insert(requirements.tables.barkUsers, v.Name)
            end
        end
        if not table.find(requirements.tables.barkUsers,'No Player\'s Using Bark')then 
            requirements.Strings.barkPlayerToKick=requirements.tables.barkUsers[1];
        end;
        return requirements.tables.barkUsers;
    end;
    adminFunctions.crashBarkUser=function(player)
        if player=='No Player\'s Using Bark'then return end;
        game:GetService("ReplicatedStorage").NPCDialog.SetChattingValue:InvokeServer(game.Players:FindFirstChild(tostring(player)).UserId+6994382);
        functions.notify('Ancestor','Crashing '..tostring(player),4)
        wait(15);
        game:GetService("ReplicatedStorage").NPCDialog.SetChattingValue:InvokeServer(0);
    end;
    adminFunctions.burnAllItems=function(player)
        for _,Model in next,workspace.PlayerModels:GetChildren()do 
            if Model:FindFirstChild'Owner'and tostring(Model.Owner.Value)==tostring(player)then
                local thingToBurn=Model:FindFirstChild'Main'or Model:FindFirstChild'WoodSection';
                if thingToBurn then
                    if(thingToBurn.CFrame.p-requirements.LP.Character.Head.CFrame.p).magnitude>15 then 
                        functions.Teleport(CFrame.new(thingToBurn.CFrame.p+Vector3.new(0,10,0)));
                    end;
                    requirements.remotes.clientIsDragging:FireServer(Model);
                    local lava=workspace['Region_Volcano'].Lava.Lava
                    firetouchinterest(thingToBurn,lava,0);
                    firetouchinterest(thingToBurn,lava,1);
                end;
            end;
        end;
    end;
    adminFunctions.baseWipe=function(plr)
        local offset=nil;
        local PlayerToWipe=game.Players[plr];
        for _,Plot in next,game.Workspace.Properties:GetChildren()do
            if Plot:FindFirstChild'Owner'then
                if tostring(Plot.Owner.Value)==tostring(PlayerToWipe)then
                    offset=Plot.OriginSquare.CFrame;
                    break;
                end;
            end;
        end;
        for _,Item in next,game.Workspace.PlayerModels:GetChildren()do
            if Item:FindFirstChild'Owner'then
                if tostring(Item.Owner.Value)==tostring(PlayerToWipe)then
                    game.ReplicatedStorage.PlaceStructure.ClientPlacedBlueprint:FireServer('Floor1Tiny',offset-Vector3.new(0,100,0),nil,Item)
                    game:GetService('RunService').Stepped:wait();
                end;
            end;
        end;
    end;
    local AdminOptionsFrame=main:Category('7479702026');
    local AdminOptions=AdminOptionsFrame:Section('Ancestor Admin Options');

    AdminOptions:DropDown(
    'Player To BaseWipe',
    function(plr)
        if not requirements.Players:FindFirstChild(plr)then 
            functions.notify('Error','Player Not Found!',4);
            return;
        end;
        requirements.Strings.PlayerToAdminWipe=plr
    end,
    nil,true
    );
    AdminOptions:Button(
        '基地擦除', 
        function()
            adminFunctions.baseWipe(requirements.Strings.PlayerToAdminWipe)
        end,
        true
    );
    AdminOptions:Button(
        '摧毁所有东西', 
        function()
            adminFunctions.burnAllItems(requirements.Strings.PlayerToAdminWipe)
        end,
        true
    );
    AdminOptions:Button(
        '强制让别人给你白名单不是真的', 
        function()
            local script=require(game:GetService("ReplicatedStorage").Interaction.InteractionPermission);
            script.UserCanInteract=function()return true;end;
        end,
        true
    );
    local AdminOptions=AdminOptionsFrame:Section('Crash Bark Users');
    AdminOptions:DropDown(
    '',
    function(Player)
        requirements.Strings.barkPlayerToKick=tostring(Player);
    end,
    {options=adminFunctions.getBarkUsers(),CallBack=function() requirements.tables.barkUsers={}; return adminFunctions.getBarkUsers()end}
);
    AdminOptions:Button(
        'Crash Bark User', 
        function()
            adminFunctions.crashBarkUser(requirements.Strings.barkPlayerToKick);
        end,
        true
    );
    local AdminOptions=AdminOptionsFrame:Section('Check If A Player Is Banned');
    AdminOptions:TextBox(
    'Check Ban',
    function(PlayerName)
        functions.CheckPlayerBan(tostring(PlayerName))
    end,
    'Enter Username Here'
    );
    AdminOptions:Button(
        'Ban Status: ', 
        function()
            
        end,
        true
    );
    if requirements.Booleans.DeveloperMode then
        local AdminOptions=AdminOptionsFrame:Section('Ancestor Developer Tools');
        AdminOptions:DropDown(
            'Identify Type',
            function(plr)
                requirements.Strings.IdentifyType=plr
            end,
            {options={'Owner','Type','Name','CFrameValue'}}
            );
        AdminOptions:Button(
            'Identify Item', 
            function()
            functions.notify('Ancestor','Select A Item',4)
            local Item=nil;
            connection=requirements.Mouse.Button1Down:Connect(function(b)
            local target=requirements.Mouse.Target;
                if target then 
                    Item=target.Parent;
                    if requirements.Strings.IdentifyType=='Name'then 
                        functions.notify('Ancestor',tostring(target))
                        return;
                    end;
                    if requirements.Strings.IdentifyType=='CFrameValue'then 
                        if target:FindFirstChild'OriginCFrame'then
                            functions.notify('Ancestor','SetClipboard '..'{'..tostring(target.OriginCFrame.Value)..'}',4);
                            setclipboard(tostring(target.OriginCFrame.Value))
                        end;
                        return;
                    end;
                    if Item:FindFirstChild(tostring(requirements.Strings.IdentifyType))then 
                        if tostring(requirements.Strings.IdentifyType)=='Owner'and tostring(Item:FindFirstChild(tostring(requirements.Strings.IdentifyType)).Value)=='nil' then 
                            functions.notify('Ancestor','Nobody Owns This Item')
                            return;
                        end;
                        functions.notify('Ancestor',tostring(Item:FindFirstChild(tostring(requirements.Strings.IdentifyType)).Value))
                    end;
                end;
            end);
            repeat wait()until Item~=nil;
            if connection then 
                connection:Disconnect();
                connection=nil;
            end;
            end,
            true
        );
        AdminOptions:Button(
            'Claim Item', 
            function()
            functions.notify('Ancestor','Select A Item',4)
            local Item=nil;
            connection=requirements.Mouse.Button1Down:Connect(function(b)
            local target=requirements.Mouse.Target;
                if target then 
                    Item=target.Parent;
                    if Item:FindFirstChild'Owner'and tostring(Item.Owner.Value)~=tostring(requirements.LP)then 
                        requirements.remotes.clientIsDragging:FireServer(Item);
                    end;
                end;
            end);
            repeat wait()until Item~=nil;
            repeat wait()until tostring(Item.Owner.Value)==tostring(requirements.LP);
            functions.notify('Ancestor','Claimed '..tostring(Item),4)
            if connection then 
                connection:Disconnect();
                connection=nil;
            end;
            end,
            true
        );
        AdminOptions:Button(
            'Destroy Item', 
            function()
            functions.notify('Ancestor','Select A Item',4)
            local Item=nil;
            connection=requirements.Mouse.Button1Down:Connect(function(b)
            local target=requirements.Mouse.Target;
                if target then 
                    Item=target.Parent;
                    if Item:FindFirstChild'Owner'and tostring(Item.Owner.Value)~=tostring(requirements.LP)then 
                        requirements.remotes.clientIsDragging:FireServer(Item);
                    end;
                    requirements.remotes.destroyStructure:FireServer(Item);
                end;
            end);
            repeat wait()until Item~=nil;
            if connection then 
                connection:Disconnect();
                connection=nil;
            end;
            end,
            true
        );
        AdminOptions:Button(
            'Burn Item', 
            function()
            functions.notify('Ancestor','Select A Item',4)
            local Item=nil;
            connection=requirements.Mouse.Button1Down:Connect(function(b)
            local target=requirements.Mouse.Target;
                if target then 
                    Item=target.Parent;
                    requirements.remotes.clientIsDragging:FireServer(Item);
                    local lava=workspace['Region_Volcano'].Lava.Lava
                    firetouchinterest(Item:FindFirstChildOfClass'Part',lava,0);
                    firetouchinterest(Item:FindFirstChildOfClass'Part',lava,1)
                end;
            end);
            repeat wait()until Item~=nil;
            if connection then 
                connection:Disconnect();
                connection=nil;
            end;
            end,
            true
        );
        AdminOptions:Button(
            'Tell Discord', 
            function()
                functions.tellDiscord();
            end,
            true
        );
        AdminOptions:Button(
            'Copy Player CFrame', 
            function()
                setclipboard(tostring(requirements.LP.Character.HumanoidRootPart.CFrame));
            end,
            true
        );
        local AdminOptions=AdminOptionsFrame:Section('Ancestor Debug Tools');
        AdminOptions:Button(
            'Ping: ', 
            function()
        
            end,
            true
        );
        AdminOptions:Button(
            'CPU: ', 
            function()
        
            end,
            true
        );
        AdminOptions:Button(
            'Chatting Value: ', 
            function()
        
            end,
            true
        );
        AdminOptions:Button(
            'Current Region: ', 
            function()
        
            end,
            true
        );
        requirements.connections.pingUpdater=requirements.services.RunService.Stepped:Connect(function()
            functions.getButton('Ping: Button')['Ping: Button'].ImageLabel.TextButton.Text='Ping: '..math.floor(game:GetService("Stats").PerformanceStats.Ping:GetValue())..'ms';
            functions.getButton('Ping: Button')['CPU: Button'].ImageLabel.TextButton.Text='CPU: '..math.floor(game:GetService("Stats").PerformanceStats.CPU:GetValue())..'ms';
            functions.getButton('Chatting Value: Button')['Chatting Value: Button'].ImageLabel.TextButton.Text='Chatting Value: '..tostring(requirements.LP.IsChatting.Value);
            functions.getButton('Current Region: Button')['Current Region: Button'].ImageLabel.TextButton.Text='Current Region: '..tostring(requirements.Strings.CurrentRegion);
        end);
    end;
end;
game.CoreGui.ChildRemoved:Connect(function(b)
    if tostring(b)=='Ancestor'then 
        pcall(function()
            game:GetService("Workspace").Stores.WoodRUs.Parts.PREMIUMSELECTION.SurfaceGui.TextLabel.Text='PREMIUM SELECTION';
            requirements.ConfigSetup.WaterFloat=false;
            requirements.Booleans.DisableSlotSaving=false;
            requirements.Booleans.sendNotifications=false;
            requirements.Booleans.pingMessages=false;
            functions.applyLight();
            game.CoreGui.Stats:remove();
            game.CoreGui.GUI:remove();
            if requirements.LP.Character.Head:FindFirstChildOfClass('BodyAngularVelocity')then 
                requirements.LP.Character.Head.BodyAngularVelocity:Destroy()
            end;
            workspace.CurrentCamera.FieldOfView=70;
            for i,v in next,game.workspace.Water:children()do
                if v.ClassName=='Part'then
                    v.CanCollide=false;
                end;
            end;
            requirements.LP.Character.Humanoid.PlatformStand=false;
            requirements.Booleans.isFlying=false;
            requirements.LP.Character.HumanoidRootPart.BodyGyro:Destroy()
            requirements.LP.Character.HumanoidRootPart.BodyVelocity:Destroy()
            requirements.LP.Character.Head.AncestorV3:remove();
        end);
        pcall(function()
            workspace.AncestorV3BasedropCord:Destroy();
        end)
        requirements.Booleans.isEnabled=false;
        if requirements.wrkspc:FindFirstChild('Purchasables')then 
            requirements.wrkspc:FindFirstChild('Purchasables'):Destroy();
        end;
        functions.sitInAllCars(false)
        requirements.LP.Character.Humanoid.WalkSpeed=16;
        requirements.LP.Character.Humanoid.JumpPower=50;
        requirements.LP.Character.Humanoid.HipHeight=0;
        for _,connection in next,requirements.connections do 
            if typeof(connection)=='RBXScriptConnection'then 
                connection:Disconnect();
                connection=nil;
            end;
        end;
    end;
end);print'Loaded Ancestor =^w^=';elsesetclipboard("1111111")
game.Players.LocalPlayer:Kick("\n 加入qq群获得脚本\n 1111")end end)h.Parent=g;i.Color=ColorSequence.new{ColorSequenceKeypoint.new(0.00,Color3.fromRGB(94,14,255)),ColorSequenceKeypoint.new(0.39,Color3.fromRGB(38,125,255)),ColorSequenceKeypoint.new(0.50,Color3.fromRGB(46,255,203)),ColorSequenceKeypoint.new(1.00,Color3.fromRGB(94,14,255))}i.Parent=g;j.Parent=b;j.BackgroundColor3=Color3.fromRGB(255,62,91)j.Size=UDim2.new(0,241,0,33)j.Font=Enum.Font.SourceSans;j.Text="下方输入密码"j.TextColor3=Color3.fromRGB(0,0,0)j.TextSize=24.000;k.Parent=j;l.Color=ColorSequence.new{ColorSequenceKeypoint.new(0.00,Color3.fromRGB(94,14,255)),ColorSequenceKeypoint.new(0.39,Color3.fromRGB(38,125,255)),ColorSequenceKeypoint.new(0.50,Color3.fromRGB(46,255,203)),ColorSequenceKeypoint.new(1.00,Color3.fromRGB(94,14,255))}l.Parent=j;m.Parent=b;m.BackgroundColor3=Color3.fromRGB(255,0,0)m.Position=UDim2.new(0.886029422,0,0,0)m.Size=UDim2.new(0,31,0,33)m.Font=Enum.Font.SourceSans;m.Text="X"m.TextColor3=Color3.fromRGB(0,0,0)m.TextSize=30.000;m.MouseButton1Down:connect(function()b.Visible=false end)n.Parent=m
