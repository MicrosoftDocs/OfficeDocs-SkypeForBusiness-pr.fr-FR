---
title: Ajouter la passerelle PSTN pour le Survivable Branch Appliance
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
ROBOTS: NOINDEX, NOFOLLOW
description: 'Pour définir la passerelle de réseau téléphonique commuté (PSTN) pour un Survivable Branch Appliance sur un site de succursale, spécifiez les éléments suivants :'
ms.openlocfilehash: c7cd0a04790fa646870d7d2002af6ba455780f9e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62401008"
---
# <a name="add-survivable-branch-appliance-pstn"></a>Ajouter la passerelle PSTN pour le Survivable Branch Appliance
 
Pour définir la passerelle de réseau téléphonique commuté (PSTN) pour un Survivable Branch Appliance sur un site de succursale, spécifiez les éléments suivants : 
  
- Un nom de domaine complet (FQDN) ou une adresse IP pour l’homologue de passerelle qui est associé au Survivable Branch Appliance ou au serveur Survivable Branch Server pour le routage des appels PSTN entrants et sortants.
    
    > [!IMPORTANT]
    > Si vous définissez un Survivable Branch Appliance, il s’agit de la passerelle à laquelle le serveur de médiation qui se trouve à l’intérieur du Survivable Branch Appliance se connectera pour la connectivité PSTN. 
  
- Le port d’écoute à utiliser pour les messages SIP (Session Initiation Protocol). Par défaut, il s’agit des ports 5066 pour TCP (Transmission Control Protocol) et 5067 pour TLS (Transport Layer Security) sur une passerelle, un PBX (Private Branch Exchange) ou un contrôleur SBC. Sur un Survivable Branch Appliance sur un site de succursale, les ports par défaut sont 5081 pour TCP et 5082 pour TLS.
    
- Pour des raisons de sécurité, nous vous recommandons fortement d’utiliser TLS. Si vous définissez un Survivable Branch Appliance, consultez la documentation du fournisseur de votre Survivable Branch Appliance pour vérifier que ce dernier prend en charge le protocole TLS.
    
    > [!IMPORTANT]
    > Pour des raisons de sécurité, nous vous recommandons fortement de déployer une passerelle pouvant utiliser TLS. 
  
> [!NOTE]
> Si vous souhaitez ajouter une passerelle PSTN, vous pouvez la configurer ultérieurement, mais son fonctionnement reste limité tant qu’elle n’a pas été définie et configurée. 
  

