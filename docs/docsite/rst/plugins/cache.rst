.. contents:: Topics


Cache Plugins
-------------

Cache plugin implement a backend caching mechanism that allows Ansible to store gathered facts or inventory source data
without the performance hit of retrieving them from source.

The default cache plugin is the :doc:`memory <cache/memory>` plugin, which only caches the data for the current execution of Ansible. Other plugins with persistent storage are available to allow caching the data across runs.


Enabling Cache Plugins
++++++++++++++++++++++

Only one cache plugin can be active at a time.

You can enable a cache plugin in the Ansible configuration, either via environment variable:

.. code-block:: shell

    export ANSIBLE_CACHE_PLUGIN=jsonfile

or in the ``ansible.cfg`` file:

.. code-block:: ini

    [defaults]
    fact_caching=redis

You will also need to configure other settings specific to each plugin. Consult the individual plugin documentation
or the Ansible :doc:`configuration <../config>` for more details.

Plugin List
+++++++++++

You can use ``ansible-doc -t cache -l`` to see the list of available plugins. 
Use ``ansible-doc -t cache <plugin name>`` to see specific documentation and examples.

.. toctree:: :maxdepth: 1
    :glob:

    cache/*

.. seealso::

   :doc:`action`
       Ansible Action plugins
   :doc:`callback`
       Ansible callback plugins
   :doc:`connection`
       Ansible connection plugins
   :doc:`inventory`
       Ansible inventory plugins
   :doc:`shell`
       Ansible Shell plugins
   :doc:`strategy`
       Ansible Strategy plugins
   :doc:`vars`
       Ansible Vars plugins
   `User Mailing List <http://groups.google.com/group/ansible-devel>`_
       Have a question?  Stop by the google group!
   `irc.freenode.net <http://irc.freenode.net>`_
       #ansible IRC chat channel
