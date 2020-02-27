.. include:: ../../Includes.txt

.. highlight:: xml

.. _fluid:

=====
Fluid
=====

TYPO3 uses the Fluid templating engine. The Fluid source code is being developed as an
independent project outside of the TYPO3 core.

Fluid is based on XML.
You can use HTML markup in Fluid, but you can do much more with Fluid, such as use conditions,
variables or custom ViewHelpers which are PHP components.

Example
=======

This is how a Fluid template could look like::

   <h4>This is your headline</h4>
   <p>
    <f:if condition="{myExpression}">
      <f:then>
         {somevariable}
      </f:then>
      <f:else>
          {someothervariable}
      </f:else>
    </f:if>
   </p>

The resulting HTML may look like this::

   <h4>This is your headline</h4>
   <p>This is the content of variable "somevariable"</p>

The above Fluid snippet contains:

ViewHelpers:
   The XML elements that start with `f:` like `<f:if>` etc. are ViewHelpers. These
   are PHP components that are supplied by Fluid and can be used in your Fluid templates.
   TYPO3 adds some more ViewHelpers for TYPO3 specific functionality. And, you can
   write your own.

   ViewHelpers can do simple processing such as remove spaces with the
   :ref:`t3viewhelper:typo3fluid-fluid-spaceless` ViewHelper or create a link
   as is done in the TYPO3 Fluid ViewHelper :ref:`t3viewhelper:link`.

Variables:
   Fluid can access variables that have been defined. Just use braces
   and the name of the variable: `{somevariable}`

Conditions:
    The conditions are supplied here by the if / then / else ViewHelpers.


To get an introduction to the basic syntax, see the following resources:

* `The Fluid Syntax <https://github.com/TYPO3/Fluid/blob/master/doc/FLUID_SYNTAX.md>`__
* `ViewHelpers - what these classes do in the Fluid language <https://github.com/TYPO3/Fluid/blob/master/doc/FLUID_VIEWHELPERS.md>`__

Once you have successfully completed your fist steps, you may want to refer
to:

* `24 TIPS & TRICKS FOR FLUID <https://usetypo3.com/24-fluid-tips.html>`__
* :ref:`Fluid ViewHelper Reference <t3viewhelper:start>`

Fluid in TYPO3
==============

.. sidebar:: Sitepackage

   In TYPO3, (almost) everything is an extension. If you want to create a theme, override
   some configuration or add custom content elements you will do this in a custom TYPO3
   extension. A sitepackage is an extension that contains everything that is necessary
   for your site: The configuration, necessary assets for your theme (images, css etc.)
   and a combination of TypoScript and Fluid.


You can use Fluid in TYPO3 to do the following:

* Create a template (theme) in combination with TypoScript :ref:`FLUIDTEMPLATE <t3tsref:t3tsrefcobj-fluidtemplate>`.
  Check out the :ref:`t3sitepackage:start` which walks you through the
  creation of a sitepackage extension.
* :ref:`Create Custom Content Elements <adding-your-own-content-elements>`.
* While the previous point describes the lightweight components which
  are created using a combination of TypoScript and Fluid, if you need more functionality,
  in your content element, content that is stored in the database, etc. you will want to create a plugin using
  for example a combination of Extbase and Fluid. This is explained in :ref:`t3extbasebook:start`
* Use Fluid to create emails using the :ref:`TYPO3 Mail API <mail-fluid-email>`.

