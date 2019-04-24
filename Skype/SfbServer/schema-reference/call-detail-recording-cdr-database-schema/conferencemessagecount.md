---
title: Table ConferenceMessageCount dans Skype pour Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Chaque enregistrement de la table représente un utilisateur dans une conférence par messagerie instantanée et inclut le nombre de messages envoyés par cet utilisateur. Chaque conférence est représenté par plusieurs enregistrements dans ce tableau ; un enregistrement pour chaque utilisateur.
ms.openlocfilehash: 60fa79de17c2db14116bd0ffe211e25a61ec9136
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213276"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>Table ConferenceMessageCount dans Skype pour Business Server 2015
 
Chaque enregistrement de la table représente un utilisateur dans une conférence par messagerie instantanée et inclut le nombre de messages envoyés par cet utilisateur. Chaque conférence est représenté par plusieurs enregistrements dans ce tableau ; un enregistrement pour chaque utilisateur.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Primaire, étrangère  <br/> |Heure de l’instance de la conférence. Utilisé en conjonction avec **SessionIdSeq** pour identifier de manière unique une instance de la conférence. Consultez le [tableau des conférences dans Skype pour Business Server 2015](conferences.md) pour plus d’informations. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primaire, étrangère  <br/> |Numéro d’identification pour identifier l’instance de la conférence. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une instance de la conférence. Consultez le [tableau des conférences dans Skype pour Business Server 2015](conferences.md) pour plus d’informations. <br/> |
|**Nom d’utilisateur** <br/> |int  <br/> |Étrangère  <br/> |Numéro unique identifiant cet utilisateur, référencé à partir de la [table des utilisateurs](users.md).  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |Le nombre de messages envoyés par cet utilisateur durant cette conférence.  <br/> |
   

