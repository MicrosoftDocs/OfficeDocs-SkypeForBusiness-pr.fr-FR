---
title: Ajouter un Pool de directeur
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Pour définir le nom de domaine complet du pool directeur, sélectionnez soit un plusieurs ordinateur pool qui sera composé de deux ou plusieurs directeurs dans un pool d’équilibrage de charge, ou un seul ordinateur. Vous devez également taper le nom de domaine complet (FQDN) qui sera utilisé pour se connecter au pool de directeur ou de nom de domaine complet du directeur unique. Pour un pool d’ordinateurs du directeur, il s’agit de l’entrée de nom de domaine (DNS) pour l’adresse IP virtuelle d’un équilibreur de charge matériel ou l’entrée DNS partagée pour l’équilibrage de la charge DNS.
ms.openlocfilehash: d71219f6e9c51d69bee8d2457cc30c19f4fa6c89
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="add-director-pool"></a>Ajouter un Pool de directeur
 
Pour **définir le nom de domaine complet du pool Director**, sélectionnez un **pool de plusieurs ordinateur** qui sera composé de deux ou plusieurs directeurs dans un pool d’équilibrage de charge ou un **pool d’un seul ordinateur**. Vous devez également taper le nom de domaine complet (FQDN) qui sera utilisé pour se connecter au pool de directeur ou de nom de domaine complet du directeur unique. Pour un pool d’ordinateurs du directeur, il s’agit de l’entrée de nom de domaine (DNS) pour l’adresse IP virtuelle d’un équilibreur de charge matériel ou l’entrée DNS partagée pour l’équilibrage de la charge DNS.
  
> [!TIP]
> Si vous envisagez d’implémenter un pool de directeur à l’avenir, sélectionnez **plusieurs pool d’ordinateur**. Même si un pool est défini en tant que deux ordinateurs ou plus qui sont à équilibrage de charge, vous pouvez créer un pool d’ordinateur unique et créer un nom de domaine complet du pool pour le seul ordinateur. Lorsque vous êtes prêt à ajouter des ordinateurs au pool ultérieurement, vous devez exécuter le Générateur de topologies pour définir le nouveau membre du pool, publiez la nouvelle topologie, puis configurer le nouveau membre du pool directeur via le Skype pour l’Assistant de déploiement de serveur Business. Vous devez également ajouter le nouveau membre du pool pour les équilibreurs de charge approprié pour le pool, système de nom de domaine (DNS)-équilibrage de la charge, ou pour le matériel des équilibreurs de charge. Dans de nombreux cas, vous avez les deux systèmes d’équilibrage de la charge. Assurez-vous que vous ajoutez le nouveau serveur membre pour les deux. 
  

