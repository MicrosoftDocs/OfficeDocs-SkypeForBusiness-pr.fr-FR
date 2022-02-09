---
title: Table VoipDetails
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: Chaque enregistrement représente un appel entre deux interlocuteurs, où l’un des interlocuteurs est un utilisateur VoIP.
ms.openlocfilehash: 4cb3513ae5eb528c5e681cd55b173749c8cf1a02
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62416367"
---
# <a name="voipdetails-table"></a>Table VoipDetails
 
Chaque enregistrement représente un appel entre deux interlocuteurs, où l’un des interlocuteurs est un utilisateur VoIP.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Primaire  <br/> |Heure de la demande de session. Utilisée conjointement avec **SessionIdSeq** pour identifier de manière unique une session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015](dialogs.md). <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaire  <br/> |Numéro d’ID identifiant la session. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une session. Pour plus [d’informations, voir la table Dialogs Skype Entreprise Server 2015](dialogs.md). <br/> |
|**FromNumberId** <br/> |int  <br/> |Étranger  <br/> |**PhoneId** de l’appelant. Pour plus [d’informations, voir la table](phones.md) Phones. Si non NULL et que **FromGatewayId** est non NULL, l’appelant était un utilisateur PSTN. <br/> |
|**ConnectedNumberId** <br/> |int  <br/> |Étranger  <br/> |**PhoneId** du destinataire de l’appel. Pour plus [d’informations, voir la table](phones.md) Phones. Si non NULL et que **ToGatewayId** est non NULL, le destinataire de l’appel était un utilisateur PSTN. <br/> |
|**FromMediationServerId** <br/> |int  <br/> |Étranger  <br/> |Serveur de médiation duquel provient l’appel. Pour plus [d’informations, voir la table MediationServers](mediationservers.md) . <br/> |
|**ToMediationServerId** <br/> |int  <br/> |Étranger  <br/> |Serveur de médiation de destination de l’appel. Pour plus [d’informations, voir la table MediationServers](mediationservers.md) . <br/> |
|**FromGatewayId** <br/> |int  <br/> |Étranger  <br/> |Passerelle de laquelle provient l’appel. Pour plus [d’informations, voir le tableau Gateways Skype Entreprise Server 2015](gateways.md). <br/> |
|**ToGatewayId** <br/> |int  <br/> |Étranger  <br/> |Passerelle de destination de l’appel. Pour plus [d’informations, voir le tableau Gateways Skype Entreprise Server 2015](gateways.md). <br/> |
|**DisconnectedbyURIId** <br/> |int  <br/> |Étranger  <br/> |URI de l’utilisateur ayant déconnecté l’appel, si l’utilisateur était une URI. Pour plus [d’informations, voir la table](users.md) Utilisateurs. <br/> |
|**DisconnectedbyPhoneId** <br/> |int  <br/> |Étranger  <br/> |ID du téléphone ayant déconnecté l’appel, si celui-ci a été déconnecté depuis un téléphone. Pour plus [d’informations, voir la table](phones.md) Phones. <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Réservé à un usage interne par le service de surveillance.  <br/> Ce champ a été introduit dans Skype Entreprise Server 2015.  <br/> |
   

