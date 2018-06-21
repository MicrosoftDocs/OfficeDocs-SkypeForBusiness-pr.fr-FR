---
title: Expanseur des paramètres généraux du serveur de médiation
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: b343152bd1a47fb749e1812a1cace372010b98ac
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/21/2018
ms.locfileid: "19987318"
---
# <a name="mediation-server-general-settings-expander"></a>Expanseur des paramètres généraux du serveur de médiation
 
## 

### <a name="general-settings"></a>Paramètres généraux

Nom de domaine complet (FQDN) du serveur de médiation pool ou du serveur de médiation. Modifiez le nom de domaine complet du serveur pour changer la valeur. Vous devez disposer d’un enregistrement d’hôte DNS (A) correspondant à la nouvelle valeur.
  
Dans la section **Associations** , vous sélectionnez un serveur Edge ou pool de serveurs Edge à associer au pool de serveurs de médiation ou un serveur de médiation. Vous sélectionnez le bord utilisées par les composants médias le serveur de médiation pour un utilisateur externe Enterprise Voice.
  
Si vous n’avez pas un serveur Edge actuellement définis et devez associer le serveur de médiation à un serveur de périphérie, cliquez sur **Nouveau** et définir le nouveau serveur de périphérie ou le pool de serveur de périphérie dans la définition de l’Assistant Nouveau Edge du pool.
  
### <a name="next-hop-settings"></a>Paramètres du tronçon suivant

Vous spécifiez le serveur ou du pool du tronçon suivant du serveur de médiation en sélectionnant le défini pool frontal Enterprise Edition ou Standard Edition serveur frontal dans la liste déroulante. Un directeur ou un directeur pool n’est pas une sélection valide pour un serveur ou du pool du tronçon suivant du serveur de médiation et n’apparaît pas dans la liste. Cliquez sur **OK** pour accepter et enregistrer vos modifications. Cliquez sur **Annuler** pour annuler les modifications et quitter la page des propriétés.
  
### <a name="pstn-gateway-settings"></a>Paramètres de la passerelle PSTN

1. Vous définissez des passerelles PSTN qui sont associés au pool de serveurs de médiation ou un serveur de médiation. Si vous avez déjà défini des passerelles, ils seront disponibles à associer au serveur de médiation. Si vous activez la colocalisation du serveur de médiation, définissez la plage de ports d’écoute des serveurs du pool pour le protocole TLS (Transport Layer Security). Par défaut, il s’agit du port 5067. Si vous sélectionnez **Activer le port TCP**, vous devez définir un protocole TCP pour le serveur de médiation colocalisé. Il s’agit d’un paramètre facultatif, et vous devez vous reporter aux conditions requises de votre passerelle ou de votre réseau public commuté pour déterminer si vous en avez besoin. Par défaut, le port TCP est le port 5068.
    
2. Jonctions associées au serveur de médiation colocalisé. Si vous avez déjà défini des jonctions, elles pourront être associées au serveur de médiation. 
    
3. Si vous avez plusieurs jonction associée à un serveur de médiation, vous pouvez spécifier une jonction par défaut en sélectionnant la jonction puis en cliquant sur **Utiliser par défaut**. Pour désélectionner une passerelle par défaut, cliquez sur **Annuler par défaut**. 
    

