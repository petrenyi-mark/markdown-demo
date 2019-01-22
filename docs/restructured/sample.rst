Sample doc
==========

:Version:
    v1.7.0

Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
tempor incididunt ut labore et dolore magna aliqua.

Level 2
-------

   simple quote

..

   Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris
   nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in
   reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
   pariatur. Excepteur sint occaecat cupidatat non proident, sunt in
   culpa qui officia deserunt mollit anim id est laborum.

Level 3
~~~~~~~

::

   Nunc sed velit dignissim sodales ut eu sem integer vitae. Laoreet non curabitur gravida arcu. Nunc scelerisque viverra mauris in aliquam sem fringilla ut morbi. Non pulvinar neque laoreet suspendisse interdum. In pellentesque massa placerat duis ultricies lacus sed turpis. Massa vitae tortor condimentum lacinia quis vel eros. Ac turpis egestas maecenas pharetra convallis posuere. A condimentum vitae sapien pellentesque habitant morbi tristique senectus. Aliquam ultrices sagittis orci a. Arcu dictum varius duis at. Ultricies lacus sed turpis tincidunt id aliquet risus feugiat. Nibh venenatis cras sed felis eget velit.
   Bibendum est ultricies integer quis auctor elit sed vulputate mi.

.. code:: java

   public SummaryResponse getSummaryResponse() throws BaseException {
           MBeanServerConnection server = ArtemisControlHelper.getMBeanServerConnection(artemisConfig.getJmxUrl());
           ActiveMQServerControl serverControl = ArtemisControlHelper.getActiveMQServerControl(server, artemisConfig.getBrokerName());
           SummaryType summaryType = new SummaryType();
           String[] queues = serverControl.getQueueNames(RoutingType.ANYCAST.name());
           for (String queue : queues) {
               JmsDataType jmsDataType = new JmsDataType().withJmsType(JmsType.QUEUE).withName(queue);
               jmsDataType.getMessages().addAll(queueMessages(queue));
               summaryType.getJmsData().add(jmsDataType);
           }

           summaryType.setAddressMemoryUsage(serverControl.getAddressMemoryUsage());
           summaryType.setAddressMemoryUsagePercentage(serverControl.getAddressMemoryUsagePercentage());
           summaryType.setConnectionCount(serverControl.getConnectionCount());
           summaryType.setTotalConnectionCount(serverControl.getTotalConnectionCount());
           summaryType.setTotalConsumerCount(serverControl.getTotalConsumerCount());
           summaryType.setTotalMessagesAcknowledged(serverControl.getTotalMessagesAcknowledged());
           summaryType.setTotalMessagesAdded(serverControl.getTotalMessagesAdded());
           summaryType.setUptimeMillis(serverControl.getUptimeMillis());
           summaryType.setVersion(serverControl.getVersion());
           SummaryResponse response = new SummaryResponse();
           // handleSuccessResultType(null);
           response.setSummary(summaryType);
           handleSuccessResultType(response);
           return response;
       }

Level 4
^^^^^^^
Formatted texts:

-  **bold**
-  *italic*
-  ***itbo***
-  m\ **i**\ x\ *e*\ d
-  ``monospace``\ (``AltGr + 7``)

Other styling:

1. highlighted
2. underlined
3. [STRIKEOUT:striked]
4. small print

http://www.google.com Google

`Index`_

.. _Index: http://index.hu