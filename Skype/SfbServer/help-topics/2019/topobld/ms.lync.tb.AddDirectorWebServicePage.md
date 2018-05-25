---
title: Ajouter un Service Web de directeur
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète pour les Services Web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.
ms.openlocfilehash: c65d7d9276aaa394d1810136a97dcc8c075d3607
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2018
---
# <a name="add-director-web-service"></a>Ajouter un Service Web de directeur
 
L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète pour les Services Web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.
  
Impossible de remplacer le nom de domaine complet de pool (FQDN) des Services Web interne si vous déployez uniquement un directeur unique. Si vous configurez une nom de domaine DNS (Domain Name System) équilibrage de charge pour le pool de directeurs, vous pouvez spécifier une autre base URL interne (qui doit être différent du nom de domaine complet du pool et peut être, par exemple, interne -\<votre URL de base\>).
  
Vous pouvez spécifier une URL de base externe qui est différente de votre URL interne de base pour différencier les noms de domaines. Par exemple, votre domaine interne est contoso.net, mais votre nom de domaine externe est contoso.com. Vous définissez l’URL de base externe en utilisant le nom de domaine contoso.com. Ceci est important pour les serveurs proxy inverse pour un déploiement de serveur edge. Le nom de domaine d’URL base externe doit être le même que le nom de domaine du nom de domaine complet du proxy inverse. 
  

