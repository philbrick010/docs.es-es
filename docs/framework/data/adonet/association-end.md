---
title: extremo de asociación
ms.date: 03/30/2017
ms.assetid: 2c345213-0296-4d90-ac6d-cef179798a75
ms.openlocfilehash: 8c156ca1c05e22e540578adfb2be06cf477b29e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744952"
---
# <a name="association-end"></a>extremo de asociación
Un *extremo de asociación* identifica el [tipo de entidad](../../../../docs/framework/data/adonet/entity-type.md) en un extremo de un [asociación](../../../../docs/framework/data/adonet/association-type.md) y el número de entidades escriba instancias que pueden existir en dicho extremo de una asociación. Los extremos de asociación se definen como parte de una asociación, y esta debe tener exactamente dos extremos. [Las propiedades de navegación](../../../../docs/framework/data/adonet/navigation-property.md) permiten la navegación de extremo de asociación de uno a otro.  
  
 Una definición de extremo de asociación contiene la información siguiente:  
  
-   Uno de los tipos de entidad implicados en la asociación. (Necesario)  
  
    > [!NOTE]
    >  En una asociación determinada, el tipo de entidad especificado para cada extremo de la asociación puede ser el mismo. Esto crea una auto-asociación.  
  
-   Un [multiplicidad de extremo de asociación](../../../../docs/framework/data/adonet/association-end-multiplicity.md) que indica el número de instancias del tipo de entidad que pueden estar en un extremo de la asociación. La multiplicidad de extremo de asociación puede tener el valor uno (1), cero o uno (0..1), o muchos (*).  
  
-   Nombre para el extremo de la asociación. (Opcional)  
  
-   Información sobre las operaciones que se realizan en el extremo de la asociación, como por ejemplo la eliminación en cascada. (Opcional)  
  
## <a name="example"></a>Ejemplo  
 El diagrama siguiente muestra un modelo conceptual con dos asociaciones: `PublishedBy` y `WrittenBy`. Los extremos de asociación para la asociación `PublishedBy` son los tipos de entidad `Book` y `Publisher`. La multiplicidad del extremo `Publisher` es uno (1) y la multiplicidad del extremo `Book` es muchos (*), lo que indica que un editor publica muchos libros y que un libro solo puede ser publicado por un editor.  
  
 ![Ejemplo de modelo](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 ADO.NET Entity Framework usa un lenguaje específico de dominio (DSL) denominado lenguaje de definición de esquemas conceptuales ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) para definir los modelos conceptuales. El CSDL siguiente define la asociación `PublishedBy` mostrada en el diagrama anterior. Tenga en cuenta que el tipo, el nombre y la multiplicidad de cada extremo de la asociación se especifican mediante atributos XML (los atributos `Type`, `Role` y `Multiplicity`, respectivamente). La información adicional sobre las operaciones realizadas en un extremo se especifica mediante un elemento XML (el elemento `OnDelete`-). En este caso, si se elimina un editor, también se eliminan todos los libros asociados.  
  
 [!code-xml[EDM_Example_Model#AssociationEnd](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#associationend)]  
  
## <a name="see-also"></a>Vea también
- [Conceptos clave de Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
