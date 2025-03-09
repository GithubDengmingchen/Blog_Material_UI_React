---

### **作业目标**
你需要实现一个基于 **React/Material UI** 的博客平台，满足以下功能需求，并提交相关的 UML 设计图和源代码。

---

### **需要提交的内容**
1. **改进的 UML 设计类图**  
   - 更新类图以反映系统设计，包含以下内容：  
     - 用户角色（学生、教职工、管理员、版主等）。  
     - 帖子（Post）、回复（Reply）、主题分类（如“学术资源”“校园文化”等）。  
     - 版主删除帖子的权限，管理员启用/禁用账户的权限。  
   - **必须包含至少一个设计模式**（例如：单例模式、观察者模式、工厂模式）。  
     - 例如：用 **观察者模式** 实现帖子更新通知，或用 **策略模式** 管理用户权限。

2. **UML 活动图**  
   - **版主删除帖子**：描述版主删除帖子的流程（如选择帖子→确认删除→更新数据库）。  
   - **用户发帖、回复、查看帖子**：分别绘制这三个功能的流程图。

3. **源代码**  
   - 使用 React 和 Material UI 实现以下功能：  
     - 导航栏包含指定主题（如“学术资源”“校友”等）。  
     - 用户登录功能（角色：学生、教职工、版主、管理员等）。  
     - 发帖、回复、查看帖子的功能。  
     - 版主删除帖子的功能。  
     - 管理员启用/禁用账户的功能。  
   - 代码需包含完整的项目文件（如 `package.json`, 组件文件等），确保可编译运行。

4. **演示视频**  
   - 录制一段 **5-10 分钟** 的视频，展示以下操作：  
     - 用户登录不同角色（如学生、版主、管理员）。  
     - 创建帖子、回复帖子、查看帖子。  
     - 版主删除帖子。  
     - 管理员禁用/启用账户。  

---

### **具体要求详解**
#### 1. 导航栏实现（Material UI）  
   - 使用 Material UI 的 `AppBar` 或 `Tabs` 组件实现顶部导航栏。  
   - 导航栏必须包含以下主题分类：  
     ```text  
     学术资源 (Academic Resources), 职业服务 (Career Services), 校园 (Campus),  
     文化 (Culture), 本地社区资源 (Local Community Resources), 社交 (Social),  
     体育 (Sports), 健康与 wellness (Health and Wellness), 技术 (Technology),  
     旅行 (Travel), 校友 (Alumni)  
     ```  
   - 示例代码框架：  
     ```jsx  
     // 使用 Material UI Tabs  
     <Tabs value={currentTab} onChange={handleTabChange}>  
       <Tab label="学术资源" />  
       <Tab label="职业服务" />  
       {/* 其他 Tab */}  
     </Tabs>  
     ```

#### 2. 用户登录与角色权限  
   - 实现一个简单的登录界面（无需后端，可用本地状态模拟）：  
     ```jsx  
     // 示例：使用下拉菜单选择角色  
     <Select value={userRole} onChange={handleRoleChange}>  
       <MenuItem value="student">学生</MenuItem>  
       <MenuItem value="moderator">版主</MenuItem>  
       <MenuItem value="admin">管理员</MenuItem>  
     </Select>  
     ```  
   - 根据角色显示不同功能（例如版主看到“删除帖子”按钮）。

#### 3. 帖子管理功能  
   - **发帖功能**：  
     - 表单包含标题、内容、选择主题分类。  
     - 使用 Material UI 的 `TextField` 和 `Button`。  
   - **回复功能**：  
     - 在每个帖子下方显示回复输入框。  
   - **查看帖子**：  
     - 按主题分类显示帖子列表，点击可展开查看详情和回复。

#### 4. 版主删除帖子  
   - 仅版主角色可见“删除”按钮。  
   - 点击后弹出确认对话框（Material UI 的 `Dialog` 组件）。  
   - 示例代码：  
     ```jsx  
     <Button onClick={openDeleteDialog}>删除帖子</Button>  
     <Dialog open={isDialogOpen}>  
       <DialogTitle>确认删除？</DialogTitle>  
       <Button onClick={deletePost}>确认</Button>  
     </Dialog>  
     ```

#### 5. 管理员管理账户  
   - 管理员界面显示用户列表。  
   - 每个用户旁有“禁用/启用”开关按钮。  
   - 使用 Material UI 的 `Switch` 组件：  
     ```jsx  
     <Switch checked={user.isActive} onChange={toggleUserStatus} />  
     ```

---

### **提交注意事项**
1. 将所有文件（UML 图、代码、视频）放入一个文件夹，命名为 `Assignment_3_你的姓氏`（如 `Assignment_3_张`）。  
2. 压缩为 ZIP 文件，命名为 `Assignment_3_你的姓氏.zip`。  
3. 确保代码可运行，视频清晰展示所有功能。

---

### **实用建议**
- **设计模式**：推荐使用 **单例模式** 管理用户登录状态，或 **工厂模式** 创建不同角色的用户对象。  
- **Material UI 文档**：直接复用官方示例代码（如 [AppBar](https://mui.com/components/app-bar/)）。  
- **测试**：先实现核心功能（如发帖），再逐步添加权限控制和界面美化。  

如有疑问，欢迎进一步沟通！