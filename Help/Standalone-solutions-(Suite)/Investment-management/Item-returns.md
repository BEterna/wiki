The Item return functionality manages two main cases on projects: an item has been spent to a project by mistake or more quantity than required was specified on item requirements for a project.
In this regard, Item return can be of 2 types:
- **Reverse** - handles cases when consumption from inventory to a project already happened, but it shouldn’t.
- **Cancel** – handles cases when there was no consumption on project yet, but there was required excessive quantity on item requirements (also already processed ones) and it must be cancelled. Note that if additional quantity is required for a project, simply new item requirement can be created.
