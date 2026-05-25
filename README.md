# Todo 演示 — Supabase × 网页应用

本仓库是 **Supabase 零基础入门**课程课节 5「实战——生成完整 Todo 应用」的参考实现。

学员可以作为对照参考，看看一份完整可运行的 Supabase Todo 应用长什么样。

## 功能

- 添加待办事项
- 查看待办列表（按创建时间倒序）
- 勾选标记完成/未完成
- 编辑标题
- 删除待办事项
- 数据实时持久化到 Supabase PostgreSQL

## 用法

1. 克隆本仓库
2. 在 Supabase 控制台创建一个 `todos` 表：

   | 字段 | 类型 |
   |------|------|
   | id | int8 (Primary Key, auto-increment) |
   | title | text |
   | is_done | bool (default: false) |
   | created_at | timestamptz (default: now()) |

3. 编辑 `index.html`，将 `SUPABASE_URL` 和 `SUPABASE_ANON_KEY` 替换成你自己的项目信息
4. 用本地服务器打开（不要直接双击）：

   ```bash
   python3 -m http.server 8080
   ```

   然后访问 http://localhost:8080

## 部署参考

部署方式请参考课程课节 7「部署上线」：

- **Vercel**: 导入 GitHub 仓库，自动部署
- **Netlify Drop**: 直接拖拽 `index.html` 到 Netlify Drop

## 注意

- 本 demo 使用 Supabase 的 `anon key` + **行级别安全（RLS）**，不涉及用户认证
- 如果你在课程中构建了带登录/注册的应用，那是另一种实现方式，两者都是有效的
- 确保 `todos` 表已开启 RLS（Row Level Security）

## 关联

- [Supabase 零基础入门课程](https://pre-course.site/members/supabase/)
