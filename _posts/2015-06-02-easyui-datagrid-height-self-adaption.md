---
layout: post
title: Easyui Datagrid的自适应高度处理方法
tags: Easyui
categories: 前端
---

处理此类问题，先将easyui-datagrid外侧套一个easyui-layout的div
然后使用div的自适应高度的方法填充，并设置属性fit="true"，easyui-datagrid的fit属性也设置为true。即可完成easyui-datagrid的自适应高度操作

代码：

{% highlight css %}
#layout {
    height: auto !important;
    height: 100px;
    min-height: 400px;
}
{% endhighlight %}

{% highlight html %}
<div id="layout" class="easyui-layout" fit="true">
    <table id="dg" title="My Users" class="easyui-datagrid" style="width:auto;height:auto" fit="true"
           url="get_users.php"
           toolbar="#toolbar"
           rownumbers="true" fitColumns="true" singleSelect="true">
        <thead>
        <tr>
            <th field="firstname" width="50">First Name</th>
            <th field="lastname" width="50">Last Name</th>
            <th field="phone" width="50">Phone</th>
            <th field="email" width="50">Email</th>
        </tr>
        </thead>
    </table>
    <div id="toolbar">
        <a href="#" class="easyui-linkbutton" iconCls="icon-add" plain="true" onclick="newUser()">New
            User</a>
        <a href="#" class="easyui-linkbutton" iconCls="icon-edit" plain="true" onclick="editUser()">Edit
            User</a>
        <a href="#" class="easyui-linkbutton" iconCls="icon-remove" plain="true" onclick="destroyUser()">Remove
            User</a>
    </div>
</div>
{% endhighlight %}


