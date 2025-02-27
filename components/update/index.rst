Update Core
===========

.. seo::
    :description: Instructions for using Update entities to manage updates on your ESPHome devices.
    :image: system-update.svg
    :keywords: Updates, OTA, ESP32, ESP8266

The `update` component allows your ESPHome devices to install updates from a remote source; instead of
:doc:`"pushing" an update to your device </components/ota/index>`, the device can retrieve an update and
install it on its own.

.. code-block:: yaml

    # Example configuration entry
    update:
      - platform: ...

.. _config-update:

Configuration variables:
------------------------

- **id** (*Optional*, :ref:`config-id`): Manually specify the ID used for code generation. At least one of **id** and **name** must be specified.
- **name** (*Optional*, string): The name of the update entity. At least one of **id** and **name** must be specified.

  .. note::

      If you have a :ref:`friendly_name <esphome-configuration_variables>` set for your device and
      you want the light to use that name, you can set ``name: None``.

- **device_class** (*Optional*, string): The device class for the update entity. See
  https://www.home-assistant.io/integrations/binary_sensor/#device-class for a list of available options.
- **disabled_by_default** (*Optional*, boolean): If true, then this entity should not be added to any client's frontend
  (usually Home Assistant) without the user manually enabling it (via the Home Assistant UI). Defaults to ``false``.
- **entity_category** (*Optional*, string): The category of the update entity. See
  https://developers.home-assistant.io/docs/core/entity/#generic-properties for a list of available options.
- **icon** (*Optional*, icon): The icon to use for the update entity in the frontend.
- **internal** (*Optional*, boolean): Mark this component as internal. Internal components will
  not be exposed to the frontend (like Home Assistant). Specifying an ``id`` without a ``name`` will
- **on_update_available** (*Optional*, :ref:`Action <config-action>`): An automation to perform when an update is available.
- If Webserver enabled and version 3 is selected, All other options from Webserver Component.. See :ref:`Webserver Version 3 <config-webserver-version-3-options>`.

Automations
-----------

``update.perform`` Action
~~~~~~~~~~~~~~~~~~~~~~~~~

This action allows you to trigger the update entity to start the update process.

Configuration variables:

- **id** (**Required**, :ref:`config-id`): The ID of the update entity.
- **force_update** (*Optional*, boolean): Perform the update even if the device is already running the same version.
  Defaults to ``false``.

``update.is_available`` Condition
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

This condition checks if an update is available for the device.

Configuration variables:

- **id** (**Required**, :ref:`config-id`): The ID of the update entity.


See Also
--------

.. toctree::
    :maxdepth: 1
    :glob:

    *

- :ghedit:`Edit`
