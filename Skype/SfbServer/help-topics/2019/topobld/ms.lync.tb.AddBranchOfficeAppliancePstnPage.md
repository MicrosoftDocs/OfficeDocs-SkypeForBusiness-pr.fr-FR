---
title: Ajouter la passerelle PSTN pour le Survivable Branch Appliance
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: 716d9546938451f0104ce31484658d6b4ea4f37b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60859321"
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
  

