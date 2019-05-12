---
title: Table VoipDetails
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: Chaque enregistrement représente un seul appel deux au moins un utilisateur est un utilisateur VoIP.
ms.openlocfilehash: e29cfe19ec8c478215c8dd011a8479de5e18c18c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929958"
---
# <a name="voipdetails-table"></a>Table VoipDetails
 
Chaque enregistrement représente un seul appel deux au moins un utilisateur est un utilisateur VoIP.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Principal  <br/> |Heure de la demande de session. Utilisé en conjonction avec **SessionIdSeq** pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal  <br/> |Numéro d’identification pour identifier la session. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une session. Consultez le [tableau dans Skype pour Business Server 2015 des boîtes de dialogue](dialogs.md) pour plus d’informations. <br/> |
|**FromNumberId** <br/> |int  <br/> |Étrangère  <br/> |**PhoneId** de l’appelant. Consultez le [tableau de téléphones](phones.md) pour plus d’informations. Si non NULL et **FromGatewayId** n’est pas NULL, l’appelant est un utilisateur PSTN. <br/> |
|**ConnectedNumberId** <br/> |int  <br/> |Étrangère  <br/> |**PhoneId** du récepteur d’appel. Consultez le [tableau de téléphones](phones.md) pour plus d’informations. Si non NULL et **ToGatewayId** n’est pas NULL, le récepteur de l’appel a un utilisateur PSTN. <br/> |
|**FromMediationServerId** <br/> |int  <br/> |Étrangère  <br/> |Le serveur de médiation que provenant de l’appel. Consultez la [table MediationServers](mediationservers.md) pour plus d’informations. <br/> |
|**ToMediationServerId** <br/> |int  <br/> |Étrangère  <br/> |Le serveur de médiation appelée va. Consultez la [table MediationServers](mediationservers.md) pour plus d’informations. <br/> |
|**FromGatewayId** <br/> |int  <br/> |Étrangère  <br/> |Passerelle l’appel provient. Consultez le [tableau passerelles Skype pour Business Server 2015](gateways.md) pour plus d’informations. <br/> |
|**ToGatewayId** <br/> |int  <br/> |Étrangère  <br/> |Passerelle l’appel va. Consultez le [tableau passerelles Skype pour Business Server 2015](gateways.md) pour plus d’informations. <br/> |
|**DisconnectedbyURIId** <br/> |int  <br/> |Étrangère  <br/> |URI de l’utilisateur qui a déconnecté l’appel, si l’utilisateur possède un URI. Reportez-vous au [tableau utilisateurs](users.md) pour plus d’informations. <br/> |
|**DisconnectedbyPhoneId** <br/> |int  <br/> |Étrangère  <br/> |ID du téléphone qui a déconnecté l’appel a été déconnecté à partir d’un téléphone. Consultez le [tableau de téléphones](phones.md) pour plus d’informations. <br/> |
|**Heure de dernière modification** <br/> |DateTime  <br/> ||Pour une utilisation interne par le service de surveillance.  <br/> Ce champ est une nouveauté dans Skype pour Business Server 2015.  <br/> |
   

