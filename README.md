git init
git add .
git commit -m "Initial SkillMine project"
git branch -M main
git remote add origin https://github.com/yourusername/skillmine-app.git
git push -u origin main{
  "app": {
    "name": "SkillMine",
    "version": "1.0",
    "theme": {
      "primaryColor": "#0D1B2A",
      "secondaryColor": "#1B263B",
      "accentColor": "#00E5FF",
      "successColor": "#00C853",
      "errorColor": "#D50000",
      "backgroundColor": "#F5F7FA",
      "textPrimary": "#FFFFFF",
      "textSecondary": "#B0BEC5",
      "font": "Inter",
      "borderRadius": 12
    },
    "navigation": {
      "type": "bottom_tab",
      "tabs": [
        { "id": "home", "label": "Home", "icon": "home" },
        { "id": "tasks", "label": "Tasks", "icon": "flash" },
        { "id": "wallet", "label": "Wallet", "icon": "wallet" },
        { "id": "leaderboard", "label": "Rank", "icon": "trophy" },
        { "id": "profile", "label": "Profile", "icon": "user" }
      ]
    }
  },

  "screens": {

    "home": {
      "layout": "column",
      "backgroundColor": "#0D1B2A",
      "components": [
        {
          "type": "card",
          "title": "Welcome Miner",
          "style": { "backgroundColor": "#1B263B" },
          "content": [
            { "type": "text", "value": "Skill Hash Score: 87%", "color": "#00E5FF" },
            { "type": "text", "value": "Token Balance: 120", "color": "#FFFFFF" }
          ]
        },
        {
          "type": "button",
          "text": "START MINING",
          "color": "#00E5FF",
          "action": "navigate:tasks"
        },
        {
          "type": "list",
          "title": "Available Tasks",
          "items": [
            { "label": "Translate Slang", "reward": "2 Tokens" },
            { "label": "Verify Image", "reward": "3 Tokens" },
            { "label": "Rate Advertisement", "reward": "1 Token" }
          ]
        }
      ]
    },

    "tasks": {
      "layout": "column",
      "backgroundColor": "#F5F7FA",
      "components": [
        {
          "type": "card",
          "title": "Current Task",
          "style": { "backgroundColor": "#FFFFFF" },
          "content": [
            { "type": "text", "value": "Translate this slang to English:" },
            { "type": "text", "value": "“Wahala dey”", "style": { "fontWeight": "bold" } },
            { "type": "input", "placeholder": "Enter your answer" },
            { "type": "timer", "duration": 120 },
            {
              "type": "button",
              "text": "SUBMIT TASK",
              "color": "#00C853",
              "action": "navigate:verification"
            }
          ]
        }
      ]
    },

    "verification": {
      "layout": "column",
      "backgroundColor": "#1B263B",
      "components": [
        {
          "type": "loader",
          "text": "Verifying your task...",
          "color": "#00E5FF"
        },
        {
          "type": "card",
          "title": "Result",
          "style": { "backgroundColor": "#0D1B2A" },
          "content": [
            { "type": "icon", "name": "check_circle", "color": "#00C853" },
            { "type": "text", "value": "Correct! +2 Tokens", "color": "#FFFFFF" },
            {
              "type": "button",
              "text": "CONTINUE MINING",
              "color": "#00E5FF",
              "action": "navigate:tasks"
            }
          ]
        }
      ]
    },

    "wallet": {
      "layout": "column",
      "backgroundColor": "#F5F7FA",
      "components": [
        {
          "type": "card",
          "title": "Wallet",
          "style": { "backgroundColor": "#FFFFFF" },
          "content": [
            { "type": "text", "value": "Total Tokens: 120", "style": { "fontSize": 22 } },
            {
              "type": "button",
              "text": "Withdraw Tokens",
              "color": "#00E5FF",
              "action": "modal:withdraw"
            }
          ]
        },
        {
          "type": "list",
          "title": "Transaction History",
          "items": [
            { "label": "Translate Slang", "amount": "+2 Tokens" },
            { "label": "Verify Image", "amount": "+3 Tokens" },
            { "label": "Rate Ad", "amount": "+1 Token" }
          ]
        }
      ]
    },

    "leaderboard": {
      "layout": "column",
      "backgroundColor": "#0D1B2A",
      "components": [
        {
          "type": "list",
          "title": "Top Skill Miners",
          "items": [
            { "rank": 1, "name": "Kelvin", "score": "320 Tokens" },
            { "rank": 2, "name": "Ada", "score": "290 Tokens" },
            { "rank": 3, "name": "Sola", "score": "250 Tokens" }
          ]
        }
      ]
    },

    "profile": {
      "layout": "column",
      "backgroundColor": "#F5F7FA",
      "components": [
        {
          "type": "avatar",
          "image": "default_avatar.png"
        },
        {
          "type": "card",
          "title": "Profile",
          "content": [
            { "type": "text", "value": "Username: Kelvin" },
            { "type": "text", "value": "Skill Hash Score: 87%" },
            { "type": "text", "value": "Tasks Completed: 56" },
            { "type": "text", "value": "Accuracy: 92%" }
          ]
        },
        {
          "type": "button",
          "text": "Logout",
          "color": "#D50000",
          "action": "logout"
        }
      ]
    }
  }
}
