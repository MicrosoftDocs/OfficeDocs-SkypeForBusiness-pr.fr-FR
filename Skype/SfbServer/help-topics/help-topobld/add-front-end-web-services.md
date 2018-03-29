---
title: Ajouter des Services Web Front-End
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
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-web-services"></a>Ajouter des Services Web Front-End
 
L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète pour les Services Web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.
  
Vous ne pouvez pas substituer l’interne des Services Web pool nom de domaine complet (FQDN) d’un serveur Standard Edition. Si vous configurez le système de nom de domaine (DNS) équilibrage de charge pour un pool Enterprise Edition Front-End, vous pouvez spécifier une autre URL base interne, qui doit être différente du nom de domaine complet du pool (par exemple, interne -\<votre URL de base de\>).
  
Vous pouvez spécifier une URL de base externe qui est différente de votre URL de base interne pour différencier les noms de domaines. Par exemple, votre domaine interne est contoso.net, mais votre nom de domaine externe est contoso.com. Vous définissez l’URL externe de base en utilisant le nom de domaine de contoso.com. Ceci est important pour les serveurs proxy inverse pour un déploiement de bord. Le nom de domaine base URL externe doit être le même que le nom de domaine de nom de domaine complet du serveur proxy inverse. La messagerie instantanée et présence requiert l’accès HTTP au pool de Front-End.
  

