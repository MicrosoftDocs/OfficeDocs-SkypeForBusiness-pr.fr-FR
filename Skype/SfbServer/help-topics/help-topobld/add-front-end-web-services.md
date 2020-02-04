---
title: Ajouter des services web frontaux
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète des services Web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.
ms.openlocfilehash: 10749cc746cf1f3d039a89fd351be6de77eafaee
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698199"
---
# <a name="add-front-end-web-services"></a>Ajouter des services web frontaux
 
L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète des services Web du pool est https://pool01.contoso.net, l’URL de base est pool01.contoso.net.
  
Vous ne pouvez pas remplacer le nom de domaine complet (FQDN) du pool de services Web interne pour un serveur Standard Edition Server. Si vous configurez l’équilibrage de charge DNS (Domain Name System) pour un pool frontal Enterprise Edition, vous pouvez spécifier une URL de base interne différente de celle du nom de domaine complet (par exemple, interne-\<votre URL\>de base).
  
Vous pouvez spécifier une URL de base externe qui est différente de votre URL de base interne pour différencier le nom de domaine. Par exemple, votre domaine interne est contoso.net, mais votre nom de domaine externe est contoso.com. Vous devez définir l’URL de base externe à l’aide du nom de domaine contoso.com. C’est important pour les serveurs proxy inverse d’un déploiement Edge. Le nom de domaine de l’URL de base externe doit être le même que le nom de domaine du nom de domaine complet (FQDN) du proxy inverse. La messagerie instantanée et la présence nécessitent un accès HTTP au pool frontal.
  

