# Branch-Based Session Architecture

This bootcamp uses a **branch-based session architecture** that provides clean, isolated learning environments for each session.

## 🏗️ How It Works

### Session Storage
- Each session is stored in `/sessions/session{N}/` on the main branch
- Contains all files needed for that specific session
- Includes workflows, step content, starter code, and dependencies

### Session Initialization
1. **Learner clicks "Start Session"** button in main README
2. **GitHub Actions workflow** creates a new branch named `session{N}`
3. **All session files** are copied to the root of the new branch
4. **Clean starting state** is guaranteed for every learner

### Branch Structure
```
main branch:
├── sessions/session1/     # Session 1 template
├── sessions/session2/     # Session 2 template
└── .github/workflows/create-session.yml

session1 branch (created dynamically):
├── package.json          # Session 1 dependencies
├── packages/             # Session 1 code
├── .github/workflows/    # Session 1 automation
└── .github/steps/        # Session 1 instructions
```

## 🎯 Benefits

### For Learners
- ✅ **Guaranteed starting state** - Every session begins with known, working code
- ✅ **Independent sessions** - Can start any session without completing others
- ✅ **Easy reset** - Broken something? Just restart the session
- ✅ **No setup required** - Everything is pre-configured and ready to use

### For Instructors  
- ✅ **Predictable outcomes** - Know exactly what files exist at session start
- ✅ **Easy maintenance** - Update sessions independently 
- ✅ **Simple testing** - Each session can be validated in isolation
- ✅ **Reliable automation** - Workflows know the exact starting file structure

## 🔄 Session Workflow

### 1. Session Creation
```yaml
# Triggered by: Manual workflow dispatch
# Creates: New branch with session content
# Result: Ready-to-use learning environment
```

### 2. Learning Progression
```yaml
# Step workflows monitor learner progress
# Issues provide step-by-step guidance  
# Automated validation checks completion
```

### 3. Session Management
```yaml
# Each session is completely independent
# Can be reset/restarted at any time
# No cross-session dependencies
```

## 🛠️ Adding New Sessions

1. **Create session directory**: `sessions/session{N}/`
2. **Add session content**: Code, workflows, steps, documentation
3. **Update main README**: Add session to the launch table
4. **Test creation**: Use the test script to validate

## 🧪 Testing Sessions

Use the provided test script to validate session setup:

```bash
./scripts/test-session1.sh
```

This checks for:
- Required file presence
- Directory structure
- Workflow syntax (if yamllint available)

## 📋 Session Checklist

When creating a new session, ensure:

- [ ] Session directory exists in `sessions/session{N}/`
- [ ] All required files are present
- [ ] Workflows reference correct branch names
- [ ] Step instructions are clear and actionable
- [ ] Dependencies are properly defined
- [ ] Test script passes validation

## 🔧 Workflow Modifications

Key changes made for branch-based approach:

1. **Branch Triggers**: Workflows trigger on `session{N}` branches instead of `main`
2. **Path Specificity**: Added path filters to prevent unnecessary workflow runs
3. **Clean Initialization**: Orphan branches ensure clean starting state
4. **Issue Creation**: Automated issue creation guides learners

## 🚀 Usage Examples

### Starting Session 1
1. Click "Start Session 1" button in README
2. Wait ~30 seconds for branch creation
3. Switch to `session1` branch  
4. Follow issue instructions

### Restarting a Session
1. Click the session button again
2. Confirm branch replacement
3. Fresh environment is created
4. Previous work is archived

This architecture ensures every learner has a consistent, reliable experience while maintaining the flexibility to work at their own pace and style.
