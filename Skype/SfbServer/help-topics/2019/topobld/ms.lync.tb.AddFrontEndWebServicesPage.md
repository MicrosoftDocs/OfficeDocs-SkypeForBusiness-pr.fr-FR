---
title: Ajouter des Services Web frontaux
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète pour les Services Web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.
ms.openlocfilehash: 6626bb14221aaa909219451d26b76b0cd15bc576
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2018
---
# <a name="add-front-end-web-services"></a>Ajouter des Services Web frontaux
 
L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète pour les Services Web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.
  
Impossible de remplacer l’interne des Services Web pool nom de domaine complet (FQDN) pour un serveur Standard Edition server. Si vous configurez le nom de domaine DNS (Domain Name System) équilibrage de charge pour un pool frontal Enterprise Edition, vous pouvez spécifier une autre URL base interne, qui doit être différente de celui du pool (par exemple, interne -\<votre URL de base\>).
  
Vous pouvez spécifier une URL de base externe qui est différente de votre URL interne de base pour différencier les noms de domaines. Par exemple, votre domaine interne est contoso.net, mais votre nom de domaine externe est contoso.com. Vous définissez l’URL de base externe en utilisant le nom de domaine contoso.com. Ceci est important pour les serveurs proxy inverse pour un déploiement de serveur edge. Le nom de domaine d’URL base externe doit être le même que le nom de domaine du nom de domaine complet du proxy inverse. Messagerie instantanée et présence requiert l’accès HTTP au pool frontal.
  

