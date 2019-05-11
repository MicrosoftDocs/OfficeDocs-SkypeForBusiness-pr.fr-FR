---
title: Ajouter un pool directeur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Pour définir le nom de domaine complet du pool directeur, sélectionnez un pool de plusieurs ordinateurs qui se compose de deux ou plusieurs directeurs dans un pool à charge équilibrée, ou un pool à ordinateur unique. Vous devez également taper le nom de domaine complet (FQDN) qui sera utilisé pour se connecter au pool directeur ou nom de domaine complet du directeur unique. Pour un pool d’ordinateurs directeur, il s’agit de l’entrée de nom de domaine DNS (Domain Name System) pour l’adresse IP virtuelle de l’équilibrage de charge matérielle ou l’entrée DNS partagée pour l’équilibrage de charge DNS.
ms.openlocfilehash: 6f1e9fd873cfbd09ab8e9bc27323082be4d125a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886528"
---
# <a name="add-director-pool"></a>Ajouter un pool directeur
 
Pour **définir le nom de domaine complet du pool directeur**, sélectionnez un **pool de plusieurs ordinateurs** qui se compose de deux ou plusieurs directeurs dans un pool à charge équilibrée ou un **seul ordinateur**. Vous devez également taper le nom de domaine complet (FQDN) qui sera utilisé pour se connecter au pool directeur ou nom de domaine complet du directeur unique. Pour un pool d’ordinateurs directeur, il s’agit de l’entrée de nom de domaine DNS (Domain Name System) pour l’adresse IP virtuelle de l’équilibrage de charge matérielle ou l’entrée DNS partagée pour l’équilibrage de charge DNS.
  
> [!TIP]
> Si vous envisagez d’implémenter un pool directeur à l’avenir, sélectionnez **pool de plusieurs ordinateurs**. Même si un pool est défini en tant que deux ou plusieurs ordinateurs qui sont à charge équilibrée, vous pouvez créer un pool à ordinateur unique et créer un nom de domaine complet du pool pour le même ordinateur. Lorsque vous êtes prêt à ajouter des ordinateurs au pool ultérieurement, vous devez exécuter le Générateur de topologie pour définir le nouveau membre du pool, publier la nouvelle topologie, puis configurer le nouveau membre du pool directeur via le Skype pour l’Assistant Déploiement Business Server. Vous devez également ajouter le nouveau membre du pool pour les équilibreurs de charge approprié pour le pool, le nom de domaine (DNS)-équilibrage de la charge, ou pour le matériel équilibreurs de charge. Dans la plupart des cas, vous devez les deux systèmes en place d’équilibrage de charge. N’oubliez pas que vous ajoutez le nouveau serveur membre pour les deux. 
  

