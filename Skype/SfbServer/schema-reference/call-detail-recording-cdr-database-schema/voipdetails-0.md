---
title: Table VoipDetails
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: Chaque enregistrement 1 2 représente un appel vers un tiers, dont au moins un utilisateur est une VoIP.
ms.openlocfilehash: 7f0be2fb2f14e34cbe989d5912db1f66d3d65d18
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295677"
---
# <a name="voipdetails-table"></a>Table VoipDetails
 
Chaque enregistrement 1 2 représente un appel vers un tiers, dont au moins un utilisateur est une VoIP.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Principal  <br/> |Durée de la demande de session. Utilisé conjointement avec **SessionIdSeq** pour identifier une session de manière unique. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Principal  <br/> |IDENTIFIant de la session. Utilisé conjointement avec **SessionIdTime** pour identifier une session de manière unique. Pour plus d’informations, voir le [tableau des boîtes de dialogue dans Skype entreprise Server 2015](dialogs.md) . <br/> |
|**FromNumberId** <br/> |int  <br/> |Externes  <br/> |**PhoneId** de l’appelant. Pour plus d’informations, consultez la [table téléphones](phones.md) . Si ce n’est pas nul et que **FromGatewayId** n’est pas null, l’appelant était un utilisateur PSTN. <br/> |
|**ConnectedNumberId** <br/> |int  <br/> |Externes  <br/> |**PhoneId** du destinataire de l’appel. Pour plus d’informations, consultez la [table téléphones](phones.md) . Si ce n’est pas nul et que **ToGatewayId** n’est pas null, le destinataire de l’appel était un utilisateur RTC. <br/> |
|**FromMediationServerId** <br/> |int  <br/> |Externes  <br/> |Serveur de médiation depuis lequel l’appel provient. Pour plus d’informations, voir la [table MediationServers](mediationservers.md) . <br/> |
|**ToMediationServerId** <br/> |int  <br/> |Externes  <br/> |Le serveur de médiation appelé va. Pour plus d’informations, voir la [table MediationServers](mediationservers.md) . <br/> |
|**FromGatewayId** <br/> |int  <br/> |Externes  <br/> |Passerelle provenant de l’appel. Pour plus d’informations, voir le [tableau des passerelles dans Skype entreprise Server 2015](gateways.md) . <br/> |
|**ToGatewayId** <br/> |int  <br/> |Externes  <br/> |Passerelle de destination de l’appel. Pour plus d’informations, voir le [tableau des passerelles dans Skype entreprise Server 2015](gateways.md) . <br/> |
|**DisconnectedbyURIId** <br/> |int  <br/> |Externes  <br/> |URI de l’utilisateur qui a déconnecté l’appel, s’il possède un URI. Pour plus d’informations, voir le [tableau utilisateurs](users.md) . <br/> |
|**DisconnectedbyPhoneId** <br/> |int  <br/> |Externes  <br/> |ID du téléphone sur lequel l’appel a été déconnecté d’un téléphone. Pour plus d’informations, consultez la [table téléphones](phones.md) . <br/> |
|**LastModifiedTime** <br/> |Valeur  <br/> ||Pour une utilisation interne par le service de surveillance.  <br/> Ce champ a été présenté dans Skype entreprise Server 2015.  <br/> |
   

