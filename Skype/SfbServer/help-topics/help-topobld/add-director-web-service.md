---
title: 'Service web : ajouter un directeur'
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: 'L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète des services Web du pool `https://pool01.contoso.net`est , l’URL de base est `pool01.contoso.net`.'
---

# <a name="add-director-web-service"></a>Service web : ajouter un directeur
 
L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète des services Web du pool `https://pool01.contoso.net`est , l’URL de base est `pool01.contoso.net`.
  
Vous ne pouvez pas remplacer le nom de domaine complet (FQDN) du pool de services web internes si vous ne déployez qu’un seul directeur. Si vous configurez un équilibrage de charge DNS (Domain Name System) pour un pool de directeurs, vous pouvez spécifier une URL de base interne différente (qui doit être différente du nom de domaine complet du pool et peut être, par exemple, interne).\<your base URL\>
  
Vous pouvez indiquer une URL de base externe qui diffère de votre URL de base interne afin de distinguer les noms de domaine. Par exemple, votre domaine interne est `contoso.net`, mais votre nom de domaine externe est `contoso.com`. Vous devez définir l’URL de base externe à l’aide du nom `contoso.com` de domaine. Cette caractéristique est importante pour les serveurs proxy inverses dans le cas d’un déploiement Edge. Le nom de domaine de l’URL de base externe est le même que le nom de domaine du nom de domaine complet du proxy inverse. 
  

