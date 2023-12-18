Tech Resources
==============

.. autosummary::
   :toctree: generated

   lumache

Funciones
---------

1. unmaskValue

.. code-block:: text

   function unmaskValue(value) {
    if (typeof value === "undefined") {
        return 0;
    }

    var reg = new RegExp('\\'+T_SEP, "g");
    value = value.replace(reg, '');
    reg = new RegExp('\\'+D_SEP, "g");
    value = value.replace(reg, '.');

    return parseFloat(value);
   }
   ...

Esta función se emplea cuando se desea o se necesita convertir una cantidad formateada con separadores de miles y decimales (formatItbidAmount) a un valor de tipo float, con el propósito de realizar operaciones matemáticas. Es importante tener presente que, para otras cantidades, los formularios cuentan con un transformador encargado de gestionar dicho formato automáticamente. En estos casos, solo es necesario agregar el transformador al tipo de formulario (formtype) correspondiente, y el proceso estará completo.

La función unmaskValue se encarga de eliminar los separadores de miles y reemplazar el separador decimal, luego convierte el valor resultante a tipo float utilizando parseFloat. En caso de que el valor sea indefinido (undefined), la función devuelve 0.
