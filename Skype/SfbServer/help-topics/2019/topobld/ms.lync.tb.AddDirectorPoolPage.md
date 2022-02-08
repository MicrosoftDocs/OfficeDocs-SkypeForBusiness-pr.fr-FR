---
title: Ajouter un pool directeur
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
ROBOTS: NOINDEX, NOFOLLOW
description: Pour Définir le nom de domaine complet du pool directeur, sélectionnez un Pool de plusieurs ordinateurs, qui sera constitué de deux directeurs ou plus dans un pool avec équilibrage de la charge, ou bien un Pool d’un seul ordinateur. Vous devez également taper le nom de domaine complet (FQDN) qui sera utilisé pour se connecter au pool directeur ou au nom de domaine complet du directeur unique. Pour un pool d'ordinateurs directeurs, c'est l'entrée DNS (Domain Name System) de l'IP virtuelle d'un mécanisme d'équilibrage de charge basé sur le matériel ou l'entrée DNS partagée pour l’équilibrage de charge DNS.
ms.openlocfilehash: 5591f8de15a898a107c25ca7e2cf29649a827110
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385002"
---
# <a name="add-director-pool"></a>Ajouter un pool directeur
 
Pour **Définir le nom de domaine complet du pool directeur**, sélectionnez un **Pool de plusieurs ordinateurs**, qui sera constitué de deux directeurs ou plus dans un pool avec équilibrage de la charge, ou bien un **Pool d’un seul ordinateur**. Vous devez également taper le nom de domaine complet (FQDN) qui sera utilisé pour se connecter au pool directeur ou au nom de domaine complet du directeur unique. Pour un pool d'ordinateurs directeurs, c'est l'entrée DNS (Domain Name System) de l'IP virtuelle d'un mécanisme d'équilibrage de charge basé sur le matériel ou l'entrée DNS partagée pour l’équilibrage de charge DNS.
  
> [!TIP]
> Si vous pensez implémenter un pool directeur ultérieurement, sélectionnez **Pool de plusieurs ordinateurs**. Même si un pool est défini comme étant composé d’au moins deux ordinateurs avec charge équilibrée, vous pouvez créer un pool d’ordinateur unique et un nom de domaine complet de pool pour l’ordinateur unique. Lorsque vous êtes prêt à ajouter d’autres ordinateurs au pool ultérieurement, vous devez à nouveau exécuter le Générateur de topologies pour définir le nouveau membre du pool, publier la nouvelle topologie, puis configurer le nouveau membre du pool directeur via l’Assistant Déploiement de Skype Entreprise Server. Vous devez également ajouter le nouveau membre du pool aux équilibreurs de la charge pour le pool, à l’équilibrage de la charge DNS ou aux équilibreurs de la charge matérielle. Dans de nombreux cas, les deux systèmes d’équilibrage de la charge seront en place. Veillez à ajouter le nouveau serveur membre aux deux systèmes. 
  

