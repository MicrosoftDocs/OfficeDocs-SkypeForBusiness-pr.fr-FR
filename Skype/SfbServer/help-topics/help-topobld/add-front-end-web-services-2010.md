---
title: Ajouter des Services de Web frontal 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète pour les Services Web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.
ms.openlocfilehash: 1e18c4956e9b9d369bae766ed557debe44586298
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21015703"
---
# <a name="add-front-end-web-services-2010"></a>Ajouter des Services de Web frontal 2010
 
L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète pour les Services Web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.
  
Impossible de remplacer l’interne des Services Web pool nom de domaine complet (FQDN) pour un serveur Standard Edition Server. Si vous configurez le nom de domaine DNS (Domain Name System) équilibrage de charge pour un pool frontal Enterprise Edition, vous pouvez spécifier une autre base URL interne (qui doit être différent du nom de domaine complet du pool et peut être, par exemple, interne -\<votre URL de base\>).
  
Vous pouvez spécifier une URL de base externe qui est différente de votre URL interne de base pour différencier les noms de domaines. Par exemple, votre domaine interne est contoso.net, mais votre nom de domaine externe est contoso.com. Vous définissez l’URL de base externe en utilisant le nom de domaine contoso.com. Ceci est important pour les serveurs proxy inverse pour un déploiement de serveur edge. Le nom de domaine d’URL base externe doit être le même que le nom de domaine du nom de domaine complet du proxy inverse. Messagerie instantanée et présence requiert l’accès HTTP au pool frontal.
  

