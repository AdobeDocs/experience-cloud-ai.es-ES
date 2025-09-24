---
title: Privacidad, seguridad y administración en el asistente de IA
description: Obtenga información acerca de las prácticas de privacidad, seguridad y gobernanza de AI Assistant.
source-git-commit: fe4d2de03e34eccd2950f87b3c57ffbb5e1cf5e9
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 0%

---

# Privacidad, seguridad y administración en el asistente de IA

El asistente de IA de Adobe Experience Platform está diseñado con privacidad, seguridad y administración en la vanguardia.

Lea este documento para obtener más información acerca de las capacidades centradas en la confianza del cliente que puede esperar de AI Assistant:

* En la actualidad, AI Assistant no utiliza datos personales, ni siquiera con fines formativos.
* El asistente de IA no tiene conocimiento de los datos de los consumidores.
* El Asistente de IA respetará todas las directivas de [control de acceso](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/home) existentes.

   * Cualquier nueva política de control de acceso basada en atributos se reflejará en el asistente de IA después de un máximo de 24 horas&ast;

* Se le debe otorgar permiso explícito para interactuar con el Ayudante de IA.

   * Puede establecer permisos diferentes para Experience Platform y Journey Optimizer mediante la interfaz de usuario de [permisos](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/abac/permissions-ui/browse) y puede usar [Admin Console](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/ui/browse) para asignar permisos para Customer Journey Analytics.
   * Los permisos son granulares y el administrador de la zona protegida puede configurar cuál de los usuarios puede hacer diferentes categorías de preguntas (preguntas basadas en el conocimiento del producto con el asistente de IA o preguntas sobre perspectivas operativas).

* AI Assistant es una función compatible con HIPAA cuando se utiliza en combinación con Adobe Experience Platform Healthcare Shield.
* Puede ver un registro de las interacciones anteriores con el asistente de IA con una política de retención de 30 días.
* El asistente de IA se basa en datos específicos de zonas protegidas y en la documentación pública de Adobe al responder a las solicitudes de los usuarios. Los datos no se comparten en entornos limitados.
* Los mensajes que proporcione al asistente de IA no se comparten con otros clientes.

&ast; *Esto implica que si se agregan etiquetas nuevas a los campos y objetos o se crean directivas nuevas, el Asistente de IA tardará hasta 24 horas en respetarlas. Durante esas 24 horas, los usuarios con acceso recién restringido aún pueden tener acceso a esos campos y objetos.*
