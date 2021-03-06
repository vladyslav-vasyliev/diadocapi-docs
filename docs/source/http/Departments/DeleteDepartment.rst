DeleteDepartment
================

.. http:post:: /admin/DeleteDepartment

    :query boxId: идентификатор ящика
    :query departmentId: идентификатор подразделения

    :reqheader Authorization: необходимые данные для :doc:`авторизации <../../Authorization>`

    :statuscode 200: операция успешно завершена
    :statuscode 400: данные в запросе имеют неверный формат или отсутствуют обязательные параметры
    :statuscode 401: в запросе отсутствует HTTP-заголовок ``Authorization``, или в этом заголовке содержатся некорректные авторизационные данные
    :statuscode 402: закончилась подписка на API
    :statuscode 403: доступ к ящику с предоставленным авторизационным токеном запрещен или запрос сделан не от имени администратора
    :statuscode 404: в указанном ящике нет подразделения с указанным идентификатором
    :statuscode 405: используется неподходящий HTTP-метод
    :statuscode 409: см. :ref:`примечания <department-delete-notes>`
    :statuscode 500: при обработке запроса возникла непредвиденная ошибка

Удаляет подразделение организации. Запрос доступен только администраторам организации.

.. _department-delete-notes:

**Примечания:**

-  Нельзя удалить головное подразделение (00000000-0000-0000-0000-000000000000)

-  Нельзя удалить подразделение, содержащее дочерние

-  Нельзя удалить подразделение, в котором есть документы, сотрудники, дочерние подразделения