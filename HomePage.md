```ad-kanban
- **快速导航**
	- 👉 [[2024|今年看板]]
	- 📙 阅读记录


- **今日待办**
    ```tasks
    short mode
    due today
    not done
    ```

- **帮助**

	- [Obsidian 文档咖啡豆版](https://coffeetea.top/zh/)
	- [Obsidian中文教程](https://publish.obsidian.md/chinesehelp/README)

```


````ad-flex
<div>

### 今年进度
```progressbar
kind: day-year
name: 今年
```

```progressbar
kind: month
name: 月份
```

```progressbar
kind: day-month
name: 这月
```

```progressbar
kind: day-week
name: 这周
```
</div>

</div>

### 今日日程
```tasks
filter by function task.file.filename.includes(DataviewAPI.func.date('0', 'x').constructor.fromJSDate(new Date()).toFormat("yyyy-MM-dd"))
short mode
group by filename
sort by due reverse
sort by description
```
</div>
````

## 最近编辑
````ad-flex
<div>

### 最近编辑
```dataview
table WITHOUT ID file.link AS "标题",file.mtime as "时间"
from !"模板" and !"kanban"
sort file.mtime desc
limit 5
```
</div>

<div>

### 三天内创建的笔记
```dataview
table WITHOUT ID file.link AS "标题",file.ctime as 创建时间
from ""
where date(today) - file.ctime <=dur(3 days)
sort file.ctime desc
limit 5
```
</div>
````