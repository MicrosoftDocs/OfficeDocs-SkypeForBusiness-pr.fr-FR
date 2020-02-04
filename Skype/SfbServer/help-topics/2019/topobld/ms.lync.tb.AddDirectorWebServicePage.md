---
title: 'Service web : ajouter un directeur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
ROBOTS: NOINDEX, NOFOLLOW
description: L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète des services Web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.
ms.openlocfilehash: 140012c548152f9473308b3be17f95adf53e918b
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41703179"
---
# <a name="add-director-web-service"></a>Service web : ajouter un directeur
 
L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète des services Web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.
  
Vous ne pouvez pas remplacer le nom de domaine complet (FQDN) du pool de services Web interne si vous déployez un seul directeur. Si vous configurez un équilibrage de charge DNS (Domain Name System) pour la réserve de directeurs, vous pouvez spécifier une autre URL de base interne (qui doit être différente de celle du nom de domaine complet\<\>).
  
Vous pouvez spécifier une URL de base externe qui est différente de votre URL de base interne pour différencier le nom de domaine. Par exemple, votre domaine interne est contoso.net, mais votre nom de domaine externe est contoso.com. Vous devez définir l’URL de base externe à l’aide du nom de domaine contoso.com. C’est important pour les serveurs proxy inverse d’un déploiement Edge. Le nom de domaine de l’URL de base externe doit être le même que le nom de domaine du nom de domaine complet (FQDN) du proxy inverse. 
  

