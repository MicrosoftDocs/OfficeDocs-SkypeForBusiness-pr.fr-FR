---
title: 'Service web : ajouter un directeur'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète des services Web du pool est , l’URL de https://pool01.contoso.net base est pool01.contoso.net.
ms.openlocfilehash: aa3c96a6a47a35ae8c65b0a7a6bcb5df696bada4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828894"
---
# <a name="add-director-web-service"></a>Service web : ajouter un directeur
 
L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète des services Web du pool est , l’URL de https://pool01.contoso.net base est pool01.contoso.net.
  
Vous ne pouvez pas remplacer le nom de domaine complet (FQDN) du pool de services web internes si vous ne déployez qu’un seul directeur. Si vous configurez un équilibrage de charge DNS (Domain Name System) pour le pool de directeurs, vous pouvez spécifier une URL de base interne différente (qui doit être différente du nom de domaine complet du pool et peut être, par exemple, internal- \<your base URL\> ).
  
Vous pouvez indiquer une URL de base externe qui diffère de votre URL de base interne afin de distinguer les noms de domaine. Par exemple, votre domaine interne est contoso.net, mais votre nom de domaine externe est contoso.com. Définissez alors l’URL à l’aide du nom de domaine contoso.com. Cette caractéristique est importante pour les serveurs proxy inverses dans le cas d’un déploiement Edge. Le nom de domaine de l’URL de base externe est le même que le nom de domaine du nom de domaine complet du proxy inverse. 
  

