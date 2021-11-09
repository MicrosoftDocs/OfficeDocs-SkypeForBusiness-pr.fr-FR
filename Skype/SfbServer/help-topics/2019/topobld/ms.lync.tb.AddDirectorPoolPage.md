---
title: Ajouter un pool directeur
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: 70df13a0339c11d47e907ff70be395f613cdb1fe
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60839336"
---
# <a name="add-director-pool"></a>Ajouter un pool directeur
 
Pour **Définir le nom de domaine complet du pool directeur**, sélectionnez un **Pool de plusieurs ordinateurs**, qui sera constitué de deux directeurs ou plus dans un pool avec équilibrage de la charge, ou bien un **Pool d’un seul ordinateur**. Vous devez également taper le nom de domaine complet (FQDN) qui sera utilisé pour se connecter au pool directeur ou au nom de domaine complet du directeur unique. Pour un pool d'ordinateurs directeurs, c'est l'entrée DNS (Domain Name System) de l'IP virtuelle d'un mécanisme d'équilibrage de charge basé sur le matériel ou l'entrée DNS partagée pour l’équilibrage de charge DNS.
  
> [!TIP]
> Si vous pensez implémenter un pool directeur ultérieurement, sélectionnez **Pool de plusieurs ordinateurs**. Même si un pool est défini comme étant composé d’au moins deux ordinateurs avec charge équilibrée, vous pouvez créer un pool d’ordinateur unique et un nom de domaine complet de pool pour l’ordinateur unique. Lorsque vous êtes prêt à ajouter d’autres ordinateurs au pool ultérieurement, vous devez à nouveau exécuter le Générateur de topologies pour définir le nouveau membre du pool, publier la nouvelle topologie, puis configurer le nouveau membre du pool directeur via l’Assistant Déploiement Skype Entreprise Server. Vous devez également ajouter le nouveau membre du pool aux équilibreurs de la charge pour le pool, à l’équilibrage de la charge DNS ou aux équilibreurs de la charge matérielle. Dans de nombreux cas, les deux systèmes d’équilibrage de la charge seront en place. Veillez à ajouter le nouveau serveur membre aux deux systèmes. 
  

