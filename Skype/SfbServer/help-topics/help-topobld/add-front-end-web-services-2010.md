---
title: Ajouter des services web frontaux 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète des services Web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.
ms.openlocfilehash: d55462bb7e8b4f5c5fac059bc6e6816ef11d0eab
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820796"
---
# <a name="add-front-end-web-services-2010"></a>Ajouter des services web frontaux 2010
 
L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète des services Web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.
  
Vous ne pouvez pas remplacer le nom de domaine complet (FQDN) du pool de services Web interne pour un serveur Standard Edition Server. Si vous configurez l’équilibrage de charge DNS (Domain Name System) pour un pool frontal Enterprise Edition, vous pouvez spécifier une autre URL de base interne (qui doit être différente du nom de domaine complet du pool et peut-\<être, par exemple\>, une URL de base).
  
Vous pouvez spécifier une URL de base externe qui est différente de votre URL de base interne pour différencier le nom de domaine. Par exemple, votre domaine interne est contoso.net, mais votre nom de domaine externe est contoso.com. Vous devez définir l’URL de base externe à l’aide du nom de domaine contoso.com. C’est important pour les serveurs proxy inverse d’un déploiement Edge. Le nom de domaine de l’URL de base externe doit être le même que le nom de domaine du nom de domaine complet (FQDN) du proxy inverse. La messagerie instantanée et la présence nécessitent un accès HTTP au pool frontal.
  

