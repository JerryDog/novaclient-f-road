修改冷迁移可指定主机
修改内容:
8.vim /usr/lib/python2.7/site-packages/novaclient/v2/servers.py
修改291行如下
def migrate(self, host=None):
    """
    Migrate a server to a new host.

    :returns: An instance of novaclient.base.TupleWithMeta
    """
    return self.manager.migrate(self, host)

修改1368行如下
def migrate(self, server, host=None):
    """
    Migrate a server to a new host.

    :param server: The :class:`Server` (or its ID).
    :returns: An instance of novaclient.base.TupleWithMeta
    """
    return self._action('migrate', server, {'host': host})