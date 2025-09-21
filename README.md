# AI Coding Assistant Enablement Bootcamp

<img src="https://octodex.github.com/images/Professortocat_v2.png" align="right" height="200px" />

Hey there! 👋

Mona here. I've prepared an exciting AI coding journey for you! Each session provides a clean, isolated environment where you can learn GitHub Copilot skills without worrying about setup or dependencies. 💚

**How it works**: Click a session button below to create a dedicated branch with all the files and instructions you need. Each session is independent and starts with a known, clean state! 🚀

## 🎯 Choose Your Learning Adventure

| Session | Topic | Branch Name |
|---------|--------|-------------|
| **1** | Accelerated Engineering Core and Environment | `session1` |
| **2** | Context Architecture and Management | `session2` |
| **3** | Discovery and Design | `session3` |
| **4** | IDE Development | `session4` |
| **5** | Agentic Development | `session5` |
| **6** | Testing | `session6` |
| **7** | Summarize | `session7` |
| **8** | Capstone Project | `session8` |

## 🚀 Quick Start Guide

1. **Choose a session** from the table above
2. **Create a new branch** with the session name (e.g., `session1`, `session2`)

   ```bash
   git checkout -b session1  # For Session 1
   git push origin session1  # Push the branch to trigger setup
   ```

3. **Wait ~30 seconds** for the automated setup to complete
4. **Check your issues tab** for step-by-step instructions
5. **Work at your own pace** - everything is automated and self-guided!

## 🆘 Need Help?

- **Want to restart?** Delete the session branch and create it again for a fresh environment
- **Questions?** Open an issue and we'll help you out!

## 🔄 Automatic Progression

When you finish the last step of a session, the final workflow will label the exercise issue with `sessionX-complete` (for example `session1-complete`). That label automatically triggers the next session's starter workflow. Just:

1. Complete all steps in the session issues
2. Let the final validation run
3. Watch the issue get the completion label
4. Session 2 setup workflow begins (branch `session2` is prepared if it exists or when you create/push it)

If the next session doesn't appear:

- Make sure the label (e.g. `session1-complete`) was added
- Manually create and push the next session branch (`git checkout -b session2 && git push origin session2`)
- Re-run the last workflow if needed

Remember, this is self-paced learning - take breaks and enjoy the journey! ☕️

---

&copy; 2025 GitHub &bull; [Code of Conduct](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md) &bull; [MIT License](https://gh.io/mit)
