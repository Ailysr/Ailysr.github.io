---
layout: home
title: "Ailysr 的个人博客"
---

<div align="center">
  <img src="/images/my-avatar.jpg" alt="我的头像" width="150">
  <h1>Hi，我是 Ailysr</h1>
  <p>欢迎来到我的个人博客！</p>
</div>


---

## ✨ 关于我

热爱编程与分享，关注前端、后端、AI、开源项目和技术成长。

- **技能标签**：Python / JavaScript / 前端开发 / 算法 / 机器学习
- **兴趣方向**：技术分享、博客写作、开源协作

---

## 📝 最新博客

<ul>
  {% for post in site.posts limit:5 %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      <span style="color: #888;">({{ post.date | date: "%Y-%m-%d" }})</span>
    </li>
  {% endfor %}
</ul>

---

## 📫 联系我

- 📮 ：wuchaokang@mail.nwpu.edu.cn
- 🌏 : [GitHub](https://github.com/Ailysr)

---

> 分享知识，记录成长，结交朋友。  
> 欢迎关注、交流与指正！