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
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète des services Web du pool est https://pool01.contoso.net , l’URL de base est pool01.contoso.net.
ms.openlocfilehash: 45705ea940fa0f43f600546a680d76b41b645e59
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217935"
---
# <a name="add-front-end-web-services"></a>Ajouter des services web frontaux
 
L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète des services Web du pool est https://pool01.contoso.net , l’URL de base est pool01.contoso.net.
  
Vous ne pouvez pas remplacer le nom de domaine complet (FQDN) du pool de services Web internes pour un serveur Standard Edition Server. Si vous configurez l’équilibrage de charge DNS (Domain Name System) pour un pool frontal Enterprise Edition, vous pouvez spécifier une URL de base interne différente, qui doit être différente du nom de domaine complet du pool (par exemple, Internal- \<your base URL\> ).
  
Vous pouvez indiquer une URL de base externe qui diffère de votre URL de base interne afin de distinguer les noms de domaine. Par exemple, votre domaine interne est contoso.net, mais votre nom de domaine externe est contoso.com. Définissez alors l’URL de base externe à l’aide du nom de domaine contoso.com. Cette caractéristique est importante pour les serveurs proxy inverses dans le cas d’un déploiement de périphérie. Le nom de domaine de l’URL de base externe est le même que le nom de domaine du nom de domaine complet du proxy inverse. La messagerie instantanée et la présence ont besoin d'un accès HTTP au pool frontal.
  

