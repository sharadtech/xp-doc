.. _tools:

Admin Tools
===========

.. WARNING::
  Admin Tool support is experimental.

Admin Tools are independent "back office" user interfaces designed to manage Enonic XP or installed applications.
Each tool will run in it's own browser tab - here are some of the reasons for this:

* Faster user interfaces and better deep-linking support
* Developers can use their favorite front-end frameworks
* Simplified debugging

**Standard Tools**

Enonic XP is shipped with the following tools by default:

* :ref:`home_tool` (The default tool)
* :ref:`application_tool` (Install, stop, start and uninstall applications)
* :ref:`content_studio` (Create and manage content and sites)
* :ref:`users_tool` (Create, setup and manage users, groups and roles)

**Launcher**

Navigation between the various Admin Tools is done via the "Launcher Panel", Accessible from the top right corner.
This icon and the Launcher panel should be available across all Admin Tools.

.. image:: images/launcher.jpg



To create a new Admin Tool, you must create a new folder in your project structure, i.e.  ``admin/tools/[tool-name]``.
Then you must place a descriptor, an icon and a controller there.


Descriptor
----------

The tool ``descriptor`` defines the basic info to be displayed in the launcher and which roles are required to access the tool.

The descriptor file must have the same name as the tool, i.e. ``admin/tools/[tool-name]/[tool-name].xml``:

.. literalinclude:: code/descriptor.xml
   :language: xml


Icon
----

You should add an SVG icon to the tool. This will be displayed in the launcher panel together with the info from the descriptor.
The icon file must have the same name as the tool, i.e. ``admin/tools/[tool-name]/[tool-name].svg``:


Controller
----------

To drive the tool, we will need a **controller** (See :ref:`http_controllers`). The controller typically produces the initial tool html.
Depending on the tool implementation it may also handle sub-requests from the tool.

The controller must have the same name as the tool, i.e. ``admin/tools/[tool-name]/[tool-name].js``:

.. literalinclude:: code/controller.js
   :language: javascript


Adding the Launcher Panel menu
------------------------------

Adding the Launcher Panel menu to a custom admin tool requires two steps.

1. In the <body> section of the view add a Javascript snippet where you define an object variable called "CONFIG" with properties
adminUrl, assetsUri and appId which will get their values from the controller:


.. literalinclude:: code/config.html
    :language: html


2. Under the Javascript snippet add a reference to the Launcher's Javascript file as shown below:

.. literalinclude:: code/launcher-reference.html
    :language: html


The entire view:

.. literalinclude:: code/view.html
    :language: html

