---
title: Expanseur des paramètres généraux du serveur de médiation
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 4/14/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: de4d09db10610bee5f498b07cca6a052b6a79a38
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852098"
---
# <a name="mediation-server-general-settings-expander"></a>Expandeur des paramètres généraux du serveur de médiation
 


## <a name="general-settings"></a>Paramètres généraux

Nom de domaine complet (FQDN) du serveur de médiation ou du pool de serveurs de médiation. Modifiez le nom de domaine complet du serveur pour changer la valeur. Vous devez disposer d’un enregistrement DNS A (hôte) qui corresponde à la nouvelle valeur.
  
Dans la section **Associations**, sélectionnez un serveur Edge ou un pool de serveurs Edge à associer au serveur de médiation ou au pool de serveurs de médiation. Vous sélectionnez le serveur Edge que les composants multimédias du serveur de médiation utiliseront pour les utilisateurs externes Voix Entreprise.
  
Si vous ne disposez pas de serveur Edge actuellement défini et que vous avez besoin d’associer le serveur de médiation à un serveur Edge, cliquez sur **Nouveau** et définissez le nouveau serveur Edge ou le pool de serveurs Edge dans l’Assistant Définir le nouveau pool Edge.
  
## <a name="next-hop-settings"></a>Paramètres du tronçon suivant

Vous spécifiez le pool de serveurs de médiation ou le tronçon suivant du serveur de médiation en sélectionnant le pool frontal Enterprise Edition défini ou le serveur frontal Standard Edition dans la liste déroulante. Un directeur ou un pool directeur n’est pas une sélection valide pour le pool de serveurs de médiation ou le tronçon suivant du serveur de médiation, et ils n’apparaîtront pas dans la liste. Cliquez **sur OK** pour accepter et enregistrer vos modifications. Cliquez sur **Annuler** pour annuler les modifications et quitter la page des propriétés.
  
## <a name="pstn-gateway-settings"></a>Paramètres de la passerelle PSTN

1. Vous définissez les passerelles PSTN qui sont associées au serveur ou au pool de serveurs de médiation. Si vous avez déjà défini des passerelles, ces dernières pourront être associées au serveur de médiation. Si vous activez la fonctionnalité de colocalisation du serveur de médiation, définissez la plage de ports d’écoute des serveurs du pool pour le protocole TLS (Transport Layer Security). Par défaut, ce port est 5067. Si vous sélectionnez **Activer le port TCP**, vous devez définir un protocole TCP (Transmission Control Protocol) pour le serveur de médiation colocalisé. Il s’agit d’un paramètre facultatif et vous devez vous reporter aux conditions requises de votre passerelle ou de votre réseau public commuté pour déterminer si vous en avez besoin. Par défaut, la valeur du port TCP est 5068.
    
2. Jonctions associées au serveur de médiation colocalisé. Si vous avez déjà défini des jonctions, elles pourront être associées au serveur de médiation. 
    
3. Si plusieurs jonctions sont associées à un serveur de médiation, vous pouvez spécifier une jonction par défaut en sélectionnant la jonction et en cliquant sur **Utiliser par défaut**. Pour désélectionner une passerelle par défaut, cliquez sur **Annuler Par défaut**. 
    

