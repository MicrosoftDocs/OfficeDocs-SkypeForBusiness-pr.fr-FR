---
title: Ajouter la passerelle PSTN pour le Survivable Branch Appliance
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddBranchOfficeAppliancePstnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7c55a43d-2589-48f9-972b-1e48a3dca52a
description: 'Pour définir la passerelle RTC (réseau téléphonique commuté) pour une branche Survivable sur un site de succursale, spécifiez les éléments suivants :'
ms.openlocfilehash: d5ba39a79f7810a64776efcd7b7c47488fe93d2b
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697949"
---
# <a name="add-survivable-branch-appliance-pstn"></a>Ajouter la passerelle PSTN pour le Survivable Branch Appliance
 
Pour définir la passerelle RTC (réseau téléphonique commuté) pour une branche Survivable sur un site de succursale, spécifiez les éléments suivants : 
  
- Le nom de domaine complet (FQDN) ou l’adresse IP de l’homologue de la passerelle qui est associé à l’unité de messagerie ou au serveur de succursales survivant est associé pour le routage des appels RTC entrants et sortants.
    
    > [!IMPORTANT]
    > S’il s’agit de la définition d’une unité de branchement survivant, il s’agit de la passerelle à laquelle le serveur de médiation de l’appareil de branchement survivant se connecte pour la connectivité PSTN. 
  
- Le port d’écoute à utiliser pour les messages SIP (Session Initiation Protocol). Par défaut, il s’agit des ports 5066 pour le protocole TCP (Transmission Control Protocol) et 5067 pour le protocole TLS (Transport Layer Security) sur une passerelle, un PBX (Private Branch Exchange) ou un contrôleur SBC. Sur un Survivable Branch Appliance sur un site de succursale, les ports par défaut sont le port 5081 pour le protocole TCP et le port 5082 pour le protocole TLS.
    
- Pour des raisons de sécurité, nous vous conseillons vivement d’utiliser le protocole TLS. Si vous définissez une application branche Survivable, consultez la documentation fournie par le fabricant de votre appareil pour vérifier que votre application de branchement Survivable prend en charge le protocole TLS.
    
    > [!IMPORTANT]
    > Pour des raisons de sécurité, nous vous recommandons vivement de déployer une passerelle pouvant utiliser le protocole TLS. 
  
> [!NOTE]
> Si vous souhaitez ajouter une passerelle RTC, vous pouvez la configurer ultérieurement, mais son fonctionnement reste limité tant qu’elle n’a pas été définie et configurée. 
  

