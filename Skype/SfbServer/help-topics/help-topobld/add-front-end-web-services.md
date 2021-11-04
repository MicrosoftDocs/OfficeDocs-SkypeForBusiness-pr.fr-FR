---
title: Ajouter des services web frontaux
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète des services Web du pool est `https://pool01.contoso.net` , l’URL de base est `pool01.contoso.net` .
ms.openlocfilehash: a02ab1d8c3013216c31d1e050e22eaf9cf614045
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60752133"
---
# <a name="add-front-end-web-services"></a>Ajouter des services web frontaux
 
L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète des services Web du pool est `https://pool01.contoso.net` , l’URL de base est `pool01.contoso.net` .
  
Vous ne pouvez pas remplacer le nom de domaine complet (FQDN) du pool de services Web internes pour un serveur Standard Edition Server. Si vous configurez l’équilibrage de charge DNS (Domain Name System) pour un pool frontal Êdition Entreprise, vous pouvez spécifier une URL de base interne différente, qui doit être différente du nom de domaine complet du pool (par exemple, internal- \<your base URL\> ).
  
Vous pouvez indiquer une URL de base externe qui diffère de votre URL de base interne afin de distinguer les noms de domaine. Par exemple, votre domaine interne est `contoso.net` , mais votre nom de domaine externe est `contoso.com` . Vous devez définir l’URL de base externe à l’aide `contoso.com` du nom de domaine. Cette caractéristique est importante pour les serveurs proxy inverses dans le cas d’un déploiement Edge. Le nom de domaine de l’URL de base externe est le même que le nom de domaine du nom de domaine complet du proxy inverse. La messagerie instantanée et la présence ont besoin d'un accès HTTP au pool frontal.
  

