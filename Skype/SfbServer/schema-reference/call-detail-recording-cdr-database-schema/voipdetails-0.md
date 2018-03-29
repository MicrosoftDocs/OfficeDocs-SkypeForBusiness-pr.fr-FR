---
title: Table VoipDetails
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: Chaque enregistrement représente les un appel entre deux personnes dans laquelle au moins un utilisateur est un utilisateur de VoIP.
ms.openlocfilehash: 8f28ec3ac1d4049f24c5af5b768026bdd8a98486
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="voipdetails-table"></a>Table VoipDetails
 
Chaque enregistrement représente les un appel entre deux personnes dans laquelle au moins un utilisateur est un utilisateur de VoIP.
  
|**Colonne**|**Type de données**|**Index de la clé**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Principal  <br/> |Heure de la demande de la session. Utilisé en association avec **SessionIdSeq** pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal  <br/> |Numéro d’ID pour identifier la session. Utilisé en association avec **SessionIdTime** pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**FromNumberId** <br/> |int  <br/> |Étrangère  <br/> |**PhoneId** de l’appelant. Consultez le [tableau des téléphones](phones.md) pour plus d’informations. Si non NULL et **FromGatewayId** n’est pas NULL, l’appelant est un utilisateur PSTN. <br/> |
|**ConnectedNumberId** <br/> |int  <br/> |Étrangère  <br/> |**PhoneId** du destinataire de l’appel. Consultez le [tableau des téléphones](phones.md) pour plus d’informations. Si non NULL et **ToGatewayId** n’est pas NULL, destinataire de l’appel a été un utilisateur PSTN. <br/> |
|**FromMediationServerId** <br/> |int  <br/> |Étrangère  <br/> |Le serveur de médiation que provenant de l’appel. Consultez le [tableau de MediationServers](mediationservers.md) pour plus d’informations. <br/> |
|**ToMediationServerId** <br/> |int  <br/> |Étrangère  <br/> |Le serveur de médiation appelé va. Consultez le [tableau de MediationServers](mediationservers.md) pour plus d’informations. <br/> |
|**FromGatewayId** <br/> |int  <br/> |Étrangère  <br/> |Provenant de la passerelle de l’appel. Consultez le [tableau des passerelles dans Skype pour Business Server 2015](gateways.md) pour plus d’informations. <br/> |
|**ToGatewayId** <br/> |int  <br/> |Étrangère  <br/> |L’appel de passerelle va. Consultez le [tableau des passerelles dans Skype pour Business Server 2015](gateways.md) pour plus d’informations. <br/> |
|**DisconnectedbyURIId** <br/> |int  <br/> |Étrangère  <br/> |URI de l’utilisateur qui a déconnecté l’appel, si l’utilisateur dispose d’un URI. Reportez-vous au [tableau utilisateurs](users.md) pour plus d’informations. <br/> |
|**DisconnectedbyPhoneId** <br/> |int  <br/> |Étrangère  <br/> |ID de téléphone qui a déconnecté l’appel a été déconnecté à partir d’un téléphone. Consultez le [tableau des téléphones](phones.md) pour plus d’informations. <br/> |
|**Heure de dernière modification** <br/> |DateTime  <br/> ||Pour un usage interne par le service de surveillance.  <br/> Ce champ a été introduit dans Skype pour Business Server 2015.  <br/> |
   

