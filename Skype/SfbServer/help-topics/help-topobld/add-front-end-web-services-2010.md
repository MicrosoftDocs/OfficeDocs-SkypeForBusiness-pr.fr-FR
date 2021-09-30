---
title: Ajouter des services web frontaux 2010
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
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète des services Web du pool est `https://pool01.contoso.net` , l’URL de base est `pool01.contoso.net` .
ms.openlocfilehash: 1e3cfa9fbf56819cb7e920ca312a2fecdd3db6b5
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013988"
---
# <a name="add-front-end-web-services-2010"></a>Ajouter des services web frontaux 2010
 
L’URL de base correspond à l’identité des services web pour l’URL, moins https://. Par exemple, si l’URL complète des services Web du pool est `https://pool01.contoso.net` , l’URL de base est `pool01.contoso.net` .
  
Vous ne pouvez pas remplacer le nom de domaine complet (FQDN) du pool de services web interne pour Édition Standard server. Si vous configurez l’équilibrage de charge DNS (Domain Name System) pour un pool frontal Êdition Entreprise, vous pouvez spécifier une URL de base interne différente (qui doit être différente du nom de domaine complet du pool et peut être, par exemple, internal- \<your base URL\> ).
  
Vous pouvez indiquer une URL de base externe qui diffère de votre URL de base interne afin de distinguer les noms de domaine. Par exemple, votre domaine interne est `contoso.net` , mais votre nom de domaine externe est `contoso.com` . Définissez alors l’URL à l’aide du nom de domaine contoso.com. Cette caractéristique est importante pour les serveurs proxy inverses dans le cas d’un déploiement Edge. Le nom de domaine de l’URL de base externe est le même que le nom de domaine du nom de domaine complet du proxy inverse. La messagerie instantanée et la présence ont besoin d'un accès HTTP au pool frontal.
  

