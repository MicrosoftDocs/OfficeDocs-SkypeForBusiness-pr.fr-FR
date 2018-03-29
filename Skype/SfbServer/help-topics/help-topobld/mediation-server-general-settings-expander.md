---
title: Expanseur des paramètres généraux du serveur de médiation
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 4/14/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: 51e00323c3c0d5df3915b2652b273f1fa189143e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="mediation-server-general-settings-expander"></a>Expanseur des paramètres généraux du serveur de médiation
 
## 

### <a name="general-settings"></a>Paramètres généraux

Nom de domaine complet (FQDN) du serveur de médiation pool ou du serveur de médiation. Modifiez le nom de domaine complet du serveur pour changer la valeur. Vous devez disposer d’un enregistrement d’hôte DNS (A) correspondant à la nouvelle valeur.
  
Dans la section **d’Associations** , vous sélectionnez un serveur de transport Edge ou le pool de serveur de transport Edge à associer au pool de serveur de médiation ou d’un serveur de médiation. Vous sélectionnez le bord qui utilisent les composants de support du serveur de médiation pour utilisateur externe de Voix Entreprise.
  
Si vous n’avez pas un serveur de transport Edge actuellement définis et doivent associer le serveur de médiation avec un serveur de transport Edge, cliquez sur **Nouveau** et définir le nouveau serveur Edge ou le pool de serveur de transport Edge dans la définition de l’Assistant de pool du bord.
  
### <a name="next-hop-settings"></a>Paramètres du tronçon suivant

Vous spécifiez le pool de serveur de médiation ou le saut suivant du serveur de médiation en sélectionnant le pool défini de Front-End de Enterprise Edition ou Standard Edition serveur frontal dans la liste déroulante. Un directeur ou un directeur pool n’est pas une sélection valide pour un pool de serveur de médiation ou le saut suivant du serveur de médiation et n’apparaît pas dans la liste. Cliquez sur **OK** pour accepter et enregistrer vos modifications. Cliquez sur **Annuler** pour annuler les modifications et quitter la page des propriétés.
  
### <a name="pstn-gateway-settings"></a>Paramètres de la passerelle PSTN

1. Vous définissez les passerelles RTPC qui sont associées au pool de serveur de médiation ou d’un serveur de médiation. Si vous avez déjà défini des passerelles, ils seront disponibles à associer avec le serveur de médiation. Si vous activez la colocalisation du serveur de médiation, définissez la plage de ports d’écoute des serveurs du pool pour le protocole TLS (Transport Layer Security). Par défaut, il s’agit du port 5067. Si vous sélectionnez **Activer le port TCP**, vous devez définir un protocole TCP pour le serveur de médiation colocalisé. Il s’agit d’un paramètre facultatif, et vous devez vous reporter aux conditions requises de votre passerelle ou de votre réseau public commuté pour déterminer si vous en avez besoin. Par défaut, le port TCP est le port 5068.
    
2. Jonctions associées au serveur de médiation colocalisé. Si vous avez déjà défini des jonctions, elles pourront être associées au serveur de médiation. 
    
3. Si vous avez plus d’un tronc associé à un serveur de médiation, vous pouvez spécifier un tronc par défaut en sélectionnant le tronc puis en cliquant sur **Par défaut**. Pour désélectionner une passerelle par défaut, cliquez sur **Annuler par défaut**. 
    

