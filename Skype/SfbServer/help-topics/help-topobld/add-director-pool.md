---
title: Ajouter un pool directeur
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
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Pour définir le nom de domaine complet (FQDN) du pool de réalisateurs, sélectionnez un pool d’ordinateurs qui sera composé de deux ou plusieurs directeurs dans un pool équilibré ou un seul pool d’ordinateurs. Vous devez également taper le nom de domaine complet (FQDN, Fully Qualified Domain Name) qui sera utilisé pour la connexion au nom de domaine complet (FQDN) du réalisateur ou du réalisateur unique. Dans le cas d’un pool d’ordinateurs Director, il s’agirait de l’entrée DNS (Domain Name System) pour l’adresse IP virtuelle d’un équilibreur de charge matériel ou de l’entrée DNS partagée pour l’équilibrage de charge DNS.
ms.openlocfilehash: 1a419c6a27118cbdf7ffe841a39b9b60e6e84577
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821186"
---
# <a name="add-director-pool"></a>Ajouter un pool directeur
 
Pour **définir le nom de domaine complet (FQDN) du pool de réalisateurs**, sélectionnez un **pool d’ordinateurs** qui sera composé de deux ou plusieurs directeurs dans un pool équilibré ou un **seul pool d’ordinateurs**. Vous devez également taper le nom de domaine complet (FQDN, Fully Qualified Domain Name) qui sera utilisé pour la connexion au nom de domaine complet (FQDN) du réalisateur ou du réalisateur unique. Dans le cas d’un pool d’ordinateurs Director, il s’agirait de l’entrée DNS (Domain Name System) pour l’adresse IP virtuelle d’un équilibreur de charge matériel ou de l’entrée DNS partagée pour l’équilibrage de charge DNS.
  
> [!TIP]
> Si vous envisagez d’implémenter un pool de réalisateurs à l’avenir, sélectionnez **pool d’ordinateurs multiples**. Même si le regroupement comporte au moins deux ordinateurs dont le chargement est équilibré, vous pouvez créer un pool d’ordinateurs unique et créer un nom de domaine complet de pool pour l’ordinateur unique. Lorsque vous êtes prêt à ajouter plus d’ordinateurs au pool par la suite, vous devez exécuter de nouveau le générateur de topologie pour définir le nouveau membre du pool, publier la nouvelle topologie, puis configurer le nouveau membre du pool de directeurs par le biais de l’Assistant Déploiement de Skype entreprise Server. Vous devez également ajouter le nouveau membre de la liste aux équilibreurs de charge appropriés pour le pool, pour l’équilibrage de charge DNS (Domain Name System) ou pour les équilibreurs de charge matérielle. Dans de nombreux cas, les deux systèmes d’équilibrage de charge sont en place. Assurez-vous d’ajouter le nouveau serveur membre aux deux. 
  

