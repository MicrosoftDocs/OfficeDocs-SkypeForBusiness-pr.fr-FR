---
title: Expanseur des paramètres généraux du serveur de médiation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/14/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: a460cfcaf696740fa108be451156d53bec96f95d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41696999"
---
# <a name="mediation-server-general-settings-expander"></a>Expanseur des paramètres généraux du serveur de médiation
 


## <a name="general-settings"></a>Paramètres généraux

Nom de domaine complet (FQDN) du pool de serveurs de médiation ou du serveur de médiation. Modifiez le nom de domaine complet du serveur pour changer la valeur. Vous devez disposer d’un enregistrement d’hôte DNS (A) correspondant à la nouvelle valeur.
  
Dans la section **associations** , vous sélectionnez un serveur Edge ou un pool de serveurs Edge à associer au pool de serveurs de médiation ou au serveur de médiation. Vous sélectionnez le bord sur lequel les composants multimédias du serveur de médiation seront utilisés pour la voix de l’entreprise externe.
  
Si vous n’avez pas de serveur Edge actuellement défini et que vous avez besoin d’associer le serveur de médiation à un serveur Edge, cliquez sur **nouveau** et définissez le nouveau serveur Edge ou pool de serveurs Edge dans l’Assistant définir le nouveau pool de périphériques.
  
## <a name="next-hop-settings"></a>Paramètres du tronçon suivant

Vous spécifiez le tronçon de la liste de serveurs de médiation ou du serveur de médiation en sélectionnant le serveur frontal Enterprise Edition défini dans la liste déroulante. Un directeur ou un pool de réalisateurs n’est pas une sélection valide pour un pool de serveurs de médiation ou un serveur de médiation qui suit le tronçon et n’apparaîtra pas dans la liste. Cliquez sur **OK** pour accepter et enregistrer vos modifications. Cliquez sur **Annuler** pour annuler les modifications et quitter la page des propriétés.
  
## <a name="pstn-gateway-settings"></a>Paramètres de la passerelle PSTN

1. Vous définissez des passerelles RTC associées au pool de serveurs de médiation ou au serveur de médiation. Si vous avez déjà défini des passerelles, celles-ci sont disponibles pour être associées au serveur de médiation. Si vous activez la colocalisation du serveur de médiation, définissez la plage de ports d’écoute des serveurs du pool pour le protocole TLS (Transport Layer Security). Par défaut, il s’agit du port 5067. Si vous sélectionnez **Activer le port TCP**, vous devez définir un protocole TCP pour le serveur de médiation colocalisé. Il s’agit d’un paramètre facultatif, et vous devez vous reporter aux conditions requises de votre passerelle ou de votre réseau public commuté pour déterminer si vous en avez besoin. Par défaut, le port TCP est le port 5068.
    
2. Jonctions associées au serveur de médiation colocalisé. Si vous avez déjà défini des jonctions, elles pourront être associées au serveur de médiation. 
    
3. Si vous avez plusieurs Trunks associés à un serveur de médiation, vous pouvez spécifier une valeur par défaut en sélectionnant le Trunk, puis en cliquant sur **définir par défaut**. Pour désélectionner une passerelle par défaut, cliquez sur **Annuler par défaut**. 
    

