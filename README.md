local function translateText(text)
    if type(text) ~= "string" or text == "" then return text end
    local dict = {
        ["Nauru Hub"] = "（ ）汉化",
        ["Join our discord server now!"] = "sf徒弟（ ）汉化",
        ["Red Light Green Light"] = "红灯绿灯",
        ["Dalgona"] = "糖饼",
        ["Pentathlon"] = "五项",
        ["Tug of War"] = "拔河",
        ["Hide and Seek"] = "捉迷藏",
        ["Jump Rope"] = "跳绳",
        ["Glass Bridge"] = "玻璃桥",
        ["Mingle"] = "旋转木马",
        ["Final"] = "决赛",
        ["Rebel/Guard"] = "反叛/守卫",
        ["Others"] = "其他",
        ["Credits"] = "制作人员",
        
        ["Shape Completion"] = "形状完成",
        ["Auto Breath Relaxing"] = "自动放松呼吸",
        ["One Click Complete"] = "一键完成",
        ["Anti Crack Dalgona"] = "防裂糖饼",
        ["Read This"] = "阅读此内容",
        ["Do not pair anti crack with free lighter because it will likely auto complete your dalgona its better to disable lighter when you're gonna use anti crack with"] = "请勿将防裂与免费打火机同时使用，因为它可能会自动完成你的糖饼。使用防裂时最好禁用打火机。",
        ["Instant Complete Dalgona"] = "立即完成糖饼",
        
        ["Visibility/Win"] = "可见性/胜利",
        ["Reveal Glass"] = "显示玻璃",
        ["Glass Immunity"] = "玻璃免疫",
        ["The glass wont break when you step on the wrong glass"] = "当踩到错误的玻璃时，玻璃不会破碎",
        ["Teleport to End"] = "传送到终点",
        
        ["Rope Pulling"] = "拉绳",
        ["Auto QTE Pull"] = "自动QTE拉绳",
        ["100% QTE Guarantee"] = "100% QTE保证",
        ["You wont miss a single time with this feature"] = "使用此功能你一次都不会错过",
        
        ["Auto Win Mini Games"] = "自动赢得小游戏",
        ["Auto Ddakji"] = "自动打纸牌",
        ["Auto Flying Stone"] = "自动飞石",
        ["Auto Gonggi"] = "自动孔基",
        ["Auto Spinning Top"] = "自动旋转陀螺",
        ["Auto Jegi"] = "自动踢毽子",
        
        ["Movements"] = "移动",
        ["Anti Injuries"] = "防受伤",
        ["Auto Stop on Red Light"] = "红灯自动停止",
        
        ["Guns"] = "枪械",
        ["Silent Aim (BETA)"] = "静默瞄准 (BETA)",
        ["No Recoil"] = "无后坐力",
        ["Rapid Fire"] = "快速射击",
        ["Infinite Ammo"] = "无限弹药",
        ["Free Guard"] = "免费守卫",
        ["For this to work you need to have at least bought guard once in your account, if you already have bought guard once then it should work"] = "要使其生效，您的账户必须至少购买过守卫一次。如果您已经购买过，它应该能正常工作。",
        
        ["Sky Squid Game"] = "天空鱿鱼游戏",
        ["Throw Pole Aim"] = "投掷长矛瞄准",
        ["Automatically aims at the nearest alive player when throwing the pole."] = "投掷长矛时自动瞄准最近的存活玩家。",
        ["Anti Fall"] = "防坠落",
        
        ["QTE and Combat"] = "QTE与战斗",
        ["Auto QTE"] = "自动QTE",
        ["This also works for jump rope, sky squid game etc"] = "这也适用于跳绳、天空鱿鱼游戏等",
        ["Noclip Through Doors"] = "穿墙过门",
        ["Grab Teleport"] = "抓取传送",
        ["Anti Stun"] = "反眩晕",
        
        ["Combat"] = "战斗",
        ["Infinite Stamina"] = "无限体力",
        ["Infinite Sprint"] = "无限冲刺",
        ["Auto Dodge"] = "自动躲避",
        ["Delete Spikes"] = "删除尖刺",
        ["ESP"] = "透视",
        ["ESP Keys"] = "透视钥匙",
        ["ESP Exit Doors"] = "透视逃生门",
        ["ESP Hiders"] = "透视躲藏者",
        ["ESP Seekers"] = "透视抓捕者",
        
        ["Teleport"] = "传送",
        ["Teleport to Exit Door"] = "传送到逃生门",
        ["Teleport to Hider"] = "传送到躲藏者",
        
        ["Balloon ESP"] = "气球透视",
        ["Peabert ESP"] = "豌豆射手透视",
        ["Emotes"] = "表情",
        ["Select Emote"] = "选择表情",
        ["Play Emote"] = "播放表情",
        ["Stop Emote"] = "停止表情",
        ["Visuals"] = "视觉",
        ["Remove Effects"] = "移除特效",
        
        ["Instant Interact"] = "即时互动",
        ["Showcase Mode"] = "展示模式",
        ["Hides all the names so they wont be exposed when you're recording for a video"] = "隐藏所有名字，以免在录制视频时暴露。",
        ["Fly (BETA)"] = "飞行 (BETA)",
        ["Free Powers"] = "免费力量",
        ["Free Parkour Artist"] = "免费跑酷艺术家",
        ["Gives you the Parkour Artist powers such as double jump and dash"] = "给予你跑酷艺术家的能力，例如二段跳和冲刺。",
        
        ["Dialogues"] = "对话",
        ["Auto Skip Dialogues"] = "自动跳过对话",
        ["Auto Vote"] = "自动投票",
        ["Phase 1"] = "第一阶段",
        ["Phase 2"] = "第二阶段",
        ["Phase 3"] = "第三阶段",
        ["Phase 4"] = "第四阶段",
        ["Continue"] = "继续",
        
        ["Community"] = "社区sf徒弟汉化",
        ["Member Count : 6817"] = "成员数量 : 6817",
        ["Online Count : 317"] = "在线人数 : 317",
        ["Refresh Info"] = "刷新信息",
        ["Join Discord"] = "加入Discord",

        -- 新增：跳绳菜单翻译
        ["Rope Control"] = "绳索控制",
        ["Freeze Rope"] = "冻结绳索",
        ["Rope Immunity"] = "绳索免疫",
        ["The rope wont knock you off the platform and wont do anything to you"] = "绳索不会将你推下平台，也不会对你造成任何效果",
        ["Auto Balance"] = "自动平衡",
        ["Automatically keeps your balance perfectly"] = "自动完美保持你的平衡",
        ["No Balance Check"] = "无平衡检测",
        ["You can jump without needing to balance yourself"] = "你可以跳跃而无需自己保持平衡",
    }
    local keys = {}
    for k, _ in pairs(dict) do table.insert(keys, k) end
    table.sort(keys, function(a, b) return #a > #b end)
    for _, eng in ipairs(keys) do
        local chn = dict[eng]
        local pattern = "%f[%a]" .. eng:gsub("(%W)", "%%%1") .. "%f[%A]"
        text = text:gsub(pattern, chn)
    end
    return text
end

local function translateContainer(container)
    if not container then return end
    for _, obj in ipairs(container:GetDescendants()) do
        if obj:IsA("TextLabel") or obj:IsA("TextButton") or obj:IsA("TextBox") then
            local original = obj.Text
            if original and original ~= "" then
                local translated = translateText(original)
                if translated ~= original then
                    pcall(function() obj.Text = translated end)
                end
            end
            obj:GetPropertyChangedSignal("Text"):Connect(function()
                local currentText = obj.Text
                if currentText and currentText ~= "" then
                    local translated = translateText(currentText)
                    if translated ~= currentText then
                        pcall(function() obj.Text = translated end)
                    end
                end
            end)
        end
    end
end

local function onDescendantAdded(obj)
    if obj:IsA("TextLabel") or obj:IsA("TextButton") or obj:IsA("TextBox") then
        task.spawn(function()
            task.wait(0.05)
            local original = obj.Text
            if original and original ~= "" then
                local translated = translateText(original)
                if translated ~= original then
                    pcall(function() obj.Text = translated end)
                end
            end
            obj:GetPropertyChangedSignal("Text"):Connect(function()
                local currentText = obj.Text
                if currentText and currentText ~= "" then
                    local translated = translateText(currentText)
                    if translated ~= currentText then
                        pcall(function() obj.Text = translated end)
                    end
                end
            end)
        end)
    end
end

local function startTranslation()
    local containers = {
        game:GetService("Players").LocalPlayer:WaitForChild("PlayerGui"),
        game:GetService("CoreGui")
    }
    for _, container in ipairs(containers) do
        translateContainer(container)
        container.DescendantAdded:Connect(onDescendantAdded)
    end
end

startTranslation()
loadstring(game:HttpGet("https://rawscripts.net/raw/Ink-Game-Nauru-Hub-KEYLESS-AND-FREE-229089"))()
