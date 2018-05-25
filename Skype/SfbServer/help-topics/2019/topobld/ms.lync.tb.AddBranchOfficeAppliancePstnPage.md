---
title: Ajouter la passerelle PSTN pour le Survivable Branch Appliance
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: 'Pour définir la passerelle de réseau téléphonique commuté pour un Survivable Branch Appliance sur un site de succursale, spécifiez les éléments suivants :'
ms.openlocfilehash: cefdc46eb2f5b7573e5e5bd9acb93cb5ab384622
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2018
---
# <a name="add-survivable-branch-appliance-pstn"></a>Ajouter la passerelle PSTN pour le Survivable Branch Appliance
 
Pour définir la passerelle de réseau téléphonique commuté pour un Survivable Branch Appliance sur un site de succursale, spécifiez les éléments suivants : 
  
- Un nom de domaine complet (FQDN) ou l’adresse IP de l’homologue de passerelle que le Survivable Branch Appliance ou serveur Survivable Branch Server est associé pour le routage entrant et sortant d’appels PSTN.
    
    > [!IMPORTANT]
    > Si vous définissez un Survivable Branch Appliance, il s’agit de la passerelle à laquelle le serveur de médiation à l’intérieur du Survivable Branch Appliance se connectera pour la connectivité PSTN. 
  
- Le port d’écoute à utiliser pour les messages SIP (Session Initiation Protocol). Par défaut, il s’agit des ports 5066 pour le protocole TCP (Transmission Control Protocol) et 5067 pour le protocole TLS (Transport Layer Security) sur une passerelle, un PBX (Private Branch Exchange) ou un contrôleur SBC. Sur un Survivable Branch Appliance sur un site de succursale, les ports par défaut sont le port 5081 pour le protocole TCP et le port 5082 pour le protocole TLS.
    
- Pour des raisons de sécurité, nous vous conseillons vivement d’utiliser le protocole TLS. Si vous définissez un Survivable Branch Appliance, reportez-vous à la documentation de votre fournisseur Survivable Branch Appliance pour vérifier que votre serveur Survivable Branch Appliance prend en charge le protocole TLS.
    
    > [!IMPORTANT]
    > Pour des raisons de sécurité, nous vous recommandons vivement de déployer une passerelle pouvant utiliser le protocole TLS. 
  
> [!NOTE]
> Si vous souhaitez ajouter une passerelle RTC, vous pouvez la configurer ultérieurement, mais son fonctionnement reste limité tant qu’elle n’a pas été définie et configurée. 
  

