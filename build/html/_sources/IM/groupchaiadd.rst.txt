群组管理
---------------------------

创建群组
>>>>>>>>>>>>>>>>>>>>>>>>>>>

创建群
:::::::::::::::::::::::::::

调用方法

::

    JCGroupWrapper.createGroup(members, groupName, type, customProperties, block);


输入参数

.. list-table::
  :header-rows: 1

  * - 参数
    - 类型
    - 必填
    - 说明
  * - members
    - @NonNull List<JCGroupMember>
    - 是
    - 成员列表，memberType 和 displayname 需要赋值
  * - groupName
    - @NonNull String
    - 是
    - 群名字
  * - type
    - @JCGroup.GroupType int
    - 是
    - 群类型
  * - customProperties
    - @NonNull Map<String, Object>
    - 是
    - 自定义属性
  * - block
    - GroupOperationBlock
    - 是
    - 结果函数

删除群组
>>>>>>>>>>>>>>>>>>>>>>>>>>>

解散群
:::::::::::::::::::::::::::

调用方法

::

    JCGroupWrapper.dissolve(groupServerUid, block);

输入参数

.. list-table::
  :header-rows: 1

  * - 参数
    - 类型
    - 必填
    - 说明
  * - groupServerUid
    - @NonNull String
    - 是
    - 群组的服务器会话id
  * - block
    - GroupOperationBlock
    - 是
    - 结果函数


更新群组
>>>>>>>>>>>>>>>>>>>>>>>>>>>

添加人员
:::::::::::::::::::::::::::
在一个群组中添加人员的方法。

调用方法

::

    JCGroupWrapper.addMembers(groupServerUid, members, block);

输入参数

.. list-table::
  :header-rows: 1

  * - 参数
    - 类型
    - 必填
    - 说明
  * - groupServerUid
    - @NonNull String
    - 是
    - 群组的服务器会话id
  * - members
    - @NonNull List<JCGroupMember>
    - 是
    - 成员列表，uid 和 displayname 需要赋值
  * - block
    - GroupOperationBlock
    - 是
    - 结果函数

踢掉人员
:::::::::::::::::::::::::::

调用方法

::

    JCGroupWrapper.kickMembers(groupServerUid, memberServerUids, block);

输入参数

.. list-table::
  :header-rows: 1

  * - 参数
    - 类型
    - 必填
    - 说明
  * - groupServerUid
    - @NonNull String
    - 是
    - 群组的服务器会话id
  * - memberServerUids
    - @NonNull List<String>
    - 是
    - 成员id列表
  * - block
    - GroupOperationBlock
    - 是
    - 结果函数


设置普通成员
:::::::::::::::::::::::::::

设置普通成员，只有当前群主可以操作。

调用方法

::

    JCGroupWrapper.modifyToMember(groupServerUid, memberServerUid, block);

输入参数

.. list-table::
  :header-rows: 1

  * - 参数
    - 类型
    - 必填
    - 说明
  * - groupServerUid
    - @NonNull String
    - 是
    - 群组的服务器会话id
  * - memberServerUid
    - @NonNull String
    - 是
    - 成员id
  * - block
    - GroupOperationBlock
    - 是
    - 结果函数


设置管理员
:::::::::::::::::::::::::::


调用方法

::

    JCGroupWrapper.modifyToManager(groupServerUid, memberServerUid, block);

输入参数

.. list-table::
  :header-rows: 1

  * - 参数
    - 类型
    - 必填
    - 说明
  * - groupServerUid
    - @NonNull String
    - 是
    - 群组的服务器会话id
  * - memberServerUid
    - @NonNull String
    - 是
    - 成员id
  * - block
    - GroupOperationBlock
    - 是
    - 结果函数


设置群主
:::::::::::::::::::::::::::
将群主转让给其他成员，只有当前群主可以操作。

调用方法

::

    JCGroupWrapper.modifyToOwner(groupServerUid, memberServerUid, block);

输入参数

.. list-table::
  :header-rows: 1

  * - 参数
    - 类型
    - 必填
    - 说明
  * - groupServerUid
    - @NonNull String
    - 是
    - 群组的服务器会话id
  * - memberServerUid
    - @NonNull String
    - 是
    - 成员id
  * - block
    - GroupOperationBlock
    - 是
    - 结果函数


离开
:::::::::::::::::::::::::::
离开群组，群主必须转移群主后才可以离开群组。

调用方法

::

    JCGroupWrapper.leave(groupServerUid, block);

输入参数

.. list-table::
  :header-rows: 1

  * - 参数
    - 类型
    - 必填
    - 说明
  * - groupServerUid
    - @NonNull String
    - 是
    - 群组的服务器会话id
  * - block
    - GroupOperationBlock
    - 是
    - 结果函数



修改自己的群昵称
:::::::::::::::::::::::::::


调用方法

::

    JCGroupWrapper.changeDisplayName(groupServerUid, displayName, block);

输入参数

.. list-table::
  :header-rows: 1

  * - 参数
    - 类型
    - 必填
    - 说明
  * - groupServerUid
    - @NonNull String
    - 是
    - 群组的服务器会话id
  * - displayName
    - @NonNull String
    - 是
    - 昵称
  * - block
    - GroupOperationBlock
    - 是
    - 结果函数


设置群自定义属性
:::::::::::::::::::::::::::
用于发布公告等。

调用方法

::

    JCGroupWrapper.setGroupCustomProperties(groupServerUid, customProperties, block);

输入参数

.. list-table::
  :header-rows: 1

  * - 参数
    - 类型
    - 必填
    - 说明
  * - groupServerUid
    - @NonNull String
    - 是
    - 群组的服务器会话id
  * - customProperties
    - Map<String, Object>
    - 否
    - 属性集
  * - block
    - GroupOperationBlock
    - 是
    - 结果函数


群备注更新
:::::::::::::::::::::::::::


调用方法

::

    JCGroupWrapper.updateComment(groupServerUid, nickName, tagMap, block);

输入参数

.. list-table::
  :header-rows: 1

  * - 参数
    - 类型
    - 必填
    - 说明
  * - groupServerUid
    - @NonNull String
    - 是
    - 群组的服务器会话id
  * - nickName
    - String
    - 否
    - 群备注名 null代表不改变该值, ""代表置空
  * - tagMap
    - Map<String, Object>
    - 否
    - 标签Map null代表不改变该值，内部会将该 Map 转为 json
  * - block
    - GroupOperationBlock
    - 是
    - 结果函数


更改群名称
:::::::::::::::::::::::::::


调用方法

::

    JCGroupWrapper.changeGroupName(groupServerUid, groupName, block);

输入参数

.. list-table::
  :header-rows: 1

  * - 参数
    - 类型
    - 必填
    - 说明
  * - groupServerUid
    - @NonNull String
    - 是
    - 群组的服务器会话id
  * - groupName
    - String
    - 否
    - 群名字
  * - block
    - GroupOperationBlock
    - 是
    - 结果函数


上传群头像
:::::::::::::::::::::::::::


调用方法

::

    JCGroupWrapper.updateGroupIcon(groupServerUid, path, block);

输入参数

.. list-table::
  :header-rows: 1

  * - 参数
    - 类型
    - 必填
    - 说明
  * - groupServerUid
    - @NonNull String
    - 是
    - 群组的服务器会话id
  * - path
    - @NonNull String
    - 否
    - 头像文件路径
  * - block
    - GroupOperationBlock
    - 是
    - 结果函数


拉取群信息
:::::::::::::::::::::::::::

调用方法

::

    JCGroupWrapper.refreshGroupInfo(groupServerUid, block);

输入参数

.. list-table::
  :header-rows: 1

  * - 参数
    - 类型
    - 必填
    - 说明
  * - groupServerUid
    - @NonNull String
    - 是
    - 群组的服务器会话id
  * - block
    - GroupOperationBlock
    - 是
    - 结果函数



拉取服务器更新
:::::::::::::::::::::::::::

调用方法

::

    JCGroupWrapper.refreshGroups(block);

输入参数

.. list-table::
  :header-rows: 1

  * - 参数
    - 类型
    - 必填
    - 说明
  * - block
    - GroupOperationBlock
    - 是
    - 结果函数



查询群组
>>>>>>>>>>>>>>>>>>>>>>>>>>>

查询群
:::::::::::::::::::::::::::

调用方法

::

    List<JCGroupMemberData> groupMemberDataList = JCCloudDatabase.getInstance().queryGroupMembers(groupServerUid);

输入参数

.. list-table::
  :header-rows: 1

  * - 参数
    - 类型
    - 必填
    - 说明
  * - groupServerUid
    - @NonNull String
    - 是
    - 群组的服务器会话id



返回结果

.. list-table::
  :header-rows: 1

  * - 返回值
    - 返回类型
    - 说明
  * - groupMemberDataList
    - List<JCGroupMemberData>
    - 群组成员信息列表

