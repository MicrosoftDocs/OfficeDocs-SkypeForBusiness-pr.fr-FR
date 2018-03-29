---
title: Ajouter des Services Web Front-End 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète pour les Services Web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.
ms.openlocfilehash: ad21132f26abd03355cb214811a67dfe0f42add2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-front-end-web-services-2010"></a>Ajouter des Services Web Front-End 2010
 
L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète pour les Services Web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.
  
Vous ne pouvez pas substituer l’interne des Services Web pool nom de domaine complet (FQDN) pour un serveur Standard Edition. Si vous configurez le système de nom de domaine (DNS) équilibrage de charge pour un pool Enterprise Edition Front-End, vous pouvez spécifier une autre URL interne de base (qui doit être différent du nom de domaine complet du pool et peut être, par exemple, interne -\<votre URL de base de\>).
  
Vous pouvez spécifier une URL de base externe qui est différente de votre URL de base interne pour différencier les noms de domaines. Par exemple, votre domaine interne est contoso.net, mais votre nom de domaine externe est contoso.com. Vous définissez l’URL de base externe en utilisant le nom de domaine de contoso.com. Ceci est important pour les serveurs proxy inverse pour un déploiement de bord. Le nom de domaine base URL externe doit être le même que le nom de domaine de nom de domaine complet du serveur proxy inverse. La messagerie instantanée et présence requiert l’accès HTTP au pool de Front-End.
  

