---
title: Table ConferenceMessageCount dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Chaque enregistrement de ce tableau représente un utilisateur dans une conférence de messagerie instantanée et inclut le nombre de messages envoyés par cet utilisateur. Chaque conférence est représentée par plusieurs enregistrements dans cette table ; un enregistrement pour chaque utilisateur.
ms.openlocfilehash: 17b6d97da1795762419fe84527d9b4f5e7bcc137
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58590968"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>Table ConferenceMessageCount dans Skype Entreprise Server 2015
 
Chaque enregistrement de ce tableau représente un utilisateur dans une conférence de messagerie instantanée et inclut le nombre de messages envoyés par cet utilisateur. Chaque conférence est représentée par plusieurs enregistrements dans cette table ; un enregistrement pour chaque utilisateur.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Primaire, étrangère  <br/> |Heure de l’instance de conférence. Utilisé conjointement avec **SessionIdSeq** pour identifier de manière unique une instance de conférence. Pour plus d’informations, voir le tableau [Conferences Skype Entreprise Server 2015.](conferences.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro d’identification de l’instance de conférence. Utilisé conjointement avec **SessionIdTime pour** identifier de manière unique une instance de conférence. Pour plus d’informations, voir le tableau [Conferences Skype Entreprise Server 2015.](conferences.md) <br/> |
|**UserId** <br/> |int  <br/> |Étranger  <br/> |Numéro unique identifiant cet utilisateur, référencé à partir de la [table Utilisateurs](users.md).  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |Nombre de messages envoyés par cet utilisateur au cours de cette conférence.  <br/> |
   

