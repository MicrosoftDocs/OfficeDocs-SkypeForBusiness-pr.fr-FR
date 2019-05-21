---
title: Table ConferenceMessageCount dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Chaque enregistrement de cette table représente un utilisateur au sein d’une conférence par messagerie instantanée et inclut le nombre de messages envoyés par cet utilisateur. Chaque conférence est représentée par plusieurs enregistrements dans ce tableau; un enregistrement pour chaque utilisateur.
ms.openlocfilehash: ef343536c34b3bd27d71ee37813e4b4e65156094
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296454"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>Table ConferenceMessageCount dans Skype entreprise Server 2015
 
Chaque enregistrement de cette table représente un utilisateur au sein d’une conférence par messagerie instantanée et inclut le nombre de messages envoyés par cet utilisateur. Chaque conférence est représentée par plusieurs enregistrements dans ce tableau; un enregistrement pour chaque utilisateur.
  
|**Colonne**|**Type de données**|**Clé/Index**|**Détails**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |DateHeure  <br/> |Etranger principal  <br/> |Durée de l’instance de conférence. Utilisé conjointement avec **SessionIdSeq** pour identifier de manière unique une instance de conférence. Pour plus d’informations, consultez le [tableau conférences dans Skype entreprise Server 2015](conferences.md) . <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Etranger principal  <br/> |Numéro d’identification pour identifier l’instance de conférence. Utilisé conjointement avec **SessionIdTime** pour identifier de manière unique une instance de conférence. Pour plus d’informations, consultez le [tableau conférences dans Skype entreprise Server 2015](conferences.md) . <br/> |
|**UserId** <br/> |int  <br/> |Externes  <br/> |Numéro unique identifiant cet utilisateur, référencé dans la [table utilisateurs](users.md).  <br/> |
|**MessageCount** <br/> |type  <br/> | <br/> |Nombre de messages envoyés par cet utilisateur au cours de cette conférence.  <br/> |
   

