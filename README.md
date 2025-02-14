# **问题日志**

## 修改侧边栏的名字

###  问题
`config.author` 已经在 `_config.yml` 里设置为 **"Gong Yiqiao"**，但侧边栏仍然显示 **"Joe"**。

### 解决方案
1. **检查 Hexo 站点的 `_config.yml`**（根目录下）：
   ```yaml
   author: Gong Yiqiao
   ```
2. **检查 `themes/ParticleX/_config.yml`**：
   ```yaml
   card:
       name: Yiqiao  # 确保这里不是 Joe
   ```
3. **如果名字仍然是 "Joe"，直接修改 `card.ejs`**：
   - 打开 `themes/ParticleX/layout/_partial/card.ejs`：
     ```ejs
     <div class="name">Yiqiao</div>  <!-- 直接写死名字 -->
     ```
   - 然后运行：
     ```sh
     hexo clean
     hexo g
     hexo s
     ```

---

##  在侧边栏添加 GitHub & Email 图标

### 问题
我希望在 **侧边栏** 里添加 GitHub 和 Email 图标，并且点击后跳转到我的 GitHub 主页或打开邮件客户端。

###  解决方案
1. **打开 `card.ejs`**：
   ```sh
   themes/ParticleX/layout/_partial/card.ejs
   ```
2. **直接添加以下代码（头像 & 名字下面）：**
   ```html
   <div class="social-icons">
       <a href="https://github.com/GongYiqiao" target="_blank">
           <i class="fa-brands fa-github"></i> GitHub
       </a>
       <a href="mailto:your-email@example.com">
           <i class="fa-solid fa-envelope"></i> Email
       </a>
   </div>
   ```
4. **重新生成 Hexo 并刷新**：
   ```sh
   hexo clean
   hexo g
   hexo s
   ```

